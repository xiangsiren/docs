### review

1. 抽象类与接口的区别：

              1. 实现：抽象类的子类使用 extends 来继承；接口必须使用 implements 来实现接口。
              2. 构造函数：抽象类可以有构造函数；接口不能有。
                 main 方法：抽象类可以有 main 方法，并且我们能运行它；接口不能有 main 方法。
              3. 实现数量：类可以实现很多个接口；但是只能继承一个抽象类。
                 访问修饰符：
              4. 接口中的方法默认使用 public 修饰；抽象类中的方法可以是任意访问修饰符。

2. 多态：同一个接口使用不同的实例，执行的操作不同

   好处：可以程序有良好的扩展，可以对类的对象通用处理

3. 并发和并行的区别：

   并行：多个事件在同一时刻发生, 并发是多个事件在同一时间间隔发生

   并行是不同实体上的多个事件，并发是一个实体上的多个事件

4. 线程与进程：一条线程线程是进程中一个单一顺序的控制流，

   一个进程是一个独立(self   contained)的运行环境，它可以被看作一个程序或者一个应用。而线程是在进程中执行的一个任务。Java运行环境是一个包含了不同的类和程序的单一进程。线程可以被称为轻量级进程。线程需要较少的资源来创建和驻留在进程中，并且可以共享进程中的资源。

   进程是程序运行和资源分配的基本单元，一个程序至少有一个进程，一个进程至少有一个线程；进程在运行过程中有独立的内存单元，而多线程共享内存资源，减少切换次数，从而效率更高；

   线程是进程的一个实体，是CPU调度和分配的基本单元，是比程序更小的能够独立运行的基本单元，同一进程的多个线程可以并发执行

5. xss攻击（css）全称（cross site script）跨站脚本攻击，如何避免

   页面被注入恶意代码，

   防范思路：对输入进行过滤，对输出编码。

6. csrf （cross site request forgey）跨站请求伪造：

   一般来说，攻击者通过伪造用户浏览器的请求

   如何避免：

   - 验证HTTP Referer字段
   - 使用验证码，但体验不太好
   - 在请求地址中添加token验证
   - 在HTTP头自定义属性并验证

7. 如何避免SQL注入：

   1. 预处理
   2. 使用正则表达式过滤传入的参数
   3. 字符串过滤

8. 死锁

   多个线程相互争夺资源僵局无法向前推进。

   产生的原因是：

   - 竞争资源（可剥夺资源，不可剥夺资源）
   - 进程间推进顺序非法

   解决基本方法：以确定的顺序获得锁，超时放弃 

9. 如何防止死锁：

   1. 尽量减少同步的代码块
   2. 尽量使用juc并发类代替自己手写锁
   3. 设置超时时间，

10. 尽量降低锁的使用粒度，避免多个功能使用同一把锁

11. 为什么要用多线程：

             1. 为了更好的利用cpu的资源，如果只有一个线程，则第二个任务必须等到第一个任务结束后才能进行，如果使用多线程则在主线程执行任务的同时可以执行其他任务，而不需要等待；
             2. 进程之间不能共享数据，线程可以；
             3. 系统创建进程需要为该进程重新分配系统资源，创建线程代价比较小
             4. Java语言内置了多线程功能支持，简化了java多线程编程

12. java虚拟机工作原理：https://www.jianshu.com/p/c0713884fb12

13. 泛型：

             泛型的本质是参数化类型，也就是所操作的类型被指定我一个参数
           
             优点：可以让我们的数据结构放置"任何"数据类型
           
             不可以是基本数据类型，只能是类对象

14. == 与 equals 区别：

             　1. 对于==，如果作用于基本数据类型的变量，则直接比较其存储的 “值”是否相等；
           
             　　如果作用于引用类型的变量，则比较的是所指向的对象的地址
           
             　2. 对于equals方法，注意：equals方法不能作用于基本数据类型的变量
           
             　　如果没有对equals方法进行重写，则比较的是引用类型的变量所指向的对象的地址；
           
             　　诸如String、Date等类对equals方法进行了重写的话，比较的是所指向的对象的内容

15. 二位

