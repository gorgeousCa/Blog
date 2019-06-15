# scrapy终端与核心组件
### scrapy shell---测试xpath表达式
*Scrapy终端是一个交互终端，供您在未启动spider的情况下尝试及调试您的爬取代码。 其本意是用来测试提取数据的代码，不过您可以将其作为正常的Python终端，在上面测试任何的Python代码。
该终端是用来测试XPath或CSS表达式，查看他们的工作方式及从爬取的网页中提取的数据。 在编写您的spider时，该终端提供了交互性测试您的表达式代码的功能，免去了每次修改后运行spider的麻烦。
一旦熟悉了Scrapy终端后，能其在开发和调试spider时发挥的巨大作用。*
#### 启用scrapy shell <url>
  - 例如在Windows命令终端下，输入scrapy shell www.jianshu.com 命令即可启用Scrapy shell 访问简书主页，并在终端下会输入如下大量信息。  
  ![image text](https://github.com/gorgeousCa/Dayup/blob/master/Scrapy/%E7%BB%88%E7%AB%AF%E4%B8%8E%E6%A0%B8%E5%BF%83%E7%BB%84%E4%BB%B6/14.PNG)  
如上图所示，表示成功访问网页。
#### 使用scrapy shell
  - Scrapy shell 可以看成是在一个Python终端基础上添加了扩充功能的Pythonk控制台程序，这些扩充包括若干函数和内置对象。
  
  
 
  



