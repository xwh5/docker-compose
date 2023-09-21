# MySQL

# 5.7

```yaml
version: '3'
services:
  mysql:
    image: bitnami/mysql:5.7.39
    environment:
      MYSQL_ROOT_USER: "root"   # 管理员账户名
      MYSQL_ROOT_PASSWORD: "123456"   # 管理员密码
      MYSQL_AUTHENTICATION_PLUGIN: "mysql_native_password"   # 认证插件
      MYSQL_CHARACTER_SET: utf8   # 默认字符集（服务器级别）
      MYSQL_COLLATE: utf8_general_ci   # 默认排序规则（服务器级别）
      MYSQL_ENABLE_SLOW_QUERY: 0   # 是否开启慢查询，0：不开启  1：开启
      MYSQL_LONG_QUERY_TIME: 5.0   # 慢查询超时时间
    ports:
      - "3306:3306"
    volumes:
      - type: volume
        source: yh_mysql_data
        target: /bitnami/mysql/data
      - type: volume
        source: yh_mysql_conf
        target: /opt/bitnami/mysql/conf
    network_mode: bridge
volumes:
  yh_mysql_data: {}
  yh_mysql_conf: {}
```

# 8.0

```yaml
version: '3'
services:
  mysql:
    image: bitnami/mysql:8.0.30
    environment:
      MYSQL_ROOT_USER: "root"   # 管理员账户名
      MYSQL_ROOT_PASSWORD: "123456"   # 管理员密码
      MYSQL_AUTHENTICATION_PLUGIN: "mysql_native_password"   # 认证插件
      MYSQL_CHARACTER_SET: utf8mb4   # 默认字符集（服务器级别）
      MYSQL_COLLATE: utf8mb4_unicode_ci   # 默认排序规则（服务器级别）
      MYSQL_ENABLE_SLOW_QUERY: 0   # 是否开启慢查询，0：不开启  1：开启
      MYSQL_LONG_QUERY_TIME: 5.0   # 慢查询超时时间
    ports:
      - "3306:3306"
    volumes:
      - type: volume
        source: yh_mysql_data
        target: /bitnami/mysql/data
      - type: volume
        source: yh_mysql_conf
        target: /opt/bitnami/mysql/conf
    network_mode: bridge
    restart: "no"
volumes:
  yh_mysql_data: {}
  yh_mysql_conf: {}
```



## Environment 变量说明

Docker在对数据库进行初始化的时候会用到以下环境变量：

| 变量名                         | 说明                    | 默认值                   |
| --------------------------- | --------------------- | --------------------- |
| MYSQL_ROOT_USER             | 超级管理员账号名，默认root，可自由更改 | root                  |
| MYSQL_ROOT_PASSWORD         | 超级管理员密码               | 123456                     |
| MYSQL_AUTHENTICATION_PLUGIN | 数据库认证插件               | mysql_native_password |
| MYSQL_CHARACTER_SET         | 默认字符集                 | utf8mb4               |
| MYSQL_COLLATE               | 默认排序规则                | utf8mb4_unicode_ci    |
| MYSQL_ENABLE_SLOW_QUERY     | 是否开启慢查询（0- 禁用，1- 开启）  | 0                     |
| MYSQL_LONG_QUERY_TIME       | 定义慢查询的超时时间（单位：秒）      | 5.0                   |