16. ewewew

17. java 面向对象设计原则：

             1. 单一职责原则(srp):一个类只负责一项职责，提高类的可读性和易维护性
             2. 开闭原则(ocp): 软件中的对象对扩展开放，修改关闭；我们可以用抽象构建框架，用实现扩展细节
             3. 里斯替换原则（lsp）：子类可以扩展父类的功能，但不能改变父类的原有功能
             4. 依赖倒置原则（dip）:高程模块不应该依赖低成模块，两者都应该依赖其抽象，抽象不应该依赖细节，细节应该依赖其抽象
             5. 接口隔离原则（ISP）：客户端不应该依赖它不需要的接口
             6. 迪米特原则（LOD）: 一个对象应该对其他对象保持最小的了解

18. 设计模式：最佳实践 ;三种类型(创建型，结构性，行为性)

19. 创建型：

             工厂模式：扩展性高，隐藏具体实现，调用者只关心接口即可
           
             单例模式：单例类只有一个实例，自己创建自己唯一的实例，并对外提供这一实例
           
             1. 主要解决：主要是为了解决类的频繁创建和销毁
           
             2. 何时使用：需要控制实例数目，节省系统资源的时候
           
             3. 关键代码：构造函数是私有的
             4. 饿汉式是声明私有静态变量并创建对象，懒汉式是只声明变量，在调用该类的方法时才会进行new 对象
             5. 静态式/静态内部类：

20. 结构性模式：

             装饰器模式：为已有类动态添加额外的功能，
           
             适配器模式：
           
             过滤器模式：

21. 行为性模式：

             观察者模式：
           
             模板模式：
           
             策略模式：

22. volatile: 在Java编程中常用于保持内存可见性和防止指令重排序

23. 线程间通信：线程间通信模型有两种（共享内存和消息传递）

             1. 使用volatile 关键字
             2. 使用object类的wait() 和notify() 方法
             3. 

24. 垃圾回收机制

             什么才是垃圾,java中对象没有被其他对象引用就是无用的，此对象被称为垃圾，其占用的内存要被销毁
           
             判断对象为垃圾的算法：
           
             1. 引用计数法：引用一次计数器加一，引用失效，计数器减一 
           
                优点：执行效率高，
           
                缺点：无法检测循环引用的情况，导致内存泄漏
           
             2. 可达性分析算法：
           
                gc boot 做起点向下搜索，节点所走过的路径称为引用链，

25. https://www.jianshu.com/p/745757d373e9

26. cap定理：指的是在一个分布式系统中，一致性，可用性，分区容错性，这三个要素最多只能同时实现两个，不可能三者兼顾

             一致性： 分布式系统中，所有的备份数据，在同一时刻是否是同样的值
           
             可用性：一部分节点故障后，集群整体是否还能响应客户端的读写请求
           
             分区容错性：系统如果时限内不能达成一致，就意味着发生分区

27. ArrayList 与 linkedlist 区别：

             ArrayList 基于动态数组的数据结构，linkedlist 基于链表结构
           
             对于随机访问的get 和set 方法，ArrayList 优于linkedlist,因为linkedlist 要移动指针
           
             对于新增和删除操作，linkedlist有优势，ArrayList 需要移动数据

28. ewweew

29. spring ：开源容器框架，是一个轻量级的控制反转(IOC)和面向切片(AOP)的容器框架

30. spring aop 可以实现业务代码与系统级服务例如日志记录，事务及安全相关的解耦，使代码更加干净整洁

31. 控制反转（IOC）：控制权的转移，应用程序本身不负责依赖对象的创建和维护，而是由外部容器创建和维护；有两种方式，一种DI(Dependency Injection)依赖注入，软件实体被动接受其依赖的其他组件被 IoC 容器注入；一种DL，Dependency Lookup（依赖查找）软件实体主动去某个服务注册地查找其依赖的那些服务

32. ssm:(springmvc + spring + mybatis)

33. 面向接口编程：

             结构设计中，分清层次和调用关系，每层只向外提供一组功能接口，各层间仅依赖接口而非实现类
           
             接口实现的变动不影响各层间的调用
           
             接口是用于隐藏具体实现和实现多态性的组件

