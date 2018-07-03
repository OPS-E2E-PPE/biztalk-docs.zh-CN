---
title: 管理 BAM 事件总线服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, migrating data
- Primary Import database [BAM], migrating data
- migrating, data [BAM]
- managing [BAM], Event Bus Service
- Event Bus Service [BAM], managing
- Tracking Data Decode Service (TDDS)
ms.assetid: 556e7fe2-4a7d-46f6-8e55-f41be4e666dc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f84b05dfe668e9777fd0d4e3ef5157bf90c59fe0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996030"
---
# <a name="managing-the-bam-event-bus-service"></a>管理 BAM 事件总线服务
“BAM 事件总线服务”也称为“跟踪数据解码服务 (TDDS)”，该服务处理源数据库中存储的跟踪数据（数据流），并将这些数据以日后可轻松查询的方式保存。  
  
 BAM 事件总线服务将商业智能数据移动到 BAM 主导入数据库，而将 BizTalk 运行状况监视数据移动到 DTA 数据库。 BAM 事件总线服务作为 BizTalk 服务中的子服务运行。  
  
 通过在执行期间，收集事件数据并将临时数据存储于应用程序状态与同一数据库中监视的活动事务的应用程序，如 Microsoft BizTalk® Server — 例如，MessageBox 数据库。  
  
> [!NOTE]
>  避免创建承载在同一计算机上的跟踪不同 BizTalk 组的多个应用程序实例。 如果同一台计算机中存在多个跟踪不同 BizTalk 组的实例，您将无法在 BizTalk 管理控制台或事件日志中区分哪个事件属于哪个 BizTalk 组，因为所有 BizTalk 组都显示为相同的名称。  
  
 BAM 事件总线服务读取并解码事件数据，然后将其存储到 Microsoft SQL Server™ 数据库中，在该数据库中，您可以轻松查询数据。  
  
 BAM 事件总线服务提供以下优势：  
  
- 事件数据始终与该应用程序的状态相匹配，并且它永远不会公开未提交的进度。  
  
- 上运行的应用程序的性能影响很小，因为事件数据将尽可能少的记录保存在应用程序状态更改相同的本地事务中。  
  
- 针对执行性能进一步优化应用程序状态的 SQL Server 存储。 TDDS 解码数据并将其存储在单独的数据库，在 BAM 主导入数据库或 DTA 数据库中。 生成报表时的数据从数据库查询，并会影响存储的应用程序状态的 Messagebox 数据库。  
  
- 若要将事件数据存储在一个表单，您可以查询表单的工作不是应用程序服务器和数据库中。 它被卸载给运行 BAM 事件总线服务和目标 SQL Server 数据库的计算机。  
  
- 较低的延迟这样 TDDS 查询过程更快地处理事件数据。 BAM 事件总线服务协调其资源，以获得可能的最小延迟。  
  
  BAM 事件总线服务器通过使用连接到中央数据库，其中包含配置信息来协调其资源。 每隔一分钟，每个活动的 BAM 事件总线服务将消息发送到中央数据库，其中包含在某个时间点的 BAM 事件总线服务的状态。  
  
  此消息被称为检测信号消息。 每个 BAM 事件总线服务还会检查新需要完成的工作。 例如，BAM 事件总线服务检查不属于，如已添加的 MessageBox 数据库的会话。  
  
  BAM 事件总线会话是事件数据源数据库，如 MessageBox，包含一种格式，您可以查询中的事件数据的目标数据库的移动。 同一个 BAM 事件总线服务可以处理一个或多个会话。  
  
  下图显示了一组 BAM 事件总线服务器，它们构成的 BAM 事件总线服务器池。  
  
  ![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")  
  BAM 事件总线服务器池的关系图  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BAM 性能计数器](../core/bam-performance-counters.md)  
  
-   [BAM 事件总线服务存储过程](../core/bam-event-bus-service-stored-procedures.md)  
  
-   [BAM 事件总线服务服务器故障转移](../core/bam-event-bus-service-server-failover.md)  
  
-   [创建 BAM 事件总线服务实例](../core/creating-instances-of-the-bam-event-bus-service.md)