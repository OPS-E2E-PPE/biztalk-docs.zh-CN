---
title: 管理用户和性能工具 |Microsoft Docs
description: 常见的工具来管理任务、 性能和 BizTalk Server 中的跟踪
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 932814f7-2ab3-45cb-8bbc-eaf00fcb24a0
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e345e001d354cf925a68bc33d43f09bb42ad2761
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980494"
---
# <a name="administrative-and-performance-tools"></a>管理用户和性能工具 

## <a name="tools-list"></a>工具列表
可以使用以下工具来管理 BizTalk ServerBizTalk 服务器来管理 BizTalk Server 组来部署 BizTalk Server 应用程序，以与贸易合作伙伴进行交互并监视 BizTalk Server 的状态：  
  
- **BizTalk Server 管理控制台**。 在 BizTalk Server 管理控制台是 BizTalk Server 的主要管理工具。 使用它提供的图形化用户界面，可以执行对 BizTalk 应用程序的所有部署操作。 例如，可以启动导入向导、安装向导和导出向导，添加和删除应用程序项目，以及对应用程序进行其他修改。  
  
   使用 BizTalk Server 管理控制台，可用于查看实时或存档的消息事件或服务实例数据跟踪您的 BizTalk Server 实施的运行状况、 确定瓶颈和监视 BizTalk Server 环境。 您可以查看特定业务流程、管道或消息实例的详细技术信息，并查看进入系统的特定消息的消息流。  
  
   有关使用 BizTalk Server 管理控制台的信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。  
  
- **BTSTask 命令行工具**。 使用 BTSTask 工具可以通过命令行执行许多管理任务。 有关使用 BTSTask 的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。  
  
- **脚本和可编程 Api**。 Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
   WMI 对象模型公开并简化了管理 API。 所有管理 API 均可公开对其管理的每个对象的以下特定形式操作：创建、枚举、修改和删除。 WMI 可对所有 WMI 对象一致地公开此功能。  
  
- **业务活动监视 (BAM)。** BAM 使用 Microsoft Office Excel 工作簿为业务用户提供一种方法，以查看业务流程的实时整体视图。 有关 BAM 的详细信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。  


- [**BizTalk 运行状况监视器**](http://blogs.msdn.com/b/biztalkhealthmonitor/ "BizTalk 运行状况监视器")已通过 BizTalk 支持团队来收集有关 BizTalk 环境，包括表使用情况和已知的问题的信息。 生成带有突出显示潜在问题领域的报告。 请考虑执行此工具并查看输出定期以帮助维护 BizTalk 环境。 这将替换 BizTalk MsbBox 查看器。

- [**BizTalk 终止符工具**](https://www.microsoft.com/download/en/details.aspx?id=2846 "BizTalk 终止符工具")已通过 BizTalk 支持团队来解决常见的数据库完整性问题通常在 BizTalk MsgBox 查看器输出中找到。 常见任务包括删除实例和清除大型表。 有关 BizTalk 终止符工具的详细信息，请转到[此文章](http://blogs.msdn.com/b/biztalkcpr/archive/2011/02/10/using-biztalk-terminator-to-resolve-issues-identified-by-biztalk-msgboxviewer.aspx)在适用于 BizTalk 工程师的一篇博客。

- [**Microsoft BizTalk LoadGen 2007** ](https://www.microsoft.com/download/details.aspx?id=14925)生成消息传输负载运行性能和压力测试，为 Microsoft BizTalk Server 应用程序，并提供要监视的性能的性能计数器运行 BizTalk Server 的基础结构。

- [**BizTalk Server Best Practices Analyzer**](https://www.microsoft.com/downloads/details.aspx?FamilyID=93d432fe-1370-4b6d-aaa8-a0c43c30f5ab "BizTalk Server Best Practices Analyzer")只通过读取和报告执行配置级别验证。 最佳实践分析工具从不同的信息源，如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项收集数据。 最佳实践分析工具使用的数据来评估部署配置。 最佳实践分析工具不会修改任何系统设置，并不是一个自我调整工具。

- [**性能分析日志 (PAL) 的**](https://github.com/clinthuffman/PAL)是一个功能强大的工具，在性能监视器计数器日志 （任何已知格式） 中读取并使用复杂，但已知阈值 （提供） 进行分析。 该工具生成基于 HTML 报表，这将以图形方式图表中显示重要的性能计数器并超出阈值时引发警报。

- [**有关 Windows DebugView** ](https://docs.microsoft.com/sysinternals/downloads/debugview)是可让你监视可通过 TCP/IP 访问的网络上的任何计算机或在本地系统上的调试结果的应用程序。 能够显示内核模式和 Win32 调试输出，因此您无需调试器来捕获调试输出生成你的应用程序或设备驱动程序，也需要修改你的应用程序或驱动程序使用非标准调试输出的 Api。

- [**Log Parser 2.2** ](https://www.microsoft.com/download/details.aspx?id=24659)是一个功能全面的强大工具，如事件日志中，在 Windows 操作系统上提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及关键的数据源的通用查询访问注册表、 文件系统和 Active Directory。

- [**处理资源管理器**](https://docs.microsoft.com/sysinternals/downloads/process-explorer)是可用于跟踪 DLL 版本问题或句柄泄漏，并有助于深入的方式 Windows 和应用程序的工作。

- [**TCP 跟踪**](http://www.pocketsoap.com/tcptrace/ "TCP 跟踪")用于监视客户端和服务器之间的基于文本网络流量。 使用如 SOAP、 HTTP、 POP3 等的适配器，查看旅行通过网络传输消息时很有用。

- [**DTCPing** ](https://www.microsoft.com/download/details.aspx?id=2868)旨在帮助进行故障排除 Microsoft DTC 防火墙问题，通常会在多服务器 BizTalk 部署中看到。

  
## <a name="see-also"></a>请参阅  
 [应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)