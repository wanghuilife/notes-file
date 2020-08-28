# node后台开发笔记

## 一、数据库

### 1、数据库基本命令

```js
mysql -u root -p // 登录mysql
mysql [-h127.0.0.1] [-P3306] -uroot -p    (端口要用大写P，与密码p加以区分）
use 数据库名 //使用数据库
show databases // 查看数据库列表
select user,host,authentication_string from mysql.user; // 查看数据库用户
flush privileges; // 刷新
update user set host='%' where user='root'; // 跟新用户
select user,host from user; // 查看用户
delete from user where host='%'; //删除
```

