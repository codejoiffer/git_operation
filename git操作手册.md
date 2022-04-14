### GIT 的教程

****

#### 初始化一个git仓库

git init

#### 添加文件到仓库

* git add <file>
* git commit -m <message>

#### 时刻掌握仓库当前的状态

git status

#### 对比查看修改

git diff <filename>

#### 版本转换

git reset --hard <版本号>(HEAD^  HEAD^^   HEAD~100)

HEAD是一颗指针 指向当前的版本文件

#### 版本转换（未来）

git reflog 记录每次的命令

#### 查看工作区和版本库里面最新版本的区别

git diff HEAD -- <filename>

#### 丢弃工作区的修改

git checkout -- file

#### 丢弃暂存区的修改

git reset HEAD <file>

第二步继续丢弃工作区

#### 丢弃仓库的修改

版本回退

#### 删除文件

* 若确实要删除工作区的文件：git rm <file>   git commit -m “”
* 若想回退： git checkout -- <file>

#### 删除远程库

* 查看远程库信息：git remote -v
* 删除远程库：git remote rm <name>

#### 分支创建

git branch name

#### 分支转换

git switch name || git checkout name

创建并切换：git checkout -b name || git switch -c name

#### 查看当前分支

git branch

#### 合并分支

git merge name(合并此分支到当前分支)

#### 删除分支

git branch -d name

#### 查看分支合并

git log --graph --pretty=oneline --abbrev-commit

#### 禁用fastforward模式

git merge --no-ff -m "merge with no-ff" dev

#### 分支管理策略

在实际开发中，我们应该按照几个基本原则进行分支管理：

首先，`master`分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；

那在哪干活呢？干活都在`dev`分支上，也就是说，`dev`分支是不稳定的，到某个时候，比如1.0版本发布时，再把`dev`分支合并到`master`上，在`master`分支发布1.0版本；

你和你的小伙伴们每个人都在`dev`分支上干活，每个人都有自己的分支，时不时地往`dev`分支上合并就可以了。

所以，团队合作的分支看起来就像这样：

![git-br-policy](https://www.liaoxuefeng.com/files/attachments/919023260793600/0)

#### Bug分支

##### 储存当前工作现场

git stash

##### 恢复工作现场

git stash pop

#### 创建本地分支并于远程关联

git checkout -b dev origin/dev

git switch -c dev origin/dev

