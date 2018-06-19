---
title: 保持性能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7e63ed-4e28-45b1-ab00-be9f9488a2e6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da10987a6532987ff7a2ed925e717a0a713cac6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298141"
---
# <a name="maintaining-performance"></a>保持性能
本部分提供旨在帮助您解决在日常维护检查过程中发现性能问题的信息。 你还可以使用的工具和此处所述主动，能够趋于严重问题之前找出潜在问题的方法。  
  
 通常需要作为一种标准要评估当前的系统性能依据其建立性能基线。  
  
 除了此部分中的主题，本文档中的其他主题解决性能问题。 下面的相关部分中会列出这些主题。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [用于维护性能的最佳方案](../technical-guides/best-practices-for-maintaining-performance.md)  
  
-   [配置批处理，以便提高适配器性能](../technical-guides/configuring-batching-to-improve-adapter-performance.md)  
  
-   [如何调整配置缓存刷新间隔](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)  
  
-   [如何禁用跟踪](../technical-guides/how-to-disable-tracking.md)  
  
-   [故障排除性能 Issues3](../technical-guides/troubleshooting-performance-issues3.md)  
  
## <a name="related-sections"></a>相关章节  
  
-   有关详细信息有关性能问题一般情况下，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南，网址[http://go.microsoft.com/fwlink/?LinkID=150492](http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
-   有关分析针对基线和阈值的每周性能监视器日志的信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)，"查找并消除瓶颈"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南[http://go.microsoft.com/fwlink/?LinkId=154675](http://go.microsoft.com/fwlink/?LinkId=154675)，和[故障排除性能 Issues3](../technical-guides/troubleshooting-performance-issues3.md)。  
  
-   有关确保系统不会遇到频繁地自动增长增量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[定义数据库的自动增长设置](../technical-guides/defining-auto-growth-settings-for-databases.md)，"跟踪数据库大小调整指南"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677)，并在的"标识数据库层中的瓶颈"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678)。  
  
-   有关维护 SQL Server 信息[执行 SQL Server 维护过程](~/technical-guides/checklist-configuring-sql-server.md)。  
  
-   有关在高负载长的响应时间和较高资源使用率检查过程中运行 SQL Server 事件探查器的信息，请参阅"使用 SQL Server 事件探查器"SQL Server 帮助中在[http://go.microsoft.com/fwlink/?LinkID=106720](http://go.microsoft.com/fwlink/?LinkID=106720)。  
  
-   有关确保消息批处理的所有适配器是否适用于资源消耗或延迟的信息，请参阅[配置批处理提高适配器性能](../technical-guides/configuring-batching-to-improve-adapter-performance.md)。  
  
-   有关增加 BizTalk Server 缓存刷新间隔的信息，请参阅[如何调整配置缓存刷新间隔](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)。  
  
-   有关限制的入站和出站主机的信息，请参阅"什么是主机限制"？ 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkId=154694](http://go.microsoft.com/fwlink/?LinkId=154694)。 有关触发器、 操作和缓解的入站和出站带宽限制的策略信息，请参阅"限制条件触发器、 操作和缓解策略"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkId = 154695](http://go.microsoft.com/fwlink/?LinkId=154695)。  
  
-   将传递发送管道而不是默认 XML 发送管道，请参阅"管理发送端口使用 BizTalk 资源管理器"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkID=154696](http://go.microsoft.com/fwlink/?LinkID=154696)。  
  
-   有关大小调整跟踪数据库的信息，请参阅"跟踪数据库大小调整指南"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkId=154677](http://go.microsoft.com/fwlink/?LinkId=154677)。  
  
-   有关大小调整的 MessageBox，BizTalkDTADb、 BAMPrimaryImport 数据库有关的信息，请参阅"中的数据库层识别瓶颈"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在帮助[http://go.microsoft.com/fwlink/?LinkId=154678](http://go.microsoft.com/fwlink/?LinkId=154678)。  
  
-   有关如何避免争用 MessageBox 数据库中的信息，请参阅[如何避免磁盘争用](http://go.microsoft.com/fwlink/?LinkId=158809)([http://go.microsoft.com/fwlink/?LinkId=158809](http://go.microsoft.com/fwlink/?LinkId=158809)) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南。