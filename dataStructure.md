1. 

2. 线性表：多个数据元素的有限序列

   - 顺序线性表：使用一段连续的地址存储空间放置线性表的数据元素 例如：数组

   - 链式线性表：线性表的数据元素可以存储在任意的存储空间，每个节点包含数据元素和下个节点的指针（基本的单链表）;

     链式线性表分类：

     单向链表

     静态链表：使用顺序结构实现链式线性表

     双向链表：每个节点包含数据元素和上个节点指针与下个节点指针

     循环连表：线性表的尾部指向头结点，形成一个闭环

3. 栈和队列：

   栈：限定在表尾进行插入和删除的线性表 (后进先出)

   - 栈的线性存储结构
   - 栈的链式存储结构

   队列：只允许在一端插入，一端删除操作的线性表

   - 线性存储结构
   - 链式存储结构

4. 串: 多个字符组成的有限序列；又叫字符串

   链式存储结构的字符串

   顺序存储结构的字符串

5. 树：n 个节点的有限集

   森林：m(m >0 )棵互不相交树的集合

   树的存储结构：

   - 双亲表示法：

   - 孩子表示法
   - 孩子兄弟表示法

   树不同结构使用：堆，线段树，字典树，并查集

   二叉树具有唯一根节点，每个节点至多有两个孩子

   平衡二叉树（动态数据结构）：avl,红黑树

   二分搜索树是二叉树，每一颗子树也是二叉树

   - 二分搜索树的每个节点的值：大于其左子树所有节点的值，小于其右子树所有节点的值

   堆 :二叉堆是一颗完全二叉树,堆中某个节点的值总是不大于其父节点的值

   优先队列：

   - 普通队列，先进先出，后进后出
   - 优先队列，出队顺序和顺序无关，和优先级有关

   红黑树：

   1. 每个节点或者为红色，或者为黑色
   2. 根节点是黑色
   3. 每个叶子节点（最后的空节点）是黑色的
   4. 如果一个节点是红色的，那么他的孩子节点是黑色的
   5. 从任意一个节点到叶子节点，经过的黑色节点是一样的

6. 图：

   无向图：图中任意两个顶点的边是无向边

   有向图：图中任意两条边是有向边

   简单图：没有自环边和平行边

   完全图：无向图中任意两个顶点都存在边

   有向完全图：任意两个顶点之间存在互为相反的的两条弧

   有很少条边或弧的图称为稀疏图，反之称为稠密图。（数量不一定）

   与图的边或者弧相关的数字叫做权，带权的图称为网。

   子图：假设有两个图G=(V, {E})和G1=(V1, {E1})，如果V1⊆V，且E1⊆E，则称G1为G的子图

   图的顶点与边的关系：

   图的遍历：从图的一个顶点出发遍历图中其余顶点，且使每个顶点访问一次

   - 深度优先遍历
   - 广度优先遍历

   最小生成树：构造连通网的最小代价生成树，

   寻找最小生成树的两种算法:普利姆算法（prim），克鲁斯卡尔算法

   最短路径:

   - 迪杰斯特算法
   - 弗洛伊德算法

   拓扑结构

   关键路径

7. https://www.jianshu.com/p/30fdd6faea79 

   ### 强记算法点：

8. 链表和数组的对比：

   数组最好用于索引有语意的情况，支持快速查询

   链表不适合用于索引有语意的情况，链表：动态数据结构，不需要处理固定容量的问题 ；缺点：丧失了随机访问的能力

9. 位（bit）:计算机内部数据存储的最小单位，11010100是一个8位二进制数。

   字节(byte):计算机中数据处理的基本单位，一个字节由八个二进制位构成，

10. list:有序,可重复

   set: 无序不重复

   map:存储键值数据对的数据结构，根据键寻找值

11. trie:字典树（又称单词查找树）

    典型应用是用于统计，排序和保存大量的字符串（但不仅限于字符串），经常被搜索引擎用于文本词频统计；

    有点：利用字符串的公共前缀来减少查询时间，最大限度的减少无畏的字符串比较，查询效率比哈希树高；

    特性：根节点不包含字符，除根节点外每个节点只包含一个字符；

    串的快速检索，串排序

12. 线段树：是一种二叉搜索树，与区间树相似，

    对于一类问题，我们关心的是区间查询，区间统计

13. 平衡二叉树与AVL树：二分搜索树有个严重的问题，如果数据是顺序添加进树结构，二分搜索树会退化成链表，大大降低二分搜索树的效率

    AVl树是最为经典的平衡二叉树，最早的可以自平衡的二分搜索树结构，

    平衡二叉树：对于任意一个节点，左子树和右子树的高度差不超过一

14. 并查集：由孩子指向父亲的树结构，高效处理连接问题，网络中节点间的连接状态，

    并查集的时间复杂度分析: log *n  ; 并查集的时间复杂度比较复杂，严格意义上是： log *n  

    近乎是O(1)级别的；

    面试考察概率低

15. 图的表示：邻接矩阵，邻接表

    邻接表适合表示稀疏的图，邻接矩阵适合表示稠密的图，比如完全图

16. hash表：hash函数的设计和hash冲突的解决

    键通过hash函数到索引的分布越均匀越好

    hash函数设计：索引一般为整数，

    1. 小范围正整数直接使用；

    2. 小范围负整数进行偏移作为索引；

    3. 大整数取模一个素数；

    4. 浮点数转换为整数；

    5. ###### 字符串转换为整数: M树素数

       $$
       hash(code)=(((c*B+o)*B + d)*B + e ) % M
       hash(code) =( c * B3 + o * B 2 + d * B 1 + e * B 0) % M
       $$

    Hash函数设计的原则：

    一致性：如果a==b 则hash(a)==hash(b)

    高效性:  计算高效便捷

    均匀性：hash值均匀分布

    hash冲突的解决方法：链地址法

17. devops：DevOps是一种软件开发方法，涉及软件在整个开发生命周期中的持续开发，持续测试，持续集成，持续部署和持续监控

    https://blog.csdn.net/g6U8W7p06dCO99fQ3/article/details/82056948

18. 多路复用：多个网络io复用一个或少量的线程来处理这里连接

19. 高级数据结构和算法面试提及的概率很低：

    红黑树，计算几何，B-tree , 数论，斐波那契堆，FFT

20. 算法面试的准备范围：

    1. 各种排序算法
    2. 数据结构和算法的实现：如堆.二叉树，图...
    3. 基础数据结构的使用：如链表，栈，队列，哈希表，图，trie,并查集...
    4. 基础算法：深度优先，广度优先，二分查找，递归。。。
    5. 基本算法思想:递归，分治，回溯搜索，贪心，动态规划

21. 算法面试没有思路：

    1. 举例简单测试用例
    2. 暴力破解法：通常是思考的起点

22. 优化算法思路：

    1. 遍历常见的算法思路：递归，分治,回溯搜索，贪心，动态规划，递归
    2. 遍历常见的数据结构：
    3. 空间和时间的交换（哈希表）
    4. 预处理信息（排序）

23. #### HashMap和ConcurrentHashMap的知识总结

    https://www.jianshu.com/p/a7767e6ff2a2

24. f是的方法

25. fdsa 

26. dsfa 

27. dsfa

28. fdsa

