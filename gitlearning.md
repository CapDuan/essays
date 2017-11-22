# git随手 #

----------

## 创建版本库 ##
    git init
创建一个empty Git repository.
  
    git init <repository name>
创建一个 名叫（文件名为 repository name）的Git repository

    git add xxx.xxx
将xxx.xxx文件添加到缓存区

    git commit -m "wrote a readme file"
提交这个文件，并添加描述信息 "wrote a readme file"

	初始化一个Git仓库，使用git init命令。
	添加文件到Git仓库，分两步：
    第一步，使用命令git add <file>，注意，可反复多次使用，添加多个文件；
    第二步，使用命令git commit，完成。

----------

## 预提交 ##

    git status
查看git工作区的状态，那些文件没有被add,哪些文件有修改

    git diff 
查看git缓存区中修改的具体内容

## 回退以及恢复 ##

    git log 
查看版本log（只显示当前版本之前的log）
> 
> 注意：假如现有ABCD四个版本，你从D版本回退git reset到C 版本，现在只显示ABC，而D版本会不显示


    git reset --hard commit_id
    git reset --hard HEAD~
恢复到 commitId 对应的版本 或上一个版本 HEAD只当前版本，HEAD~上版本 HEAD~200 上200版本

    git reflog
查看操作log（可以查询所有版本ID，可以根据ID恢复到上述的D版本)

----------

## 理解工作区 暂存区 版本库 ##
工作区修改 -> add -> 暂存区 -> commit -> 版本库

----------
## 删除文件 ##

误删

    git checkout -- filename
可以回复最新版本库中代码

真实删除

    git rm filename
	git commit -m

版本库中删除文件

----------


## 关联远程库 ##

    git remote add origin git@server-name:path/repo-name.git
关联远程库,比如github,或自己搭建的服务器

    git push -u origin master
第一次推送，将master和远程库的master关联

    git push origin master
之后的每次推送

## 分支 ##

git 分支原理：指针变化

O - O - O （<-master<-HEAD）

添加分支，添加dev指针，HEAD指针指向dev

O - O - O（<-master） - O (dev<-HEAD)

合并后,HEAD指向->dev和master

O - O - O - O (dev/master<-HEAD)

    git branch 
查看分支

    git branch xxx
添加xxx分支

    git checkout xxx
切换到xxx分支

    git checkout -b xxx
创建并切换到xxx分支

    git merge xxx
将目标分支合并到当前分支

    git barnch -d xxx
删除某分支


----------

## git 解决冲突 ##
当两条分支都有各自的提交后，使用快速merge，很可能造成conflict。

O - O （master commit something） - O(dev1 commit something)

merge cause conflict, fix the conflict in the file.
add and commit.

    git log --graph --pretty=oneline --abbrev-commit
可以查看分支合并图

**可以删除dev1分支*

----------

## git 分支管理策略 ##
git 使用Fast forward 模式时，删除分支后，会丢失分支信息
Fast forward 模式简写ff,git 支持 --no--ff 方式做git merge操作

github TEST 
with ff