mysql表情乱码处理
======
- 将数据库导出、并改变数据库编码

修改mysql的配置文件/etc/mysql/my.cnf, 添加如下内容
```ini
[client]
default-character-set=utf8mb4

[mysql]
default-character-set=utf8mb4

[mysqld]
character-set-client-handshake=FALSE
character-set-server=utf8mb4
collation-server=utf8mb4_unicode_ci
init_connect='SET NAMES utf8mb4'

```
- 重启数据库
```cmd
mysql restart
```
- 检查配置

```mysql
mysql> SHOW VARIABLES WHERE Variable_name LIKE 'char%' OR Variable_name LIKE 'collation%';

+--------------------------+--------------------+
| Variable_name            | Value              |
+--------------------------+--------------------+
| character_set_client     | utf8mb4            |
| character_set_connection | utf8mb4            |
| character_set_database   | utf8mb4            |
| character_set_filesystem | binary             |
| character_set_results    | utf8mb4            |
| character_set_server     | utf8mb4            |
| character_set_system     | utf8               |
| collation_connection     | utf8mb4_unicode_ci |
| collation_database       | utf8mb4_unicode_ci |
| collation_server         | utf8mb4_unicode_ci |
+--------------------------+--------------------+
11 rows in set (0.05 sec)

mysql>

collation_connection/collation_database/collation_server如果是utf8mb4_general_ci没有关系
但必须保证:  character_set_client/character_se_connection/character_set_database/character_set_results/character_set_server为utf8mb4。


---+
| character_set_client     | utf8                                |
| character_set_connection | utf8                                |
| character_set_database   | utf8mb4                             |
| character_set_filesystem | binary                              |
| character_set_results    | utf8                                |
| character_set_server     | utf8mb4                             |
| character_set_system     | utf8                                |
| character_sets_dir       | /u01/mysql_20170714/share/charsets/ |
| collation_connection     | utf8_general_ci                     |
| collation_database       | utf8mb4_unicode_ci                  |
| collation_server         | utf8mb4_general_ci                  |
+--------------------------+-------------------------------------+


```

- 将导出数据库，更改sql编码，重新建库导入
