---
title: 使用组中心页 |Microsoft Docs
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
ms.openlocfilehash: 4f705305422f47cbf5510823a82356c9781d82aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396011"
---
# <a name="using-the-group-hub-page"></a>使用组中心页
选择**BizTalk 组**BizTalk Server 管理控制台中，节点详细信息窗格中显示 BizTalk Server 组中心页。 BizTalk Server 组中心页分为三个部分，其中提供的 BizTalk Server 系统运行状况的总体视图：  
  
-   **配置概述**部分中，位于组中心页的上半部分中指示的 BizTalk 组的总体运行状况通过显示应用程序，主机实例的状态和适配器处理程序中配置此组。  
  
-   **正在进行的工作**并**挂起的项**部分位于组中心页的中间。  
  
    -   **正在进行的工作**部分显示正在运行的服务实例、 冻结的业务流程、 正在重试和空闲的端口、 就绪的服务实例和计划的服务实例。  
  
    -   **挂起的项**部分显示挂起的服务实例和可恢复和不可恢复的实例的数量。  
  
-   **分组的挂起服务实例**部分显示按应用程序、 服务名称、 错误代码和 URI 分组的挂起的服务实例。  
  
    > [!NOTE]
    >  在组中心页上列出的编号只是近似数目。 例如下, 显示的数字**正在运行的服务实例**或**挂起的服务实例**可能不等于正在运行的服务实例或挂起的服务实例的总数因为正在生成中心页面上的各种统计信息时，无法更改系统的状态。  
  
-   **跟踪的服务实例**并**跟踪的消息事件**部分消息事件和状态的最大匹配的服务实例上执行查询 = 50。  
  
    -   **跟踪服务实例**查询将搜索跟踪的服务实例。  
  
    -   **已完成实例**查询将搜索具有等于已完成状态的跟踪的服务实例。  
  
    -   **终止实例**查询将搜索具有相等的状态终止跟踪的服务实例。  
  
    -   **跟踪消息事件**查询将搜索跟踪的消息事件。  
  
    -   **传输失败事件数**查询将搜索跟踪的消息传输失败的事件类型的事件。  
  
-   **EDI 状态报告**并**EDIINT 状态报告**部分中，位于组中心页底部将显示有关 EDI 交换的四个报表和一个有关 AS2 交换： EDI 交换和相关 ACK 状态报告、 批处理状态报告、 交换聚合报告、 事务集聚合报告和的 AS2 消息和相关 MDN 状态报告。 有关这些报告的详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。  
  
    > [!NOTE]
    >  如果为此 BizTalk 组配置 EDI/AS2 功能，将仅显示 EDI 和 EDIINT 状态报告部分。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [服务实例状态](../core/service-instance-states.md)  
  
-   [调查业务流程、端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)  
  
-   [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)  
  
-   [查看跟踪的消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [运行状况与活动跟踪](../core/health-and-activity-tracking.md)