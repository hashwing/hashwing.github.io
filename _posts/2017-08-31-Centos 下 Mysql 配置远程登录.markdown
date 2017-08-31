---
layout: post
title:  "Centos 下 Mysql 配置远程登录"
date:   2017-08-31 21:05:13 +0000
categories: jekyll update
---

如果想让root用户支持远程登录，是需要进行额外配置的；配置步骤如下：


* 修改root密码 (可选)

```

# 切换到mysql这个数据库
mysql> use mysql;

# 将root用户的密码修改为：123456
mysql> update user set password=PASSWORD('123456') where user='root';

```

* 检查root配置

```

# root用户登录
$ mysql -u root -p

# 切换到mysql这个数据库
mysql> use mysql;

# 查看root用户配置
mysql> select host,user from user where user='root';
修改root配置 

```
mysql> update user set host = '%' where user = 'root' and host='127.0.0.1';

```

* 给用户授权
```
mysql> grant all privileges on *.* to 'root'@'%' identified by '123456' with grant option;

```

*使配置生效
```
mysql> flush privileges;

```