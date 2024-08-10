## 使用git的一些原则

1. 永远记得 git status 和 git  log --oneline 来确认当前分支的状态
2. 宁愿临时制造一些无用的 commit 来保证代码不会丢失，也不要轻信自己的记忆力
3. 谨慎（最好能避免）使用 [git stash](https://www.zhihu.com/search?q=git%20stash&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22article%22%2C%22sourceId%22%3A%22250493093%22%7D) ，极易造成代码丢失
4. 认真对待、编写每次的 commit

常用的核心命令：

第一个是 git status

我通常在 **写完代码后、做任何git操作前、做复杂的git操作的途中（比如 [rebase](https://www.zhihu.com/search?q=rebase&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22article%22%2C%22sourceId%22%3A%22250493093%22%7D)、merge遇到冲突时）和 做完任何git操作后**，都会使用 git st 去查看当前的状态 —— 哪些文件还在工作区（还没 git add）、哪些文件还在暂存区（还没 git commit）或者 rebase、merge 的进展等。

充分、及时了解当前的 git 状态可以避免一些误操作。



第二个是  git log --oneline 

这个指令可以打印出最近的commit messages，每条message只占一行，界面更干净、美观。

我通常会在 **切换分支的前后，拉取线上分支的前后** 使用git logl，它能帮我根据 commit message 确认我当前的分支以及当前分支是否是最新的 （前提是每次 commit 时一定要认真填写 commit message）



第三个是 git commit

git 之所以使用广泛，是因为它有非常优秀的设计和性能。而其中，commit 是git 设计中的核心。

在日常开发工作中，通常会在 **写完一部分代码后，准备暂时休息前或确认某个功能/bug处理完成后** 使用 **git add** 和 **[git ci](https://www.zhihu.com/search?q=git%20ci&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22article%22%2C%22sourceId%22%3A%22250493093%22%7D)** 来保存代码到本地仓库。

记住：只要正确地 commit了，代码就几乎永远不会丢失。
