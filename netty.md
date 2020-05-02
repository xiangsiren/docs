1. ssfdafd 

2. netty: 高性能，事件驱动，异步非阻塞的Java io 开源框架

   支持 http websoket protobuf tcp udp binary

   使用场景：高性能领域，多线程并发领域，异步通信领域

   **以下是几种常用的IO 模型**

3. BIO: 阻塞io(blocking io)，新来一个请求对应创建一个线程,线程数量过多会消耗服务器资源

4. 伪异步IO: 与BIO类似，只是将客户端-线程的模式换成了线程池，可以灵活设置线程池大小，超出线程池大小就丢进队列等候。只是对BIO 的优化，没有解决线程连接的阻塞问题

5. NIO: 非阻塞IO(non-blocking io) 同步非阻塞IO模型，利用selector 多路复用器轮询用户创建线程，只需要一个线程轮询IO事件，比较适合做高并发; 

6. AIO: 异步非阻塞，适合较多IO任务较长的场景，

7. NIO 与 BIO 的比较：

   1. bio 以流的方式处理数据，nio 以块的方式处理数据，块io 效率比流的高很多
   2. bio 是阻塞的，nio 是非阻塞的
   3. bio 基于字节流与字符流进行操作，nio基于channel（通道）和buffer(缓存区)进行操作，数据总是从通道读取到缓存区，或者从缓存区写入到通道中；selector 用于监听多个通道的事件，因此使用单线程就可以监听多个客户端通道

8. sfsad 

9. websocket: h5协议规范，基于tcp的协议

   解决客户端与服务端实时通信产生的技术：  先通过http/https发起握手请求，之后创建一个用于交换数据的tcp 连接，此后客户端与服务端通过tcp连接进行实时通信，不再需要http连接的参与

10. websocket 优点：

    节省系统开销， 服务器主动传送数据到客户端，实时通信

11. sdafsdf

12. sdaf

13. fdsa

14. adsf

15. fdsa

16. dfsa

17. fdsa

18. dsf

19. dfsa

20. dfsa

21. dfsa