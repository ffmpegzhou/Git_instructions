# Git简介

<!--TOC-->

## 1.1 Git的安装

分布式版本控制系统没有中央服务器，每个人都有一个完整的版本库，通过各自的修改推送给对方，使得可以多个人协作。

Git用于版本控制：

1、辅助合并代码；

2、区分代码提交人

![2022-12-21_161458.jpg](C:\Users\Cpp_Zhou\Desktop\C++学习笔记（Markdown格式）\源图片\2022-12-21_161458.jpg)

### git常用操作

```c
pull（拉取）:获取远程仓库中的代码更新，并且合并到本地仓库中(pull=fetch+merge)

fetch（获取）:获取远程仓库的代码更新（即是否有人push新的代码到远程仓库）

merge（合并）：将获取到的远程更新合并到本地仓库

commit:（提交）：将更新的代码提交到本地仓库

push:（推送）：将更新的代码推送到远程仓库

commit and push：（提交且推送）：将更新的代码提交到本地仓库后推送到远程仓库----常用

diff:（比较差异）：比较本地的最近一次受版本控制（提交或拉取后）的文件与该文件修改后的
差异----常用

diff with previous version：（与上一版本比较差异）比较本地的上一次受版本控制的
（上一次提交或拉取）文件与该文件修改后的差异

show log：（显示日志）：显示远程仓库所有开发提交记录日志（要看最新的首先拉取）----常用

show Reflog:（显示引用日志）：显示自己本地仓库的所有操作（从克隆开始，克隆、拉取、提交）

check for modifications：（检查已修改）好像功能与diff(比较差异)差不多

revert：（还原）：还原代码至最近一次版本控制（可以单个还原和批量选择还原）----常用

clean up；（清理）：删除某些文件，如未受版本控制文件、忽略文件

add：（添加）：可以把未受版本控制文件加入本地仓库
```

操作过程记录

1、从gitee克隆到本地

<img src="file:///C:/Users/Cpp_Zhou/Desktop/C++学习笔记（Markdown格式）/源图片/2022-12-21_121627.jpg" title="" alt="2022-12-21_121627.jpg" width="609">

2、发现ssh不能用，<mark>改到http地址</mark>

<img src="file:///C:/Users/Cpp_Zhou/Desktop/C++学习笔记（Markdown格式）/源图片/2022-12-21_121646.jpg" title="" alt="2022-12-21_121646.jpg" width="526">

3、克隆成功

<img src="file:///C:/Users/Cpp_Zhou/Desktop/C++学习笔记（Markdown格式）/源图片/2022-12-21_150900.jpg" title="" alt="2022-12-21_150900.jpg" width="537">

4、修改后频繁报错。

该报错在git push时出现，

> 就是在本地仓库上的修改没有基于远程库最新版本，你的本地仓库版本落后于远程仓库。（这个报错告诉我们在本地开发的时候，要经常使用git pull获取远程分支最新改动，这样才能保证在最终git push的时候本地commit历史和远程commit历史是一致的）

> 场景一：
> 起初本地仓库和远程仓库是同步的，某一天在远程仓库上直接做了修改，此时远程和本地就不同步了。过了几天你在本地仓库做了一些修改，修改完成后使用git push想要提交，此时就会报错。

```c
!rejected]master -> master (non-fast-forwarderror: failed to push some refs to
 "https://gitee.com/ffmpegzhou/romote-control,githint: Updates were rejected 
because the tip of your current branch is behindhint: its remote counterpart.
 Integrate the remote changes (e.g.hint:'git pull ...) before pushing 
again.hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

<img src="file:///C:/Users/Cpp_Zhou/Desktop/C++学习笔记（Markdown格式）/源图片/2022-12-21_155228.jpg" title="" alt="2022-12-21_155228.jpg" width="581">

<img src="file:///C:/Users/Cpp_Zhou/Desktop/C++学习笔记（Markdown格式）/源图片/2022-12-21_155358.jpg" title="" alt="2022-12-21_155358.jpg" width="559">

5、已解决问题

<img title="" src="file:///C:/Users/Cpp_Zhou/Desktop/C++学习笔记（Markdown格式）/源图片/2022-12-21_163214.jpg" alt="2022-12-21_163214.jpg" width="547">

解决方法1、先pull最新代码再修改即可
//在修改本地代码前，**先使用git pull拉取远程最新代码，然后再进行修改**（推荐--rebase）
`git pull 远程仓库名 远程分支名 --rebase`
解决方法2、git push --force。在确认代码无误的情况下，直接使用--force强制推送（不推荐
`git push 远程仓库名 远程分支名 --force`

### 创建、修改分支

 Git 的分支**本质是指向快照的指针**。它仅是包含所指对象校验和（长度为 40 的 SHA-1 值字符串）的文件，所以它的创建和销毁都异常高效。分支可以把工作从开发主线上分离开来，以保证开发主线的稳定性。

任何参与开发的人，只要不是一次性修改，都应该开一个分支，把自己的工作先合入这个分支；等开发完全完成后再合并自己的分支到主版本。

添加环境变量后，用powershell直接可以以命令行形式创建分支。

powershell常用命令

```cpp
git init -b "name": 指定并创建当前目录
git branch -a :显示所有分支
git branch "name": 创建分支
git checkout -b "name": 创建并立即切换到指定分支
git checkout  "name": 切换到指定分支
git merge :合并分支
git add . : 提交修改
git stash: 暂存
git branch -m "oldname" "newname":修改分支名
git merge "name":把指定分支合并到主分支
git commit -m 'text':将本地暂存的修改提交到版本库,并加注释
```

## 
