# Python Flask Web 框架

   Flask 是一个 web 框架。也就是说 Flask 为你提供工具，库和技术来允许你构建一个 web 应用程序。这个 web 应用程序可以是一些 web 页面、博客、wiki、基于 web 的日历应用或商业网站。

   Flask 属于微框架（micro-framework）这一类别，微架构通常是很小的不依赖于外部库的框架。这既有优点也有缺点，优点是框架很轻量，更新时依赖少，并且专注安全方面的 bug，缺点是，你不得不自己做更多的工作，或通过添加插件增加自己的依赖列表。Flask 的依赖如下：

    Werkzeug 一个 WSGI
    工具包
    jinja2 模板引擎  
 1.  使用 pip 安装 Python 包

   使用  pip install flask 安装 Flask  
所有的Flask应用程序都必须创建一个 应用程序实例 。使用web服务器网关接口协议将所有从客户端接收的请求传递给这个对象处理。这个应用程序实例就是Flask类的一个对象，通常使用下面的方式创建：  
	
    1.from flask import Flask  
    2.app = Flask(__name__)  
2.  路由和视图函数   

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
3. 服务启动
应用程序实例有一个run方法用于启动Flask集成的web服务：
	
	if __name__ == '__main__':
 	app.run(debug=True)

__name__ == '__main__'在此处使用是用于确保web服务已经启动当脚本被立即执行。当脚本被另一个脚本导入，它被看做父脚本将启动不同的服务，所以app.run()调用会被跳过。

一旦服务启动，它将进入循环等待请求并为之服务。这个循环持续到应用程序停止，例如通过按下Ctrl-C。

有几个选项参数可以给app.run()配置web服务的操作模式。在开发期间，可以很方便的开启debug模式，将激活 debugger 和 reloader 。这样做是通过传递debug为True来实现的。

注：Flask提供的web服务并不用于生产环境。你将在十七章学习生产环境的web服务。

4. 一个完整的应用程序
在上一节，你学习了Flask web应用程序的不同部分，现在是时候写一个了。整个 hello.py 应用程序脚本只不过将前面描述的三个部分结合在一个文件中。应用程序示例2-1所示。

示例 hello.py：一个完整的Flask应用程序
	
	from flask import Flask
	app = Flask(__name__)
 
	@app.route('/')
	def index():
 	return '
 
	<h1>Hello World!</h1>
 
	'
 
	if __name__ == '__main__':
 	app.run(debug=True)
运行如下图所示：
![Image text](https://github.com/gorgeousCa/Dayup/blob/master/Python%20Flask%20Web%E6%A1%86%E6%9E%B6/flaskr.png)
如果上面的例子继续写下去的时候，我们或许会在视图views中引入models文件以操作数据，在models文件中引入manage文件中的db以定义类和字段，

然后在manage文件中引入views文件以注册蓝图（register_blueprint），这样就出现了a引入b，b引入c，c引入a的问题，就会报错，

解决办法就是另外创建一个ext.py文件，专门用来创建db，代码如下：
1
2
3
	
from flask_sqlalchemy import SQLAlchemy
 
db = SQLAlchemy()

　　注意：此时先不讲app传入

然后在manage.py文件中，导入db，然后初始化，将app传进去：
1
	
db.init_app(app)

这样，在视图中需要用db的之后直接从ext导入，而不再从manage里导入
