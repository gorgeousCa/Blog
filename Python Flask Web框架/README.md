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
2.2 路由和视图函数

程序实例保存了一个 URL 到 Python 函数的映射关系，处理 URL 和函数之间关系的程序成为路由。
Flask 中定义路由最简单的方式是使用程序提供的 app.route 修饰器，把修饰的函数注册为路由。

@app.route('/')
def index():
    return '<h1>Hello World!</h1>'  
    
   修饰器是 Python 语言的标准特性，可以使用不同的方式修改函数的行为

把 index 函数注册为程序跟地址的处理程序，不过在 Pthon 代码中嵌入响应字符串会导致代码难以维护，以后将会介绍生成响应的正确方法。像 index 这样的函数称为视图函数。
地址中也可以包含可变部分，可以在路由中定义可变的这部分

@app.route('/user/<name>')
def user(name):
    return '<h1>Hello, %s!</h1>' % name

尖括号中的内容是动态部分，任何能匹配静态部分的 URL 都会映射到这个路由上。

