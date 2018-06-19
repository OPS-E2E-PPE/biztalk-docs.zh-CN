---
title: 活动关系 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], relationships
ms.assetid: da7c7205-18c6-44df-af03-3140214c84e6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3709ad02ed082595665c68485502847b52e5a1d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225229"
---
# <a name="activity-relationships"></a>活动关系
当活动与一个或多个其他活动关联时，则存在活动关系。 例如，多个发货活动与单个采购订单活动相关，或者一个发货活动包含来自两个采购订单活动中的项。  
  
 若要指出两个活动相关，需要知道它们的名称及其对应的内存中 ActivityID，以便调用 AddRelatedActivity。 此 API 在对应的活动记录之间创建链接。  
  
 在下图中，突出显示的代码行说明如何在采购订单活动实例 #123 与发货活动 #1549、#1550 和 #1551 之间建立关系。  
  
 ![](../core/media/activity-relationships-example.gif "activity_relationships_example")  
  
 业务最终用户将查看显示采购订单历史记录的网页。 这可能表明，在上午 10 点 其到达时、 两天后收到批准、 和页提供对实际文档的链接。 上述代码还使该页提供能够将业务最终用户连接到对应发货网页的超链接。  
  
> [!NOTE]
>  对所有调用`AddRelatedActivity`应执行的操作之间`BeginActivity`和`EndActivity`。  
  
## <a name="see-also"></a>另请参阅  
  
 [活动延续](../core/activity-continuation.md)   
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)   
 [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)   
 [BAM API 从 Orchestration 表达式 （BizTalk Server 示例）](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)