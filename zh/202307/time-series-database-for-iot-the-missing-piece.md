## 什么是时序数据库？

时序数据库（TSDB）是一种专门用于处理时间序列数据的软件系统。时间序列数据是按照时间顺序进行索引的数据点序列。这些数据点通常是在一段时间内连续测量得到的，用于跟踪和分析随时间变化的模式。

时间序列数据与其他数据类型的区别在于，时间信息是数据不可或缺的一部分。比如，监控股市的情况，某只股票的价格只有在特定的时刻才有意义。所以，时间序列数据通常包括时间戳和对应的数值，这与传统的关系型数据有所不同。

时序数据库对处理这类数据进行了优化，提供了一些其他数据库系统没有的功能。它们能够高效地接收、存储和查询大量带有时间戳的数据。这使得它们适用于多种应用场景，尤其是来自物联网设备的数据流。

## 时序数据库的工作原理

时序数据库按照时间序列格式存储数据，并根据时间戳对数据进行排序。这种结构便于从时间维度对数据进行高效的查询和分析。当时序数据库接收到新数据时，它会根据时间戳将其添加到已有数据之后，形成一个连续的时间序列。数据库会利用各种索引和压缩技术来高效地存储这些数据，从而在查询特定时间段或模式时能够快速获取数据。

时序数据库的一个重要特点是它能够承受高强度的写入和读取操作。由于时间序列数据是持续产生的，这要求数据库能够实时处理大量数据。同样，数据库也需要提供快速的查询响应，因为用户经常需要及时地分析最新的数据。

## 时序数据库对物联网的重要性

物联网设备广泛应用于各个工业领域，这些设备（如传感器、执行器和联网的机器）实时采集环境、设备和过程的数据，产生了海量的数据。

时间序列数据对于工业场景特别重要。它反映了变量随时间的变化历史，有助于进行趋势分析、异常检测和预测分析。利用这些数据，工业领域可以监测性能、识别模式、发现低效环节，并且能够预见未来事件。

时序数据库是存储和分析物联网数据的理想选择。它具有一些独特的优势，非常适合处理物联网设备生成的时间序列数据：

- **高效的存储和可扩展性：**时序数据库旨在高效地存储和管理海量的时间序列数据。它采用了先进的存储技术，如数据压缩和时间分区，这些技术节省了存储空间并提升了查询性能。由于物联网设备会产生大量的数据，而时序数据库能够处理大数据集并进行水平扩展，使其非常适合物联网应用。
- **高速的数据摄取：**物联网设备通常以高速产生大量数据，因此需要快速的数据摄取能力。时序数据库在这方面具有显著优势，它能够快速摄取数据，每秒处理数百万个数据点。这确保了来自物联网设备的数据能够及时有效地存储在数据库中，而不会给系统带来负担。
- **快速灵活的查询：**时序数据库提供了专门用于时间序列数据分析的查询功能。它包含了经过优化的函数、操作符和索引技术，能够高效地查询和分析带有时间戳的数据。通过其处理复杂查询（比如涉及时间间隔、滑动窗口和聚合的查询）的能力，时序数据库使用户能够快速而准确地从物联网时间序列数据中获取有价值的信息。
- **连续聚合：**时序数据库引入了连续聚合的概念，它允许用户预先计算和存储不同时间间隔的聚合数据。这个特性大大加快了常用聚合查询的性能，例如计算特定时间范围内的平均值、总和或计数。对于需要实时分析和仪表盘的物联网应用，连续聚合带来了显著的性能提升。

## 缺失的一环：为什么时序数据库需要高效的物联网通信协议

尽管时序数据库非常适合处理时间序列物联网数据，但它们并非独立运行的实体。实际上，它们只是庞大物联网生态系统中的一个组成部分。为了顺利地融入该生态系统，时序数据库需要一个高效的通信协议。该协议必须能够稳定而有效地传输由物联网设备生成的大规模、高速的时间序列数据。

对高效通信协议的需求来自于物联网数据所遇到的特殊挑战：

**数据对时间敏感**

物联网设备产生的数据通常对时间有严格的要求，需要快速可靠的传输。任何延迟或数据丢失都可能严重影响实时分析和决策过程。

**连接不可靠**

物联网设备经常在不稳定或低带宽的连接环境下运行。传统的数据传输协议在稳定、高带宽的环境下表现良好，但在这种情况下不适用。因此，通信协议必须是轻量级的，确保数据即使在恶劣的网络条件下也能高效地传输。

**规模非常大**

物联网部署的规模之大也是一个挑战。可能有数百万个设备不断地产生数据，通信协议必须能够应对这种海量的数据量，而不成为瓶颈。这需要协议能够在高负载下保持高吞吐量和低延迟。

**发布-订阅的需求**

为了有效地分发数据，通信协议需要支持发布-订阅模式。在物联网设备中，常常存在一些数据有多个应用或服务对其感兴趣。与每个服务分别从每个设备拉取数据这种非常低效的方法相比，发布-订阅模式允许设备一次发布数据，由协议负责将数据分发给所有感兴趣的订阅者。

总的来说，时序数据库具备存储和分析时间序列物联网数据所需的能力，然而，为了充分发挥它的作用，需要一个高效的通信协议。这个协议应当具备快速、可靠、轻量级、可扩展的特性，并支持发布-订阅模式。如果没有这样一个协议，时序数据库在物联网应用中将无法发挥其全部潜力，而 MQTT 先可以就是一个具备这些特性的理想选择。

## 什么是 MQTT？

