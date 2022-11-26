# 开启mysql慢查询日志

## 相关变量

mysql慢查询日志主要涉及如下三个变量

```c++

slow_query_log = 1 // 表示是否开启慢查询
slow_query_log_file=/var/mysql/slow-log.log // 设置慢查询的日志路径和文件名
long_query_time=3 // 查询超过多少秒会被记录在日志中

```

## 开启慢查询

1. 通过`show variables like 'slow_query_log%';` 命令查看相应变量的值

2. 通过`show variables like 'long_query_time%';` 命令查看相应查询时间设置

3. 通过`set global long_query_time=3;` 命令更改查询超时时间

4. 通过`set global slow_query_log=1;`命令开启慢查询

5. 重启服务，慢查询生效