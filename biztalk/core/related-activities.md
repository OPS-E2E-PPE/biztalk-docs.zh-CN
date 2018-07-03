---
title: 相关活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], related activities
- Query Builder [BAM portal], related activities
- queries [BAM], related activities
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
ms.assetid: 141b7943-d244-4810-aa88-12aa4a2b7658
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 547a8f80dbb84e12a89c96a5b85ec6a5cc6421ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013862"
---
# <a name="related-activities"></a>相关的活动
“相关活动”区域包含与查询所基于的活动相关的活动的列表。 例如，“采购订单”活动的相关活动可以是多个“发货”活动，因为一个采购订单中的货物可以通过多次发货来交付。  
  
## <a name="creating-related-activities"></a>创建相关活动  
 可以通过以下两种方式之一来生成相关活动的列表：  
  
- 首先定义两个活动，然后创建一个包含这两个活动的视图。 开发人员通过实现活动之间的关键字关系、字段关系和值关系来建立这两个活动之间的相关连接。  
  
- 定义两个活动。 开发人员通过调用 AddRelationship() 并定义活动之间的关键字关系、字段关系和值关系，在自定义应用程序中建立相关连接。  
  
  在任一种方式中定义的活动关系将添加中的某一行\<activityname\>_Relationships 表。  
  
> [!NOTE]
>  只有第一种定义关系的方法会使相关活动实时地相互连接。 由于第二种方法不能定义延伸视图，因此门户无法知道两个活动之间的关系。  
  
## <a name="see-also"></a>请参阅  
 [如何查看活动搜索的结果](../core/how-to-view-the-results-of-an-activity-search.md)