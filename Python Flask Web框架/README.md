# Python Flask Web 框架

   Flask 是一个 web 框架。也就是说 Flask 为你提供工具，库和技术来允许你构建一个 web 应用程序。这个 web 应用程序可以是一些 web 页面、博客、wiki、基于 web 的日历应用或商业网站。
   Flask 属于微框架（micro-framework）这一类别，微架构通常是很小的不依赖于外部库的框架。这既有优点也有缺点，优点是框架很轻量，更新时依赖少，并且专注安全方面的 bug，缺点是，你不得不自己做更多的工作，或通过添加插件增加自己的依赖列表。Flask 的依赖如下：
   ```Werkzeug 一个 WSGI
   工具包
   jinja2 模板引擎 
   ```
 - 使用 pip 安装 Python 包
   使用  pip install flask 安装 Flask  
所有的Flask应用程序都必须创建一个 应用程序实例 。使用web服务器网关接口协议将所有从客户端接收的请求传递给这个对象处理。这个应用程序实例就是Flask类的一个对象，通常使用下面的方式创建：  
       1.from flask import Flask  
        2.app = Flask(__name__)  
    
- 路由和视图函数   
程序实例保存了一个 URL 到 Python 函数的映射关系，处理 URL 和函数之间关系的程序成为路由。  
Flask 中定义路由最简单的方式是使用程序提供的 app.route 修饰器，把修饰的函数注册为路由。  

	@app.route('/')  
	def index():  
        return '<h1>Hello World!</h1>'     
   修饰器是 Python 语言的标准特性，可以使用不同的方式修改函数的行为  
把 index 函数注册为程序跟地址的处理程序，不过在 Pthon 代码中嵌入响应字符串会导致代码难以维护，以后将会介绍生成响应的正确方法。像 index 这样的函数称为视图函数。  
地址中也可以包含可变部分，可以在路由中定义可变的这部分  
	``` @app.route('/user/<name>')
	def user(name):
	return '<h1>Hello,%s!</h1>' % name   ```
尖括号中的内容是动态部分，任何能匹配静态部分的 URL 都会映射到这个路由上。  
- 服务启动
应用程序实例有一个run方法用于启动Flask集成的web服务：

	if __name__ == '__main__':
 	app.run(debug=True)
__name__ == '__main__'在此处使用是用于确保web服务已经启动当脚本被立即执行。当脚本被另一个脚本导入，它被看做父脚本将启动不同的服务，所以app.run()调用会被跳过。
一旦服务启动，它将进入循环等待请求并为之服务。这个循环持续到应用程序停止，例如通过按下Ctrl-C。
有几个选项参数可以给app.run()配置web服务的操作模式。在开发期间，可以很方便的开启debug模式，将激活 debugger 和 reloader 。这样做是通过传递debug为True来实现的。
注：Flask提供的web服务并不用于生产环境
- 一个完整的应用程序
在上一节，你学习了Flask web应用程序的不同部分，现在是时候写一个了。整个 hello.py 应用程序脚本只不过将前面描述的三个部分结合在一个文件中。应用程序示例2-1所示。
示例 hello.py：一个完整的Flask应用程序
	
	from flask import Flask
	app = Flask(__name__)
 
	@app.route('/')
	def index():
 	return '
 
	<h1>我爱你</h1>
 
	'
 
	if __name__ == '__main__':
 	app.run(debug=True)
