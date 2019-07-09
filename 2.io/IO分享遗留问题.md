## 1. 阻塞状态下，线程状态的变化（信号量）
我们知道传统的I/O都是阻塞式（blocked）的，原因是I/O操作比起cpu来实在是太慢了，可能差到好几个数量级都说不定。如果让 cpu 去等I/O 的操作，很可能时间片都用完了，I/O 操作还没完成呢，不管怎样，它会导致 cpu 的利用率极低。
所以，解决办法就是：一旦线程中执行到 I/O 有关的代码，相应线程立马被切走，然后调度 ready 队列中另一个线程来运行。
而当 I/O 完成时，则用一种叫中断（interrupt）的机制来通知 cpu。
cpu 会收到一个比如说来自硬盘的中断信号，并进入中断处理例程，手头正在执行的线程因此被打断，回到 ready 队列。而先前因 I/O 而waiting 的线程随着 I/O 的完成也再次回到 ready 队列，这时 cpu 可能会选择它来执行。
以上摘自：https://my.oschina.net/goldenshaw/blog/705397
## 2. 线程各个状态的切换，以及各个状态的场景（祖乐 JVM  P384）
- [ ] 对于线程各个状态的切换可以参考这个解释https://www.cnblogs.com/bhlsheji/p/5099362.html
## 3. 同步 异步IO  和 阻塞  与 非阻塞IO 区别（需要明确区分并举例）
## 4. IO多路复用的三种机制Select,Poll,Epoll理解
- [ ] 对于Epoll模型可以参考这边博客https://blog.csdn.net/linkedin_38454662/article/details/73337208
## 5. Nginx 里面的多路复用
## 6. Netty时如何实现NIO
## 7. Tengin的了解
