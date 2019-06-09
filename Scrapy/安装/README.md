# Windows 10 安装 scrapy
Scrapy 是一个快速的高层次的屏幕抓取和网页爬虫框架，爬取网站，从网站页面得到结构化的数据，它有着广泛的用途，从数据挖掘到监测和自动测试，Scrapy完全用Python实现，完全开源，代码托管在Github上，可运行在Linux，Windows，Mac和BSD平台上，基于Twisted的异步网络库来处理网络通讯，用户只需要定制开发几个模块就可以轻松的实现一个爬虫，用来抓取网页内容以及各种图片。
- 安装Scarpy依赖的包
wheel
Lxml
twisted
Pywin32 
其中Twisted在windows上安装时需要依赖 Microsoft Visual C++ 14.0进行编译,如果没有这个环境在安装时必然报错，一般提示信息是这样的：
```running build_ext
building 'twisted.test.raiser' extension
error: Microsoft Visual C++ 14.0 is required. Get it with "Microsoft Visual C++ Build Tools": https://visualstudio.microsoft.com/downloads/
```
- 经过多次尝试之后，发现可以单独安装上面的依赖包，就可以顺利的安装好Scarpy
wheel可以直接安装 pip install wheel
下面给出剩下的3个的下载路径：
https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml
https://www.lfd.uci.edu/~gohlke/pythonlibs/#pywin32
https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted

这个url是Python的非官方二进制扩展包的汇总页面，如果打开上面的URL后显示的界面是下面这个样子，可以根据模块名字搜索得到包的下载版本列表。



    
