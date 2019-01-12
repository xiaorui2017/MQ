## 用 ActiveMQ构建应用

Broken:相当于一个 ActivemQ服务器实例

#### 命令行启动参数小例如下:

- actived start:使用默认的 active.xml来启动

- actived start xbean:file: ../conf/  activemq-2.xml :使用指定的配置文件来启动

- 如果不指定file,也就是 xbean: actively-2.xm1,那么xm1必须在 classpath下面

  ​

#### 用 ActivemQ来构建Java应用

这里主要将用 ActiveMQ broker作为独立的消息服务器来构建JAVA应用 。Active也支持在vm中通信基于嵌入式的 broker,能够无缝的集成其它java应用

##### 嵌入式 Broker启动

1: Broker service启动 broker,示例如下:

```java
Broker Service broker new BrokerService();
broker.setUseJmx(true);
broker.addConnector(tcp://localhost:61616)
broker.start();
```

2: BrokerFactory启动 broker,示例如下

```java
String Uri properties: "broker.properties";
BrokerService brokerl BrokerFactory.createBroker(new URI(Uri));
brokerl.addConnector("tcp://localhost:61616);
broker1.start();
```

3: broker. properties的内容示例如下

```xml
useJmx=true
persistent=false
brokerName=Cheese
```





