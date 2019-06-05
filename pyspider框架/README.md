# pyspider 框架
## 简介
- 通过python脚本进行结构化信息的提取，follow链接调度抓取控制，实现最大的灵活性
- 通过web化的脚本编写、调试环境。web展现调度状态
- 抓取环模型成熟稳定，模块间相互独立，通过消息队列连接，从单进程到多机分布式灵活拓展
## pyspider安装及启动
`pip install pyspider`
由于目前很多网站都是动态js生成页面，需要安装PhantomJS来获得js执行后的页面，而不是原本静态的html页面，我们再来装一下
`pip install  phantomjs`

