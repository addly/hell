git，只有git

一设置
#用于唯一识别某个用户，所以需要绑定用户名和密码

git config --global user.name "name"
git config --global user.email "email"


二操作
git init 创建仓库
git add  添加
git commit -m "##" 提交带注释

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