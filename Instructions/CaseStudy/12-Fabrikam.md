﻿---
casestudy:
    title: '可选案例研究：Fabrikam Residences'
    module: '可选案例研究：Fabrikam Residences'
---
# 可选案例研究：Fabrikam Residences

预计用时：90 分钟

## 要求

**本案例研究要求你完成以下模块和案例研究:  计算、关系数据、非关系数据、身份验证、应用程序体系结构**

你在 Fabrikam Residences 获得了一个新职位，该公司非常成功，并且正在快速发展。Fabrikam Residences 是一家建筑承包商，负责新房和重要的房屋装修，并通过提供高质量的建筑和比其竞争对手更新的集成家庭技术而获得成功。  

目前，这些技术由独立的分包公司提供和管理。Fabrikam Residences 的所有者希望开始在内部提供这些升级的技术选项，为客户模式和需求提供更好的质量、支持和数据。 
 
最初，该公司希望提供 HVAC（供暖和制冷）控制和监视、安全系统监视和警报以及家庭自动化。这将需要一个新的网站、数据存储解决方案和数据引入解决方案。

该公司在过去两年中取得了巨大的发展。该公司预计，在未来的 12 到 18 个月，其规模可能会翻倍。由于在地区性市场的快速增长，该公司目前没有向该地区市场以外扩张的计划。

## 现状

Fabrikam 总部在单个位置运营一个小型数据中心。该数据中心托管公司的**项目管理 (PM) 软件**。

![项目管理软件体系结构](media/fabrikam.png)

- PM 软件使用第三方 Windows 应用程序。该应用程序在一个双节点网络负载均衡 (NLB) 群集上运行，只有一个 Microsoft SQL Server 后端。  

- 图像和文档存储在服务器的映射驱动器上，该驱动器位于专用的 NAS 设备上。

- 企业用户和办公人员使用 Web 前端输入数据，如提供交付计划和更改订单。

-	现场监督人员离线使用 Windows 笔记本电脑和平板电脑，持续记录修建进度和其他详细信息。  这些更改（例如新工作订单）存储在本地更改文件中。  在每天的工作结束时，监督员回到办公室连接无线网络并运行一个小脚本将更改文件上传到 FTP 服务器。  按照计划，每晚会运行第二个脚本来处理所有更改文件，并将其内容输入到项目管理数据库 (Microsoft SQL Server)。

**家庭技术软件**目前由第三方提供和托管，客户必须访问至少三个不同的网站。  建议采用内部开发的统一解决方案来替代该软件。

![示意图：HVAC、安全性和自动化应用](media/software.png)

## 要求 

**项目管理软件**

- 将尽可能多的系统迁移到公共云提供商。

- 随着安全问题的出现，应替换现有的脚本以采用比 FTP 更安全的系统。此外，你还需要确保更改文件在上传后立即得到处理。

- 提高项目管理数据库的复原能力。虽然性能不算什么问题，但该公司希望避免在单个硬件出现故障时无法访问数据库。

**新的家居技术解决方案**

- 添加一种新的解决方案，从家居监控传感器持续收集数据。
  - 为用于趋势分析和报告的一些传感器读数建立数据库。
  - 根据用户需求提供可配置的实时警报。
  
- 设计一个关系数据库解决方案来保存屋主的偏好和设置。
  - 系统必须可缩放。
  - 冗余至关重要。
  
- 新的统一网站将在内部开发，并在 Linux 上托管。  此网站将用于查看监视器和更改温度或警报阈值等项的偏好设置。负载可能变化很大，系统必须能够快速缩放。

-	为用户提供一种无需创建另一个用户帐户和密码即可登录系统的方式。

- 实施安全控制并提供每周报告，概述该公司对行业标准最佳做法的遵从情况。

## 任务 

1. 为项目管理软件设计一个解决方案。准备好解释为什么选择设计的每个组件，以及它如何满足解决方案的需求。

2. 为新的家居技术解决方案设计一个体系结构。准备好解释为什么选择设计的每个组件，以及它如何满足解决方案的需求。

如何结合架构良好框架的支柱来生成高质量、稳定和高效的云体系结构?