[MQTT](https://www.emqx.com/zh/blog/the-easiest-guide-to-getting-started-with-mqtt)（Message Queuing Telemetry Transport）是一种轻量级的消息传输协议，用于在设备之间传输数据，在物联网场景中被广泛使用。它特别适用于网络带宽有限的环境，并在其他协议表现不佳的场景表现出色。

MQTT 基于[发布-订阅模式](https://www.emqx.com/zh/blog/mqtt-5-introduction-to-publish-subscribe-model)。设备或“客户端”订阅主题。当一个消息发布到一个主题时，MQTT Broker 负责让所有订阅者收到消息。这种模式既高效又灵活，可以在各种设备和系统之间进行通信，而不需要他们直接连接。

MQTT 专为物联网场景而设计，在时间序列数据中扮演着关键角色。其能够应对不稳地连接并确保消息传递的特性，使其非常适用于将时间序列数据从物联网设备发送到时序数据库。MQTT 的轻量级特性意味着它能够处理来自物联网设备产生的海量数据，使其成为数据管道中不可或缺的重要组成部分。

## MQTT 在工业物联网数据采集和存储中的应用

在工业物联网应用中，许多应用场景展示了 MQTT 与时序数据库集成带来的多样性和强大性。

- **工业生产监控：**从制造设备、机械和过程中采集和存储实时传感器数据，以监控性能、检测异常和优化操作。
- **能源管理：**将 MQTT 与时序数据库集成，以跟踪和分析工业设施的能耗模式，实现更好的能源管理策略并寻找节能机会。
- **预测性维护：**利用 MQTT 和时序数据库采集工业机械和设备的传感器数据，进行预测性维护分析，实现主动的维护安排并减少意外停机。
- **质量控制和缺陷检测：**从与制造过程集成的物联网传感器和设备中采集和存储时间序列数据，以实时监测产品质量，检测缺陷并触发纠正措施。
- **供应链和物流：**利用 MQTT 实时追踪和监控供应链中的货物、车辆和资产。同时，使用时序数据库存储和分析数据，以优化物流操作，提高库存管理和交付效率。

## EMQX 如何实现时序数据库与 MQTT 的轻松集成

[EMQX](https://www.emqx.io/) 是一款全球领先的[ MQTT Broker](https://www.emqx.com/zh/mqtt/public-mqtt5-broker)，它能够与 Timescale、InfluxDB、Apache IoTDB 等多种时序数据库无缝集成，实现与各种物联网框架和工具的兼容。这种集成极大地促进了工业物联网设备与时序数据库之间的顺畅数据流动，优化了数据处理流程，简化了工业物联网数据管理架构。

![时序数据库与 MQTT 的方便集成](https://assets.emqx.com/images/5b34d4ed43c44eb0c9c379a13c1a9686.png)

EMQX Data Integration 组件在与时序数据库集成中提供了以下特性：

- **完全支持 MQTT 5.0：**EMQX 允许设备通过 MQTT 5.0 或 3.1.1 版本协议连接到时序数据库。
- **可靠的数据摄取：**EMQX 提供了消息缓冲区，以防止在时序数据库不可用时数据丢失。
- **实时数据转换：**使用基于 SQL 的规则引擎提取、过滤、丰富和转换在途数据。
- **实时指标和监控：**通过 EMQX，可以实现对 MQTT Broker 和时序数据库之间消息传输的实时监控。

将 EMQX 与时序数据库解决方案集成，可以为物联网时序数据处理带来以下几个显著优势：

- **高效的数据收集：**MQTT 是一种适合资源有限的物联网设备的轻量级和高效的消息传输协议，可以实现物联网设备与 Broker 之间高效可靠的数据传输。通过将 EMQX 与时序数据库集成，物联网时序数据可以无缝地收集和导入到数据库中，从而确保从大量设备中可靠而高效地收集数据。
- **可扩展性和高吞吐量：**利用 EMQX 和时序数据库的强大集成，组织能够实现极高的可扩展性和吞吐量，以应对物联网时序负载的挑战。EMQX 采用了水平扩展的架构，能够轻松应对物联网设备数量不断增加所带来的海量消息流量。这种解决方案能够随着数据量的增长而弹性扩展，并支持高并发访问。因此，无论物联网部署规模如何扩大，物联网时序负载都可以轻松地满足数据采集、存储和处理不断增长的需求。
- **优化的时序存储：**时序数据库是专为时序数据设计的数据库，专注于优化时序数据的存储。通过时间分区、压缩和数据保留策略，时序数据库能够高效地存储和管理大量的时序数据。这种设计保证了最小的存储空间占用，同时提供了卓越的性能，这对物联网负载产生的海量时序数据至关重要。
- **快速和复杂的查询：**时序数据库提供了强大的时序相关函数、运算符和索引技术，从而实现了时序数据的快速和高效查询。这使得基于时间间隔或特定条件进行复杂的分析、聚合和过滤成为可能。通过将 EMQX 数据与时序数据库集成，组织可以轻松地对物联网时序数据进行查询，从中提取有价值的信息，并进行实时监控、预测性维护和决策支持等高级分析。

## **结语**

将 MQTT 和 EMQX 与时序数据库集成，为管理工业物联网时序数据提供了强大的解决方案。EMQX 具有高可靠性、高可扩展性和高消息吞吐能力，是处理工业物联网设备产生的海量数据的理想选择。EMQX 和时序数据库的结合，使组织能够高效地收集、存储、处理和分析物联网时序数据，从而获得实时洞察，做出主动决策，并提升运营效率。



<section class="promotion">
    <div>
        免费试用 EMQX 企业版
            <div class="is-size-14 is-text-normal has-text-weight-normal">无限连接，任意集成，随处运行。</div>
    </div>
    <a href="https://www.emqx.com/zh/try?product=enterprise" class="button is-gradient px-5">开始试用 →</a>
</section>