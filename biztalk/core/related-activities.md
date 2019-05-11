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
ms.openlocfilehash: ef8cf9e4b73b4d2eda00c022270ba4cb2db8cf6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397988"
---
# <a name="related-activities"></a>相关的活动
相关活动区域包含与查询所基于的活动相关的活动的列表。 采购订单活动的相关活动的示例将多个发货活动，因为一个采购订单上的项可以提供在多个发货。  
  
## <a name="creating-related-activities"></a>创建相关的活动  
 有两种生成相关活动的列表：  
  
- 您定义两个活动，然后创建一个包含这两个值的单个视图。 开发人员建立两个通过实现密钥、 字段和值在活动之间的关系之间的相关连接。  
  
- 定义两个活动。 开发人员通过调用 addrelationship （） 并定义密钥、 字段和值在活动之间的关系，在自定义应用程序中建立相关连接。  
  
  在任一种方式中定义的活动关系将添加中的某一行\<activityname\>_Relationships 表。  
  
> [!NOTE]
>  仅在需要实时链接到每个其他的相关活动中定义的关系结果的第一种方法。 第二种方法不会定义延伸视图，因此门户无法知道两个活动之间的关系。  
  
## <a name="see-also"></a>请参阅  
 [如何查看活动搜索的结果](../core/how-to-view-the-results-of-an-activity-search.md)