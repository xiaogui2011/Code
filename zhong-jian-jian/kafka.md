# kafka

## 认证方式

`config.Net.TLS.Enable`表示是否启用TLS加密通信；`config.Net.SASL.Mechanism`表示使用的安全协议类型。

当`config.Net.TLS.Enable=true`时，Kafka broker要求客户端使用SSL/TLS进行身份验证并加密通信。在这种情况下，您可以使用以下安全协议类型之一：

* `sarama.SASLTypePlain`，即明文密码Authentication
* `sarama.SASLTypeScramSha512`或`sarama.SASLTypeScramSha256`，分别代表SCRAM-SHA-512和SCRAM-SHA-256密码Authentication

当`config.Net.TLS.Enable=false`时，不必使用安全协议类型，因为没有 TLS 层保护连接。此时可以选择以下任意一种方式：

* `sarama.SASLTypeNone`，表示无安全性保证
* `sarama.SASLTypeGSSAPI`，表示通过Kerberos进行安全认证
* `sarama.SASLTypePlain`，即明文密码Authentication

总之，`config.Net.TLS.Enable`控制的是与broker之间的通信是否加密，而`config.Net.SASL.Mechanism`则控制了客户端如何向broker进行身份验证。



## 参与过的项目时序图

<img src="../.gitbook/assets/file.excalidraw (1).svg" alt="" class="gitbook-drawing">

## 格式

就是个json

## 操作

启动消费者

```sh
kafka-console-consumer --bootstrap-server localhost:9092 --topic foobar --from-beginning
```

查看端口状态

```
lsof -i:9092
```



##

## 消费者组
