# Windows 下创建Python虚拟环境

- 为什么要使用 Virtualenv 呢？举个例子，假设你已经在系统中安装了 Python，并且在阅读此教程前你已经进行过一些 Django 的学习，但那时候安装的 Django 还是 1.8 版本。
我们教程使用的是最新版的 Django 1.10.6 版本，你可能不愿意删除掉旧版的 Django 1.8，因为那可能导致你以前的项目无法运行。既想让原本项目在 Django 1.8 环境下运行，又想再安装 Django 1.10.6 来开启本教程的项目，怎么办呢？使用 Virtualenv 就能够完美解决这个问题。

Virtualenv 帮我们从系统的 Python 环境中克隆一个全新的 Python 环境出来，这个环境独立于原来的 Python 环境。我们可以在这个新克隆的环境下安装 Django 1.10.6，并且在这个新环境下运行我们的新项目。

Virtualenv 的使用非常简单，首先安装 Virtualenv，打开命令行工具，输入 pip install virtualenv 命令即可安装 Virtualenv。

`pip install virtualenv`

   

- 安装成功后就可以开始创建虚拟环境，指定一个你喜欢的目录，Virtualenv 会把这个新的虚拟环境装到你指定目录下。例如我把它装到 D:\PyCharm_WorkSpace目录下，并将虚拟环境命名为 blogproject_env（也可以取任何你喜欢的名字）。在命令栏运行如下命令：

virtualenv  D:\PyCharm_WorkSpace\blogproject_env

 

虚拟环境已经创建好了，我们需要激活这个环境，运行 blogproject_env\Scripts\ 目录下的 activate 程序激活它：

`D:\PyCharm_WorkSpace\blogproject_env\Scripts\activate`
