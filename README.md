# Windows上的git的基本使用
```git
<!-- 配置信息 -->
git config --global user.name "your name"
git config --global user.email "email@example.com"
<!-- 创建仓库 -->
git init 
<!-- 将文件添加到版本仓库 -->
git add <filename>
git commit -m <版本信息>
```
# 进阶使用
```git
<!-- 查看版本号 -->
git log
<!-- 查看仓库状态,可以看到那些文件被修改了 -->
git status
<!-- 查看工作区修改了什么内容 diff -> difference -->
git diff
对比文件笔筒
git diff HEAD HEAD^ -- <文件名>
<!-- 回溯版本 -->
git reset --hard DEAD^
git reset --hard DEAD~1
git reset --hard 版本号
<!-- 查看之前操作记录,可以查找回溯之前的版本 -->
git reflog
<!-- 取消工作区修改 -->
git checkout -- <文件名>
<!-- 取消暂存 -->
git checkout <文件名>
```
## git分支操作
```git
<!-- 查看分支 -->
git branch
<!-- 创建并进如分支 -->
git checkout -b <分支名>
<!-- 切换分支 -->
git checkout <分支名>
<!-- 合并分支 -->
git merge <分支名>
<!-- 创建分支 -->
git branch <分支名>
<!-- 删除分支 -->
git branch -d <分支名>
<!-- 查看分支图 -->
git log --graph --pretty=oneline
<!-- 禁用快速提交 -->
git merge --no-ff -m "禁用快速合并fast-forward" <分支名>
<!-- 保存工作现场 -->
git stash
<!-- 查看已保存的工作线程 -->
git stash list
<!-- 恢复工作现场 -->
git stash pop
```
容易起冲突,我们需要手动解决,然后提交
```
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/mylapyop/.ssh/id_rsa):
Created directory '/c/Users/mylapyop/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/mylapyop/.ssh/id_rsa.
Your public key has been saved in /c/Users/mylapyop/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:GSlzP6j1i33Jkip4AzmPHBGc465+M3XTrlpFdyohb54 2285839445@qq.com
```
## github 的使用
```
<!-- 创建ssh密钥 -->
shh-keygen -t rsa -C "邮箱地址"
<!-- 克隆远端分支代码 -->
git clone <ssh地址>
<!-- 推送分支到远端github账户 -->
git push origin <分支名>
<!-- 远程跟踪分支 -->
git branch --set-upstream-to=origin/<远端分支名> <本地分支名>
<!-- 推送到远端,因为已经跟踪分支就可以直接push了 -->
git push
<!-- 拉取远端代码,如果跟踪了课就可以直接pull -->
git pull origin <分支名> 
```
## git在团队中的使用
### 老大
1. 老大搭建项目框架
2. 把框架代码放到服务器
### 小弟
1. 在自己电脑生成ssh公钥，交给老大，老大把ssh公钥添加到服务器
2. 大佬给每个小弟项目代码地址，小弟把代码克隆到自己电脑上
3. 在本地创建 __dev__ 分支,在 __dev__ 分支中开发
4. 每个小弟开发完之后，都需要把自己的 __dev__ 分支提交到远端 __dev__ 分支上去


__Master__ :用户保存的项目代码
__Dev__ ：保存开发过程中的代码

# 关注(watch)和收藏(star)的区别
__watch__ :会通知你项目的修改
__star__ :能让你快速找到收藏的仓库

