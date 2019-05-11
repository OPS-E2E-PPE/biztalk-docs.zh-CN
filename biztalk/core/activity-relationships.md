---
title: 活动关系 |Microsoft Docs
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
ms.openlocfilehash: a3266501df57b9350e70369327fdc3142b3019d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361660"
---
# <a name="activity-relationships"></a>活动关系
当活动与一个或多个其他活动时，存在一个活动关系。 此示例多个发货活动与单个采购订单活动或一个发货活动包含两个采购订单活动中的项。  
  
 若要指示两个活动将相关，需要知道它们的名称，并在内存中具有相应的 Activityid，以便调用 AddRelatedActivity。 此 API 创建相应的活动记录之间的链接。  
  
 下图中突出显示的代码行说明如何在采购订单活动实例 #123 与发货活动 # 1549年、 # 1550年和 1551年之间建立关系。  
  
 ![](../core/media/activity-relationships-example.gif "activity_relationships_example")  
  
 业务最终用户将查看显示采购订单的历史记录的一个网页。 它可能指示在上午 10 点 到达、 两天后，它被审批，和的页提供了指向实际文档的链接。 由于在上图中的代码，该页面还将提供将业务最终用户转到对应发货网页的超链接。  
  
> [!NOTE]
>  所有调用的`AddRelatedActivity`应执行的操作之间`BeginActivity`和`EndActivity`。  
  
## <a name="see-also"></a>请参阅  
  
 [活动继续符](../core/activity-continuation.md)   
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)   
 [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)   
 [业务流程表达式中的 BAM API（BizTalk Server 示例）](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)