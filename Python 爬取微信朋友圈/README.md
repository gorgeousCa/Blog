# python爬取微信朋友圈  
         
## 环境准备
   - jdk1.7.0   
   - Android Studio
   - python:3.6  
   - appium 
   - Node.js：node-v4.4.7-x64   
   - Appium-Python-Client  

## jdk安装
   - 下载jdk包，我的是64位1.7版本。    
   - 一路傻瓜式安装，注意安装路径不要有空格，不要有中文。jdk和jre不要放在一个文件夹下  
   - 设置三个环境变量,我的电脑>选择“属性”->“高级”->“环境变量”->“系统变量”->“新建”  
     JAVA_HOME----D:\Java\jdk1.6.0” （根据自己安装路径填写）       
     CLASSPATH--- .;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar;     
    PATH-----;%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;  
  ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B7.PNG)  
   ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B71.PNG)
  - 打开cmd验证是否安装成功，输入java -version，然后输入javac能显示版本号和下面的帮助信息说明安装成功:        
   如下图：    
   ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/javav.PNG)  
   ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B75.PNG)   
  
## 安卓开发环境配置     
 - 如果我们要使用Android设备做App抓取的话，还需要下载和配置Android SDK.  
  这里我们直接下载Android Studio。下载后直接安装即可。  
  ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B74.PNG)  
  确保在安装 Android Studio之前，已经安装好 Java JDK。    
  
  - 检查创建应用程序所需的组件，下图选中了 "Android Studio", "Android SDK", "Android 虚拟机"和"外观(Intel chip)":  
  ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B77.PNG)  
   - 需要指定本机上的 Android Studio 和 Android SDK 的路径:    
   ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B76.PNG)  
  - 指定 Android 模拟器默认需要的 ram 空间为512M : 
  ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B78.PNG)  
 最后，解压 SDK 软件包到本地机器，这将持续一段时间并占用2626M 的硬盘空间。  
 

   - 完成上面的步骤，将看到结束按钮，并可以在欢迎界面中打开 Android Studio 项目，如下图：  
  ![image](https://github.com/gorgeousCa/Dayup/blob/master/%E6%8D%95%E8%8E%B710.PNG)  
    - android-sdk下载安装 :    
    勾选你要下载的API版本和对应的android版本，后面模拟器会用到（不下载用其它模拟器也行，或者真机），然后坐等下载
  ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B71-1.PNG)
  ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/1.1.11.png)    
 - android-sdk环境变量 :       
    1.在系统变量新建：ANDROID_HOME，对应变量值为：C:\Users\lenovo\AppData\Local\Android\Sdksdk安装路径）
    ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/%E6%8D%95%E8%8E%B71-2.PNG)  
   2.path里面添加C:\Users\lenovo\AppData\Local\Android\Sdk\tools和C:\Users\lenovo\AppData\Local\Android\Sdk\platform-tools
     ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/1-3.PNG)  
## adb环境
  - 因为adb是在C:\Users\lenovo\AppData\Local\Android\Sdk\platform-tools这个目录下的，所以上面添加了环境变量后，可以直接在cmd里面运行了。  
  - 在cmd输入adb -version可以查看对应版本号
  ![Iamge](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/adb.png)
  
## 连接手机  
  - 手机用数据线连电脑，如果安装了91助手或者360什么的可以先下载手机驱动，确认手机能连上
  
 - 打开cmd输入：adb devices,当屏幕上出现一串字符，后面显示devices说明连接成功（出现其它的提示，得检查自己的环境了）
 ![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/adbdevices.png)
