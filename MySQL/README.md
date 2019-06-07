# Python 操作 MySQL 数据库  
#### 使用环境：Windows+python3.x+MySQL5.5+Navicat  
### 创建连接
- 准备工作，想要使用Python操作MySQL，首先需要安装MySQL-Python的包，在Python 3.x下，该包已经改名为MySQLClient。可以使用pip方式安装:  
    pip install MySQLClient  
* 如下图所示:  
![Image text](https://github.com/gorgeousCa/Dayup/blob/master/MySQL/20190303204126.png)
- Python中使用MySQL导入方法：import MySQLdb
- 创建Connection
Connection：创建了Python客户端与数据库之间的网络通路
- 获取Cursor
Cursor:游标对象，用于执行查询和获取结果
 例如:  
 ```import MySQLdb
 conn=MySQLdb.connect(host='localhost',port=3306,user='root',passwd='mysql',db='lms',charset='utf8')
 cursor=conn.cursor()  
 print(conn)    
 print(cursor)    
 cursor.close()   
 conn.close()
 ```    
 - 运行结果如下:  
 ![Iamge text](https://github.com/gorgeousCa/Dayup/blob/master/MySQL/20190303211447.png)   
 从结果中我们可以看见成功创建了一个Connection和Cursor对象
 ### 建立数据库，进行一些简单操作
 - 简单的创建一个student表，并且插入一些数据。student表中只有两个字段：stuid和stuname。代码如下：  
  ```import  
  conn=MySQLdb.connect(host='localhost',port=3306,user='root',passwd='mysql',db='lms',charset='utf8')`  
  cur=conn.cursor()  
  cur.execute(""" 
  create table if not EXISTS student1  
  (  
  stuid int(11) PRIMARY KEY ,  
  stuname VARCHAR(20)  
   ) 
  """)   
  for i in range(1,10): 
   cur.execute("insert into student1(stuid,stuname ) values('%d','%s')" %(int(i),'name'+str(i)))
  conn.commit()
  cur.close() 
  conn.close()
  ``` 
   - 我们用Navicat打开数据库，查看一下结果:  
![Iamge text](https://github.com/gorgeousCa/Dayup/blob/master/MySQL/1.png)



 
 



