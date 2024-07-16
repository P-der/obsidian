# 开始学习
- 如何启动
 psql -l 查看， 默认无密码，默认端口号为 5432
 mac vscode 使用deatabase插件，直接连接，需要修改用户名为电脑用户名
 - 新建数据库
 执行 `CREATE DATABASE new_database;` 即可；如果有现成的创建文件，也可以在 `psql` 中执行，或者在页面右上角的箭头中执行![[Pasted image 20240716134620.png]]
- 如何运行代码
vscode插件直接new query 添加
![[Pasted image 20240716134218.png]]
展开后，在`Query` 中添加对应的目录或者直接新家sql文件即可
![[Pasted image 20240716134325.png]]
点击`run` 即可执行
# 记录

- OR vs IN
多条where语句时`IN` 性能更好