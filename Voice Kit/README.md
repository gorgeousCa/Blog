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



