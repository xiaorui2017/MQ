## **ActivemQ简介**

##### ActiveMQ是什么

activeMQ是 Apache推出的,一款开源的,完全支持JMS1.1和J2EE1.4规范的JMS Provider实现的消息中间件 Message Oriented Middleware,MOM)

##### **ActiveMQ能干什么**



最主要的功能就是:实现JMS Provider,用来帮助实现高可用、高性能、可伸缩、易用和安全的企业级面向消息服务的系统

##### ActiveMQ特点

完全支持JMS1.1和J2EE1.4规范(持久化,XA消息,事务)

支持多种传送协议:in-VM,TCP,SSL,NIO,UDP, JGroups,JXTA

可插拔的体系结构,可以灵活定制,如：消息存储方式、安全管理等

很容易和Application server集成使用

多种语言和协议编写客户端。语言:Java,C,C++,C#,Ruby,Perl, Python,PHP

从设计上保证了高性能的集群, 客户端-服务器, 点对点

可以很容易的和 Spring结合使用

支持通过JDBC和 journal提供高速的消息持久化

支持与Axis的整合



## 消息中间件

##### MOM基本功能:

​	将信息以消息的形式,从一个应用程序传送到另一个或多个应用程序

##### MOM主要特点

- 消息异步接受,类似手机短信的行为,消息发送者不需要等待消息接受者的响应,减少软件多系统集成的耦合度
- 消息可靠接收,确保消息在中间件可靠保存,只有接收方收到后才删除消息,多个消息也可以组成原子事务

##### 消息中间件的主要应用场景

在多个系统间进行整合和通讯的时候,通常会要求:

- 可靠传输,数据不能丢失,有的时候,也会要求不能重复传输
- 异步传输,否则各个系统同步发送接受数据,互相等待,造成系统瓶颈

目前比较知名的消息中间件

IBM MOSerie

BEA WebLogic JMS Server

Oracle AQ

Tibco

SwiftMQ

alibaba RocketMQ

RibbitMQ

ActiveMQ RocketMQ RibbitMQ:是免费的Jva实现的消息中间件,也是现在用的比较多的消息中间件



## ActiveMQ安装和基本使用

##### 下载并安装 ActiveMQ服务器端

- 从http://activemq.apache.org/download.html下载最新的ActiveMQ
- 直接解压,然后拷贝到你要安装的位置就好了

##### 启动运行

- 普通启动:到 ActiveMQ/bin下面, ./activemg start
- 启动并指定日志文件 ./activemg start > /tmp/ activemqlog

##### 检查是否已经启动

ActiveMQ默认采用61616端口提供JMS服务,使用8161端口提供管理控制台服务,执行以下命令以便检验是否已经成功启动 ActivemQ服务

比如查看61616端口是否打开:  netstat -an | grep 61616

也可以直接查看控制台输出或者日志文件

还可以直接访问ActiveMQ的管理页面 http://192.168.1.106:8161/admin/

默认的用户名和密码是 admin/ admin

##### 关闭 ActiveMQ

可以用 ./activemq stop

暴力点的可以用 ps-ef| grep activemq来得到进程号,然后kill掉

