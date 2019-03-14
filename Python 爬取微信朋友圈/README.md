# python爬取微信朋友圈之环境以及软件的安装
## 一、环境准备
    1.jdk1.7.0 

    2.android-sdk_r24.3.4-windows

    3.python:3.6

    4.appium：1.4.13.1

    5.Node.js：node-v4.4.7-x64

    6.Appium-Python-Client
## 二、jdk安装
    1.下载jdk包，我的是64位1.7版本。

    2.一路傻瓜式安装，注意安装路径不要有空格，不要有中文。jdk和jre不要放在一个文件夹下

    3.设置三个环境变量,我的电脑>选择“属性”->“高级”->“环境变量”->“系统变量”->“新建”
    JAVA_HOME----D:\Java\jdk1.6.0” （根据自己安装路径填写）
    CLASSPATH--- .;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar;
    PATH-----;%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;
     4.打开cmd验证是否安装成功，输入java -version，然后输入javac
    能显示版本号和下面的帮助信息说明安装成功
    如下图：
## 三、安卓开发环境配置
如果我们要使用Android设备做App抓取的话，还需要下载和配置Android SDK，这里我们直接下载Android Studio。下载后直接安装即可。  
确保在安装 Android Studio 之前，已经安装好 Java JDK。  
以下图片为 Android SDK 初始化 JDK  
检查创建应用程序所需的组件，下图选中了 "Android Studio", "Android SDK", "Android 虚拟机"和"外观(Intel chip)"。    
需要指定本机上的 Android Studio 和 Android SDK 的路径
指定 Android 模拟器默认需要的 ram 空间为512M  
最后，解压 SDK 软件包到本地机器，这将持续一段时间并占用2626M 的硬盘空间。  
完成上面的步骤，将看到结束按钮，并可以在欢迎界面中打开 Android Studio 项目，如下图：
android-sdk下载安装
3.勾选你要下载的API版本和对应的android版本，后面模拟器会用到（不下载用其它模拟器也行，或者真机），然后坐等下载
android-sdk环境变量
1.在系统变量新建：ANDROID_HOME，对应变量值为：D:\androidsdk\android-sdk-windows（sdk安装路径）
2.path添加两个变量，将以下箭头所指的两个文件路径添加到path里
3.path里面添加D:\androidsdk\android-sdk-windows\tools和D:\androidsdk\android-sdk-windows\platform-tools
四、adb环境
1.因为adb是在D:\androidsdk\android-sdk-windows\platform-tools这个目录下的，所以上面添加了环境变量后，可以直接在cmd里面运行了。
2.在cmd输入adb -version可以查看对应版本号
五、连接手机
    1.手机用数据线连电脑，如果安装了91助手或者360什么的可以先下载手机驱动，确认手机能连上  
    2.打开cmd输入：adb devices,当屏幕上出现一串字符，后面显示devices说明连接成功（出现其它的提示，得检查自己的环境了）  
六、Python安装
2.下载Python安装包，选择2.7版本和3.6版本都可以

官网下载地址：https://www.python.org/15

    1.Python安装，双击傻瓜式安装（别安装在c盘哦）

    2.小编的安装目录在d盘：D:\python

    3.安装完成后，看下这个目录D:\python\Scripts，有没pip.exe和easy_install.exe（一般都有）

    4.将D:\python和D:\python\Scripts，添加到环境变量path下

    5.打开cmd输入python,出现版本号，然后输入print("hello world!")
  七、安装node.js
   1.下载官网地址：https://nodejs.org/en/download/23
   2.2.下载后一路傻瓜式安装，安装完成后，运行cmd，输入node –v查看版本号，然后输入npm
   3.出现如上图信息，表示node.js安装成功。npm是一个node包管理和分发工具，有了npm，后面就可以输入指令在线安装appium(打开 cmd输入：npm install –g appium但是一般不推荐这种，下载比较慢，所以用下面这种客户端安装)
   八、安装appium
    1.下载安装地址：https://bitbucket.org/appium/appium.app/downloads/16
    2.直接双击appium-installer.exe文件安装就好，桌面会生成一个appium的图标，启动后界面显示如下  
   九、安装.net framework
   1.Appium是用.net开发的，所以需要安装.net framework4.5，下载地址：https://www.microsoft.com/zh-cn/download/details.aspx?id=3065332
   十、appium-doctor
   1.appium安装好后，找到这个文件目录D:\appium\Appium\node_modules\.bin

   2.将上面的地址添加到环境变量path下

   3.打卡cmd，输入appium-doctor,检查环境是否OK，出现如下图所示，说明环境OK
十一、安装Appium-Python-Client
1.前面python环境安装，已经准备好pip了，所以这里直接打开cmd，输入：pip install Appium-Python-Client
至此，所有的环境以及软件都已全部安装完毕，下面我们就开始使用吧！
   
   
    


