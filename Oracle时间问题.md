# 时间操作

当前时间减去88秒的时间

```
select sysdate - interval '88' second  from dual;
```

- 秒——second
- 分钟——minute
- 小时——hour
- 天——day
- 月——month

日期转为字符的用法

```
select to_char(sysdate,'yyyy-mm-dd hh24:mi:ss') from dual
select to_char(sysdate,'yyyy-mm-dd hh:mi:ss') from dual
select to_char(sysdate,'yyyy-ddd hh:mi:ss') from dual
select to_char(sysdate,'yyyy-mm iw-d hh:mi:ss') from dual
```

