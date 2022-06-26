1. 解压版安装参考
https://blog.csdn.net/shijinjins/article/details/124211887

1. 启动
>net stop mysql
>net start mysql


2. 密码设置
> mysql -u root -p
第一次可以直接回车进入
> use mysql
> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '12345';
> flush privileges;                                             # 刷新权限
 
之前的旧版本设置密码:
>update mysql.user set authentication_string=password('123456') where user='root'; # 密码设置
mysql5.7.9之后，就没有了password函数，所以，使⽤传统的password()函数修改root密码的话，就会提⽰sql错误
我尝试过直接去掉password()但是实际上重新登录密码报错


skip-grant-tables





ALTERUSER'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456'
 
