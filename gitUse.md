1.从github上clone一个分支下来：git clone git@github.com:Abyetc/helloWorld2
  也可以直接git clone http://... 这样的话只有读的权限。

2.$ git branch -a
* master
  origin/HEAD
  origin/master
  origin/v1.0-stable
  origin/experimental

如果你现快速的代上面的分支，你可以直接切换到那个分支：

$ git checkout origin/experimental

但是，如果你想在那个分支工作的话，你就需要创建一个本地分支：

$ git checkout -b experimental origin/experimental

现在，如果你看看你的本地分支，你会看到：

$ git branch
  master
* experimental

你还可以用git remote命令跟踪多个远程分支

$ git remote add win32 git://gutup.com/users/joe/myproject-linux-port
$ git branch -a
* master
  origin/HEAD
  origin/master
  origin/v1.0-stable
  origin/experimental
  linux/master
  linux/new-widgets


3.查看git的配置信息：git config --list
4.增加一个文件，要git去track它的话，就要：git add newFileName
5.修改一个文件之后，也要：git add ..
6.git commit是将本地修改过的文件提交到本地库中。
  git push是将本地库中的最新信息发送给远程库。

7.git fetch origin master		# 从远程的origin的master主分支下载最新的版本到origin/master分支上
  git log -p master origin/master	# 比较本地的master分支和origin/master分支的差别
  git merge origin/master		# 最后进行合并

8.上面相当于：git pull origin master	# 从远程获取最新版本并merge到本地git fetch更安全一些，因为在merge前，我们可以查看更新情况，然后再决定是否合并
