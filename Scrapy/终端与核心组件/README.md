# scrapy终端与核心组件
## scrapy shell---测试xpath表达式
*Scrapy终端是一个交互终端，供您在未启动spider的情况下尝试及调试您的爬取代码。 其本意是用来测试提取数据的代码，不过您可以将其作为正常的Python终端，在上面测试任何的Python代码。
该终端是用来测试XPath或CSS表达式，查看他们的工作方式及从爬取的网页中提取的数据。 在编写您的spider时，该终端提供了交互性测试您的表达式代码的功能，免去了每次修改后运行spider的麻烦。
一旦熟悉了Scrapy终端后，能其在开发和调试spider时发挥的巨大作用。*
## 启用scrapy shell <url>
  - 例如在Windows命令终端下，输入scrapy shell www.jianshu.com 命令即可启用Scrapy shell 访问简书主页，并在终端下会输入如下大量信息。    
  ![image text](https://github.com/gorgeousCa/Dayup/blob/master/Scrapy/%E7%BB%88%E7%AB%AF%E4%B8%8E%E6%A0%B8%E5%BF%83%E7%BB%84%E4%BB%B6/14.PNG)    
如上图所示，表示成功访问网页。  
##使用scrapy shell   
- Scrapy shell 可以看成是在一个Python终端基础上添加了扩充功能的Python控制台程序，这些扩充包括若干函数和内置对象。    
Scrapy shell提供的功能函数有三种：   
shelp() - 打印可用对象及快捷命令的帮助列表    
        fetch(request_or_url) - 根据给定的请求(request)或URL获取一个新的response，并更新相关的对象  
        view(response) - 在本机的浏览器打开给定的response。 其会在response的body中添加一个 <base> tag ，使得外部链接(例如图片及css)能正确显示。 注意，该操作会在本地创建一个临时文件，且该文件不会被自动删除。  
内置对象  
        crawler - 当前 Crawler 对象.  
        spider - 处理URL的spider。 对当前URL没有处理的Spider时则为一个 Spider 对象。  
        request - 最近获取到的页面的 Request 对象。 您可以使用 replace() 修改该request。或者 使用 fetch 快捷方式来获取新的request。  
        response - 包含最近获取到的页面的 Response 对象。  
        sel - 根据最近获取到的response构建的 Selector 对象。  
        settings - 当前的 Scrapy settings  
