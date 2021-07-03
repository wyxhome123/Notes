# Git学习笔记

## 本地操作

- git init
- git add
- git commit -m "..."  
- git status
- git restore  
- git branch -c branch_name
- git switch

git相关操作图形展示:
![git_area](/images/git_area.jfif)
图片来自[这里](https://www.liaoxuefeng.com/wiki/896043488029600/897271968352576)
git init: 把当前文件夹作初始化为Git仓库  
git add file_name: 把对应文件添加到暂存区  
git commit -m "message": 把暂存区的改动提交到本地版本库中
git status:显示当前git信息，比如所处分支,与哪个远程仓库建立了连接,工作区中修改了的文件,暂存区中需要提交的文件

一例:
>On branch main //处于main分支
>Your branch is up to date with 'origin/main'. //与origin下的main建立了连接
>
>Untracked files:
>>(use "git add <file>..." to include in what will be committed)  //一下文件已经在工作区修改了,但还没有添加到暂存区
>>>        GItLearn.md
>>>       images/git_area.jfif
>
>nothing added to commit but untracked files present (use "git add" to track)  //没有文件需要commit(需要从暂存区提交到本地版本库),但工作区有文件需要被提交到暂存区
另一例
>On branch main //分支在main
>Your branch is up to date with 'origin/main'.//本地版本库与远程orgin/main相连接
>
>Changes to be committed: //需要被commit
>>(use "git restore --staged <file>..." to unstage) //下列文件可以使用git restore --staged 命令撤销修改, git add的逆向操作
>>>        new file:   GItLearn.md
>>>        new file:   images/git_area.jfif

git branch -c name: 创建一个新的分支
git switch name:切换到另一个分支

