# 边缘网关

拓扑图

![边缘网关](C:\Users\nt806\Desktop\笔记\笔记\边缘网关.jpg)

* 边缘/IDC节点安装VPP。

* 管理员通过server配置设备(私网接口)。
* proxy与节点通过RPC互相发送信息(公网接口)。

完成工作：

​	开发工作

* 管理员从server下发acl规则给边缘节点

    关键词：发布订阅模式，分界路由

* 边缘节点定时上报心跳到etcd数据库

    关键词：定时任务，公网接口token校验

* 边缘节点定时上报自身流量信息到influxDB

    关键词：vpp查询自身流量，通过环境变量传递token，无锁队列加快上报速度

    性能测试：

* 并发测试完全可支持业务需求

* acl下发规则 < 3S
