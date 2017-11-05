1.Pull is not possible because you have unmerged files.

症状：pull的时候\
$ git pull

`Pull is not possible because you have unmerged files.
Please, fix them up in the work tree, and then use 'git add/rm <file>'
as appropriate to mark resolution, or use 'git commit -a'`\

应该是因为local文件冲突了
解决方法：
引用――
“
1.pull会使用git merge导致冲突，需要将冲突的文件resolve掉 git add -u, git commit之后才能成功pull.

2.如果想放弃本地的文件修改，可以使用git reset --hard FETCH_HEAD，FETCH_HEAD表示上一次成功git pull之后形成的commit点。然后git pull.
注意：

git merge会形成MERGE-HEAD(FETCH-HEAD) 。git push会形成HEAD这样的引用。HEAD代表本地最近成功push后形成的引用。

”
就我的经验，有时候会莫名其妙地出现这种状况，而且Untracked files 还特别多（实际上自己可能只改了一两个文件），所以只好先保存好自己确定做出的local的修改，然后用git reset --hard FETCH_HEAD回到上次成功pull之后的点，然后再pull就没有问题了

2.You are not currently on a branch.\
症状：有一次pull的时候又出现冲突，这回用“git reset --hard FETCH_HEAD”方法都不行了，出现：\
$ git pull
You are not currently on a branch, so I cannot use any
'branch.<branchname>.merge' in your configuration file.
Please specify which remote branch you want to use on the command\
line and try again (e.g. 'git pull <repository> <refspec>').\
See git-pull(1) for details.\
解决方法：
首先git checkout -b temp
其次git checkout master
即可恢复到master repository的状态，然后就可以pull了