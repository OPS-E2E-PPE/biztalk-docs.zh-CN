---
title: 监视的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5b180e2-bdd3-4081-9531-d96be7dabe1a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bfb2b5575fe46c1104ddc6b852695fb777275ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981654"
---
# <a name="best-practices-for-monitoring"></a>监视的最佳做法
本主题提供用于监视你的 Microsoft BizTalk Server 环境和应用程序的最佳实践。  
  
 **创建，然后实现您的 BizTalk 应用程序和基础结构的监视计划**  
  
- 阅读本指南，以确保更完整的监视解决方案中的监视主题。 要考虑的因素包括：  
  
  -   谁将执行每日、 每周、 每月和作为所需的监视任务？  
  
  -   有人通知的事件、 挂起的消息或其他系统或应用程序故障？  
  
  -   已筛选或给定的较低优先级是否"预期"的异常？  
  
  -   是否所有的主机实例监视，以确保它们继续运行？  
  
  -   所有自定义服务、 自定义的事件日志和监视的自定义数据库？  
  
  -   是 SQL Server 计算机和 BizTalk Server SQL 代理作业监视？  
  
  **如果可能，请安装监视应用程序，如[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]才能自动执行 BizTalk Server 应用程序和基础结构监视**  
  
- 使用 Microsoft System Center Operations Manager 是自动监视，因为 BizTalk Server 管理包为 BizTalk Server 提供数百个内置的规则的首选的方法。  
  
   有关详细信息，请参阅下列资源：  
  
  -   [System Center Operations manager 2007 的 Microsoft BizTalk Server 管理包](http://go.microsoft.com/fwlink/?LinkID=190339)(http://go.microsoft.com/fwlink/?LinkID=190339)。  
  
  -   [如何导入管理包在 Operations Manager 2007 中的](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)  
  
  -   [如何为自定义监视标记 BizTalk Server 数据库](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
  **运行 BizTalk Server 最佳实践分析工具**  
  
- BizTalk Server Best Practices Analyzer 会检查 BizTalk Server 部署，并生成与最佳做法标准相关的问题的列表。 该工具通过不同的信息源，如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项中的数据收集执行配置级别验证。 数据然后用于评估部署配置。 该工具读取和仅报告并不会修改任何系统设置，并不是一个自我调整工具。  
  
   您可以下载 BizTalk Server Best Practices Analyzer 处[ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)。  
  
  **运行日志的性能分析工具 (PAL)**  
  
- PAL 是可作为免费下载[ https://github.com/clinthuffman/PAL ](https://github.com/clinthuffman/PAL)。 重要的安装信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。  
  
  **运行日志分析程序**  
  
- Log Parser 是 Windows® 操作系统 （如事件日志、 注册表、 文件系统和活动提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及关键的数据源的通用查询访问的功能全面的强大工具Directory®。 您可能想要使用此工具来查询大量的日志记录信息。 您可以下载在 Log Parser 工具 [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)  
  
  **运行 BizTalk MsgBoxViewer 工具**  
  
  运行[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkId=151930)从可用[ http://go.microsoft.com/fwlink/?LinkId=151930 ](http://go.microsoft.com/fwlink/?LinkId=151930)。 此工具分析 BizTalk MessageBox 和其他数据库，并生成 HTML 报表包含警告，如果与数据库相关的任何，和其他信息。 此外可以保存以供将来使用的报表。 BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。  
  
  如果 BizTalk MsgBoxViewer 工具确定任何问题，运行[终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)网址[ http://go.microsoft.com/fwlink/?LinkId=151931 ](http://go.microsoft.com/fwlink/?LinkId=151931)。 此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。 有关如何使用 BizTalk MsgBoxViewer 工具相集成的终结器工具的详细信息，请参阅[使用 BizTalk 终止符，以解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932)。  
  
> [!NOTE]  
>  使用这些工具不受 Microsoft，因此 Microsoft 不保证这些程序的适用性。 使用这些程序完全需要您自担风险。  
  
 **请监视优先级**  
  
-   BizTalk Server 应用程序和基础结构的持续不断的监视是必要的维护正常运行的环境。  
  
-   定期评估并调整监视工具，随着时间的推移和作为 BizTalk Server 应用程序和基础结构更改。