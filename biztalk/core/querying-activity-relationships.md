---
title: 查询活动关系 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, activity relationships
- queries [BAM], relationships
ms.assetid: e3d42b7c-cc11-4707-9095-cfc518902b26
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eb6c74ddd5a480f3e4048079e346cf23570c1f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398318"
---
# <a name="querying-activity-relationships"></a>查询活动关系
在每个活动动态创建的 SQL 视图提供了活动关系信息。 此视图的名称是  
  
 **bam_\<**  *活动*  **\>_AllRelationships**  
  
 其中\<*活动*\>是 BAM 定义 XML 中的 Activity 元素的 Name 属性与输入使用 Excel BAM 外接程序的活动名称相同。  
  
 关系事件发生在特定活动的上下文中。 例如，如果采购订单和发货之间的关系发生在采购订单活动的上下文中，该关系的记录将显示在**bam_PurchaseOrder_AllRelationships**，但不能在**bam_Shipment_AllRelationships**。 有关详细信息，请参阅[活动关系](../core/activity-relationships.md)。  
  
 若要查找所有相关的活动的购买的订购需要查询这两个视图**bam_PurchaseOrder_AllRelationships**以及所有视图**bam_\<**<em>OtherActivity</em>  **\>_AllRelationships**，其中\< *OtherActivity* \>是相同的 BAM 视图中的活动。  
  
 关系记录是活动实例的一部分，它们都保留在与实例数据的同步，如中所述[活动数据存储](../core/activity-data-storage.md)。  
  
## <a name="see-also"></a>请参阅  
 [查询 BAM 数据](../core/querying-bam-data.md)