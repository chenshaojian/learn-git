===========================================================GitHub帐号密码=======================
879937342@qq.com
jian
===============================================================创建=============================
mkdir learngit
cd learngit
git init
git add readme.txt
git commit -m "wrote readme file"
================================================================时光穿梭============================
git diff readme.txt  查看difference
git status 看看仓库的当前状态
git log (--pretty=oneline) 查看提交日志
git reset --hard HEAD^(或id) 回到前一个版本或某个版本
git reflog 查找commit id
git diff HEAD -- readme.txt 查看工作区和版本库里面最新版本的区别
git checkout -- file 丢弃工作区的修改
git reset HEAD file 把暂存区的修改撤销掉（unstage），重新放回工作区
rm test.txt 后git rm test.txt再 git commit -m "remove test.txt"删除该文件
=================================================================远程仓库==============================
ssh-keygen -t rsa -C "youremail@example.com" 创建SSH Key
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++上传GitHub+++++++++++++
echo "# learngit" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/chenshaojian/learngit.git 远程库的名字就是origin，这是Git默认的叫法
git remote add origin git@github.com:chenshaojian/gitskills.git
git push -u origin master我们第一次推送master分支时，加上了-u参数，Git不但
会把本地的master分支内容推送的远程新的master分支，还会把
本地的master分支和远程的master分支关联起来，在以后的推送或者
拉取时就可以简化命令。
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++下载到本地库+++++++++++++
git clone https://github.com/chenshaojian/gitskills.git
git clone git@github.com:chenshaojian/gitskills.git
==================================================================分支管理==============================
git checkout -b dev -b参数表示创建并切换.相当于git branch dev和git checkout dev
git branch 查看当前分支
git checkout master切换回master分支
git merge dev 合并分支,之前的分支必须不能改.
git branch -d dev 删除dev分支
git log --graph --pretty=oneline --abbrev-commit 分支的合并情况
git merge --no-ff -m "merge with no-ff" dev --no-ff参数，表示禁用Fast forward.为了方便查看过去的分支
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++bug分支++++++++++++++++++++++++++++++++++++
git stash 存储
git stash list 列表
git stash apply恢复
git stash pop 恢复并删除
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
git remote -v 显示了可以抓取和推送的origin的地址
git clone git@github.com:chenshaojian/learngit.git抓取分支 发现只有master
git checkout -b dev origin/dev创建远程origin的dev分支到本地
++++++++++++++++++++++github上代码未被修改时+++++++++++++++++++++++++++++++++++++
git push origin master 推送分支到github但是github上的代码被其他人改了就会失败需要它下载合并上传
++++++++++++++++++++++github上代码被修改后+++++++++++++++++++++++++++++++++++++
git pull最新的提交从origin/dev抓下来,若失败
git branch --set-upstream dev origin/dev建立本地分支和远程分支的关联
再git pull,如果有冲突，要先处理冲突,手动解决
===================标签管理:标签需要远程推送不会自动推送==============================
git tag v1.0 打一个新标签
git tag 查看标签
git tag v0.9 6224937 找到历史提交的commit id，然后打上标签
git show v0.9 标签信息
git tag -a v0.1 -m "version 0.1 released" 3628164用-a指定标签名，-m指定说明文字
git tag -d v0.1 删除标签
git push origin v1.0 推送某个标签到远程
 git push origin --tags 一次性推送全部尚未推送到远程的本地标签
++++++++++++++++删除远程标签++++++++++++++++++++++++=
git tag -d v0.9 先删本地标签
git push origin :refs/tags/v0.9 远程删除



















