# 设备数据转发MQTT平台

设备数据转发到MQTT平台的前提是你需要有一个可用的MQTT Broker，获得可用的MQTT Broker有2种方式：
1. 互联网上公开免费的MQTT Broker。收集的免费MQTT Broker地址如下：
   * mqtt.eclipse.org (TCP端口号1883，匿名连接)
   * broker.hivemq.com (TCP端口号1883，匿名连接)
   * mqtt.fluux.io(TCP端口号1883，匿名连接)
2. 使用开源的免费软件自建MQTT Broker。厂家的免费MQTT Broker软件如下：
   * [mosquitto](http://mosquitto.org/download/)
   * [emqx](https://www.emqx.io/cn/downloads#broker)

### 安装MQTT Broker

本节内容以将网关的数据推送到自建MQTT服务器为例进行说明。

建MQTT Broker实际很简单，你可以在一台网关能访问的主机上安装MQTT Broker软件，在这次演示中，我们在局域网的一台Windows 主机上安装国产的MQTT Broker [EMQ X Broker](https://www.emqx.io/cn/downloads#broker)，EMQ X Broker支持主流的各种操作系统Linux/Mac OS/Windows，这里我们选择Windows版本，[按照官方安装指南](https://docs.emqx.io/broker/v3/cn/install.html#windows)非常容易的就将EMQ X Broker安装并运行起来了。如遇到启动EMQ X Broker时提示缺少动态库文件，请下载[AIO微软常用运行库合集](https://thingscloud.oss-cn-beijing.aliyuncs.com/download/AIO%E5%BE%AE%E8%BD%AF%E5%B8%B8%E7%94%A8%E8%BF%90%E8%A1%8C%E5%BA%93%E5%90%88%E9%9B%86.2019.10.19.X86%20X64.exe)并安装到EMQ X Broker所在的系统中，EMQ X Broker自带WEB管理端，




### MQTT客户端
MQTT Broker完成安装后，可通过mqtt客户端工具测试一下EMQ X Broker工作是否正常，这里使用网上使用者较多的mqtt客户端工具[mqttfx](http://mqttfx.jensd.de/index.php/download),通过此客户端工具，能和自己部署的MQTT Broker收发消息，就说明工作正常了。


下面继续介绍如何在ThingsCloud平台给网关安装配置“智能云平台”应用，将ThingsLink网关的数据推送到自建的MQTT Broker。


### 安装配置“智能云平台”应用
在网关配置的页面中点击“安装新应用”按钮，在应用商店页面找到“智能云平台”应用并进行安装。


#### 应用之服务器信息
服务器信息部分参数如下表：

| 参数选项         | 参数描述                                                |
| :--------------- | :------------------------------------------------------ |
| MQTT地址         | MQTT Broker服务器的地址         |
| MQTT端口         | MQTT Broker服务器的端口（默认值1883）                             |
| 使用自定义认证方式         |                                              |
| MQTT用户     |  MQTT Broker连接用户名                        |
| MQTT密码   |  MQTT Broker连接密码                |
| 客户端ID   |  MQTT Broker连接客户端ID，如不填写，就是网关序列号        |
| 使用TLS         |  TLS（Transport Layer Security Protocol，传输层安全协议）主要目的是提供隐私和数据两个通信应用之间的完整性                                           |
| 非安全TLS         |   支持不受信任的证书颁发机构的签名，一般指软件的自签名证书。             |
| （SSL/TLS）自签名证书     | 使用MQTT Broker服务器CA证书及客户端证书                   |

![](imgs/2019-10-11-18-55-20.png)

#### 应用之数据传输选项
数据传输参数如下表：

| 参数选项         | 参数描述                                                |
| :--------------- | :------------------------------------------------------ |
| 上送周期         | 网关批量上传数据的间隔        |
| 打包数量         | 网关每次批量上传数据的最大数据条数                        |
| 开启断线缓存      | 网关是否启用断线缓存，默认开启                           |

![](imgs/2019-10-11-18-55-39.png)

#### 应用之高级选项
高级选项一般无需配置，如是需要通过mqtt客户端程序验证数据是，可将高级选项中的禁止压缩勾选。
高级选项参数如下表：

| 参数选项         | 参数描述                                                |
| :--------------- | :------------------------------------------------------ |
| 禁止数据上送         | 禁止网关上传数据到MQTT　Broker        |
| 事件上送(最小等级)    | 大于此数值的事件等级才会被上传                    |
| 禁止设备输出     　　 | 禁止网关接收平台的数据下置操作                       |
| 禁止设备指令         | 禁止网关接收平台的指令        |
| 禁止设备信息上送         | 禁止设备信息上送，关闭后，设备点表等信息不再上传                   |
| 禁止上送紧急数据      | 禁止网关上传紧急数据，紧急数据一般数据下置成功后立即告知平台数据改变    |
| 禁止压缩（调试使用）      | 关闭上传时的数据压缩，关闭后可在MQTT客户端中看到JSON格式字符串     |

![](imgs/2019-10-11-18-55-56.png)

#### 应用之需要上传的设备列表
输入准确的设备序列号（可通过网关的设备列表去查看设备序列号）。

核实以上的应用配置信息准确无误后，将应用安装到网关中。下一节[在MQTT平台中验证数据](data-verify.md)将介绍如何通过MQTT 客户端查看设备数据并对设备进行数据下置。

