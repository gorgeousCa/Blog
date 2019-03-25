# 搭建个人博客网站
###### hexo + github pages + mac
### 一、准备工作：
1.安装Node.js和Git
Mac上安装可以选择图形化方式和终端安装，此处直接使用客户端方式安装。Node.js官网下载文件，根据提示安装即可，安装成功后在目录/usr/local/bin目录下。测试Node.js和npm，出现下述信息则安装成功。
![image](https://github.com/gorgeousCa/Dayup/blob/master/搭建个人博客网站/1.png)

  
### 二、搭建github博客
1.创建仓库  
新建一个名为你的用户名.github.io的仓库，比如说，如果你的github用户名是test，那么你就新建test.github.io的仓库（必须是你的用户名，其它名称无效），将来你的网站访问地址就是 http://test.github.io 了，是不是很方便？  

由此可见，每一个github账户最多只能创建一个这样可以直接使用域名访问的仓库。  

几个注意的地方：  
注册的邮箱一定要验证，否则不会成功；    
仓库名字必须是：username.github.io，其中username是你的用户名；   
创建成功后，默认会在你这个仓库里生成一些示例页面，以后你的网站所有代码都是放在这个仓库里啦。

2.配置SSH key  
### 三、使用hexo写博客  
 3.1、安装Hexo  
 
`sudo npm install -g hexo`  
3.2、博客初始化
创建存储博客的文件，如blog  
 `mkdir blog`
 进入blog中
 `cd blog`
 执行下述命令初始化本地博客，下载一系列文件。  

`hexo init`

执行下述命令安装npm。

`sudo npm install`  

执行下述命令生成本地网页文件并开启服务器，然后通过http://localhost:4000 查看本地博客。

`hexo g`
`hexo s`
如下图所示：
![image](https://github.com/gorgeousCa/Dayup/blob/master/搭建个人博客网站/2.png)

3.3、本地博客关联GitHub
注册并登陆GitHub账号后，新建仓库，名称必须为user.github.io，如gorgeousCa.github.io。  
终端cd到myblog文件夹下，打开_config.yml文件。或者用其他文本编辑器打开可以，推荐sublime。  
`vim _config.yml` 
打开后到文档最后部分，将deploy配置如下。  
          `deploy:   `     
           `type: git  `    
        `repository: https://github.com/gorgeousCa/gorgeousCa.github.io.git   `   
 ` branch: master  `     
  
其中将repository中gorgeousCa改为自己的用户名，注意type、repository、branch后均有空格。通过如下命令在myblog下生成静态文件并上传到服务器。  
`hexo g `       
`hexo d`        

若执行hexo g出错则执行npm install hexo --save，若执行hexo d出错则执行npm install hexo-deployer-git --save。错误修正后再次执行hexo g和hexo d上传到服务器。     
若未关联GitHub，执行hexo d时会提示输入GitHub账号用户名和密码，即:  
`username for 'https://github.com':    
password for 'https://github.com':`    
hexo d执行成功后便可通过https://gorgeousCa.github.io 访问博客，看到的内容和 http://localhost:4000 相同。    
3.4、添加ssh keys到GitHub  
添加ssh key后不需要每次更新博客再输入用户名和密码。首先检查本地是否包含ssh keys。如果存在则直接将ssh key添加到GitHub之中，否则新生成ssh key。
执行下述命令生成新的ssh key，将your_email@example.com改成自己注册的GitHub邮箱地址。默认会在~/.ssh/id_rsa.pub中生成id_rsa和id_rsa.pub文件。
ssh-keygen -t rsa -C "your_email@exampl"        

Mac下利用open ~/.ssh打开文件夹，打开id_rsa.pub文件，里面的信息即为ssh key，将此信息复制到GitHub的Add ssh key路径GitHub->Setting->SSH keys->add SSH key中即可。Title里填写任意标题，将复制的内容粘贴到key中，点击Add key完成添加。  
此时本地博客内容便已关联到GitHub之中，本地博客改变之后，通过hexo g和hexo d便可更新到GitHub之中，通过https://gorgeousCa.github.io 访问便可看到更新内容。
5.更换Hexo主题
可以选择Hexo主题官网页面搜索喜欢的theme，这里我选择hexo-theme-next当作自己主题，hex-theme-next主题是GitHub中hexo主题star最高的项目，非常推荐使用。
终端cd到myblog目录下执行如下所示命令。
git clone https://github.com/iissnan/hexo-theme-next themes/next

将blog目录下_config.yml里的theme的名称landscape更改为next。
执行如下命令（每次部署文章的步骤）
hexo g  //生成缓存和静态文件
hexo d  //重新部署到服务器

当本地博客部署到服务器后，网页端无变化时可以采用下述命令。
hexo clean  //清楚缓存文件(db.json)和已生成的静态文件(public)

6.配置Hexo-theme-next主题
Hexo-theme-next主题为精于心、简于形，简洁的界面中能够呈现丰富的内容，访问next官网查看配置内容。配置文件主要修改主题next文件夹中_config.yml文件，next有三种主题选择，分别为Muse、Mist、Pisces三种，个人选择的是Pisces主题。主题增加标签、分类、归档、喜欢（书籍和电影信息流）、文章阅读统计、访问人数统计、评论等功能，博客界面如下所示。





 



    

