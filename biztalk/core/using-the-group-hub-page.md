---
title: 使用组中心页 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50693ccc-a3b2-4ad0-9a05-d60dab404a07
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e035a363b71b70db390d88a8b0e32e2e9b531d92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288085"
---
# <a name="using-the-group-hub-page"></a>使用“组中心”页
选择**BizTalk 组**节点在 BizTalk Server 管理控制台中，显示 BizTalk Server 组中心数据库页的详细信息窗格中。 BizTalk Server 组中心页分为三个部分，提供 BizTalk Server 系统运行状况的总体概况。  
  
-   **配置概述**部分中，在组中心数据库页的上半部分中找到通过显示应用程序，主机实例的状态来指示 BizTalk 组的总体运行状况和适配器处理程序配置中此组中。  
  
-   **正在进行的工作**和**挂起项**部分位于中间组中心数据库页。  
  
    -   **正在进行的工作**部分显示运行服务实例、 冻结的业务流程，正在重试和空闲端口、 就绪的服务实例和计划的服务实例。  
  
    -   **挂起项**部分显示的挂起的服务实例和可恢复和非可恢复实例数。  
  
-   **分组挂起的服务实例**部分显示按应用程序、 服务名称、 错误代码和 URI 分组的挂起的服务实例。  
  
    > [!NOTE]
    >  “组中心”页上列出的数目只是近似数目。 例如下, 显示的数字**正在运行的服务实例**或**挂起的服务实例**可能不等于正在运行的服务实例或挂起的服务实例的总数因为正在生成中心页面上的各种统计信息时，无法更改系统的状态。  
  
-   **跟踪服务实例**和**跟踪消息事件**部分执行查询的消息活动和最大匹配的服务实例的状态 = 50。  
  
    -   **跟踪服务实例**查询将搜索跟踪的服务实例。  
  
    -   **已完成实例**查询将搜索具有相等完成状态的跟踪的服务实例。  
  
    -   **终止实例**查询将搜索具有相等的状态终止跟踪的服务实例。  
  
    -   **跟踪消息事件**查询搜索的跟踪的消息事件。  
  
    -   **传输失败事件**查询将搜索的跟踪的消息事件的事件类型的传输故障。  
  
-   **EDI 状态报告**和**EDIINT 状态报告**部分中，位于底部的组中心数据库页显示有关 EDI 的交换的四个报告和有关 AS2 的交换： EDI 交换和关联 ACK 状态报表、 批处理状态报表、 交换聚合报表、 事务组聚合报表和 AS2 消息和相关 MDN 状态报表。 有关这些报表的详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。  
  
    > [!NOTE]
    >  如果为此 BizTalk 组配置 EDI/AS2 功能，才会显示 EDI 和 EDIINT 状态报表部分。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [服务实例状态](../core/service-instance-states.md)  
  
-   [调查业务流程、 端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)  
  
-   [使用管理控制台的查询选项卡](../core/using-the-administration-console-query-tab.md)  
  
-   [查看跟踪的消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [运行状况和活动跟踪](../core/health-and-activity-tracking.md)