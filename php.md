1. 

2. 嗯嗯嗯

3. resful 即表述层状态转移（Representational State Transfer)

   http://www.ruanyifeng.com/blog/2014/05/restful_api.html?bsh_bid=516759003

4. php-fpm 是一个针对PHP实现了fastcgi 协议的程序，是一个PHP fastCGI 

   进程管理器，负责管理进程池，php-fpm 是master/worker进程模式

   PHPweb请求会指向具体的入口文件，

   css,js等静态文件请求会返回给浏览器，.php 的请求会由php-fm 调用PHP解析器处理，

5. 高并发及大流量解决方案

   流量优化：防盗链处理

   前端优化：cdn加速，启用浏览器缓存和图片压缩，添加异步请求

   服务端优化：页面静态化，并发处理，队列处理

   数据库优化：数据库缓存，读写分离

   web服务器优化：负载均衡

6. php默认不支持多线程

   PHP是单进程执行的，PHP处理多并发主要依赖服务器或php-fpm的多进程及进程复用；

   PHP多线程也称被人提及，但是进程内多线程资源共享和分配的问题难以解决，相关的扩展也不太稳定，

7. php-fpm 与swoole区别：https://www.yisu.com/zixun/132598.html

   **对比不同**

   **PHP-FPM**

   ● Master 主进程 / Worker 多进程模式。

   ● 启动 Master，通过 FastCGI 协议监听来自 Nginx 传输的请求。

   ● 每个 Worker 进程只对应一个连接，用于执行完整的 PHP 代码。

   ● PHP 代码执行完毕，占用的内存会全部销毁，下一次请求需要重新再进行初始化等各种繁琐的操作。

   ● 只用于 HTTP Server。

   **Swoole**

   ● Master 主进程（由多个 Reactor 线程组成）/ Worker 多进程（或多线程）模式

   ● 启动 Master，初始化 PHP 代码，由 Reactor 监听 Socket 句柄的事件变化。

   ● Reactor 主线程负责子多线程的均衡问题，Manager 进程管理 Worker 多进程，包括 TaskWorker 的进程。

   ● 每个 Worker 接受来自 Reactor 的请求，只需要执行回调函数部分的 PHP 代码。

   ● 只在 Master 启动时执行一遍 PHP 初始化代码，Master 进入监听状态，并不会结束进程。

   ● 不仅可以用于 HTTP Server，还可以建立 TCP 连接、WebSocket 连接。

8. eeeqw