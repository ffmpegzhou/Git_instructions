# Git说明书

写给自己的几个git基本原理、常用案例，深入探索几个常用命令行的基本原理。

文件的版本管理有一定共性知识点。无论哪一种工具，解决的都是“多人协作编辑”的问题，这个问题的核心痛点两个：

1. 加锁：多人编辑同一文件，但同一时间仅允许一人编辑；

2. 同步：多人编辑多份副本之后冲突，之后同步合并，手动处理冲突。

普通工作根本用不了那么多花里胡哨的装逼技巧，掌握十个命令足以覆盖99%的使用场景:

add+commit+pull+push， 能完成90%的日常工作；

再加上rebase, rebase -i, gcb, gco, stash, reset能完成99%工作,剩下1%不用记, 记不住没事,遇到就现查。
