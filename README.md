# StatusBarColor
##设置大于4.4兼容版本的状态栏渐变色,让你的toolbar的状态栏在4.4以上版本实现5.0的Material Design效果

<p>代码中的SystemBarTintManager文件引用了<a href="https://github.com/jgilfelt/SystemBarTint" title="Title">
SystemBarTint</a>的开源类库,感谢作者的开源精神.</p>

**步骤**

1.首先在res资源文件目录下建立values-19目录,只要系统版本大于kitkat系统会自己读取该目录下的style文件,将默认的values下的style中的主题样式拷贝到values-19目录下的style文件中,需要添加两个设置如下

        <item name="android:windowTranslucentNavigation" >true</item>
        
        <item name="android:windowTranslucentStatus">true</item>


2.在mainactivity的布局中的根标签下面设置如下参数

<pre><code>
android:fitsSystemWindows="true"

</code></pre>


3.然后代码中添加:

<pre><code>
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
            SystemBarTintManager tintManager = new SystemBarTintManager(this);
            tintManager.setStatusBarTintEnabled(true);
            tintManager.setStatusBarTintResource(R.color.colorPrimaryDark);
        }
</code></pre>



#####红米note4.4.4截图如下：

![Alt text](https://github.com/hzy87email/StatusBarColor/blob/master/screenshot/diorKTU84Pjason05212015215658.gif)

![Alt text](https://github.com/hzy87email/StatusBarColor/blob/master/screenshot/demo1.png)

![Alt text](https://github.com/hzy87email/StatusBarColor/blob/master/screenshot/demo2.png)

#####解决之前样式问题导致nexus原生虚拟键栏bug问题，添加了虚拟键颜色样式
![Alt text](https://github.com/hzy87email/StatusBarColor/blob/master/screenshot/解决nexus原生系统底部虚拟按键导致的bug问题.png)