34. spring 注入：是指在启动spring 容器加载bean配置的时候，完成对变量的赋值常用的两种注入方式：

             设值注入 ，构造注入

35. bean 是一个被实例化，组装，并通过spring IOC容器管理的对象，

             spring配置元数据，以下三个方法把配置元数据提供给spring容器：
           
             1. 基于xml的配置文件
             2. 基于注解的配置
             3. 基于Java的配置

36. 线程的生命周期：

             新建状态：new 或thread 及其子类创建线程对象
           
             就绪状态：线程调用start() 方法后，处于就绪队列中，等待jvm线程调度器的调度
           
             运行状态：获取CPU资源，就可以执行run()；他可以变为就绪，阻塞，死亡等状态
           
             阻塞状态：
           
             死亡状态：

37. java 提供三种方式创建线程：

             实现runable接口，继承thread类， 通过callable 和future

38. jar 包的作用：

             1. 用于发布和使用类库
             2. 应用程序和扩展的构建单元

39. 内存溢出和内存泄漏：

             内存溢出是指程序申请内存时没有足够的内存空间供其使用，出现out of memory
           
             ​ 解决办法：修改jvm参数，直接增加内存
           
             ​ 查看错误日志，对代码进行走查分析
           
             内存泄漏：分配出去的内存不在使用，但无法回收

40. springcloud 五大组件：

             1. 服务发现eureka: nacos代替
             2. 客户端负载均衡Ribbon:
             3. 熔断器hystrix: 保护系统，控制故障 Sentinel代替
             4. 服务网关zuul: api 网关路由 spring cloud getaway代替
             5. 分布式配置springcloud config：配置管理  nacos-config 代替

41. hash冲突的解决方法：

                1. 链地址法
                2. 再hash法

42. java里面线程池的顶级接口是Executor;真正的线程池接口是ExecutorService;**ThreadPoolExecutor** :ExecutorService的默认实现。

43. 几种常见的运行时异常：

             1. 类型转换异常
             2. 空指针异常
             3. 类找不到异常
             4. 数组越界异常
             5. 同步修改异常

44. jvm结构：https://baijiahao.baidu.com/s?id=1632503816780923946&wfr=spider&for=pc

       https://blog.csdn.net/qq_41701956/article/details/81664921

       ```
            类的加载机制，jvm内存结构，gc(gc算法,垃圾回收器)，性能调优
          
            类的加载：加载，连接，初始化，使用， 卸载
          
            1. 加载：字节流转换为运行时数据结构并在堆中生成class对象
            2. 连接：校验，准备，解析
            3. 初始化：执行类的构造方法
            4. 使用：实例化调用
            5. 卸载： class对象不再被引用时，生命结束
          
            [内存分配](https://www.jianshu.com/p/f36ca4e4bd10)
          
            ​	堆：存放对象的实例，1. 年轻代(1/3):Eden:s0:s1 = 8:1:1 + 老年代（2/3）
          
            ​	方法区：存放虚拟机加载的类信息，常量，静态常量
          
            常见垃圾回收算法：标记清除，复制，标记整理，分代收集
          
            常见的垃圾回收器：G1收集器，Cms收集器，serial收集器，Parnew收集器
          
            JVM调优：
          
            1. 初始化内存尽量和最大内存报纸一致，避免内存不够用继续扩充内存
            2. gc/full gc 频率不要太高，
       ```
       

45. full gc 触发条件：https://www.cnblogs.com/williamjie/p/9516367.html

46. sychronized 与 lock区别：

                sychronized : java关键字，异常释放锁，不会发生死锁，不可中断，锁状态不可判断,少量同步
              
                lock : 类，需要手动释放锁，可能发生死锁，可中断，锁状态可判断,适合大量同步

