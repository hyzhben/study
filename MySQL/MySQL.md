显示所有数据库

```
show databases;
```

使用数据库

```
use 数据库名;
```

显示所有数据表

```
show tables;
```

截断表（不可回滚，彻底删除表中的信息，慎用）

```
truncate table 表名;
```

- truncate table是清空一个表，是一个DDL语言，效率高
- delete是DML语言;
- delete时会触发与表相关的触发器，而truncate不会;
- delete可以有删除条件，truncate没有。





仅仅列出不同的值

```
select distinct * from table
```

