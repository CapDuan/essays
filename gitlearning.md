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

## 工作时 ##

    git status
查看git工作区的状态，那些文件没有被add,哪些文件有修改

    git diff 
查看git缓存区中修改内容