47. voletile 与 sycronized区别：   https://blog.csdn.net/mifffy_java/article/details/99944946

           作用：
             synchronized 表示只有一个线程可以获取作用对象的锁，执行代码，阻塞其他线程。
             volatile 表示变量在 CPU 的寄存器中是不确定的，必须从主存中读取。保证多线程环境下变量的可见性；禁止指令重排序。


    区别：
       synchronized 可以作用于变量、方法、对象；volatile 只能作用于变量。
       synchronized 可以保证线程间的有序性（猜测是无法保证线程内的有序性，即线程内的代码可能被 CPU 指令重排序）、 		原子性和可见性；volatile 只保证了可见性和有序性，无法保证原子性。
       synchronized 线程阻塞，volatile 线程不阻塞。

48. Java 线程池参数：https://blog.csdn.net/ye17186/article/details/89467919

       https://www.jianshu.com/p/7ab4ae9443b9  https://www.jianshu.com/p/7726c70cdc40

          corePoolSize：线程池核心线程大小
        
          maximumPoolSize：线程池最大线程数量
        
          keepAliveTime：空闲线程存货时间
        
          unit：空闲线程存活时间单位
        
          workQueue：工作队列
        
          threadFactory：线程工厂
        
          handler：拒绝策略

49. 分布式事务：http://www.imooc.com/article/289274

50. springMVC框架的执行步骤：

          1. 用户发起请求到前端控制器（DispatchServlet）
          2. handler处理完成返回ModelAndView

51. RPC

          https://www.jianshu.com/p/b0343bfd216e

52. 反射：https://www.jianshu.com/p/9d13a9eeccdf

       动态获取类的信息，调用类的方法；

53. for 与foreach区别

    foreach适用于只是进行集合或数组遍历，for则在较复杂的循环中效率更高。
    foreach不能对数组或集合进行修改（添加删除操作），如果想要修改就要用for循环。

54. dsfsfd 

55. 手动阀

56. 地方撒 

57. 手动阀


52. 常见生成全局唯一ID：https://www.jianshu.com/p/5a71cd4e2de5

       1. 使用UUID实现：利用java.util.UUID类生成
       2. 使用Redis实现：用Redis的原子操作 INCR和INCRBY来实现
       3. 使用twitter的snowflake算法实现：
       4. 使用数据库实现：数据库自增主键，步长不一样
          5. 时间戳+ 业务字段+ 随机组合：比如时间戳+用户ID+随机数就是一个很好的例子

53. string ：创建字符串pool 与heap

    https://blog.csdn.net/yrwan95/article/details/81212714

54. Stringbuffer 与sringbuilder 区别：https://segmentfault.com/a/1190000017909550

    1. StringBuffer：线程安全，StringBuilder：线程不安全。

       因为 StringBuffer 的所有公开方法都是 synchronized 修饰的，

       而 StringBuilder 并没有 synchronized 修饰。

    2. 既然 StringBuffer 是线程安全的，它的所有公开方法都是同步的，StringBuilder 是没有对方法加锁同步的，所以毫无疑问，StringBuilder 的性能要远大于 StringBuffer。

55. Spring框架对单例的支持是采用单例注册表的方式进行实现的

56. callable 与runable 区别：https://www.cnblogs.com/kaituorensheng/p/9502968.html

    Runnable没有返回值；Callable可以返回执行结果，是个泛型，和Future、FutureTask配合可以用来获取异步执行的结果

    Callable接口的call()方法允许抛出异常；Runnable的run()方法异常只能在内部消化，不能往上继续抛

57. sychronize ：https://www.cnblogs.com/xuxinstyle/p/9690316.html

    1. java代码执行sychronize
    2. 字节码执行：moniterenter moniterexit
    3. jvm执行过程中自动锁升级
    4. cpu汇编层级lock cmpxchg

58. <? super E> 有下界的通配符，能接受指定类及其父类的数据，E就是该泛型的下边界。

59. <? extends E> 有上限的通配符，能接受指定类及其子类的数据，E就是该泛型的上边界。

60. <?> 无限定的通配符，泛型能够接受未知类型的数据

61. 泛型信息只存在于代码编译阶段，编译器编译完带有泛型的java程序后，生成的class文件中与泛型相关的信息会被擦除，对程序运行效率不影响，这个过程叫类型擦除，也就是说泛型类和其他普通在java虚拟机内是一样的；

