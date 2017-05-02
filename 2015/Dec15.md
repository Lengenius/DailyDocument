###Dec. 15 2015 天气 晴好
***
#####Tips：
需要不骄不躁

####Daily Comment
尝试了一点Android 开发，会在Achievements里面详细叙述。

另外，今天终于开始了慢跑之旅。只能说慢慢来吧，刚好学习调整自己的姿势，增强力量。既然是决定要做一辈子的事情，就要学会细水长流，而不是急功近利。天气不算是太冷，但是还是要注意跑后不要着凉了。

####Achievements

	public class FirstActivity extends Activity {
    @Override
    protected void onCreate(Bundle SavedInstanceState){
        super.onCreate(SavedInstanceState);
        requestWindowFeature(Window.FEATURE_NO_TITLE);
        setContentView(R.layout.first_layout);
        Button button1 = (Button) findViewById(R.id.button_1);
        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v){
                Intent intent = new Intent(Intent.ACTION_VIEW);
                intent.setData(Uri.parse("http://www.baidu.com"));
                startActivity(intent);
            }
        });
    }
    
+ 学习了手动创建Activity 
+ 编写Activity 的Layout 文件
+ 在Mainfest中注册 Activity Intent－filter标签的用法与含义，
+ 许多新型的Android Device好像都去除了Menu菜单。不过这个还是可以用其他的方式唤醒的。
+ 不同Activity之间的调用。信息传递方式。（显式的和隐式的）
+ Toast的含义与基本用法。包括两个SHORT 和 LONG的含义，引用方式。

> 简单来说，Layout 文件 Activity 和 AndroidMainfest文件三者的关系可以总结如下：
> 
> Activity 是工厂做工的工人，如果想要顺利的开始工作，就需要在AndroidMainfest这里进行登记注册。注册的时候需要说明许多信息。工人传成什么模样，就有Layout文件来进行决定。其实用工作室来做比喻更加形象，因为每个Activity能够做的事物很多，每Activity 都是多面手。有许多的接口能够完成各种各样的工作。

###Next Daily Plan
+ 运动 深蹲，俯卧撑 引体向上 悬垂举腿。
+ Think again 虽然考试赶不及了，但是还是可以看一下作为补充不是。一来提高英语水平，而来学习系统的逻辑思考方式，这些都是极好的啦。
+ 开始重新学习Android编程。先从整体架构开始，按照检视阅读的方式开始第一遍。

######一个人应当是身心合一的，全面发展的才是，你可能在不同的阶段重点不同，有所损益。然而，未来的日子一定会反映出来。

