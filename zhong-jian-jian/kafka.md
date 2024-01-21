# kafka

```plant-uml
@startuml
'https://plantuml.com/sequence-diagram


autonumber

collections Idcs
actor       郭坚
queue       Kafka
actor       zzy
database    Mysql

box "Internal Service" #LightBlue
participant Kafka
participant zzy
participant Mysql
end box

'采集上报数据
Idcs --> 郭坚  : 采集各个IDC的数据

郭坚  -> Kafka : 使用`flink`框架, \n 将所有数据提交
activate Kafka #Yellow
note over Kafka #Yellow
- 本地搭建kafka
- 造点假数据
end note
Kafka --> 郭坚 : 成功

deactivate Kafka

'-------------------------------- -------------------------------- --------------------------------

'消费Kafka
Kafka -[#red]> zzy :  golang 消费kafka, 取到原始数据
activate zzy #red

zyz -> zzy : 咱们分库分表，每个资源池一个库\n每个资源池内，表就是这19个表\n这样有个好处，就是id就是唯一了。

note over zzy
- 根据topic确定入哪个库
    - flink_info_beijing05
    - 入库 beijing05

- 根据Kafka获取数据, 获取table_name
    - { "table_name": "hosts"}
    - 入表hosts

- 分库分表这个事情谁创建?
    - 线上环境的脚本谁提供

end note


zzy -[#red]> Mysql : json unMarsh 落库
deactivate zzy #red

note over Mysql #blue
- 处理
end note

activate Mysql #blue
return 成功

deactivate Mysql


郭坚 <-- Mysql : 其他的操作
@enduml
```
