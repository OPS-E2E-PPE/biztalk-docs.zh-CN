---
title: "监视的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5b180e2-bdd3-4081-9531-d96be7dabe1a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d520026b9037f10f2ed20f52a366b1ff9d3183a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-monitoring"></a>用于监视的最佳做法
本主题提供有关监视你的 Microsoft 最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境和应用程序。  
  
 **创建和实现你的 BizTalk 应用程序和基础结构的监视计划**  
  
-   阅读本指南，以确保更完整的监视解决方案中监视的主题。 要考虑的因素包括：  
  
    -   谁将执行每日、 每周、 每月，和为所需的监视任务？  
  
    -   有人通知的事件、 挂起的消息或其他系统或应用程序故障？  
  
    -   筛选或给定的较低优先级，则是"预期"异常？  
  
    -   是否所有主机监视以确保它们继续运行的实例？  
  
    -   所有自定义服务、 自定义的事件日志和监视的自定义数据库？  
  
    -   SQL Server 计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]监视 SQL 代理作业？  
  
 **如果可能，请安装监视应用程序，如[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]为了自动执行 BizTalk Server 应用程序和基础结构监视**  
  
-   使用 Microsoft System Center Operations Manager 是首选的方法，用于自动监视，因为 BizTalk Server 管理包提供数百个内置规则，用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
     有关详细信息，请参阅下列资源：  
  
    -   [Microsoft BizTalk Server 适用于 System Center Operations Manager 2007 管理包](http://go.microsoft.com/fwlink/?LinkID=190339)(http://go.microsoft.com/fwlink/?LinkID=190339)。  
  
    -   [如何导入 Operations Manager 2007 中的管理包](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)  
  
    -   [如何将 BizTalk Server 数据库标记为自定义监视](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
 **运行 BizTalk Server 最佳做法分析器**  
  
-   BizTalk Server 最佳做法分析器检查[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署，并生成与最佳做法标准相关的问题的列表。 该工具执行配置级别验证从不同的信息源，例如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项收集数据。 数据然后用于评估部署配置。 该工具读取和仅限报告并不会修改任何系统设置，并不是自我调整工具。  
  
     你可以下载 BizTalk Server 最佳做法分析器在[http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)。  
  
 **运行日志的性能分析工具 (PAL)**  
  
-   PAL 是可用作在免费下载[http://go.microsoft.com/fwlink/LinkID=98098](http://go.microsoft.com/fwlink/?LinkID=98098)。 重要的安装信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。  
  
 **运行日志分析器**  
  
-   Log Parser 是一个功能强大、 通用的工具，如事件日志、 注册表、 文件系统和活动 Windows® 操作系统提供对基于文本的数据，例如日志文件、 XML 文件和 CSV 文件，以及密钥的数据源的通用查询访问权限Directory®。 你可能想要使用此工具来查询占用大量的日志记录信息。 你可以下载的 Log Parser 工具在[http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)  
  
 **运行 BizTalk MsgBoxViewer 工具**  
  
 运行[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkId=151930)可从[http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930)。 此工具可分析 BizTalk MessageBox 和其他数据库并生成 HTML 报告包含警告，如果与数据库相关的任何，和其他信息。 你还可以保存以供将来使用的报表。 与 BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。  
  
 如果 BizTalk MsgBoxViewer 工具标识的任何问题，运行[终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)在[http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931)。 此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。 有关如何使用 BizTalk MsgBoxViewer 工具相集成终止符工具的详细信息，请参阅[使用 BizTalk 终止符，若要解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932)。  
  
> [!NOTE]  
>  使用这些工具不支持由 Microsoft 和 Microsoft 则没有有关这些程序的适用性的保证。 使用这些程序完全需要您自担风险。  
  
 **请监视优先级**  
  
-   一致的监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构是至关重要维护一个正常的环境。  
  
-   定期评估并调整监视工具，随着时间的推移和作为你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构更改。