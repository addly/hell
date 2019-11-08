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

