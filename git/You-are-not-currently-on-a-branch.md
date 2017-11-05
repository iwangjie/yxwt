# push的时候出现了You are not currently on a branch

解决方法：

首先执行：git reset --hard FETCH_HEAD

如果还是不行就：

首先`git checkout -b temp`

其次`git checkout master`

完美解决