## 背景

许多城市的传统燃气系统正面临严峻挑战。随着人口增长和建筑密度上升，燃气管网分布日益密集，这不仅显著增加了燃气供应和管理的复杂性，也使得燃气安全问题更加突出。

燃气管网事故不仅可能影响工业生产，更直接威胁到居民的生命和财产安全。此外，依赖人工巡检的传统燃气管理系统效率较低，难以满足日益增长的实时运维需求，并容易忽视潜在的安全风险。

在这种背景下，城市级燃气物联网和智慧燃气平台代表了燃气行业的未来发展方向。

城市级燃气物联网的建设，通过在燃气管道、阀门、调压站等关键节点部署传感器、智能燃气表以及其他监控设备，实现了对燃气管网的全面感知和精确控制，为智慧燃气平台的开发提供了所需的基础架构和丰富的数据资源。智慧燃气平台则能充分利用这些数据，实现智能抄表、用气预测、安全隐患监控、预警和应急响应、故障诊断等一系列功能，显著提升燃气管理的自动化和智能化水平。

## 建设智慧燃气平台面临的挑战

- **数据采集难题**：城市燃气物联网涵盖了众多设备和传感器，如智能燃气表、压力传感器、温度传感器、流量计、泄漏检测器等。由于每种设备可能由不同的制造商生产，它们通常使用不同的通讯协议和报文规范，导致数据难以统一采集和整合。因此，城市燃气物联网的建设者和运营商需要采用灵活的通信架构，并利用先进的协议转换和集成工具，以确保系统的高效运行和可扩展性。
- **智能边缘管理**：燃气系统的边缘端涉及大量设备和节点的管理。为了确保边缘计算的可靠性和性能，包括电源状态、网络连接、数据处理和通讯能力等在内的各种因素需要得到充分考虑，这要求有一个集中的智能监控系统来实时收集和分析设备状态信息，从而实现对燃气系统边缘端的全面管理和控制。
- **实时数据处理**：燃气门站需要实时处理大量数据，如供气量、供气压力和温度等。在保障数据处理速度的同时，还需确保数据处理的准确性和实时性，以满足燃气系统高效运行的需求。传统的数据处理方案难以满足云端和边缘端 AI 算法以及智能应用对实时数据和历史数据的处理需求。

## 基于 EMQ 云边协同方案构建新一代智慧燃气平台

EMQ 映云科技（以下简称"EMQ"） 推出云边协同方案，旨在帮助燃气系统运营商构建新一代智慧燃气平台。该平台具备高效数据采集与集成、实时监测、智能控制、故障预警、远程维护以及数据分析等多项功能，从而显著提高燃气系统的管理效率和运行安全性，推动智慧城市发展。

基于 EMQ 云边协同方案，新一代智慧燃气平台可实现以下的主要功能：

