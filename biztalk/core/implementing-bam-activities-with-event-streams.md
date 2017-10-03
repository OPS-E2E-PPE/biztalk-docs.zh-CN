---
title: "实现事件流 BAM 活动 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], about activities
- activities [BAM]
- BAM, activities
ms.assetid: 94e6d9dd-93c3-4ab0-9de7-a860dd1e3406
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63594b956affc0f5b94f26ccdcb10d904ef171cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-bam-activities-with-event-streams"></a>实现事件流 BAM 活动
BAM 活动表示业务，例如采购订单或贷款应用程序中的工作单元。 活动向业务最终用户或信息工作者显示有关此工作单位的历史记录（里程碑）和数据。 例如，贷款申请活动可能包含里程碑（如“贷款已批准”）和数据（如“申请人姓名”和“贷款金额”）。 BAM 活动常常直接映射到业务流程，尽管作为高级抽象概念，活动独立于 IT 基础结构的实际实现。  
  
 开发人员可以只在特定活动的上下文公开实现的相关里程碑和数据，以此来维护这种抽象概念。 有关演示如何使用活动的代码示例，请参阅[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为什么为 BAM 编写代码？](../core/why-write-code-for-bam.md)  
  
-   [开发人员的 BAM 概念](../core/bam-concepts-for-the-developer.md)  
  
-   [BAM 开发过程概述](../core/overview-of-the-bam-development-process.md)  
  
-   [EventStream 类](../core/eventstream-classes.md)  
  
-   [使用活动](../core/using-an-activity.md)  
  
-   [活动关系](../core/activity-relationships.md)  
  
-   [活动延续](../core/activity-continuation.md)  
  
-   [循环的活动](../core/looping-activities.md)  
  
-   [在插入检测点解决方案： 分步 API 使用情况](../core/instrumenting-a-solution-step-by-step-api-usage.md)