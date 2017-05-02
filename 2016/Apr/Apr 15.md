###Apr. 15 2016 天气 阴雨 深圳
***
#####Tips：
获取 理解 拓展 纠错 应用 测试

####Daily Comment
1. 大丰收的一天啊，终于实现了控件同时计时，虽然还有点bug misbehavior。
> 1. 先是实现了界面的显示，出bug 的原因是在Activity中使用了onCreate函数的另一个重载，不过还没有搞清楚是什么原因。
> 2. 之后是搞清楚了时间没有更新的原因，getView 方法中没有对convertView存在的情况进行处理，导致notifyDataSetChanged() 的时候没有处理。 这里用了View 的setTag 和 getTag方法进行了缓存。
> 3. 目前还剩下的一个Bug 是同时开多个计时器的时候会多次跳表，暂停单个计时器后，另一个还是会继续“跳表”。

2. 是不是应该重写一个TimerTextView 控件来计时比较好呢？这应该就算是另一种方法了吧？

####Achievements
+ 跑步计划完成 
+ 运动计划完成
+ 代码计划完成
+ 

####Disorder
* 读书计划未完成
* 

###Next Daily Plan
1. 解决计时时的“跳针问题”
2. 早起跑步一次 
3. 马拉松训练手册 前三章笔记。

### Weekly Plan
1. 一定要完成Android Programing 并写出总结。
2. 项目进度跟进
3. 跑步四次
4. **简历准备。**

######说好的用一年练好human flag啊……