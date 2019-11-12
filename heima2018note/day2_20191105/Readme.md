git，只有git

一设置
#用于唯一识别某个用户，所以需要绑定用户名和密码

git config --global user.name "name"
git config --global user.email "email"


二操作
git init 创建仓库
git add  添加
git commit -m "##" 提交带注释 -m 后面加注释

**git push**

git push 搞了好久，基本上实现从入门到放弃的过程，最终在队友助攻下成功了，遇到的坑：
1.git remote add name ip   这里的 name是新建仓库的name，ip是新仓库所对应的github的地址
2.git push 远程仓库名  本地分支名字：后面分支名字
eg： git push learngit master:master
3.如果仓库add错误，别害怕，有补救机制的！！
先查看现有的仓库
git remote -v
然后将添加错的仓库删掉
git remote remove <name> name为错误的仓库名字

**git push**


git status 查看当前状态
git diff 查看具体修改了啥

git log 查看历史日志。
但是如果是：
git log  --pretty=oneline,显示的则是commit_id & 提交的文本。


版本问题
当前版本 HEAD ，上个版本HEAD^,上上个版本HEAD^^。但是呢，如果版本忒多了，那么有一个更简洁的表示出来了，eg.HEAD~100,标识往上100个版本

git reset 调整版本
eg. git reset --hard HEAD^ 将版本调整为上一个版本
？？--hard 这个含义我还不懂，回头补上？？
eg. git reset --hard <commit_id>  commit_id 为前几位就行了

git reflog 用来记录版本变化的日志

三、工作区和暂存区
工作区：简单理解为本地电脑
版本库=暂存区+各个分支以及各个分支所有包含的节点
工作区+add操作->暂存区
暂存区+commit操作->具体分支

放弃修改
git checkout -- <file> 此命令回到 上次 git add 或 git commit 状态
如果已经commit，那就用reset切换到之前的版本，再执行checkout。
但是如果推送到远程库，那就没有补救措施了。

删除：从版本中删除东西
git rm <file>，
如果删错了，还有checkout补救


推送远程库
1.首先要连上自己的github账号，要创建SSH Key：
ssh-keygen -t rsa -C "<my_email>",
通过此命令生成公钥和私钥
2.github上将公钥配上
Account settings->add ssh key
3.github上建一个新的仓库，用于推送暂存区代码
4.本地链接远程仓库
git remote add origin <仓库ip地址> origin为远程库名字，系统默认名为此。
5.git push 见前面的笔记
git push -u 本地分支名 远程分支名，
eg. git push -u origin master,
其中-u是互相关联的意思，远程&本地仓库


克隆远程库
git clone <ip_address>



git checkout -b dev 创建并切换到新分支，
相当于：
git branch dev //创建新分支，
git checkout dev //切换分支

查看分支
git branch 查看当前分支，/* 所在分支为当前分支

合并分支
将分支合并到master：
1.将分支切换到master：git checkout master,
2.将dev合并到master：git merge dev

查看分支合并情况：
git log --graph --pretty=oneline --abbrev-commit

--no-ff  作用是禁止快进式合并
git merge --no-f -m "merge but fix 101" issue-101,
作用是将分支issue-101合并到当前分支的下一个节点，而不是合并到issue-101当前的节点。


git stash 存储当前工作现场，方便以后恢复，
git stash list 查看之前的工作现场，
git stash apply 恢复之前的工作现场，但是stash内容还存在，
需要 git stash drop 来删除。
git stash pop 恢复现场的同时，删除stash上相应内容。


git pull 拉代码
git pull 远程仓库名  本地分支名字：后面分支名字
eg： git pull learngit master:master



打tag
1.先确认分支，
2.git tag <name>






