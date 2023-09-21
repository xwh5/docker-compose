# Mariadb-Docker Compose 使用说明

MariaDB是MySQL的一个分支，也是一个开源的关系型数据库软件，由MySQL之父Michael Widenius主导开发。 

## 

## 启动步骤

### Windows、Linux用户：

1、下载Docker Compose文件

2、按需修改compose文件内的变量参数，[详见Environment变量说明](#Environment 变量说明)

3、检查配置文件，在compose文件所在的当前目录下执行：`docker compose config`，正常情况会输出yaml，请您确认没有任务错误信息输出

4、启动应用：`docker compose up -d`

## Environment 变量说明

Docker在对数据库进行初始化的时候会用到以下环境变量：

| 变量名                           | 说明                    | 默认值                   |
| ----------------------------- | --------------------- | --------------------- |
| MARIADB_ROOT_USER             | 超级管理员账号名，默认root，可自由更改 | root                  |
| MARIADB_ROOT_PASSWORD         | 超级管理员密码               | 123456                     |
| MARIADB_AUTHENTICATION_PLUGIN | 数据库认证插件               | mysql_native_password |
| MARIADB_CHARACTER_SET         | 默认字符集                 | utf8                  |
| MARIADB_COLLATE               | 默认排序规则                | utf8_general_ci       |
| MARIADB_ENABLE_SLOW_QUERY     | 是否开启慢查询（0- 禁用，1- 开启）  | 0                     |
| MARIADB_LONG_QUERY_TIME       | 定义慢查询的超时时间（单位：秒）      | 5.0                   |
