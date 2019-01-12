## 在一台机器上启动多个Borker

步奏如下：

- 把整个conf文件夹复制一份，比如叫做conf2

- 修改里面的activemq.xml文件

  - 里面的brokerName 不能跟原来的重复

  - 数据存放的文件名称不能重复，比如：

    ```xml
    <kahaDB directory="${activemq.data}/kahadb_2">
    ```

  - 所有涉及的transportConnectors 的端口都要跟以前的不一样

- 修改jetty.xml，主要就是修改端口，比如：

  ```xml
  <property name="port" value="8181" />   <!--端口必须和以前的不一样-->
  ```

- 到bin下面，复制一个activemq，比如叫做activemq2:

  - 修改程序的id，不能和前面的重复

    ```xml
    ACTIVEMQ_PIDFILE="$ACTIVEMQ_DATA/activemq2-`hostname`.pid"
    ```

  - 修改配置文件路径

    ```xml
    ACTIVEMQ_CONF="$ACTIVEMQ_BASE/conf2"
    ```

  - 修改端口，里面有个tcp的61616的端口，要改成不一样的，最好跟activemq.xml里面的tcp的不一致

  - 然后就可以执行了，如果没有执行权限，就授权

    ```shell
    chmod 751 activemq2
    ```

    ​