62. 泛型先声明再使用，通配符直接使用，需要用object对象接收

63. 父类只有有参构造器，会覆盖父类本身的无参构造器，就会没有无参构造器

    如果子类没有显示的构造器，默认创建无参构造器，子类的无参构造器回去调用父类的无参构造器

    此时可以在父类创建无参构造器，或者子类使用super调用父类的有参构造器

58. 创建多少个线程合适：

    https://www.jianshu.com/p/f30ee2346f9f

    CPU密集型，i/o密集型

    对于CPU密集型来说，多线程主要目的是提成CPU利用率，保持和CPU核数一致即可

    对于IO密集型来说，一般是最佳线程数 =CPU 核数 * [ 1 +（I/O 耗时 / CPU 耗时）]

65. java sychronize 原理：https://blog.csdn.net/javazejian/article/details/72828483

    sychronize 的两种用法：

    1. 对象锁：包括方法锁（默认锁对象为this当前实例对象）和同步代码块锁
    2. 类锁：指sychronize 修饰的静态方法或指定锁为class 对象 https://www.imooc.com/video/18489

66. 重入锁：线程获取到锁之后，再次获取该锁不会被阻塞 ，

    sychronize 可重入是线程而非调用，

    可重入原理：加锁次数计数器，jvm负责跟踪对象被加锁的次数，线程第一次给对象加锁的时候，计数变为1，每当这个相同的线程再次获得锁时，计数器会递增，当任务离开时，计数器减一，当计数器为0时，锁被完全释放；

    ReetrantLock 设计目的是用来替代synchronized 关键字

67. sychronize : 不可中断指的是：线程被占用，只能选择等待或者阻塞；可中断：指的是可中断正在执行的线程或者退出等待

68. 对比：

    | 特征     | synchronize          | reetrantlock               |
    | :------- | -------------------- | -------------------------- |
    | 底层原理 | jvm实现              | jdk实现                    |
    | 锁的释放 | 自动释放(编译器保证) | 手动释放(finally保证)      |
    | 编码程度 | 简单                 | 复杂                       |
    | 锁的粒度 | 读写不分离           | 读锁，写锁                 |
    | 高级功能 | 无                   | 公平锁，非公平锁，中断唤醒 |
    | 性能     | 低-》高（1.5+）      | 高                         |

69. JUC :

    CountDownLatch : 倒计时锁

    Semaphore：信号量主要用于限制某个资源的线程数量

    CyclicBarrier: 循环屏障 同步工具类，允许线程相互等待，直到达到某个公共屏障点，与countDownLatch不同的是其在释放等待线程后可以重用 ；适用于多线程必须同时开始的场景

    ReetrantLock : 重入锁 线程获取锁之后，再次获取该锁不会被锁阻塞

    Condition 线程等待与唤醒：用于让指定线程等待唤醒，它必须与ReetrantLock重入锁配合使用；Condition 用于替代wait / notify 方法；notify只能随机唤醒等待的线程，而condition 可以唤醒指定的线程这有利于更好的并发控制

    Callable 与 Runable一样代表着任务，区别在于callable有返回值并且可以抛出异常

    Future是一个接口，用于表示异步计算的结果

    线程安全-并发容器类：ArrayList -> CopyOnWriteArrayList  写复制列表

    ​									HashSet-> CopyOnWriteArraySet   写复制集合

    ​									HashMap-> ConCurrentHashMap 分段锁映射

    原子性： 一个或多个操作要么全部执行，要么全部不执行；

    Atomic常用类：AtomicInteger AtomicLong  AtomicBoolean

70. cas算法：

    锁是用来做并发最简单的方式，代价也是最高的，独占锁是一种悲观锁，synchronize 是独占锁，它假设最坏的情况，确保不会有其他线程干扰的情况下执行，会导致其他需要锁的线程挂起，等待有锁的线程释放锁；

    乐观锁：不加锁，假设没有冲突执行操作，如果有冲突失败就重试，直到成功，其中cas(比较与交换，compare and swap)无锁算法

    atomic 应用场景：虽然基于cas 的线程安全机制很高效，但是只适合一些粒度较小型，如计数器这样的需求用起来才有效；

