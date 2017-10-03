---
title: "管理和性能工具 |Microsoft 文档"
description: "常用工具来管理任务、 性能和在 BizTalk Server 中的跟踪"
ms.custom: 
ms.date: 09/04/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.ops.admintools
ms.assetid: 932814f7-2ab3-45cb-8bbc-eaf00fcb24a0
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc7420fa6bd59e3653f510e96d41015d266bcebc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="administrative-and-performance-tools"></a>管理和性能工具 

## <a name="tools-list"></a>工具列表
使用以下工具可以管理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、管理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组、部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序、与贸易合作伙伴进行交互，还可以监视 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的状态：  
  
-   **BizTalk Server 管理控制台**。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的主要管理工具。 使用它提供的图形化用户界面，可以执行对 BizTalk 应用程序的所有部署操作。 例如，可以启动导入向导、安装向导和导出向导，添加和删除应用程序项目，以及对应用程序进行其他修改。  
  
     使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，您可以通过查看实时或存档的消息事件或服务实例数据来跟踪 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 实现的健康状况，标识瓶颈和监视 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境。 您可以查看特定业务流程、管道或消息实例的详细技术信息，并查看进入系统的特定消息的消息流。  
  
     有关使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。  
  
-   **BTSTask 命令行工具**。 使用 BTSTask 工具可以通过命令行执行许多管理任务。 有关使用 BTSTask 的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。  
  
-   **脚本和可编程性 Api**。 Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
     WMI 对象模型公开并简化了管理 API。 所有管理 API 均可公开对其管理的每个对象的以下特定形式操作：创建、枚举、修改和删除。 WMI 可对所有 WMI 对象一致地公开此功能。  
  
-   **业务活动监视 (BAM)。** BAM 使用 Microsoft [!INCLUDE[btsOfficeNoVersion](../includes/btsofficenoversion-md.md)] [!INCLUDE[btsExcel](../includes/btsexcel-md.md)]工作簿业务用户提供一种方法，以查看实时业务流程的整体视图。 BAM 有关的详细信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。  


-   [**BizTalk 运行状况监视器**](http://blogs.msdn.com/b/biztalkhealthmonitor/ "BizTalk 运行状况监视器")由 BizTalk 支持团队，以收集有关 BizTalk 环境，包括使用表和已知的问题的信息。 报表将生成带有突出显示潜在问题区域。 请考虑执行此工具并查看定期以帮助保持你的 BizTalk 环境输出。 这将替换 BizTalk MsbBox 查看器。

-   [**BizTalk 终止符工具**](https://www.microsoft.com/download/en/details.aspx?id=2846 "BizTalk 终止符工具")由 BizTalk 支持团队，以解决常见的数据库完整性问题通常在 BizTalk MsgBox 查看器输出中找到。 常见任务包括删除实例和清除大型表。 有关 BizTalk 终止符工具的详细信息，请转到[此文章](http://blogs.msdn.com/b/biztalkcpr/archive/2011/02/10/using-biztalk-terminator-to-resolve-issues-identified-by-biztalk-msgboxviewer.aspx)BizTalk 工程师一个博客中。

-   [**Microsoft BizTalk LoadGen 2007**](https://www.microsoft.com/downloads/details.aspx?FamilyID=c8af583f-7044-48db-b7b9-969072df1689&displaylang=en "Microsoft BizTalk LoadGen 2007")生成消息传输负载，以运行性能和压力测试，为 Microsoft BizTalk Server 应用程序，并提供性能计数器来监视运行 BizTalk Server 基础结构的性能。

-   [**BizTalk Server 最佳做法分析器**](https://www.microsoft.com/downloads/details.aspx?FamilyID=93d432fe-1370-4b6d-aaa8-a0c43c30f5ab "BizTalk Server 最佳做法分析器")执行读取和仅报告配置级别验证。 最佳实践分析工具收集数据，从不同的信息源，例如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项。 最佳做法分析器使用数据来评估部署配置。 最佳做法分析器不会修改任何系统设置，并不是自我调整工具。

-   [**性能分析的日志 (PAL)**](http://www.codeplex.com/PAL "性能分析的日志 (PAL)")复杂，但已知是一种功能强大的工具，性能监视器计数器日志 （任何已知格式） 中读取和分析使用（提供） 的阈值。 该工具生成一个基于 HTML 报告，该图表重要的性能计数器以图形和超出阈值时，会引发警报报告。

-   [**DebugView for Windows**](https://technet.microsoft.com/en-us/sysinternals/bb896647.aspx "DebugView for Windows")是应用程序，你可以监视您的本地系统上的调试输出或可以访问通过 TCP/IP 网络上的任何计算机。 它能够显示内核模式和 Win32 调试输出，因此您无需调试程序，以捕获你的应用程序或设备驱动程序生成、 调试输出也不需要修改您的应用程序或驱动程序以使用非标准调试输出 Api。

-   [**日志分析器 2.2**](https://www.microsoft.com/downloads/details.aspx?familyid=890CD06B-ABF8-4C25-91B2-F8D975CF8C07&displaylang=en "日志分析器 2.2")是一个功能强大、 通用的工具，在 Windows 上提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及密钥的数据源的通用查询访问权限如事件日志、 注册表、 文件系统和 Active Directory 的操作系统。

-   [**处理资源管理器**](https://technet.microsoft.com/en-us/sysinternals/bb896653.aspx "进程资源管理器")可用于跟踪 DLL 版本问题或句柄泄漏，并有助于深入的方式 Windows 和应用程序工作。

-   [**TCP 跟踪**](http://www.pocketsoap.com/tcptrace/ "TCP 跟踪")用于监视客户端和服务器之间的基于文本网络流量。 使用如 SOAP、 HTTP、 POP3 等的适配器以查看通过网络旅行消息时很有用。

-   [**DTCPing**](https://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=5e325025-4dcd-4658-a549-1d549ac17644 "DTCPing")旨在帮助 Microsoft DTC 防火墙问题，您通常可以看到在多服务器部署中 BizTalk 进行疑难解答。

  
## <a name="see-also"></a>另请参阅  
 [应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)