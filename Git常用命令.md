# Git命令

<!--TOC-->

任何参与开发的人，只要不是一次性修改，都应该开分支，把自己的工作先合入这个分支；等开发完全完成后再合并自己的分支到主版本。

添加环境变量后，用powershell直接可以以命令行形式创建分支。

虽然GUI比较快，但个人认为前期应多用命令行，熟悉基本原理。

powershell-git常用命令行：

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

## 常用场景

### 配置http代理

```cpp
例如clash的端口号为7890，那么要新增一下，否则无法在命令行模式推送。
git config --global http.proxy 127.0.0.1:7890   
```

### 新建本地仓库文件夹并同步到远端

在需要添加为仓库的本地文件夹里打开powershell输入命令.

初始化git仓库,并把文件加入暂存区, 暂时提交。

```cpp
git init
git add .
git commit -m"text"
```

接着把本地仓库连接远程地址

```c
 git remote add origin [url]
```

推送

```cpp
git push
```

### 首次从远端克隆到本地文件夹

在其他电脑上新建了仓库推送到了远端，去公司电脑上需要从远端拉取。

新建一个文件夹，并在此处创建git版本库。输入url地址克隆到本地。

```cpp
git init
git clone [url]
```

### 远端修改后合入本地

在远端上传了修改后的文件，回到其他设备需要拉取最新修改到本地，再进行修改，否则会冲突。

此处注意pull和fetch的区别。日常用fetch更安全。

git pull=git fetch+pull

```cpp
git fetch origin [branch_name]
```

### 强制推送/拉取

不管有无冲突，加上--force参数都可以强制推送和拉取（慎用）

```cpp
git pull --force
gir push --force
```



### 查看、切换分支

查看所有分支

```cpp
git branch -a
```

切换到指定分支

```cpp
git checkout [branch_name]
```

### 查看所有历史版本

```c
git reflog 
```
