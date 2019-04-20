# Djiang 搭建教程
## 一、windows 下安装Djiango
官网下载需要的版本 https://docs.djangoproject.com/en/1.11/
选择想要的版本。
安装Django，这里是重点，需要使用命令行进行安装。
步骤：
a、命令行安装Django 
　　从官网上下载下来的Django是压缩包，解压在任意一个磁盘，通过命令行进入到setup.py所在目录，然后在安装（python setup.py）
　　具体命令：cd D:\学习\Django\Django-2.2\Django-1.11.5  python setup.py install
　　如果说找不到python，那么说明没有安装python
   大概需要1分钟的时间安装完成，Django将被安装到Python安装目录`` 的site-package`` 目录（我的在C:\Users\422221\AppData\Local\Programs\Python\Python35-32\Lib\site-packages），当然有些依赖的文件也分别附加到Python 相关类库里了，这个系统安装的时候已经自动做好了
b，配置环境变量
添加pathC:\Users\422221\AppData\Local\Programs\Python\Python35-32\Lib\site-packages\Django-1.11.5-py3.5.egg\django；C:\Users\422221\AppData\Local\Programs\Python\Python35-32\Scripts（其实就是安装的django目录，和python下的scripts目录）
c、到这里就大功告成了，接下来验证一下，有没有安装成功呢
　　通过命令行进入到从官网下载并解压的django文件夹下

　　具体：cd D:\学习\Django\Django-1.11.5\Django-1.11.5 回车python 可以看到 python的版本
