## 什么是Git？
Git是目前世界上最先进的分布式版本控制系统（没有之一）。


你得先有一个Git仓库，才能进行操作。创库就是Git存放你要保存的快照的数据的地方。   

拥有一个Git仓库，有**两种**方法。
>1. 创建一个目录并初始化。    
**$ git init**
>2. 克隆一个公开的Git仓库    
 **$ git clone git://github.com/schacon/simplegit.git**


**以下实现在本地创建一个仓库并同步远程Github上**

**第一步：**新建本地仓库，例如新建仓库名为work(和你的github里的仓库名称一致)，初始化一个Git仓库，使用git init命令。


	$ mkdir work
	$ cd work
	$ git init    
	// 在work下出现.git该文件，说明初始化Git仓库完毕

  
**第二步：**添加文件到Git仓库，使用命令git add <file>，注意，可反复多次使用，添加多个文件；也可以使用git add . 将添加所在根目录下所有文件

	$ git add .

**第三步：**使用命令git commit -m "本次提交说明，可以输入任意内容"，完成。

	$ git commit -m "不能为空"


**第四步：**同步远程仓库：
要关联一个远程库，**要确保github上新建仓库名与本地仓库名一致**。
使用命令git remote add origin git@github.com:path/repo-name.git
path为同步账号名，repo-name为要同步的仓库名 
例如我的github用户名为whybingo3

	$ git remote add origin git@github.com:whybingo3/work.git


关联后，使用命令git push -u origin master（第一次可能需要输入用户名密码之类哦）第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；
	
	$ git push -u origin master
	

**tips:**
origin可以是任意名字哦，是你远程仓库名，当然你可以添加多个哦，push的时候指定一个就可以。加完之后进入.git文件夹，打开config文件，这里会多出一个remote “origin”内容，这就是刚才添加的远程地址，也可以直接修改config来配置远程地址。

当然后面的地址是ssh形式，前面没有部署密钥的话是出错的哦，你也可以用https形式来上传：

	$ git remote add origin https://github.com/whybingo3/work.git
	
这样你就会在你的github对应的仓库下看到对应的文件了哦。

git push命令会将本地仓库推送到远程服务器。git pull命令则相反。
$ git pull -u origin master //从远程服务器更新到本地仓库，相当于git fetch + git merge

修改完代码后，使用git status可以查看文件的差别，使用git add 添加要commit的文件，也可以用git add -i来智能添加文件。之后git commit提交本次修改，git push上传到github。

详细的Git技术可以参考以下链接：

1. [图文并茂git-建明指南]( http://rogerdudler.github.io/git-guide/index.zh.html)
2. [Git参考手册](http://gitref.org/zh/creating/)
3. [廖雪峰Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
4. [常用 Git 命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
5. [Git常用命令速查表](http://i1.piimg.com/567571/cef2ffbf10018944.png)
