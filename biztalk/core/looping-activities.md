---
title: 循环活动 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], looping activities
- activities [BAM], orchestrations
- orchestrations, looping
- orchestrations, activities
ms.assetid: fb40fdd0-ac8f-486a-b3d0-9d2200a87cda
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f66382a27ed564da0c41257e8abe95accba5e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262077"
---
# <a name="looping-activities"></a>循环的活动
循环活动是指在某个业务流程内循环的操作。 可以从在业务流程内循环的操作中捕获事件。 为此，需要创建另一个活动，并映射该循环内的所有新活动里程碑和数据。 这样做是有必要的，因为在循环中数据处理在每次计划的执行中将发生多次。 下图显示的就是这种情况的一个示例。  
  
 ![](../core/media/handlingloops2.gif "handlingloops2")  
  
 如图所示，如果你有具有在循环中处理的多个行项的购买订单，此类问题:"的采购订单有 100 美元的项价格？" 不明确。 下面的问题则含义明确：  
  
-   哪些采购订单包含价格为 $100 的货物行？  
  
-   哪些采购订单的货物的总计/最小/最大价格为 $100？  
  
 要提出含义明确的问题，则需要将货物行同采购订单分开考虑。 在跟踪配置文件编辑器中，根活动（例如，采购订单）映射到循环外的所有操作。 子活动 （例如，行项） 将映射到循环内的操作。  
  
 您需要将负载项目用作根活动的 ActivityID。 使此负载项目可供循环内的某些消息使用。 映射到的子活动下显示的关系节点的活动并将它作为根活动。  
  
## <a name="see-also"></a>另请参阅  
 [实现事件流 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)