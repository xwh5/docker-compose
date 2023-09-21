# Elatic Apm

在仓库根目录，执行下面命令：

```shell
cd hub/yhwms/elastic-apm-secure-7.16.2
docker-compose up -d
```

当前目录下的 docker 目录为 apm server 启动必要的文件配置，请保持目录存在。



参考地址 https://github.com/elastic/apm-contrib


kibana:  [http://localhost:6501](http://localhost:6501)	默认账号：admin		默认密码：changeme

apm server: [http://localhost:8200](http://localhost:8200)

elatic search: [http://localhost:9200](http://localhost:9200) 账号：admin		默认密码：changeme


# 在当前目录下生成最新版本 docker-compose.yml
```shell
git clone https://github.com/elastic/apm-integration-testing -b 8.x
python3 ./scripts/compose.py start 8.2.3 --release  --docker-compose-path docker-compose.yml | sed 's/8.2.3/${STACK_VERSION:-8.2.3}/'
```