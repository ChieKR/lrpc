# 介绍
lrpc 是一款使用 Netty 作为网络通信，序列化机制选择了Kyro代替了JDK自带的序列化机制，使用Zookeeper作为注册中心，管理相关服务地址信息。
lrpc代码注释详细，结构清晰，非常适合阅读和学习。

### lrpc架构

此项目目前架构如图：


![](./images/rpc-architure.png)

服务提供端 Server 向注册中心注册服务，服务消费者 Client 通过注册中心拿到服务相关信息，然后再通过网络请求服务提供端 Server。

### 项目亮点
1. 注释非常详细，使代码非常容易看懂，适合阅读和学习（实际项目上不建议这么做！能用代码表示清楚用意就不要添加注释。）
2. 使用 Netty（基于 NIO），并在代码中实现Netty 重用 Channel 避免重复连接服务端，实现高性能网络传输
3. 使用CompletableFuture接受服务提供端返回结果，优化了接收服务端返回值的过程
4. 运用了SPI机制
5. ...

### 项目待优化点
1. 更完善的客户端与服务端通信协议（数据包结构，可参考Dubbo框架对这块的设计）
2. 更完善的负载均衡功能
3. 完善的容错功能
4. ...
