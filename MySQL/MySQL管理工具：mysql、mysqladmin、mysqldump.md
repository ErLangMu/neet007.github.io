**mysql：**
功能：命令行SQL工具

```
# mysql
# mysql -u root -p
输入密码
mysql>
mysql>exit
# mysql -u root -p '密码'（不能登录）
```

进入指定数据库：

```
mysql>use 数据库
```

```
# mysql --user=账户 --password=密码 数据库
mysql>
mysql>exit
```

SQL语句操作：

```
sql语句结尾：；或\g 或\G
退出mysql>：exit或quit或ctrl+z（ctrl+C不起作用）
```

执行SQL语句脚本：

```
# mysql --user=账户 --password=密码 数据库<脚本
# mysql --user=账户 --password=密码 数据库 < 脚本 > 重定向输出文件
```
```
root远程连接mysql服务器：
# mysql -u root -p -h 远程mysql服务器地址
输入密码
（默认安装时，mysql5.7已做安全设置，禁止远程root连接）
```
```
# mysql -u root -p -h localhost
输入密码
```

**mysqladmin：**
功能：执行管理操作的工具
检查服务器配置、当前运行状态
创建、删除数据库
设置新密码
flush-privileges、reload重新加载权限数据表
refresh刷新数据表、重启日志
start-slave从服务器上启动复制
stop-slave从服务器上停止复制

```
# mysqladmin -u root password 新密码
# mysqladmin -u root -p password 新密码
输入旧密码
```

**mysqldump：**
功能：数据库逻辑备份程序
非大数据备份解决方案
SQL语句重现
备份数据表需要SELECT权限
（物理备份：
功能：适合大规模数据备份和还原
直接复制数据文件
mysqlbackup工具）
备份：数据表、整个数据库、所有数据库
mysqldump备份、mysql还原

```
# mysqldump 数据库 表
# mysqldump --databases 数据库1 数据库2 ...
# mysqldump --all-databases

# mysqldump -u root -p mysql user>user_table
# mysqldump -u root -p --databases mysql>mysql_database
```

系统默认数据库：information_schema、mysql、performance_schema、sys
information_schema不能删除
performance_schema、sys可删除，不可恢复
mysql等自建数据库，可删除、可恢复（但不可批量删除）
（不能通过清空/usr/local/mysql/data目录来删除数据库，否则无法恢复
`# rm -rf *`）

```
# mysqldump -u root -p --all-databases>all_databases

# mysql -u root -p mysql<user_table
# mysql -u root -p <mysql_database
恢复mysql等自建数据库
# mysql -u root -p <all_databases
```

**动态网站API：**

**MySQL WorkBench：**

