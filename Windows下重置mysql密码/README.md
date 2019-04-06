# Windows下重置mysql密码 

今天发现 连接不上数据库，登录 window server 服务器查看，所有服务均运行正常。  
使用 root 账号登录 mysql 数据库，结果提示密码不匹配。即使使用mysql -u  root -p 命令也没有作用  
如下图所示：  
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Windows%E4%B8%8B%E9%87%8D%E7%BD%AEmysql%E5%AF%86%E7%A0%81/mysql1.PNG)

这里我主要讲一下 mysql 用户密码的重置步骤。

1. 停止 MySQL 服务
快捷键 windows + R ；  
输入 services.msc  ；  
找到MySQL  停止其服务（前提是你之前已经把MySQL加入了系统服务中）
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Windows%E4%B8%8B%E9%87%8D%E7%BD%AEmysql%E5%AF%86%E7%A0%81/%E6%9C%8D%E5%8A%A1.PNG)
