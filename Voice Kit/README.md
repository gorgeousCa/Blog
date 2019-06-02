# CREATE A VOICE KIT WITH YOUR Raspberry Pi
## 准备工作：
- wifi能自由访问学术资源
- 树莓派
- SD 卡
- VoiceKit 配件
- 获取VOICE KIT系统映像
Voice Kit需要特殊版本的Raspbian操作系统，其中包括一些额外的AIY软件。因此，在开始之前，您需要下载Voice Kit系统映像并将其闪存到MicroSD卡。
.img.xz从GitHub上的发布页面下载最新文件。
## PART 1 物理组装  
- ![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/IMG_20190531_210459.jpg)  
- 打开盒子，可见有如下配件：
![iamge text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/IMG_20190531_213101.jpg)
- 按照官网链接并组装：
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/tp.png)
- 现在您的盒子已组装好，请将外围设备插入：  
1 USB键盘   2USB鼠标   3 HDMI监视器  
- 将SD卡（带有Voice Kit SD图像的SD卡）插入Raspberry Pi板底部的插槽中。SD卡插槽应通过外部纸板形式提供的切口进入。
- 插上电源，Raspberry Pi将开始启动。如果显示器上没有显示任何内容，或者看到“Openbox语法错误”，请查看附录中的故障排除指南。    
- 单击 Raspberry Pi桌面右上角的网络图标。选择您首选的Wi-Fi接入点。    
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/%E6%A1%8C%E9%9D%A2.PNG)

## PART 2 验证是否有效
- 此脚本验证Voice HAT附件板上的音频输入和输出组件是否正常工作。双击桌面上的“ Check audio”图标。
单击脚本时，它将运行下面列出的每个步骤。注意：某些步骤需要语音输入，您将被提示 - 所以请密切关注！      
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/a1.png)      
- 按照脚本进行操作，如果一切正常，您将看到一条消息 The audio seems to be working如果看到错误消息，请按照消息详细信息解决问题，然后重试。  
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/a2.png)
- 在终端输入alsamixer命令，来调节音量的大小，如下图所示：
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/2.png)
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/1.png)
- 双击桌面上的“Check WiFi”图标。它将检查您的Raspberry Pi是否通过Wi-Fi连接到互联网。  
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/w1.png)  
如果一切正常，您会看到一条消息The Wi-Fi connection seems to be working。  
如果看到错误，请单击右上角的网络图标，确认您已连接到有效的接入点。  
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/w2.png)  
至此，已完成VOICE KIT的物理组装及测试
## PART 3 安装Google Assistant SDK
- 前往Google云端平台
要使用Google智能助理和云语音API，您需要从Google的开发者控制台获取凭据。
在您的计算机上（不是Raspberry Pi），请访问https://console.cloud.google.com/。  
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/dl.png) 
- 使用您的Google帐户登录    
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/%E5%AF%86%E7%A0%81.PNG)
- 首先，我们必须创建一个项目来跟踪我们想要在Voice Kit上使用的所有API。在顶部栏中，单击“ 选择项目”。
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Voice%20Kit/3.png)
- 创建一个新项目  
将出现类似左侧图像的对话框。
单击对话框右上角的“ 新建项目。  
- 输入并创建项目名称
在栏中输入项目名称，然后单击“ 创建”。（您可以单独保留“位置”选项。） 
- 打开项目
现在我们已经创建了项目，我们需要选择它，以便我们可以打开我们想要使用的API。
单击左侧导航中的“ 主页”链接。然后再次单击屏幕顶部的选择项目。然后选择刚刚创建的项目。
这将打开项目的仪表板视图（您可以通过屏幕顶部的下拉列表来显示;它应显示您在上一步中选择的名称）。
- 导航到库
现在我们需要打开Cloud Speech和Google Assistant API。
如果左侧导航尚未显示，请单击页面左上角的三行菜单图标将其打开。将鼠标悬停在API和服务上，然后单击“ 库”。
- 创建凭据
您将被定向到Google智能助理API的信息中心页面。从这里，您可以获得有关如何使用API​​的更多详细信息，并查看您正在进行的请求数量。
但是现在，我们将创建一个凭证文件，以便演示可以告诉Google他们是谁以及他们参与的项目。
单击“ 创建凭据”按钮。
- 向项目添加凭据
您应该被定向到Credentials帮助页面。
在“您使用的是哪种API？”下，选择Google Assistant API。
在“你将从哪里调用API？” 字段，选择其他UI（例如Windows，CLI工具）。
-最后，在“您将访问哪些数据？”下，选择“ 用户数据”我们这样做是因为我们将使用Google智能助理，这需要访问用户的数据。。
完成所有操作后，单击“ 我需要什么凭据”？按钮。
- 创建OAuth 2.0客户端ID
输入客户端ID。我们建议使用您之前使用的相同项目名称。
单击“ 创建OAuth客户端ID”按钮。
- 下载凭据
单击“ 下载”，将.json文件下载到您的计算机上。
在以下步骤中，您将把它复制到您的Raspberry Pi并保存在~/assistant.json
- 打开client_id.json文件
打开Downloads文件夹，右键单击client_id.json文件。
对于Mac：选择打开方式> TextEdit
对于Windows：选择打开方式>更多应用程序>记事本。








