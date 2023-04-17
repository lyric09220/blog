3 月，[Neuron](https://neugates.io/zh) 团队主要在为 2.4.0 版本的发布做准备，进行了官网文档的重构与完善，为常用驱动增加了相应的连接示例及常见问题。同时新增南向驱动 ABB COMLI，此驱动可通过串口连接 ABB 某些型号的 PLC。

## 新增驱动插件

### 南向驱动 IEC61850 

此驱动在电力系统自动化中应用广泛，它由国际电工委员会 IEC 制定，定义了用于通信的数据模型、数据服务、通信协议等。Neuron 目前实现了 IEC61850 下的 MMS 消息数据，MMS 是一种面向连接的基于客户端/服务器架构的通信协议，主要用来在 IEC61850 设备之间进行高效可靠的数据采集以及设备控制写入。

### 南向驱动 AB DF1

由罗克韦尔自动化公司开发的串行通信协议，主要用于 PLC 和其他设备之间进行通信。此通信协议包含两种数据帧格式，二进制格式以及 ASCII 格式，Neuron 实现二进制数据传输，传输效率更高，速度更快。

### 南向驱动环保 HJ-212

中国环境监测网络中使用的一种通信协议，主要用于在环境监测设备之间进行数据交换，如环境中各种污染物的浓度等。此协议由中国环境保护部分和通信行业专家共同制定，212 为协议版本号，为环境监测工作提供了重要的支持，也为中国环境监测设备的国产化提供了技术支持和保障。此协议在中国环境监测领域有着广泛的应用，包括大气监测、水监测、土壤监测等各个方面。

### 南向驱动 ABB COMLI 

由 ABB 公司开发的一种串行通信协议，主要用于在其 PLC 和其他设备之间进行通信。此协议是一种点对点的通信协议，支持两种数据帧格式、二进制格式和 ASCII 格式。Neuron 实现二进制数据帧格式进行数据采集与设备控制。

### 北向 WebSocket 

主要用于对接 WebSocket Server，可以与 WebSocket Server 通过以 JSON 为基础数据进行采集点位的数据上报等。

## 文档与 UI 完善

为了用户能更方便使用 Neuron 连接各种设备进行数据采集以及设备控制，我们对现有的官网文档进行了整体的重构完善，增加更多常用功能特性的使用示例，并在持续更新中。

此外我们对 UI 也进行了如下优化：

- NeuronEX 版本的数据处理相关 UI 进行的升级扩展，支持在 NeuronEX 版本中创建数据处理流，上传插件等。
- 设备节点管理支持列表模式，多种排序以及搜索，在配置设备节点较多时，能更快找到相关设备节点。
- 点位配置支持列表模式，简化了配置点位时的部分操作，通过页面配置多个点位时更便捷。
- 点位列表支持多种排序以及搜索，可以方便的在数据监控页面或是配置页面更快的找到点位。

## 问题修复

- 修复部分 UI 报错提示不明确的问题。
- 修复 OPC UA 连接某些型号的 PLC 时连接异常的问题。
- 修复在配置的节点数以及点位数较多时，重启后数据加载较慢的问题。
- 修复 Docker 版本中下载日志失败的问题。



<section class="promotion">
    <div>
        免费试用 Neuron
    </div>
    <a href="https://www.emqx.com/zh/try?product=neuron" class="button is-gradient px-5">开始试用 →</a>
</section>