## Python安装:
  - 下载Python安装包，选择2.7版本和3.6版本都可以:
  官网下载地址：https://www.python.org/15
  - 小编的安装目录在d盘：D:\python
  - 安装完成后，看下这个目录D:\python\Scripts，有没pip.exe和easy_install.exe（一般都有:  
  - 将D:\python和D:\python\Scripts，添加到环境变量path下:
  - 打开cmd输入python,出现版本号，然后输入print("hello world!"):
  ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/hello%20world.png)
  ## 七、安装node.js
   - 下载官网地址：https://nodejs.org/en/download/23:
   ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/1-6.PNG)
    - 下载后一路傻瓜式安装，安装完成后，运行cmd，输入node –v查看版本号，然后输入npm:
     ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/1.1.1.png)
    - 出现如上图信息，表示node.js安装成功。npm是一个node包管理和分发工具，有了npm，后面就可以输入指令在线安装appium(打开 cmd输入：npm install –g appium但是一般不推荐这种，下载比较慢，所以用下面这种客户端安装)
  ## 八、安装appium
   - 下载安装地址：https://bitbucket.org/appium/appium.app/downloads/16:  

   - 直接双击appium-installer.exe文件安装就好，桌面会生成一个appium的图标，启动后界面显示如下
     ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/qppium.png)
  ## 九、安装.net framework
   - Appium是用.net开发的，所以需要安装.net framework4.5，下载地址：https://www.microsoft.com/zh-cn/download/details.aspx?id=3065332
     ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/1.1.3.png)
   
 ## 十、appium-doctor
   - appium安装好后，找到这个文件目录D:\appium\Appium\node_modules\.bin  
   - 将上面的地址添加到环境变量path下  
     ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/modules.png)  
   - 打卡cmd，输入appium-doctor,检查环境是否OK，出现如下图所示，说明环境OK  
     ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/success.png)  
  ## 十一、安装Appium-Python-Client  
   - 前面python环境安装，已经准备好pip了，所以这里直接打开cmd，输入：pip install Appium-Python-Client
   ## 十二、代码实现
   - 在完成了上述一系列安装以及配置环境之后，接下来咱们终于进入了正题:   
   - 首先，将手机与pc端用数据线连接，并打开手机端的USB调试，并且中途使手机不要息屏，打开桌面上的appium,如下图所示：   
   ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/1.png)    
   - 点击start Server,进入以下界面：    
   ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/2.png)         
   - 点击右上角的搜索符号，进入以下界面：  
   ![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/3.png)
   - 该界面的详细说明：  
  ![image]( https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/img.jpg)  
 -下面我们输入以下脚本: 
