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

## 撤销修改方式 ##
    git check -- file



123