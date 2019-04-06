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

2. 切换到 bin 目录
在命令提示符窗口中，通过 cd 命令切换到 mysql 安装目录下的 bin 目录。
默认安装目录为 C:\Program Files\MySQL\MySQL Server   
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Windows%E4%B8%8B%E9%87%8D%E7%BD%AEmysql%E5%AF%86%E7%A0%81/bin.PNG)

3. 进入安全模式 
在 bin 目录下输入 mysqld --skip-grant-tables ，跳过权限检查启动 mysql。
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Windows%E4%B8%8B%E9%87%8D%E7%BD%AEmysql%E5%AF%86%E7%A0%81/bin1.PNG)

如果你配置了 my.ini 文件，则需要将其引入： mysqld --defaults-file="../my.ini" --skip-grant-tables 

4. 重置账户密码
打开另一个命令提示符窗口（别关闭安全模式窗口），同样切换到 mysql \ bin 目录，输入 mysql 跳过权限验证连接数据库。