71. java虚拟机对synchronize的优化：锁的状态共有四种

    [https://blog.csdn.net/javazejian/article/details/72828483#synchronized%E5%BA%95%E5%B1%82%E8%AF%AD%E4%B9%89%E5%8E%9F%E7%90%86](https://blog.csdn.net/javazejian/article/details/72828483#synchronized底层语义原理)

    无锁状态，偏向锁，轻量级锁，重量级锁

    偏向锁：线程获得了锁，那么锁就进入偏向模式，此时Mark Word 的结构也变为偏向锁结构，当这个线程再次请求锁时，无需再做任何同步操作，即获取锁的过程，这样就省去了大量有关锁申请的操作，从而也就提供程序的性；所以，对于没有锁竞争的场合，偏向锁有很好的优化效果，毕竟极有可能连续多次是同一个线程申请相同的锁

    轻量级锁：倘若偏向锁失败，虚拟机并不会立即升级为重量级锁；轻量级锁能够提升程序性能的依据是“对绝大部分的锁，在整个同步周期内都不存在竞争”，注意这是经验数据。需要了解的是，轻量级锁所适应的场景是线程交替执行同步块的场合，如果存在同一时间访问同一锁的场合，就会导致轻量级锁膨胀为重量级锁。

    自旋锁：

    锁消除：

72. 注解：https://www.jianshu.com/p/9471d6bcf4cf

73. 反射：https://www.jianshu.com/p/9be58ee20dee

74. 反射机制：在运行状态，对任意一个类，都能知道这个类的属性和方法，对任意一个对象，都能调用它的方法和属性，动态调用属性及动态调用方法的功能称为Java语言的反射机制

75. 代理：jdk代理 与Cglib代理 区别：

    jdk代理有个限制，它只能为接口创建代理实例，对于没有通过接口定义业务方法的类，，可以使用cglib代理

    1. jdk 动态代理生成的代理类和委托类实现了相同的接口
    2. cglib动态代理生成的字节码更加复杂，生成的代理类是委托类的子类，且不能处理final 关键字修饰的方法
    3. jdk采用反射机制调用委托类的方法，cglib 采用类似索引的方式直接调用委托类方法

76. ConcurrentHashMap底层实现原理 : https://www.jianshu.com/p/865c813f2726

77. java 的四种引用 - 强软弱虚 https://www.ixigua.com/6808445147794113038?id=6808404438659629576&logTag=kEyLllTYFIQl0ppe0G_mh

    强引用：普通引用，没用引用指向对象的时候，垃圾回收

    软引用：堆内存不足时，内存分配不够是，垃圾回收；主要用在缓存

    弱引用：垃圾回收执行就会回收

78. 代码优化与完善：

    注释：主要业务流程，核心方法，条件，分支判断前

79. 阿里巴巴 代码p3c规约：https://home08.oss-cn-hangzhou.aliyuncs.com/tmp/Java%E5%BC%80%E5%8F%91%E6%89%8B%E5%86%8C%EF%BC%88%E5%B5%A9%E5%B1%B1%E7%89%88%EF%BC%89.pdf

80. sonarQube : http://www.imooc.com/article/291857

81. ThreadLocal :  提供线程局部变量，一个线程局部变量在多个线程中，分别有独立的副本

    如果多个线程同时访问进程中的全局变量，就会产生竞争条件，会有一致性问题，需要加锁；

    特点：简单，快速，安全

    使用场景：多线程场景（资源持有，线程一致性，并发计算，线程安全）

82. springboot 与 spring cloud 区别 : https://www.cnblogs.com/wwct/p/12942982.html

83. jvm监控： 

    springboot atuator : metrics , heapdump , threaddump

    java自带的jvm 监控工具： jconsole ,jvisualvm

    日志监控：ELK(elasticsearch + logstash + kibabna) 

84. 对称加密 与非对称加密：https://www.cnblogs.com/sdusrz/p/6233432.html
    SHA或者MD5签名算法
    RSA：非对称加密，有公钥和私钥

85. fa 

86. ds

87. dsa

88. s



