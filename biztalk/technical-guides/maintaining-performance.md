---
title: 维护性能 |Microsoft Docs
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
ms.openlocfilehash: 44beb0700d1c5de5a606708e5a6dbc343db128b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396264"
---
# <a name="maintaining-performance"></a>维护性能
本部分提供了旨在帮助您解决在日常维护检查过程发现性能问题的信息。 此外可以使用的工具和技术此处所述主动，关键问题之前找出潜在问题。  

 通常需要作为依据来评估当前的系统性能的标准建立性能基线。  

 除了此部分中的主题，本文档中的其他主题解决性能问题。 以下相关各节列出了这些主题。  

## <a name="in-this-section"></a>本节内容  

-   [维护性能的最佳做法](../technical-guides/best-practices-for-maintaining-performance.md)  

-   [配置批处理以优化适配器性能](../technical-guides/configuring-batching-to-improve-adapter-performance.md)  

-   [如何调整高速缓存刷新的间隔配置](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)  

-   [如何禁用跟踪](../technical-guides/how-to-disable-tracking.md)  

-   [故障排除性能 Issues3](../technical-guides/troubleshooting-performance-issues3.md)  

## <a name="related-sections"></a>相关章节  

- 详细了解性能问题一般情况下，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南，网址[ http://go.microsoft.com/fwlink/?LinkID=150492 ](http://go.microsoft.com/fwlink/?LinkID=150492)。  

- 有关分析针对基线和阈值的每周性能监视器日志的信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)，"查找并消除瓶颈"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南[ http://go.microsoft.com/fwlink/?LinkId=154675 ](http://go.microsoft.com/fwlink/?LinkId=154675)，和[故障排除性能 Issues3](../technical-guides/troubleshooting-performance-issues3.md)。  

- 确保系统不出现频繁地自动增长的有关信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[定义数据库的自动增长设置](../technical-guides/defining-auto-growth-settings-for-databases.md)，"跟踪数据库大小调整指南"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154677 ](http://go.microsoft.com/fwlink/?LinkId=154677)，并在的"标识数据库层的瓶颈"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154678 ](http://go.microsoft.com/fwlink/?LinkId=154678)。  

- 有关维护 SQL Server 信息[执行 SQL Server 维护过程](~/technical-guides/checklist-configuring-sql-server.md)。  

- 有关在高负载，以检查长时间响应时间和高资源使用率期间运行 SQL Server Profiler 的信息，请参阅"使用 SQL Server Profiler"SQL Server 帮助中在[ http://go.microsoft.com/fwlink/?LinkID=106720 ](http://go.microsoft.com/fwlink/?LinkID=106720)。  

- 有关确保用于所有适配器的消息批处理适用于资源消耗或延迟的信息，请参阅[提高适配器性能配置批处理](../technical-guides/configuring-batching-to-improve-adapter-performance.md)。  

- 有关增加 BizTalk Server 缓存刷新间隔的信息，请参阅[如何调整配置缓存刷新间隔](../technical-guides/how-to-adjust-the-configuration-cache-refresh-interval.md)。  

- 入站和出站主机阻止有关的信息，请参阅"什么是主机限制？" 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154694 ](http://go.microsoft.com/fwlink/?LinkId=154694)。 有关触发器、 操作和缓解策略的入站和出站阻止功能的信息，请参阅"限制条件触发器、 操作和缓解策略"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154695 ](http://go.microsoft.com/fwlink/?LinkId=154695)。  

- 将直通发送管道而不是默认 XML 发送管道，请参阅"管理发送端口使用 BizTalk 浏览器"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkID=154696 ](http://go.microsoft.com/fwlink/?LinkID=154696)。  

- 有关调整跟踪数据库大小的信息，请参阅"跟踪数据库大小调整指南"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154677 ](http://go.microsoft.com/fwlink/?LinkId=154677)。  

- 有关大小调整 MessageBox 和 BizTalkDTADb、 BAMPrimaryImport 数据库的信息，请参阅"中的数据库层确定瓶颈"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助[ http://go.microsoft.com/fwlink/?LinkId=154678 ](http://go.microsoft.com/fwlink/?LinkId=154678)。  

- 有关如何避免争用 MessageBox 数据库中的信息，请参阅[如何避免磁盘争用](http://go.microsoft.com/fwlink/?LinkId=158809)([http://go.microsoft.com/fwlink/?LinkId=158809](http://go.microsoft.com/fwlink/?LinkId=158809)) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南。
