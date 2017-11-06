# 本地项目如何上传到git

1.初始化仓库

`git init`

2.文件添加到git

`git add .`

3.文件提交到仓库

`git commit -m '说明...'`

4.关联到远程仓库

`git remote add origin 你的远程库地址`
>git remote add origin https://github.com/cade8800/ionic-demo.git

5.获取远程库与本地同步合并（如果远程库不为空必须做这一步，否则后面的提交会失败）
`git pull --rebase origin master` ``如果失败就去掉 --rebase 试试``

6.把本地库的内容推送到远程，使用 git push命令，实际上是把当前分支master推送到远程。执行此命令后会要求输入用户名、密码，验证通过后即开始上传。

7.状态查询
`git status`