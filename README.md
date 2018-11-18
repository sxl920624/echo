分享一下关于Java网络通讯方面的内容.
    下载地址：https://github.com/mldn/echo

Java基础知识：BIO、NIO、AIO三者的技术实现，以及彼此之间的区别

Netty：TCP 程序实现为主


    代码的核心：Echo程序模型，通过网络实现一个基础的Echo。


一、BIO模型：同步阻塞IO处理
    在程序的开发之中Java里面最小的处理单元就是线程，也就是说每一个线程可以进行IO的处理，在处理之中，该线程无法进行任何的其他操作。
    多线程是不可能无限制进行创造的，所以需要去考虑堆线程进行有效的个数控制。如果产生的线程过多，那么直接的问题在于，处理性能降低 ，响应的速度变慢。
    需要去区分操作系统的内核线程，以及用户线程的区别，所以最好与内核线程有直接联系，需要使用到固定线程池。
    【BIO】现在烧水，意味着你现在需要一直盯着水壶去看，一直看它已经烧为止，在这之中你什么都干不了。


二、NIO模型：同步非阻塞IO处理
   在传统的Java环境里面，最初的程序需要依赖于JVM虚拟机技术。最早的时候由于虚拟机的性能很差，所以很少有人去关注通讯的速度问题，大部分的问题都出现在了CPU处理上。
   但是随着硬件的性能提升，实际上CPU的处理速度加强了。所以从JDK 1.4开始就引入NIO的开发包，可以带来底层数据的传输性能。
   在NIO之中采用了一个Reactor事件模型，注册的汇集点Selector
  【NIO】烧水，不会一直傻站着看，你采用轮询的方式来观察水是否烧开。
  
