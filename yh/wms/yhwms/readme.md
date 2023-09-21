# YHWMS 基础设施

### 清单
启动大概需要 5-7G 内存，请提前预留好避免启动失败，由于服务较多启动时电脑会略微卡顿。
| 应用名 | 版本号 | 端口号 | 是否需要访问 | 规格 | 用途 |
| -------- | -------- | -------- | -------- | -------- | -------- |
| zookeeper     | 3.8.0     | 无     | 否     | 单节点     | 存储kafka元数据     |
| kafka     | 3.1.1     | 29092     | 是     | 单节点     | 存储消息     |
| kafka-ui     | master     | 8888     | 是   | 单节点   | 查看修改 kafka topic  |
| redis     | 7.0.9     | 6379     | 是     | 单节点     | 存储缓存数据     |
| mysql     | 8.0.31     | 3306     | 是     | 单节点     | 存储数据     |
| sequenceid     | 2.0.1     | 8080     | 是     | 单节点     | 生成有序id     |
| apm-server     | 7.16.2     | 8201     | 是     | 单节点     | 链路追踪     |
| elasticsearch     | 7.16.2     | 9200     | 是     | 单节点     | 存储日志     |
| kibana     | 7.16.2     | 5601     | 是     | 单节点     | 查看日志     |
| filebeat     | 7.16.2     | 无     | 否     | 单节点     | 抽取kafka数据到es     |



mysql                     管理员账号：`root`         密码：`1q2w3E*`

redis                      无账号密码

ElasticSearch        管理员账号：`admin`            密码：`changeme`

Kibana                   管理员账号：`admin`            密码：`changeme`


### 启动
![](https://markdown.liuchengtu.com/work/uploads/upload_9322c3259d08b8a44b29862de9a946bf.png)
```yaml
## 在当前目录执行
docker-compose up -d
```
### 检查
共计 13 个容器，其中两个是一次性任务，执行完毕会自动退出不用管。
![](https://markdown.liuchengtu.com/work/uploads/upload_3710a95f1750c3c5b9a18114dc706036.png)

filebeat 默认监听的 topic 为以下名称，如果消息没有写到以下 topic，将不会有数据在 Elastic Search 中

```yaml
YHWms.Operations.TLog.pro
YHWms.Express.AuditLog.pro
YHWms.Express.RequestLog.pro
YHWms.Adapter.QiMen.RequestLog.pro
YHWms.Operations.AuditLog.pro
YHWms.Operations.OrderAuditLog.pro
YHWms.Adapter.Boe.RequestLog.pro
YHWms.Adapter.Nike.RequestLog.pro
YHWms.Adapter.Standard.RequestLog.pro
```


### 删除
``` yaml
## 如果服务运行异常，可先删除再启动。
docker-compose down
```


