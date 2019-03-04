# Python 操作 MySQL 数据库  
##### 使用环境：Windows+python3.4+MySQL5.5+Navicat  
### 一、创建连接
#### 1. 准备工作，想要使用Python操作MySQL，首先需要安装MySQL-Python的包，在Python 3.x下，该包已经改名为MySQLClient。可以使用pip方式安装:  
    pip install MySQLClient  
* 如下图所示：*
![Image text](https://github.com/gorgeousCa/Dayup/blob/master/MySQL/20190303204126.png)
#### 2.Python中使用MySQL导入方法：import MySQLdb
#### 3.创建Connection
#### Connection：创建了Python客户端与数据库之间的网络通路
#### 4.获取Cursor
#### Cursor:游标对象，用于执行查询和获取结果
* 例如:*
 `import MySQLdb`    
 `conn=MySQLdb.connect(host='localhost',port=3306,user='root',passwd='mysql',db='lms',charset='utf8')` 
 `cursor=conn.cursor()`  
    `print(conn)`  
    `print(cursor) ` 
 `cursor.close()`  
 `conn.close()`
* 运行结果如下:* 
 ![Iamge text](https://github.com/gorgeousCa/Dayup/blob/master/MySQL/20190303211447.png)



