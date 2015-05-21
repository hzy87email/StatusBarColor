# StatusBarColor
设置大于兼容4.4版本的状态栏渐变色


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

![Alt text](https://github.com/hzy87email/StatusBarColor/blob/master/screenshot/demo1.png)

![Alt text](https://github.com/hzy87email/StatusBarColor/blob/master/screenshot/demo2.png)


