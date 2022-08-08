
# Macos源码构建mysql

## 下载mysql

本部分通过压缩包下载 https://github.com/mysql/mysql-server/archive/refs/heads/8.0.zip

## cmake安装

brew install cmake

## 构建mysql

将mysql目录命名为mysql-8

cd mysql-8

mkdir build

然后输入如下构建命令

```c++

cmake .. \
 -DCMAKE_INSTALL_PREFIX=/Users/qinliansong/Downloads/mysql-server-test \
-DMYSQL_DATADIR=/Users/qinliansong/Downloads/mysql-server-test/data \
-DSYSCONFDIR=/Users/qinliansong/Downloads/mysql-server-test \
-DMYSQL_UNIX_ADDR=/Users/qinliansong/Downloads/mysql-server-test/data/mysql.sock \
-DWITH_DEBUG=1 \
-DDOWNLOAD_BOOST=1 \
-DWITH_BOOST=/Users/qinliansong/Downloads/boost_1_79_0

```
# 运行make

```

make -j 4

```

构建完成会出现如下截图

![](https://pic3.zhimg.com/80/v2-5c177b540450cdf86440b9100468e7f0_1440w.png)

# 安装mysql

```c++

make install -j 4

```

# 启动mysql

```c++

./mysqld --basedir=/Users/qinliansong/Downloads/mysql-server-test --datadir=/Users/qinliansong/Downloads/mysql-server-test/data

```

mysql在启动的时候也可通过配置文件加载相应的配置项，若要查看其相应配置文件的加载顺序，可在unix机器上运行如下命令

```c++

./mysqld --verbose --help | head -15

```

会出现如下结果

```C++

mysqld  Ver 8.0.29-debug for Linux on x86_64 (Source distribution)
Copyright (c) 2000, 2022, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Starts the MySQL database server.

Usage: mysqld [OPTIONS]

Default options are read from the following files in the given order:
/etc/my.cnf /etc/mysql/my.cnf /home/qls/mysql-serve-learn/my.cnf ~/.my.cnf
The following groups are read: mysqld server mysqld-8.0
The following options may be given as the first argument:

```

# 参考

[Macos 编译运行调试Mysql源代码](https://www.cnblogs.com/yantt/p/macos-bian-yi-yun-xing-diao-shimysql-yuan-dai-ma.html)

[Chapter 3 Installing MySQL Using a Development Source Tree](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/installing-development-tree.html)