```"platformName": "Android",
   "deviceName": "MI_8",//手机设备名称，通过adb devices查看
   "app_package": "com.tencent.mm",
   "app_activity": ".ui.LauncherUI",
   "driver_server": "http://127.0.0.1:4723/wd/hub",
    "app": "F:\\迅雷下载\\weixin_1400.apk"
```
- 即：  
![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/4.png)  
- 点击右下角的 start session，手机会自动转到微信的登陆界面，运行结果如下：  
![image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/5.png) 
- 随后在手机上会弹出安装下面两个软件的提示，安装后，桌面上多两个图标。那么恭喜你启动成功:
![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/d1.png)
![Image](https://github.com/gorgeousCa/Dayup/blob/master/Python%20%E7%88%AC%E5%8F%96%E5%BE%AE%E4%BF%A1%E6%9C%8B%E5%8F%8B%E5%9C%88/d2.png)
- 要先点击图中的按钮，才会出现手机上的画面，图中我已经定位到登陆按钮，可以在右边看到属性resource-id,以及clickable=True，确实是可以点击的。    
下面我们就模拟登陆，具体就是通过找到登陆这个元素，然后点击它    
```  from appium import webdriver    
from selenium.webdriver.support.ui import WebDriverWait  
from selenium.webdriver.support import expected_conditions as EC  
from selenium.webdriver.common.by import By  

PLATFORM='Android'  
deviceName='MI_8'  
app_package='com.tencent.mm'  
app_activity='.ui.LauncherUI'  
driver_server='http://127.0.0.1:4723/wd/hub'  

class Moments():  
    def __init__(self):  
        self.desired_caps={  
        'platformName':PLATFORM,  
        'deviceName':deviceName,  
        'appPackage':app_package,  
        'appActivity':app_activity}  
        self.driver=webdriver.Remote(driver_server,self.desired_caps)  
        self.wait=WebDriverWait(self.driver,300)  
def login(self):  
        print('点击登陆按钮——————')  
        login=self.wait.until(EC.presence_of_element_located((By.ID,'com.tencent.mm:id/d75')))  
        login.click()  

 def main(self):  
        self.login()  

M=Moments()   
M.main()
```
- 运行后就会跳出登陆界面，接下来就都是定位元素与点击元素的事情：

```from appium import webdriver  
from selenium.webdriver.support.ui import WebDriverWait  
from selenium.webdriver.support import expected_conditions as EC  
from selenium.webdriver.common.by import By  
import time  
import pymongo  
PLATFORM='Android' 
deviceName='MI_8'
app_package='com.tencent.mm'
app_activity='.ui.LauncherUI'
driver_server='http://127.0.0.1:4723/wd/hub'  

class Moments():  
    def __init__(self):  
        self.desired_caps={  
        'platformName':PLATFORM,  
        'deviceName':deviceName,  
        'appPackage':app_package,  
        'appActivity':app_activity}  
        self.driver=webdriver.Remote(driver_server,self.desired_caps)  
        self.wait=WebDriverWait(self.driver,300)  
        self.client=pymongo.MongoClient()  
        self.db=self.client.weixin  
        self.collection=self.db.weixin  

    def login(self):  
        print('点击登陆按钮——————')
        login=self.wait.until(EC.presence_of_element_located((By.ID,'com.tencent.mm:id/d75')))  
        login.click()  
        #输入手机号  
        phone=self.wait.until(EC.presence_of_element_located((By.ID,    'com.tencent.mm:id/hz')))  
        phone_num=input('请输入手机号：')  
        phone.send_keys(phone_num)  
        print('点击下一步中')  
        button=self.wait.until(EC.presence_of_element_located((By.ID,       'com.tencent.mm:id/alr')))  
        button.click()  
        pass_w=input('请输入密码：')  
        password=self.wait.until(EC.presence_of_element_located((By.ID,'com.tencent.mm:id/hz')))  
        password.send_keys(pass_w)  

        login=self.driver.find_element_by_id('com.tencent.mm:id/alr')  
        login.click()  
        #提示 叉掉
        tip=self.wait.until(EC.element_to_be_clickable((By.ID,'com.tencent.mm:id/an2')))  
        tip.click()  

    def enter(self):  
        print('点击发现——')  
        tab=self.wait.until(EC.element_to_be_clickable((By.XPATH,'//*[@resource-id="com.tencent.mm:id/cdh"]/..')))  
        print('已经找到发现按钮')  
        time.sleep(6)  
        tab.click()  
        # self.wait.until(EC.text_to_be_present_in_element((By.ID,'com.tencent.mm:id/cdj'),'发现'))  
        print('点击朋友圈')  
        friends=self.wait.until(EC.presence_of_element_located((By.XPATH,'//*[@resource-id="android:id/list"]/*[@class="android.widget.LinearLayout"][1]')))  
        friends.click()  

    def crawl(self):  
        while True:  
            items=self.wait.until(EC.presence_of_all_elements_located((By.XPATH,'//*[@resource-id="com.tencent.mm:id/dja"]  //*[@class="android.widget.FrameLayout"]')))  
            self.driver.swipe(300,1000,300,300)  
            for item in items:  
                try:  
                    nickname=item.find_element_by_id('com.tencent.mm:id/as6').get_attribute('text')  
                    print(nickname)  
                    content=item.find_element_by_id('com.tencent.mm:id/dkf').get_attribute('text')  
                    print(content)  
                    data={'nickname':nickname,  
                    'content':content}  
                    self.collection.update({'nickname':nickname,'content':content},{'$set':data},True)  

                except:  
                    pass  


    def main(self):  
        self.login()  
        self.enter()  
        self.crawl()  

M=Moments()  
M.main()
```


- driver.swipe()是从点A滑动到点B,driver.swipe(300,1000,300,300)是从点（300，1000）滑动到（300，300）  
- self.collection.update({'nickname':nickname,'content':content},{'$set':data},True)
- 首先根据昵称和正文来查询，如果信息不存在，则插入数据，否则更新数据，关键点是第三个参数True，这可以实现存在即更新，不存在即插入的代码。


