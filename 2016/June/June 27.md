####进度条 2016年6月27日
进度条是一个非常不错的发明，它直击了人类的弱点。

设想一个没有进度条的世界。安装游戏的时候一直在显示“Loading”界面，迟迟不见安装完毕。银行办理业务的时候一直没有提示，被人插队了也不知道。去加油站加油也并不知道需要多久能够加满。是不是隐约有着一丝不安？大部分人都是不确定性的俘虏，他们有时候宁愿面对一个确定的bad ending，也不愿意忍受一点煎熬。可惜人生并没有一个确定的进度条，也不是一张详细的进度清单。你必须要有足够的勇气和耐心去面对未来的挑战，看到周围的人做了些什么也不能动摇。

你要向着目标前进，有时候会有迂回，但是你不能停下来。

#####今日
+ 开始做界面的部分，其实真正开发起来时间是过得很快的。不要被完美主义所牵绊，你需要的是“新泽西”精神。
+ 学习整理了 Creating View Class 的方法。大体总结如下：

> + 一个全新的控件分为“视觉”和“功能”两个部分。视觉方面主要负责控件的外观和Layout 等。功能方面则用来处理一些交互事件。
> + 视觉：

> > + `onDraw()` 方法负责绘制控件，相关的`Paint` 和 `Canvas`对象最好在构造方法中准备好，因为每次准备这些对象都会调用很多资源，出于性能的考虑，最好减少初始化的次数。 其中Canvas 对象负责What to 的问题，Paint 对象负责 How to 的问题。直观一点来说，Canvas 就是画布，Paint 就是画笔。
> > + 构造方法中可以结合`TypeArray` 和 `obtainStyledAttributes()`方法来定义一些初始属性。
> > + `onMeasure()` 方法用来计算控件的外观尺寸等等，因为控件并不是一个独立的单元，它会同周围的元素产生一定的相对位置关系，所以需要这个方法来计算控件的尺寸。这个方法并没有返回值，它通过`setMeasuredDimension()` 方法绑定结果，如果未调用这个方法会产生RunTimeException同样 `onSizeChanged()`方法也是有着类似的作用，但是相对来说其精确度会差一点，因为`onMeasure()`方法通过`View.MeasureSpec` 可以与父元素产生相互作用。

#####明日
+ Chart 的绘制。先伪造数据测试。
+ 基本条目的读取和存储。