---
title: 监视运行状况和性能使用内置工具 |Microsoft Docs
description: 可用性、 运行状况和性能监视中 BizTalk Server 和监视 SQL 代理作业
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
ms.openlocfilehash: c1fe69e9d1b63516a51230335aaf109e2de35f1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394391"
---
# <a name="monitoring-biztalk-server"></a>监视 BizTalk Server
监视 BizTalk Server 应用程序和定期的基础结构和解决您发现任何问题有助于使 BizTalk Server 应用程序保持在用户访问的。 监视的目的是时间的最小化的异常存在未检测到，因此，未解决量。 此外，您可以使用监视来帮助检测可能会导致异常的情况。  
  
 当监视 BizTalk Server，您应查找任何意外或异常行为。 监视可以手动或自动过程。 你可以监视使用 BizTalk Server 基础结构使用 BizTalk Server 管理控制台的运行状况。 可以使用 BizTalk Server 管理控制台监视 BizTalk Server 应用程序的运行状况并执行根本原因分析，以确定任何问题的根本原因。 . 当监视 BizTalk Server，请记住以下几点：  
  
- 你的基础结构可能处于正常状态，但可能不是您的应用程序 （例如，它们正在接收无效消息和无法处理它们）。  
  
- 你的基础结构可能并不正常，但您的应用程序可能正在正常运行 （例如，如果服务器已关闭，但有足够的服务器分配给主机来接管负载）。  
  
- 基础结构问题可能表现为应用程序问题 （例如，不处理消息速度不够快因为服务器已关闭）。  
  
  监视 BizTalk Server 和应用程序划分为三个主要类别：  
  
- 可用性监视  
  
- 运行状况监视  
  
- 性能监视  
  
## <a name="availability-monitoring"></a>可用性监视  
 可用性监视回答的问题"是阻止您以最佳方式运行的 BizTalk Server 应用程序的系统或应用程序资源不可用导致？" 这些问题是几乎专用系统级别，如服务和连接的可用性。 例如，如果适配器失败，因为企业单一登录服务已停止，这是一个可用性问题。 如果其中一个分配给主机的服务器出现故障，并且你的应用程序落后在处理消息，您遇到了可用性问题。 同样，如果应用程序已停止，且无法处理消息，则您遇到了可用性问题。 下表显示了监视工具的可用性。  
  
|Tool|任务|  
|----------|----------|  
|BizTalk Server 管理控制台|您应查看 BizTalk Server 管理控制台以查看已停止应用程序或其组件 （端口/业务流程） 中的组中心页。|  
|事件查看器|查找适配器连接问题、 已停止的服务，等等。|  
  
## <a name="health-monitoring"></a>运行状况监视  
 运行状况监视有助于回答问题，"在我的应用程序或资源的任何错误运行状况中？" 例如，是我的应用程序或其构成项目的任何当前遇到异常条件？ 或者，由于消息负载中的数据无效而挂起的消息？ 下表显示了运行状况监视工具。  
  
