# Git命令

<!--TOC-->



任何参与开发的人，只要不是一次性修改，都应该开一个分支，把自己的工作先合入这个分支；等开发完全完成后再合并自己的分支到主版本。

添加环境变量后，用powershell直接可以以命令行形式创建分支。

powershell-git常用命令



配置http代理

```cpp
例如clash的端口号为7890，那么要新增一下，否则无法推送。
git config --global http.proxy 127.0.0.1:7890   

```



```cpp
git init -b "name": 指定新的分支
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

## 场景常用

### 新建本地文件夹并同步到github

在新建的文件夹里打开powershell.
