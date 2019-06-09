# Windows 10 安装 scrapy
Scrapy 是一个快速的高层次的屏幕抓取和网页爬虫框架，爬取网站，从网站页面得到结构化的数据，它有着广泛的用途，从数据挖掘到监测和自动测试，Scrapy完全用Python实现，完全开源，代码托管在Github上，可运行在Linux，Windows，Mac和BSD平台上，基于Twisted的异步网络库来处理网络通讯，用户只需要定制开发几个模块就可以轻松的实现一个爬虫，用来抓取网页内容以及各种图片。
- 安装Scarpy依赖的包
wheel
Lxml
twisted
Pywin32 
其中Twisted在windows上安装时需要依赖 Microsoft Visual C++ 14.0进行编译,如果没有这个环境在安装时必然报错，一般提示信息是这样的：
![Image text](https://github.com/gorgeousCa/Dayup/blob/master/Scrapy/%E5%AE%89%E8%A3%85/2.PNG)
```running build_ext
building 'twisted.test.raiser' extension
error: Microsoft Visual C++ 14.0 is required. Get it with "Microsoft Visual C++ Build Tools": https://visualstudio.microsoft.com/downloads/
```
- 经过多次尝试之后，发现可以单独安装上面的依赖包，就可以顺利的安装好Scarpy
wheel可以直接安装 pip install wheel  
下面给出剩下的下载路径:    
https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted  
这个url是Python的非官方二进制扩展包的汇总页面，如果打开上面的URL后显示的界面是下面这个样子，可以根据模块名字搜索得到包的下载版本列表。  
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Scrapy/%E5%AE%89%E8%A3%85/1.1.PNG)

- 选择符合你Python和Windows版本的wheel文件下载，如我下载的是 Twisted-19.2.1-cp37-cp37m-win_amd64.whl 
- 待下载完成后（当然这可能要等待很久的时间，可能会失败很多次，哎呀呀，血的教训哪），在windows c 下，切换到wheel 文件所在的目录之下，并使用
`pip install  Twisted-19.2.1-cp37-cp37m-win_amd64.whl`
来完成安装，如下图所示：





    
 