|Tool|任务|  
|----------|----------|  
|BizTalk 运行状况监视器 (BHM) 工具|用户可以监视 BizTalk Server 环境的运行状况 mmc 管理单元检测关键和非关键问题，并执行维护任务。  [下载 BizTalk 运行状况监视器](https://www.microsoft.com/download/details.aspx?id=43716)。|  
|BizTalk Server 管理控制台|您将使用的组中心页和查询页在 BizTalk Server 管理控制台中，识别应用程序运行状况问题和分析问题原因。|  
|事件查看器|检测到的消息和业务流程处理过程中出现的问题。|  
  
## <a name="performance-monitoring"></a>性能监视  
 性能监视回答的问题，"如何有效地为系统执行其工作的？" 这种监视主要关注物理资源上的负载，如数据库和磁盘。 例如，如果 CPU 使用率一致地为 90 到 100%且造成消息积压，这是在计算机级别的性能问题。 下表显示了性能监视工具。  
  
|Tool|任务|  
|----------|----------|  
|SQL 查询分析器|监视数据库大小和内容，以诊断系统问题。|  
|BizTalk Server 管理控制台|组中心页显示关键性能指标，如服务实例数，当前处于活动状态、 已冻结，您可以随时运行、 计划、 挂起、 等。 在 BizTalk Server 应用程序中。|  
|业务活动监视 (BAM)|你想要跟踪与业务应用程序无关的关键性能指标在业务流程中，可以指定特定阶段。|  
  
## <a name="biztalk-server-monitoring"></a>BizTalk 服务器监视  
 你可以运行**监视 BizTalk Server** SQL 代理作业，以标识管理、 消息框中或 DTA 数据库中的任何已知的问题。 在 BizTalk Server 管理控制台中配置 BizTalk 组或从早期版本升级 BizTalk 时创建作业。  
  
 监视 BizTalk Server 作业扫描管理、 消息框和 DTA 数据库中的以下问题：  
  
> [!NOTE]
>  监视 BizTalk Server 作业仅扫描问题。 它不能解决发现的问题。  
  
- 没有任何引用的消息  
  
- 没有引用计数的消息  
  
- 具有引用计数小于 0 的消息  
  
- 无后台行的消息引用  
  
- 没有实例的消息引用  
  
- 没有实例的实例状态  
  
- 没有相应的实例的实例订阅  
  
- 孤立的 DTA 服务实例  
  
- 孤立的 DTA 服务实例异常  
  
- TDDS 未运行任何主机实例上启用全局跟踪选项。  
  
  监视 BizTalk Server 作业配置和自动运行一次在一周内。 由于是计算密集型作业，我们建议您计划在停机/低流量期间。  
  
  作业失败时如果遇到任何问题;错误字符串包含找到的问题数。 否则，它将成功运行。 您可以看到作业历史记录中的详细信息。 如果使用管理员特权运行该作业，错误字符串将会记录到事件查看器还 （以及作业历史记录）。  
  
## <a name="troubleshooting"></a>疑难解答  
 注意与 BizTalk Server 应用程序 （而不是基础结构） 的运行状况问题后，你可以使用组中心页和查询页在 BizTalk Server 管理控制台来分析此问题。 在 BizTalk Server 管理控制台提供了集成的配置、 部署和疑难解答体验，并可以修复配置和部署后当您在查明它们相关的管理控制台中的问题。 通常情况下，大多数应用程序问题由于消息未获得按预期方式 (这可能表现为挂起的服务实例，或重试端口或尚未重新激活的已冻结的实例，等等。)  
  
 可以使用组中心页和查询页服务实例进行分组 (它们处于任何状态： 运行、 挂起、 已冻结，等等) 的应用程序，错误的类型、 服务类型、 主机等，来隔离不同错误、 逐个进行，调查和修复它们。 你还可以监视 BizTalk Server 管理控制台中，以调查消息流的历史记录中的跟踪数据或业务流程或规则的执行历史记录设置。 此跟踪数据包含有关 BizTalk Server 应用程序的历史数据。  
  
 如果已启用跟踪 BizTalk 管理控制台中的，可以使用跟踪来查找消息流和服务实例使用的查询。 如果想要查找的消息并知道，例如，消息类型 （架构）、 一个属性及其值 （例如，客户名称）、 等，这很有用。  
  
 以下主题讨论如何监视和使用 BizTalk Server 管理控制台中，组中心页上，进行故障排除和查询页。 本部分还讨论了跟踪，可以使用疑难解答和根本原因分析提供帮助。  
  
## <a name="more-good-stuff"></a>更多有用资料  
  
-   [使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)  
  
-   [查看跟踪的消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)  
  
-   [跟踪 BizTalk Server 应用程序中的项目之间的依赖关系](../core/tracking-dependencies-between-artifacts-in-a-biztalk-server-application.md)

- [性能计数器](performance-counters.md)