# Scrapy 框架的基本操作
*Scrapy是一个为了爬取网站数据，提取结构性数据而编写的应用框架。 其可以应用在数据挖掘，信息处理或存储历史数据等一系列的程序中。
其最初是为了页面抓取 (更确切来说, 网络抓取 )所设计的， 也可以应用在获取API所返回的数据(例如 Amazon Associates Web Services ) 或者通用的网络爬虫。Scrapy用途广泛，可以用于数据挖掘、监测和自动化测试。
Scrapy 使用了 Twisted异步网络库来处理网络通讯。整体架构大致如下：*     
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Scrapy/%E6%A1%86%E6%9E%B6%E7%9A%84%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C/7.png)
## Scrapy主要包括了以下组件：
- 引擎(Scrapy)
用来处理整个系统的数据流处理, 触发事务(框架核心)
- 调度器(Scheduler)
用来接受引擎发过来的请求, 压入队列中, 并在引擎再次请求的时候返回. 可以想像成一个URL（抓取网页的网址或者说是链接）的优先队列, 由它来决定下一个要抓取的网址是什么, 同时去除重复的网址
- 下载器(Downloader)
用于下载网页内容, 并将网页内容返回给蜘蛛(Scrapy下载器是建立在twisted这个高效的异步模型上的)
- 爬虫(Spiders)
爬虫是主要干活的, 用于从特定的网页中提取自己需要的信息, 即所谓的实体(Item)。用户也可以从中提取出链接,让Scrapy继续抓取下一个页面
- 项目管道(Pipeline)
负责处理爬虫从网页中抽取的实体，主要的功能是持久化实体、验证实体的有效性、清除不需要的信息。当页面被爬虫解析后，将被发送到项目管道，并经过几个特定的次序处理数据。
- 下载器中间件(Downloader Middlewares)
位于Scrapy引擎和下载器之间的框架，主要是处理Scrapy引擎与下载器之间的请求及响应。
- 爬虫中间件(Spider Middlewares)
介于Scrapy引擎和爬虫之间的框架，主要工作是处理蜘蛛的响应输入和请求输出。
- 调度中间件(Scheduler Middewares)
介于Scrapy引擎和调度之间的中间件，从Scrapy引擎发送到调度的请求和响应。
### Scrapy运行流程大概如下：
- 引擎从调度器中取出一个链接(URL)用于接下来的抓取
- 引擎把URL封装成一个请求(Request)传给下载器
- 下载器把资源下载下来，并封装成应答包(Response)
- 爬虫解析Response
- 解析出实体（Item）,则交给实体管道进行进一步的处理
- 解析出的是链接（URL）,则把URL交给调度器等待抓取
### 基本命令
- scrapy startproject 项目名称
   - 在当前目录中创建中创建一个项目文件（类似于Django）
- scrapy genspider [-t template] <name> <domain>
   - 创建爬虫应用
   如：  
      scrapy gensipider -t basic oldboy oldboy.com  
      scrapy gensipider -t xmlfeed autohome autohome.com.cn  
   PS:  
      查看所有命令：scrapy gensipider -l
      查看模板命令：scrapy gensipider -d 模板名称
- scrapy list  
   - 展示爬虫应用列表
- scrapy crawl 爬虫应用名称  
   - 运行单独爬虫应用
### 创建简单项目
   - 在终端下输入  
  `scrapy startproject myfrsit`   
![image text](https://github.com/gorgeousCa/Dayup/blob/master/Scrapy/%E6%A1%86%E6%9E%B6%E7%9A%84%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C/8.PNG)  
   - 我们使用Pycharm 打开刚刚创建的项目，可看到其文件结构，如下图所示：  
   ![image text](https://github.com/gorgeousCa/Dayup/blob/master/Scrapy/%E6%A1%86%E6%9E%B6%E7%9A%84%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C/9.PNG)
   - 我们在终端下使用 scrapy genspider jiansu(文件名）来在spiders下创建文件,使用pycharm打开，并输入以下代码：  
   
   ```import scrapy
    from jianshu.items import JianshuItem
    class JiansuSpider(scrapy.Spider):
    name = 'jiansu'
    allowed_domains = ['souke.xdf.cn/']
    start_urls = ['http://souke.xdf.cn/Teacher/0.html']
    def parse(self, response):
       with open("exmple.txt","w",encoding="utf-8") as file:
           file.write(response.text)
           ``` 
           
           
 - 在终端上使用 scrapy crawl jiansu 执行程序，如下图所示，即代表程序运行完毕：
 - 打卡pycharm，我们可以发现生成了exmple.txt，打开文件，我们可以看到网址http://souke.xdf.cn/Teacher/0.html的网页 “源码”  
 

   

   



