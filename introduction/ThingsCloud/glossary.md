# 名词解释

本章主要介绍ThingsCloud中相关的产品名词。

| 名词         | 解释                                                                     |
| ------------ | ------------------------------------------------------------------------ |
| 边缘计算 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | 边缘计算（Edge computing），是一种分散式运算的架构，将应用程序、数据资料与服务的运算，由网络中心节点，移往网络逻辑上的边缘节点来处理。 <br>  边缘运算将原本完全由中心节点处理大型服务加以分解，切割成更小与更容易管理的部分，分散到边缘节点去处理。  <br> 边缘节点更接近于用户终端装置，可以加快资料的处理与传送速度，减少延迟，提供安全可靠的数据计算能力，可供本地处理设备数据，减少上传云端的成本。 |
| FreeIOE      | [FreeIOE](https://github.com/freeioe/freeioe)  是一个为快速开发工业物联网（IIOT）边缘计算应用而产生的开发框架。                    |
| FreeIOE 应用 | 基于[FreeIOE](https://github.com/freeioe/freeioe) 框架开发的边缘计算应用程序。                                                   |
| 边缘网关     | 运行了边缘计算功能的程序（如FreeIOE）的嵌入式盒子。                                                                       |
| FreeIOE网关     | 泛指运行了[FreeIOE](https://github.com/freeioe/freeioe) 程序的嵌入式盒子。                                                                       |
| 应用配置     | FreeIOE 应用提供的配置界面或配置参数。                                                                       |
| 应用市场     | FreeIOE 应用分发平台。                                                                       |
| 应用日志     | FreeIOE 应用运行时产生的程序日志。 可在平台上实时查看                                                                      |
| 设备报文     | FreeIOE 应用和现场设备通讯交互时的通讯协议报文。 可在平台上实时查看                                                                    |
| 设备模板     | FreeIOE 应用针对设备数据进行解析和处理时由用户定义的一份设备变量信息表。                                                                |
| 设备事件     | 边缘网关和现场设备通讯交互时由设备或应用根据设备数据产生的事件。                                                                       |
| 平台日志     | 用户或网关在ThingsCloud平台留下的活动记录。                                                                       |
| 远程调试     | 用户在ThingsCloud平台对边缘网关中的FreeIOE 应用进行代码编辑，代码调试。                                                                       |
| 远程编程     | 借助ThingsCloud平台和在边缘网关中安装FreeIOE 远程编程应用，可为用户安装了设备编程软件的电脑和远程的设备之间搭建一条直连的虚拟通道，让用户可直接操作配置远程设备。        |
| 网关序列号   | 边缘网关对外提供的一组全局唯一的识别信息。                                                                       |
| 设备序列号   | FreeIOE框架中用于定位设备的一组全局唯一的识别信息，一般可通过FreeIOE应用产生全局唯一的虚拟设备序列号，也可使用设备自身的序列号（如果能保证全局唯一）。                   |
| 应用开发环境 | 开发FreeIOE 应用的开发环境。                                                                       |
| WEB IDE     | 在ThingsCLoud上开发FreeIOE 应用的编码环境。                                                                       |
| LUA 语言     | Lua（发音： /ˈluːə/）是一个简洁、轻量、可扩展的脚本语言。是FreeIOE开发边缘应用的语言        |