运行如下图所示：
![Image text](https://github.com/gorgeousCa/Dayup/blob/master/Python%20Flask%20Web%E6%A1%86%E6%9E%B6/flaskr.png)  
如果上面的例子继续写下去的时候，我们或许会在视图views中引入models文件以操作数据，在models文件中引入manage文件中的db以定义类和字段，然后在manage文件中引入views文件以注册蓝图（register_blueprint），这样就出现了a引入b，b引入c，c引入a的问题，就会报错，
解决办法就是另外创建一个ext.py文件，专门用来创建db，代码如下：
	
     from flask_sqlalchemy import SQLAlchemy
 
     db = SQLAlchemy()
注意：此时先不讲app传入
然后在manage.py文件中，导入db，然后初始化，将app传进去：
     db.init_app(app)
这样，在视图中需要用db的之后直接从ext导入，而不再从manage里导入
# Web表单
Web 表单是 Web 应用程序的基本功能。
它是HTML页面中负责数据采集的部件。表单有三个部分组成：表单标签、表单域、表单按钮。表单允许用户输入数据，负责HTML页面数据采集，通过表单将用户输入的数据提交给服务器。
在Flask中，为了处理web表单，我们可以使用 Flask-WTF 扩展，它封装了 WTForms，并且它有验证表单数据的功能
## WTForms支持的HTML标准字段

| 字段对象 | 说明 |
| :--- | :--- |
| StringField | 文本字段 |
| TextAreaField | 多行文本字段 |
| PasswordField | 密码文本字段 |
| HiddenField | 隐藏文件字段 |
| DateField | 文本字段，值为 datetime.date 文本格式 |
| DateTimeField | 文本字段，值为 datetime.datetime 文本格式 |
| IntegerField | 文本字段，值为整数 |
| DecimalField | 文本字段，值为decimal.Decimal |
| FloatField | 文本字段，值为浮点数 |
| BooleanField | 复选框，值为True 和 False |
| RadioField | 一组单选框 |
| SelectField | 下拉列表 |
| SelectMutipleField | 下拉列表，可选择多个值 |
| FileField | 文件上传字段 |
| SubmitField | 表单提交按钮 |
| FormField | 把表单作为字段嵌入另一个表单 |
| FieldList | 一组指定类型的字段 |

## WTForms常用验证函数

| 验证函数 | 说明 |
| :--- | :--- |
| DataRequired | 确保字段中有数据 |
| EqualTo | 比较两个字段的值，常用于比较两次密码输入 |
| Length | 验证输入的字符串长度 |
| NumberRange | 验证输入的值在数字范围内 |
| URL | 验证URL |
| AnyOf | 验证输入值在可选列表中 |
| NoneOf | 验证输入值不在可选列表中 |


使用 Flask-WTF 需要配置参数 SECRET\_KEY。
CSRF\_ENABLED是为了CSRF（跨站请求伪造）保护。 SECRET\_KEY用来生成加密令牌，当CSRF激活的时候，该设置会根据设置的密匙生成加密令牌。
## 代码验证

### 使用 html 自带的表单

- 创建模板文件 `login.html`，在其中直接写form表单：

```html
<form method="post">
    <label>用户名：</label><input type="text" name="username" placeholder="请输入用户名"><br/>
    <label>密码：</label><input type="password" name="password" placeholder="请输入密码"><br/>
    <label>确认密码：</label><input type="password" name="password2" placeholder="请输入确认密码"><br/>
    <input type="submit" value="注册">
</form>

{% for message in get_flashed_messages() %}
    {{ message }}
{% endfor %}

```

- 视图函数中获取表单数据验证登录逻辑：

```python
@app.route('/demo1', methods=["get", "post"])
def demo1():
    if request.method == "POST":
        # 取到表单中提交上来的三个参数
        username = request.form.get("username")
        password = request.form.get("password")
        password2 = request.form.get("password2")

        if not all([username, password, password2]):
            # 向前端界面弹出一条提示(闪现消息)
            flash("参数不足")
        elif password != password2:
            flash("两次密码不一致")
        else:
            # 假装做注册操作
            print(username, password, password2)
            return "success"

    return render_template('temp_register.html')	
```

### 使用 Flask-WTF 实现表单

- 配置参数，关闭 CSRF 校验

```python
 app.config['WTF_CSRF_ENABLED'] = False
```

> CSRF:跨站请求伪造，后续会讲到
#### 模板页面：

```html
<form method="post">
    {{ form.username.label }} {{ form.username }}<br/>
    {{ form.password.label }} {{ form.password }}<br/>
    {{ form.password2.label }} {{ form.password2 }}<br/>
    {{ form.submit }}
</form>
```

#### 视图函数： {#视图函数：}

```python

from flask import Flask,render_template, flash
#导入wtf扩展的表单类
from flask_wtf import FlaskForm
#导入自定义表单需要的字段
from wtforms import SubmitField,StringField,PasswordField
#导入wtf扩展提供的表单验证器
from wtforms.validators import DataRequired,EqualTo


app = Flask(__name__)
app.config['SECRET_KEY']='SECRET_KEY'

#自定义表单类，文本字段、密码字段、提交按钮
class RegisterForm(FlaskForm):
    username = StringField("用户名：", validators=[DataRequired("请输入用户名")], render_kw={"placeholder": "请输入用户名"})
    password = PasswordField("密码：", validators=[DataRequired("请输入密码")])
    password2 = PasswordField("确认密码：", validators=[DataRequired("请输入确认密码"), EqualTo("password", "两次密码不一致")])
    submit = SubmitField("注册")

#定义根路由视图函数，生成表单对象，获取表单数据，进行表单数据验证
@app.route('/demo2', methods=["get", "post"])
def demo2():
    register_form = RegisterForm()
    # 验证表单
    if register_form.validate_on_submit():
        # 如果代码能走到这个地方，那么就代码表单中所有的数据都能验证成功
        username = request.form.get("username")
        password = request.form.get("password")
        password2 = request.form.get("password2")
        # 假装做注册操作
        print(username, password, password2)
        return "success"
    else:
        if request.method == "POST":
            flash("参数有误或者不完整")

    return render_template('temp_register.html', form=register_form)

if __name__ == '__main__':
    app.run(debug=True)
```

> 运行测试
