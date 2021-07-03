# Git学习笔记

## 单分支

>git相关知识:
>git分为三个区域，工作区,暂存区,本地版本库
>通过git add命令可以将修改从工作区添加到暂存区
>通过git commit命令可以将修改从暂存区提交到本地版本库
>通过git push命令将修改从本地版本库推送到远程版本库

* git init: 把当前文件夹作初始化为Git仓库  
* git add file_name: 把对应文件添加到暂存区  
* git commit -m "message": 把暂存区的改动提交到本地版本库中
* git status:显示当前git信息，比如所处分支,与哪个远程仓库建立了连接,工作区中修改了的文件,暂存区中需要提交的文件,以下是两个例子:

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

另一例:
>On branch main //分支在main
>Your branch is up to date with 'origin/main'.//本地版本库与远程orgin/main相连接
>
>Changes to be committed: //需要被commit
>>(use "git restore --staged <file>..." to unstage) //下列文件可以使用git restore --staged 命令撤销修改, git add的逆向操作
>>>        new file:   GItLearn.md
>>>        new file:   images/git_area.jfif

* git rm file_name:删除版本库中的文件

删除文件一般先用rm命令删除本地文件，再用git rm删除版本库中的文件,一般经过如下三步:  

>1. rm file_name
>1. git rm file_name
>1. git commit -m "delete file_name"  

如果误删了文件,但没有commit的情况下可以用下列命令恢复:

>1. git restore file_name

* git log --pretty=oneline: 查看历史提交记录，每条记录用一行展示
* git reset --hard HEAD^: 回退到上一个版本
* git reset --hard commit_id:回退到对应commit_it的版本
* git reflog:查看已执行的git命令,方便回到未来的版本

* git add remote origin git@github.com:username/repo_name.git:将本地库与远程库建立联系,将远程库的名字命名为origin,远程库的地址是github.com中的用户username下的名为repo_name的版本库
* git push [-u] origin master:将当前分支master推送到远程库origin,第一次推送加参数-u
* git remote -v:查看连接的远程库
* git remote rm repo_name:与远程库断开连接
* git stash: 保存工作现场
* git stash apply ...:恢复工作现场,但不删除曾经保存的工作现场,需要指明工作现场编号
* git stash pop:恢复工作现场,并删除被恢复的工作现场
* git cherry-pick commit_id:将曾经提交的bug提交到当前分支中

---

## 多分支

* git branch  name: 创建一个新的分支,加-b参数可以直接切换到新分支
* git branch -d name:删除分支
* git branch:查看分支,前面有*号的是当前分支
* git merge name:合并分支,将名为name的分支合并到当前分支
* git switch name:切换到另一个分支

>git推送到远程版本库出现冲突时:
>
>1. 设置本地分支与远程分支的连接 git branch --set-upstream-to=origin/dev dev
>1. 运行git pull命令将远程分支的最新提交抓取下来
>1. 手动解决冲突

* git tag tag_name commit_id:将commit_id打上标签,标签名为tag_name
* git tag:查看标签
* git show tag_name:查看标签详细信息
* git tag -d tag_name:删除标签
