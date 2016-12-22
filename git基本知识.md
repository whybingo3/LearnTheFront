<font face="微软雅黑" size=4>

GIT

初始化一个Git仓库，使用git init命令。

添加文件到Git仓库，分两步：

第一步，使用命令git add <file>，注意，可反复多次使用，添加多个文件；

第二步，使用命令git commit -m "本次提交说明，可以输入任意内容"，完成。

要随时掌握工作区的状态，使用git status命令。
如果git status告诉你有文件被修改过，用git diff可以查看修改内容。


同步远程仓库：
要关联一个远程库，使用命令git remote add origin git@github.com:path/repo-name.git；
#path为同步账号名，repo-name为要同步的仓库名

git remote add origin git@github.com:whybingo3/yao.git


关联后，使用命令git push -u origin master第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；





提交、上传

1 .创建仓库

到你的github页面，创建一个仓库，比如HelloWorld



2 .提交

本地新建一个文件夹HelloWorld(和你的github里的仓库名称一致)，进入该文件夹，右键git bash，初始化git，添加文件并提交commit


$ git init //初始化git，创建.git文件夹

$ git add README.md //建立一个待提交的文件README.md

$ echo "hello world!" >> README.md  //文件里写点东西，问候下美好的世界

$ git commit . -m "first commit" //提交文件，.是当前目录，就是提交所有文件


3 上传


$ git remote add origin git@github.com:yourName/yourRepo.git

$ git push -u origin master //可能需要输入用户名密码之类哦


origin可以是任意名字哦，是你远程仓库名，当然你可以添加多个哦，push的时候指定一个就可以。后面的yourName和yourRepo表示你再github的用户名和刚才新建的仓库，加完之后进入.git文件夹，打开config文件，这里会多出一个remote “origin”内容，这就是刚才添加的远程地址，也可以直接修改config来配置远程地址。



当然后面的地址是ssh形式，前面没有部署密钥的话是出错的哦，你也可以用https形式来上传：


$ git remote add origin https://github.com/yourName/yourRepo.git


这样你就会在你的github对应的仓库下看到对应的文件了哦。
git push命令会将本地仓库推送到远程服务器。git pull命令则相反。


$ git pull -u origin master //从远程服务器更新到本地仓库，相当于git fetch + git merge

修改完代码后，使用git status可以查看文件的差别，使用git add 添加要commit的文件，也可以用git add -i来智能添加文件。之后git commit提交本次修改，git push上传到github。


</font>

