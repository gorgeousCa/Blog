# MyQR 生成个性二维码
## python中有一个好玩的库，不仅可以生成各种花色的二维码，还可以生成动态二维码。MyQR是一个能够生成自定义二维码的第三方库，可以根据需要生成普通二维码、带图片的艺术二维码，也可以生成动态二维码效果图如下：
![Alt text](https://github.com/gorgeousCa/Dayup/blob/master/QR%20code/test1.png)    
## MyQR是Python的一个第三方库，专门用来制作个性二维码。在Python调用MyQR之前需要先安装MyQR库:
## 安装方法  

## 1、通过【Windows】+【R】键打开一个对话框，在对话框中输入cmd并确定，即可打开cmd窗口。  
## 2、在cmd窗口中输入pip install MyQR并回车，即可下载。  
![Alt text](https://github.com/gorgeousCa/Dayup/blob/master/QR%20code/2.png)  
## 3、当出现Successfully installed MyQR字样时说明安装成功，就可以愉快地使用啦！  
## 实战演练
    from MyQR import myqr
    import os
    myqr.run(
        words='you are the appple in my eyes',        
        version=1,                   
        level='H',                  
        #picture='WChat.png',         
        colorized=False,              
        contrast=1.0,               
        brightness=1.0,              
        save_name='test00.png',        
        save_dir=os.getcwd()
        )
## 结果：
![Alt text](https://github.com/gorgeousCa/Dayup/blob/master/QR%20code/test00.png)  
## 用QQ扫一扫，得到我们words的值：you are the appple in my eyes
![Alt text](https://github.com/gorgeousCa/Dayup/blob/master/QR%20code/ap.png)
## 当然了，我们可以把words换成网页
## 如：  
`words='https://www.baidu.com/'#url`  
`picture='WChat.png',#想要合成的照片`  
`colorized=True, '# 使变成彩色`  
## 结果：
![Alt text](https://github.com/gorgeousCa/Dayup/blob/master/QR%20code/test01.png)
## 当然还可以生成动态的二维码，只需你把想要合成的图片变成动图，即.git 图片
## 扫描结果：

## 至此，我们就为百度的二维码，扫描即可进入新浪财经官方网站，是不是很简单呢？下面我们附上参数列表及含义。
##




