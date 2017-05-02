####鸡汤 2016年5月25日
其实鸡汤都是别人吃完肉剩下的，但是对于濒临饿死的人来说，一口鸡汤或许就是救命的灵药，就是人生的转折。 喝完鸡汤，赶紧去找点吃的。





#####今日
+ CSAPP 编码方式的学习。没有学习太多内容，今天比较浪费。
+ 上午看了一会小说。
+ 下午写了一点TimeTracker 之后一觉睡到5点钟，实在是很累。
+ 膝盖不知道为何一直在疼，看来单纯的休息恐怕也不是最好的办法。
+ 了解了反射机制，目前来看反射似乎提供了另外一种访问对象的方式，而且还可以避开许多编译时的问题，提供更多的灵活性，但是因为要在运行时调用，会牺牲一部分性能。

> ##[Drawbacks of Reflection](http://docs.oracle.com/javase/tutorial/reflect/index.html "title")

> Reflection is powerful, but should not be used indiscriminately. If it is possible to perform an operation without using reflection, then it is preferable to avoid using it. The following concerns should be kept in mind when accessing code via reflection.

> #####Performance Overhead
> + Because reflection involves types that are dynamically resolved, certain Java virtual machine optimizations can not be performed. Consequently, reflective operations have slower performance than their non-reflective counterparts, and should be avoided in sections of code which are called frequently in performance-sensitive applications.
> 
> #####Security Restrictions
+ Reflection requires a runtime permission which may not be present when running under a security manager. This is in an important consideration for code which has to run in a restricted security context, such as in an Applet.
>
> #####Exposure of Internals
+ Since reflection allows code to perform operations that would be illegal in non-reflective code, such as accessing private fields and methods, the use of reflection can result in unexpected side-effects, which may render code dysfunctional and may destroy portability. Reflective code breaks abstractions and therefore may change behavior with upgrades of the platform.

#####明日
+ 继续CSAPP 虽然基础很重要，但是更重要的事情是找到一份工作，好好开始自己的生活。
+ 还是好好开发TimeTracker 吧，尽快上线，毕竟有自己开发的应用好办得多。