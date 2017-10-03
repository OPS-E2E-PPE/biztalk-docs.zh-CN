---
title: "监视 BizTalk Server 环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baae51cf-0284-429b-8335-bc1ac3e63f4c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57abd599c10ead5084eae59c9f7dbe1746be346a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-biztalk-server-environment"></a>监视 BizTalk Server 环境
你可以监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基础结构和应用程序而进行的手动或自动过程中或两个方法下, 表中所示使用的工具的组合。  
  
|手动或自动监视|工具|  
|------------------------------------|-----------|  
|自动监视|Microsoft System Center Operations Manager (Operations Manager)|  
|手动监视|-**组中心数据库**页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台<br />日志 (PAL) 工具的性能分析<br />事件查看器|  
  
 是否实现监视应用程序时，应使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台监视的运行状况你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序并执行根本原因分析，以找出任何问题的根本原因。  
  
 监视时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请记住以下几点：  
  
-   基础结构的运行状况可能处于正常状态，但应用程序则未必（例如，它们正在接收无效消息，但无法处理这些消息）。  
  
-   基础结构的运行状况可能并不正常，但应用程序可能正在正常运行（例如，如果服务器停机，但向主机分配了足够的服务器来接管负载）。  
  
-   基础结构问题可能表现为应用程序问题（例如，由于服务器停机，导致处理消息的速度不够快）。  
  
## <a name="monitoring-types"></a>监视类型  
 监视你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和应用程序操作划分为四种主要类别：  
  
-   可用性监视  
  
-   运行状况监视  
  
-   性能监视  
  
-   阈值监视  
  
### <a name="availability-monitoring"></a>可用性监视  
 可用性监视解答问题"是不可用的系统或应用程序资源阻止你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以最佳方式运行的应用程序？" 这些问题几乎毫无例外都是系统级别的问题，如服务和连接的可用性。 例如，如果某个适配器由于停止了企业单一登录服务而失败，这就是一个可用性问题。 如果分配给主机的服务器之一失败且应用程序在处理消息时速度很慢，则您遇到了可用性问题。 同样，如果应用程序停止而无法处理消息，您也遇到了可用性问题。 下表列出的可用性监视工具。  
  
|工具|任务|  
|----------|----------|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台|检查**组中心数据库**页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台以查看应用程序或其组件 （端口业务流程） 都已停止。|  
|Operations Manager 2007|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包和 Operations Manager 操作控制台显示警报，如果关键的低级别服务，例如适配器都不可用。 若要有效地监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你必须监视非[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你的应用程序依赖资源，如数据库和服务器。 此外，你还必须安装并使用 SQL Server、 Internet 信息服务和 Windows 基本操作系统管理包。 Operations Manager 合并从事件日志、 WMI 和其他事件提供程序感兴趣的事件。 有关安装所有相关的管理包的详细信息，请参阅[清单： Operations Manager 2007 监视 BizTalk Server](../technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md)。|  
|事件查看器|查找适配器连接问题、停止的服务以及其他问题。|  
  
### <a name="health-monitoring"></a>运行状况监视  
 运行状况监视有助于回答问题“某些应用程序或资源的运行状况是否较差？” 例如，是否我的应用程序或其构成项目的任何当前遇到异常条件？ 或者，由于消息负载中的数据无效消息将被挂起。 下表显示了运行状况监视工具。  
  
|工具|任务|  
|----------|----------|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台|你使用**组中心数据库**页和查询页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，以确定应用程序运行状况问题和分析其原因。|  
|Operations Manager|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包是你第一行的预防措施，通知你，你已挂起消息和/或服务实例中的你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。 后从 Operations Manager 接收通知，则可以转换为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，以解决该问题。|  
|事件查看器|检测在处理消息和业务流程的过程中出现的问题。|  
  
### <a name="performance-monitoring"></a>性能监视  
 性能监视回答的问题是“系统执行其工作的效率如何？” 这种监视主要关注物理资源（如数据库和磁盘）上的负载。 例如，如果 CPU 利用率始终保持在 90% 到 100% 且造成消息积压，则这是计算机级别的性能问题。 下表显示了性能监视工具。  
  
|工具|任务|  
|----------|----------|  
|SQL 查询分析器|监视数据库大小和内容以诊断系统问题。|  
|Operations Manager|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将配置管理包和 Operations Manager 操作控制台为显示警报，如果关键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能计数器，如消息框 Q 大小或主机 Q 大小超过定义的阈值。 若要监视的非性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你的应用程序依赖的、 的资源如数据库和服务器，你必须还会安装和使用 SQL Server、 Internet 信息服务和 Windows 基本操作系统管理包。 有关安装所有相关的管理包的详细信息，请参阅[清单： Operations Manager 2007 监视 BizTalk Server](../technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md)。<br /><br /> 你还可以使用性能分析的日志 (PAL) 工具捕获从测试中的阈值规则中使用的吞吐量的阈值[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包。 有关 PAL 工具的详细信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台|**组中心数据库**页显示的服务实例数等的关键性能度量值当前处于活动状态，冻结，准备好要运行，请计划、 挂起，等中你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。|  
|业务活动监视 (BAM)|您可以指定业务流程中的特定阶段，以便针对其跟踪与业务应用程序相关的关键性能指示器。 使用 BAM，你可以监视业务指标，以及 IT 度量值 （例如，SLA 的和执行时间）。|  
  
### <a name="threshold-monitoring"></a>阈值监视  
 自定义的阈值规则是在成熟的操作环境中的基本元素。 你可以在 Operations Manager 中创建很这些阈值规则。 这些阈值规则通常基于 BizTalk 应用程序的要求。 性能分析的日志 (PAL) 工具可以简化确定你的环境这些阈值的正确值的过程。 PAL 工具附带了可以用作适用于 Microsoft System Center Operations Manager 的数据的核心某些基本阈值值。 在 Operations Manager 中实现这些阈值规则允许自动监视。 此外，管理员可以设置通知规则，并可以执行基于阈值规则 （如运行脚本，调用.NET 代码、 发送电子邮件，等等） 的触发的操作。 下表显示阈值监视工具。  
  
|工具|任务|  
|----------|----------|  
|性能日志分析 (PAL) 工具|PAL 工具会自动报告性能计数器时超出阈值。 阈值动态更改以适合于服务器环境。 例如，阈值更改的内核内存池基于用户提供 32 位/64 位体系结构，物理内存量和 /3GB 开关的答案。 在可免费下载 PAL 工具[http://www.codeplex.com/PAL](http://www.codeplex.com/PAL)。|  
|Operations Manager|可以配置 BizTalk Server 管理包和 Operation Manager 操作控制台为显示警报，如果关键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计数器超过定义的阈值。|  
  
## <a name="troubleshooting"></a>故障排除  
 一旦您发现的运行状况问题你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，你可以使用**组中心数据库**页和**查询**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来分析问题。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台提供的集成的配置、 部署和故障排除体验，并可以修复配置和部署后具有精确定位它们相关的管理控制台内的问题。 通常，大多数应用程序问题是由于消息未按预期到达而导致的（这可能表现为已挂起的服务实例、正在重试端口或尚未重新激活的已冻结实例等）。  
  
 你可以使用**组中心数据库**页和**查询**页进行分组服务实例 (它们处于任何状态： 运行、 挂起、 已冻结等) 应用程序，错误类型，由服务类型、 主机，等等。，若要隔离不同的错误，调查逐个，并修复它们。