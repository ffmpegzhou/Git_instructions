偶尔显示中文为t\347\256\200\350\246\201\350\257\264\346\230\216.md，就是编码设置错误。

- 解决办法  
  将git 配置文件 `core.quotepath`项设置为false。  
  quotepath表示引用路径  
  加上`--global`表示全局配置

    git config --global core.quotepath false 
    


