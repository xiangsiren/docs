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

7. dfssdfad

8. eeeqw