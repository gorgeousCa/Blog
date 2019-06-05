# pyspider 框架
## 简介
- 通过python脚本进行结构化信息的提取，follow链接调度抓取控制，实现最大的灵活性
- 通过web化的脚本编写、调试环境。web展现调度状态
- 抓取环模型成熟稳定，模块间相互独立，通过消息队列连接，从单进程到多机分布式灵活拓展
## pyspider安装及启动  
- `pip install pyspider`  
由于目前很多网站都是动态js生成页面，需要安装PhantomJS来获得js执行后的页面，而不是原本静态的html页面，我们再来装一下  
- `pip install  phantomjs`  
待安装完成后，我们先看一下pyspider对应的可执行命令  
Usage: pyspider [OPTIONS] COMMAND [ARGS]...
  A powerful spider system in python.
Options:
  -c, --config FILENAME    a json file with default values for subcommands.
                           {“webui”: {“port”:5001}}
  --logging-config TEXT    logging config file for built-in python logging
                           module  [default: pyspider/pyspider/logging.conf]
  --debug                  debug mode
  --queue-maxsize INTEGER  maxsize of queue
  --taskdb TEXT            database url for taskdb, default: sqlite
  --projectdb TEXT         database url for projectdb, default: sqlite
  --resultdb TEXT          database url for resultdb, default: sqlite
  --message-queue TEXT     connection url to message queue, default: builtin
                           multiprocessing.Queue
  --amqp-url TEXT          [deprecated] amqp url for rabbitmq. please use
                           --message-queue instead.
  --beanstalk TEXT         [deprecated] beanstalk config for beanstalk queue.
                           please use --message-queue instead.
  --phantomjs-proxy TEXT   phantomjs proxy ip:port
  --data-path TEXT         data dir path
  --version                Show the version and exit.
  --help                   Show this message and exit.

