---
title: 查询活动关系 |Microsoft 文档
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
ms.openlocfilehash: 70c94644e505409f863e5104168740232d57c664
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970405"
---
# <a name="querying-activity-relationships"></a>查询活动关系
在为每个活动动态创建的 SQL 视图中，可以找到活动关系信息。 此视图的名称是  
  
 **bam_\<**  *活动*  **\>_AllRelationships**  
  
 其中\<*活动*\>为 BAM 定义 XML 中的活动元素的名称属性即为 Excel BAM 外接程序使用输入的活动名称相同。  
  
 关系事件发生在特定活动的上下文中。 例如，如果采购订单和装运之间的关系发生在采购订单活动的上下文中，关系记录将显示在**bam_PurchaseOrder_AllRelationships**，但未显示在**bam_Shipment_AllRelationships**。 有关详细信息，请参阅[活动关系](../core/activity-relationships.md)。  
  
 若要查找所有相关的活动与购买排序需要查询这两个视图**bam_PurchaseOrder_AllRelationships**以及所有视图**bam_\<***OtherActivity*  **\>_AllRelationships**，其中\< *OtherActivity* \>相同 BAM 视图中的活动。  
  
 关系记录的活动实例的一部分，维护多维数据集与实例数据同步中所述[活动数据存储](../core/activity-data-storage.md)。  
  
## <a name="see-also"></a>另请参阅  
 [查询 BAM 数据](../core/querying-bam-data.md)