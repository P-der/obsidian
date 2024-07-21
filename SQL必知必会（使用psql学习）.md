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
 - like 匹配字符时需要注意数据库配置
有的数据库存储字符串时会用空格进行部位，会导致`x%x` 匹配固定开头结尾的字符串失效，这时就需要用`x%x%` 匹配，但是这样就无法针对固定结尾的匹配了；更好的解决办法是用函数去掉空格
- like 后面添加正则时，`postgresql` 不支持全部这种语法（比如[ab]，这种情况下，无法匹配），`postgresql` 使用 `SIMILAR TO` 替换like 即可
- 使用 `||` 做字符床拼接
- 使用`select` 不加 from 可以做测试验证， eg: `select 3*2` 为 6
- `SOUNDEX`  可以判断转换为读音，用来判断读音是否一致，但是psql不支持
- `where` vs `having` ; where 分组前过滤，having 分组后过滤
- 子查询 如果写在select中需要返回一个值（需要固定或者聚合），如果写在in里可以返回一列值
- `union` 前面不能有`;` ，否则断开了，排序只能在最后
- 