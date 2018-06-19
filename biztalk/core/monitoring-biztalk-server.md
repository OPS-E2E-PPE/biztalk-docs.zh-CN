---
title: 监视的运行状况和性能使用内置的工具 |Microsoft 文档
description: 可用性、 运行状况和性能监视在 BizTalk Server 中和监视 SQL 代理作业
ms.custom: ''
ms.date: 01/14/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96e244dc-b826-4a9f-a4e1-6dabc41eb144
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6652c962d8ef522128dfb4c9febeca55ce42669
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "22265357"
---
# <a name="monitoring-biztalk-server"></a>监视 BizTalk Server
定期监视 BizTalk Server 应用程序和基础结构并解决发现的任何问题，有助于使用户保持对 BizTalk Server 应用程序的访问。 监视的目的在于最大限度地减少未检测到（并因此导致未解决）的异常存在的时间。 此外，还可以使用监视来帮助检测可能导致异常的情形。  
  
 当监视 BizTalk Server 时，您应查找任何意外或异常行为。 监视既可以是手动过程，也可以是自动过程。 您可以使用 BizTalk Server 管理控制台监视 BizTalk Server 基础结构的运行状况。 您可以使用 BizTalk Server 管理控制台监视 BizTalk Server 应用程序的运行状况，执行根源分析以确定任何问题的基本原因。 。 监视 BizTalk Server 时，请谨记以下几点：  
  
-   基础结构的运行状况可能处于正常状态，但应用程序则未必（例如，它们正在接收无效消息，但无法处理这些消息）。  
  
-   基础结构的运行状况可能并不正常，但应用程序可能正在正常运行（例如，如果服务器停机，但向主机分配了足够的服务器来接管负载）。  
  
-   基础结构问题可能表现为应用程序问题（例如，由于服务器停机，导致处理消息的速度不够快）。  
  
 对 BizTalk Server 和应用程序的监视归为以下三个主要类别：  
  
-   可用性监视  
  
-   运行状况监视  
  
-   性能监视  
  
## <a name="availability-monitoring"></a>可用性监视  
 可用性监视回答的问题是“系统或应用程序资源的不可用是否导致 BizTalk Server 应用程序无法以最佳方式运行？” 这些问题几乎毫无例外都是系统级别的问题，如服务和连接的可用性。 例如，如果某个适配器由于停止了企业单一登录服务而失败，这就是一个可用性问题。 如果分配给主机的服务器之一失败且应用程序在处理消息时速度很慢，则您遇到了可用性问题。 同样，如果应用程序停止而无法处理消息，您也遇到了可用性问题。 下表显示了可用性监视工具。  
  
|工具|任务|  
|----------|----------|  
|BizTalk Server 管理控制台|您应查看 BizTalk Server 管理控制台中的“组中心”页，以查看应用程序或其组件（端口/业务流程）是否已停止。|  
|事件查看器|查找适配器连接问题、停止的服务以及其他问题。|  
  
## <a name="health-monitoring"></a>运行状况监视  
 运行状况监视有助于回答问题“某些应用程序或资源的运行状况是否较差？” 例如，是否我的应用程序或其构成项目的任何当前遇到异常条件？ 或者，由于消息负载中的数据无效消息将被挂起。 下表显示了运行状况监视工具。  
  