1. **实时监测与智能控制：**利用 EMQ 的 **NeuronEX 工业边缘网关软件**，智慧燃气平台能够充分发挥其强大的工业数采和协议转换能力，实现一体化、实时的采集和集成。NeuronEX 支持超过 100 种工业协议，确保平台能灵活、兼容地从各种燃气设备中实时采集数据。这些数据经过 NeuronEX 转换成轻量级的 MQTT 消息格式，高效地传输至云端，为智慧燃气平台提供了实时、可靠的数据流。基于这些数据，智慧燃气平台可以实现智能控制和调度，优化燃气资源利用、提高安全性和节能效果。此外，平台还能实时监测燃气设备的状态、传感器数据、用气情况以及管网的运行压力、流量等关键参数。

   ![智慧燃气平台](https://assets.emqx.com/images/1ec5b415709c969ae5121c121ef81675.png)

1. **强大的消息传递能力：**在云端部署 MQTT 接入平台 EMQX Enterprise，使其成为智慧燃气平台的消息传递核心。EMQX 负责数据接入，消息传递的中介以及集成各类数据库和数据应用工具。EMQX 提供可扩展、高可用集群架构，具备高效、可靠和安全的消息传递能力。支持 MQTT、HTTP、WebSocket 等多种协议，实现不同设备、系统之间的实时数据传输和消息交互，为智慧燃气平台提供稳定和可靠的通信基础。
2. **云边协同管理平台：**EMQ 的云边协同方案将云端和边缘计算相结合，构建智慧燃气平台的分布式架构。该方案通过将设备和传感器连接到边缘节点，实现本地数据处理和分析，从而降低对云端的依赖，减少延迟，提升响应速度和整体效率。
3. **故障预警和远程维护：**EMQ 云边协同方案让智慧燃气平台具备了故障预警和远程维护的功能。一旦设备发生异常或故障时，平台能够迅速发出警报，并通知相关维护人员。同时，提供远程监控和诊断工具，以便快速定位并解决问题，大幅提高运维效率。
4. **数据分析和智能决策：**利用 EMQ 的大规模流式数据处理平台 HStream Platform，智慧燃气平台可以获得强大的数据预处理的能力，为大数据分析和挖掘提供支持。通过对数据的深度分析和学习，智慧燃气平台可以提供更精确的预测和智能化决策支持，为管理者提供科学决策依据，优化燃气资源的分配和管理策略。

## 方案价值

1. **提升智慧燃气平台效率：**EMQ 云边协同方案通过整合边缘计算能力和云端资源，优化智慧燃气平台的架构设计。该方案利用边缘计算技术，让设备和传感器数据能在源头被即时处理和分析，从而降低云端的负载压力，并显著缩短了数据处理时间。
2. **降低运维成本：**EMQ 城市智慧燃气方案采用云边协同架构，实现数据的实时传输和高效处理，从而实现了对燃气设备的实时监测与远程控制。这种方法显著提升了燃气管理的智能化水平，减少了对现场人工巡检的依赖，进而降低了运维的人力和时间成本，提高了整体的管理效率。
3. **提高运行安全性：**EMQ 方案通过故障预警和远程维护机制，增强了智慧燃气平台的安全性。一旦检测到设备异常或故障征兆，系统会自动触发警报，及时通知维护团队，并通过远程诊断工具迅速响应，准确定位问题所在。这种主动式的维护策略极大提升了燃气系统的可靠性和安全性，确保了燃气供应的连续性和稳定性。

## 案例：某燃气集团基于 EMQ 物联网方案构建新一代智慧燃气平台

某集团具备全国 20 多家泛能站的运维服务经验，专注于提供新能源技术应用的分布式综合能源平台服务，其服务内容包括泛能操作系统（OS）、用能侧能效管理系统、泛能 APP 和智慧运维服务。

项目需求：

该集团需要构建一个支持自有品牌以及生态企业的燃气与相关泛能物联网设备的混合接入平台，设备协议类型包括 MQTT、NB-IoT 等。此外，平台还需涵盖煤改气、场站管理、泛能设备管理、安全运营等多业务数据接入，并要求数据接入层能够根据业务需求对数据实时分流。 

![新一代智慧燃气平台](https://assets.emqx.com/images/8d23f8e279f2f11d1fafa393a1937c67.png)

EMQ 方案：

1. 提供全面的数据接入能力：EMQX Enterprise 提供多协议接入能力，为物联管理服务平台提供了对接各类协议设备以及公司及第三方平台实时数据的能力，实现了设备之间的无缝通信和数据交互。
2. 提升智慧燃气平台开发效率：利用 EMQX Enterprise 的规则引擎，该方案实现了对多业务数据的实时分流，并能与 Kafka、Redis、MongoDB 以及不同种类的应用接口对接，节省了应用开发时间，还提高了开发效率。与传统工业信息化方案相比，EMQ 方案使企业在大数据分析、设备管理、安全运营、场站管理等智能业务上的开发效率提升了 40%。

## 相关产品

### NeuronEX

[NeuronEX](https://www.emqx.com/zh/products/neuronex) 是一款工业边缘网关软件，提供工业多协议接入与边缘计算能力。主要部署在工业现场，实现工业设备通信及工业总线协议采集、工业系统数据集成、边端数据过滤分析及 AI 算法集成，以及工业互联网平台对接集成等。其提供了以下特性：

- 统一连接：NeuronEX 支持 100 多种常见的工业协议接入，支持如 Modbus、OPCUA、Ethernet/IP、BACnet、Siemens、Mitsubishi 等数十种工业协议的同时接入；提供企业内 MES、WMS 等各系统多数据源的集成对接；NeuronEX 同时支持数据流的双向打通，既可实现数采，也支持控制指令下发到设备。
- 流式处理：NeuronEX 包含 160 多种内置函数，支持数据过滤、数据操作、设备控制以及数据持久化，将数据存储于时序数据库中。
- 无缝集成：支持将 C/Python/Go 等语言的算法集成到 NeuronEX，支持工业机理模型、机器和深度学习等模型在边端的实时推理，输出告警及智能决策。
- 灵活部署：NeuronEX 具有极低的内存占用，在 x86、ARM、RISC-V 等低配置架构设备上运行表现出色。此外，它还支持 Docker 容器化部署，能够与 K8s 环境中的其他容器共同运行。
- 边缘到云：通过 MQTT、SparkplugB 等协议，NeuronEX 将工业数据推送汇聚到云平台，NeuronEX 与云平台之间的双向数据流，形成云边数据协同及控制协同，利用平台侧大数据存储及分析能力，放大 NeuronEX 使用价值。

<section class="promotion">
    <div>
        免费下载 NeuronEX 产品规格书
    </div>
    <a href="https://www.emqx.com/zh/resources/neuronex-datasheet" class="button is-gradient px-5">立即下载 →</a>
</section>

### EMQX 企业版

[EMQX 企业版](https://www.emqx.com/zh/products/emqx) (以下简称 EMQX) 是一个强大的企业级物联网消息平台，专为大规模部署和物联网应用中的高可靠性而设计。在燃气行业中，EMQX 通过以下能力为用户带来收益：

- 高可靠性和可扩展性：EMQX 采用分布式架构，具有高可用性和可扩展性，可以处理大规模并发消息传输。它支持水平扩展，以适应不断增长的物联网设备和数据流量，确保系统稳定性。
- 丰富的协议支持：除了 MQTT 协议外，EMQX 还支持多种消息传输协议。它允许开发人员扩展以支持各种私有协议，以满足其应用需求。
- 数据集成：EMQX 与各种数据存储服务、消息队列、云平台和应用无缝集成。它可以连接到云服务，实现远程数据传输和基于云的分析。
- 安全和认证：EMQX 提供强大的安全功能，包括 TLS/SSL 加密传输、客户端认证和访问控制。它支持多种认证方法，如用户名/密码、X.509 证书和 OAuth，确保物联网通信的安全性。
- 规则引擎和数据处理：EMQX 具有灵活的规则引擎，可以基于设备数据进行实时数据处理和转发。它支持数据过滤、转换、聚合和持久化等操作，帮助用户根据业务需求进行分析和决策。
- 可视化监控和管理：EMQX 提供直观的可视化监控和管理界面，允许用户实时监控物联网设备和消息传输。用户可以查看连接状态、消息流量和其他指标，还可以进行设备管理、故障排除和系统配置操作。

### EMQX ECP

[EMQX ECP](https://www.emqx.cn/products/emqx-ecp) 一款面向工业 4.0 的工业互联数据平台，旨在满足工业场景大规模数据采集、处理和存储分析的需求，ECP 提供边缘服务的快速部署、远程操作和集中管理等功能，助力工业领域数据互联互通，实现数据驱动的生产和运营。在智能燃气场景中，ECP 可以提供以下能力：

- 边云协作：EMQX ECP 边缘服务管理实现了对边缘软件 NeuronEX 等边缘服务部署、管理、配置下发、批量操作、监控和优化。通过提供统一的管理平台，实现双向数据传输与运管边能力；
- 多集群管理：在分租户分项目的基础上实现多集群管理，可以创建新集群或纳管已有集群，并对管理的集群进行修复、水平和垂直扩展、修改网络类型、修改连接数、升降级、集群转让和删除等操作；同时集成 EMQX Dashboard，方便用户直接在 ECP 平台操作和配置 EMQX 集群；
- 多组织多项目管理：EMQX ECP 提供的组织管理功能是一个支持企业级多租户的管理系统，能够实现不同组织的资源隔离和管理。EMQX ECP 可以在同一平台中为多个企业或业务部门提供隔离的 EMQX 数据基础架构服务，每个组织都能够使用自己的数据和配置，互不干扰，保证数据安全。
- 企业级安全性：基于角色的访问控制（RBAC）、单点登录（SSO）、链路加密以及带审计的操作日志确保企业级安全性。
- 监控运维与告警：ECP 的监控平台提供了在云端 EMQX 集群和边缘端进行统一管理和监控的方案。 在 ECP 平台中，系统会收集和分析来自云端 EMQX 集群和边缘端的监控数据，以提供更全面和精细化的管理和监控进行预测故障和风险。



<section class="promotion">
    <div>
        咨询 EMQ 技术专家
    </div>
    <a href="https://www.emqx.com/zh/contact?product=solutions" class="button is-gradient">联系我们 →</a>
</section>