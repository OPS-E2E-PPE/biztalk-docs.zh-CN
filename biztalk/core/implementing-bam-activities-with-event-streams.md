---
title: 实现通过事件流的 BAM 活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], about activities
- activities [BAM]
- BAM, activities
ms.assetid: 94e6d9dd-93c3-4ab0-9de7-a860dd1e3406
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f64b52fe6985da2f5f83cabe77fc3841c1a4db8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382621"
---
# <a name="implementing-bam-activities-with-event-streams"></a>与事件流实现 BAM 活动
BAM 活动代表在企业中，如采购订单或贷款申请的工作单元。 活动向业务最终用户或信息工作者显示历史记录 （里程碑） 和有关此工作单位的数据。 例如，贷款申请活动可能包含如"贷款已批准"的里程碑和数据，如"申请人姓名"和"贷款金额"。 BAM 活动常常直接映射到业务流程，尽管作为高级抽象活动是独立于你的 IT 基础结构的实际实现。  
  
 您作为开发人员的工作是通过公开的相关里程碑和上下文中的特定活动的实现中的数据来保持这种抽象。 有关演示如何将活动的代码示例，请参阅[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为什么为 BAM 编写代码？](../core/why-write-code-for-bam.md)  
  
-   [适用于开发人员的 BAM 概念](../core/bam-concepts-for-the-developer.md)  
  
-   [BAM 开发过程概述](../core/overview-of-the-bam-development-process.md)  
  
-   [EventStream 类](../core/eventstream-classes.md)  
  
-   [通过使用活动](../core/using-an-activity.md)  
  
-   [活动关系](../core/activity-relationships.md)  
  
-   [活动延续](../core/activity-continuation.md)  
  
-   [循环活动](../core/looping-activities.md)  
  
-   [检测解决方案：分步 API 使用情况](../core/instrumenting-a-solution-step-by-step-api-usage.md)