# 产品概述

  网络负载均衡（Network Load Balancer，简称NLB）是京东云自主研发、专注四层业务服务的负载均衡产品，支持过亿并发连接和每秒百万级新建连接的高性能、低延时、会话保持等能力。

  网络负载均衡具备以下功能及特点：

* 高性能：支持过亿并发连接、每秒百万级新建连接。

* 高可靠：支持多可用区创建，后端服务可紧密配合高可用组AG的自动跨AZ、跨机架的容错域分配，实现业务自动高可用部署。

* 自动弹性伸缩：服务实例可根据业务情况自动调整，免除用户业务规划与手动升级的繁琐。

* 会话保持：无论NLB还是后端服务的实例扩展时，NLB都能完美实现会话保持能力。

* 连接耗尽：网络负载均衡NLB支持注册实例按照用户定义的连接耗尽条件进行优雅退出，以减少用户业务的中断。

* 后端丰富性：支持虚机、原生容器作为后端服务实例，为用户业务部署提供灵活选择。

* 源地址透传：NLB可完整透传用户源IP地址，便于服务端感知或者统计真实源端信息。

* 按用量计费：NLB计费除了最小资源保有费之外，完全按照用户实际使用流量进行计费，按用付费为用户提供最经济实用的服务使用方式。


## 应用负载均衡&网络负载均衡&分布式网络负载均衡对比

| 比较项   |  应用负载均衡 | 网络负载均衡 | 分布式网络负载均衡 |
|:-----|  :---- | :---- | :---- |
|性能 	| 百万并发连接、每秒万级新建连接 | 上亿级并发连接、每秒百万级新建连接 | 转发性能无瓶颈 |
|服务协议层 |   四层/七层 | 四层（有状态）| 四层（无状态）|
|协议类型	| HTTP、HTTPS、TLS和TCP | TCP | TCP |
|WebSocket支持| ✔ | —— | —— |
|服务实例弹性伸缩 | ✔ | ✔ | ✔ |
|多可用区高可用部署 | ✔ | ✔ | ✔ |
|调度算法	| 加权轮询、加权最小连接数和源IP | 加权轮询、加权最小连接数和源IP | 加权源IP和加权五元组 |
|SSL卸载与证书管理 | ✔ | —— | —— |
|空闲连接超时 | ✔ | ✔ | —— |
|源IP保留	| 基于HTTP头的X-forward-for机制透传 | 三层报文源IP透传 | 三层报文源IP透传 |
|会话保持 | 基于Cookie的会话保持  |  TCP连接的会话保持 | —— |
|连接耗尽超时 | 只支持连接耗尽，不支持配置超时时间 |  ✔ | —— |
|后端服务实例类型 | 云主机/原生容器/高可用组| 云主机/原生容器/高可用组 | 云主机/原生容器/高可用组 |
|健康检查 | ✔ | ✔ | ✔ |
|内外网负载均衡切换	 | ✔ |	✔ | ✔ |
|删除保护 | ✔  | ✔ | ✔ |
|计费标准	| 费率相对高（暂时免费）| 费率相对低（暂时免费） | 免费 |

## 常用操作

- 创建NLB实例
  - [创建实例](../Getting-Started/Create-Instance.md)
  
- 创建服务实例资源（AG/虚拟服务器组）
  - [创建虚拟服务器组](../Operation-Guide/TargetGroup-Management.md)
	
- 配置侦听策略（包括listener、backend）
  - [配置侦听策略](../Operation-Guide/Listener-Management.md)
	
- 后端服务管理&查看服务实例健康状态
  - [后端服务管理与服务实例健康状态查看](../Operation-Guide/Backend-Management.md)
	
- 运维管理
  - [查看监控信息](../Operation-Guide/Monitoring.md)
  - [设置报警规则](../Operation-Guide/Monitoring.md)

## 计费

网络负载均衡支持按流量计费类型。详细说明请参见“[计费规则](../Pricing/Billing-Rules.md)”。