#安装git
sudo apt-get install git
yum install git

#创建一个git用户，用来运行git服务
sudo adduser git

#创建证书使用公钥免密码登录(可选)
ssh-keygen -t rsa
vi ~/.ssh/authorized_keys

#初始化Git仓库
sudo git init --bare sample.git
sudo chown -R git:git sample.git

#禁用shell登录
vi /etc/passwd
git:x:1001:1001:,,,:/home/git:/usr/bin/git-shell

#在客户端上克隆远程仓库
git clone git@server:/srv/sample.git

#以最基本的Git命令行为例，先下载Git
https://git-scm.com/download/

#配置git提交用户名和邮箱，定义别名方便区分
git config --global user.name "你的姓名"
git config --global user.email "you@example.com"

#克隆仓库
git clone cap@172.28.70.243:/cap/cap.git

$ git clone cap@172.28.70.243:/cap/cap.git
Cloning into 'cap'...
warning: You appear to have cloned an empty repository.
Checking connectivity... done.

#测试推送
touch README
git add README
git commit -m "add readme"
git push origin master

Counting objects: 3, done.
Writing objects: 100% (3/3), 199 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To cap@172.28.70.243:/cap/cap.git
 * [new branch]      master -> master

#初始设置
git config --global user.name "<用户名>" #设置用户名
git config --global user.email "<电子邮件>" #设置电子邮件

#本地操作
git add [-i] #保存更新，-i为逐个确认。
git status #检查更新。
git commit [-a] -m "<更新说明>" #提交更新，-a为包含内容修改和增删，-m为说明信息，也可以使用 -am。

#远端操作
git clone <git地址> #克隆到本地。
git fetch #远端抓取。
git merge #与本地当前分支合并。
git pull [<远端别名>] [<远端branch>] #抓取并合并,相当于第2、3步
git push [-f] [<远端别名>] [<远端branch>] #推送到远端，-f为强制覆盖
git remote add <别名> <git地址> #设置远端别名
git remote [-v] #列出远端，-v为详细信息
git remote show <远端别名> #查看远端信息
git remote rename <远端别名> <新远端别名> #重命名远端
git remote rm <远端别名> #删除远端
git remote update [<远端别名>] #更新分支列表

#分支相关
git branch [-r] [-a] #列出分支，-r远端 ,-a全部
git branch <分支名> #新建分支
git branch -b <分支名> #新建并切换分支
git branch -d <分支名> #删除分支
git checkout <分支名> #切换到分支
git checkout -b <本地branch> [-t <远端别名>/<远端分支>] #-b新建本地分支并切换到分支, -t绑定远端分支
git merge <分支名> #合并某分支到当前分支

作者：王奥OX
链接：http://www.jianshu.com/p/e2da872ce206
來源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。