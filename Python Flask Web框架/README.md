# Python Flask Web 框架

Flask 是一个 web 框架。也就是说 Flask 为你提供工具，库和技术来允许你构建一个 web 应用程序。这个 web 应用程序可以是一些 web 页面、博客、wiki、基于 web 的日历应用或商业网站。

Flask 属于微框架（micro-framework）这一类别，微架构通常是很小的不依赖于外部库的框架。这既有优点也有缺点，优点是框架很轻量，更新时依赖少，并且专注安全方面的 bug，缺点是，你不得不自己做更多的工作，或通过添加插件增加自己的依赖列表。Flask 的依赖如下：

    Werkzeug 一个 WSGI
    工具包
    jinja2 模板引擎  
    1.2 使用 pip 安装 Python 包

使用  pip install flask 安装 Flask
所有的Flask应用程序都必须创建一个 应用程序实例 。使用web服务器网关接口协议将所有从客户端接收的请求传递给这个对象处理。这个应用程序实例就是Flask类的一个对象，通常使用下面的方式创建：
	
    1.from flask import Flask
    2.app = Flask(__name__)