|工具|任务|  
|----------|----------|  
|BizTalk 运行状况监视器工具 (BHM)|用户监视 BizTalk Server 环境的运行状况 mmc 管理单元检测关键和非关键问题并执行维护任务。  [下载 BizTalk 运行状况监视器](https://www.microsoft.com/download/details.aspx?id=43716)。|  
|BizTalk Server 管理控制台|可以使用 BizTalk Server 管理控制台中的“组中心”页和查询页来确定应用程序运行状况问题并分析问题原因。|  
|事件查看器|检测在处理消息和业务流程的过程中出现的问题。|  
  
## <a name="performance-monitoring"></a>性能监视  
 性能监视回答的问题是“系统执行其工作的效率如何？” 这种监视主要关注物理资源（如数据库和磁盘）上的负载。 例如，如果 CPU 利用率始终保持在 90% 到 100% 且造成消息积压，则这是计算机级别的性能问题。 下表显示了性能监视工具。  
  
|工具|任务|  
|----------|----------|  
|SQL 查询分析器|监视数据库大小和内容以诊断系统问题。|  
|BizTalk Server 管理控制台|“组中心”页显示关键的性能度量，如 BizTalk Server 应用程序中当前活动的、已冻结的、准备运行的、已计划的以及已挂起的服务实例数等。|  
|业务活动监视 (BAM)|您可以指定业务流程中的特定阶段，以便针对其跟踪与业务应用程序相关的关键性能指示器。|  
  
## <a name="biztalk-server-monitoring"></a>BizTalk 服务器监视  
 你可以运行 **监视器 BizTalk Server** SQL 代理作业来标识管理、 消息框中或 DTA 数据库中的所有已知的问题。 在 BizTalk Server 管理控制台中配置 BizTalk 组或从以前的版本升级 BizTalk 时创建该作业。  
  
 监视 BizTalk 服务器作业扫描管理、 消息框中，和 DTA 数据库中的以下问题︰  
  
> [!NOTE]
>  监视 BizTalk 服务器作业仅扫描的问题。 它不能解决找到的问题。  
  
-   没有任何引用的消息  
  
-   而无需引用计数的消息  
  
-   引用计数小于 0 的消息  
  
-   无后台行的消息引用  
  
-   无实例的消息引用  
  
-   不包含实例的实例状态  
  
-   实例不包含相应的实例的订阅  
  
-   孤立的 DTA 服务实例  
  
-   孤立的 DTA 服务实例异常  
  
-   TDDS 未运行任何主机实例上启用全局跟踪选项。  
  
 “监视 BizTalk Server”作业已配置为每周自动运行一次。 因为作业需要大量的计算，所以建议在停机/低流量时安排。  
  
 如果遇到任何问题，作业将会失败；错误字符串包含找到的问题数。 否则，它将成功运行。 您可以在作业历史中查看详细信息。 如果使用管理员权限运行作业，则错误字符串和作业历史还将记录到事件查看器中。  
  
## <a name="troubleshooting"></a>故障排除  
 在发觉 BizTalk Server 应用程序（而非基础结构）的运行状况问题之后，可以使用 BizTalk Server 管理控制台中的“组中心”页和“查询”页来分析此问题。 BizTalk Server 管理控制台提供了全面的配置、部署和疑难解答体验，当您在查明与配置和部署相关的问题之后，可以在管理控制台内修复它们。 通常，大多数应用程序问题是由于消息未按预期到达而导致的（这可能表现为已挂起的服务实例、正在重试端口或尚未重新激活的已冻结实例等）。  
  
 可以使用“组中心”页和“查询”页按应用程序、错误类型、服务类型、主机等对服务实例进行分组（无论它们处于何种状态：正在运行、已挂起、已冻结等），以隔离不同的错误、逐个调查错误并修复它们。 还可以从 BizTalk Server 管理控制台中监视跟踪数据，以调查消息流的历史数据或有关业务流程或规则集执行的历史数据。 此跟踪数据包含有关 BizTalk Server 应用程序的历史数据。  
  
 如果已在 BizTalk 管理控制台中启用跟踪，则可以使用跟踪以通过查询找到消息流和服务。 例如，如果您希望找到某条消息，但您只知道消息类型（架构）、某个属性及其值（如客户名称）等，此功能很有用。  
  
 以下主题讨论如何使用 BizTalk Server 管理控制台的“组中心”页和“查询”页来进行监视和疑难解答。 本节还讨论了跟踪，您可以使用它来帮助您进行疑难解答和根源分析。  
  
## <a name="more-good-stuff"></a>多个很好的内容  
  
-   [使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)  
  
-   [查看跟踪的消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)  
  
-   [跟踪 BizTalk Server 应用程序中的项目之间的依赖关系](../core/tracking-dependencies-between-artifacts-in-a-biztalk-server-application.md)

- [性能计数器](performance-counters.md)