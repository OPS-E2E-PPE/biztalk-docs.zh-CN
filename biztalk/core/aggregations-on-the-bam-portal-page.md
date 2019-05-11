---
title: BAM 门户上的聚合页面 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], alerts
- aggregations [BAM], viewing results
- alerts, aggregations
- Aggregations page [BAM portal]
- BAM portal, aggregations
ms.assetid: 6bc1a6f2-9e9a-4db6-aaa1-188ed2f2641f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5b242091e72ec4bc0ae56fdf27be5228583b7b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360151"
---
# <a name="aggregations-on-the-bam-portal-page"></a>BAM 门户上的聚合页
业务最终用户、 开发人员和业务分析员使用 BAM 门户页时需要显示聚合的数据，这是传达该数据集的典型特征的预先计算的汇总的数据集。 BAM 门户的聚合页上，可在图形图表和随附的数据透视表的形式显示聚合的数据。  
  
## <a name="the-aggregations-page"></a>聚合页  
 聚合页显示传达的运行状况的过程或整个业务的活动的结果。 例如，用户可能想要查看简单的饼图，显示 1,000 张发票按所处的阶段的处理已达到通过每个发票 （400 张仍在"评估"，400 个已拒绝，100 付款，还有 100 仍处于"资金调拨"中） 的细分。  
  
### <a name="creating-alerts-for-aggregations"></a>创建聚合警报  
 创建警报时通知我"如果"评估"阶段的过程中有超过 500 发票） 可作为基础用于聚合。 若要执行此操作，请右键单击任何数据透视表单元，并选择**设置警报**，或单击的单元格，然后单击**设置警报**按钮右侧的数据透视表报表。 有关创建警报的详细信息，请参阅[如何设置警报](../core/how-to-set-an-alert.md)。  
  
### <a name="viewing-individual-results-of-aggregations"></a>查看聚合的各个结果  
 您还可以选择任意聚合数量 （例如，400 张发票仍在"评估"），并查看聚合的各个结果。 右键单击数据透视表的任何单元格并选择访问各个结果**显示结果**。 此操作的响应，发送到的活动搜索页、 自动构建搜索本身，和结果显示 （在此示例中，为每个 400 张发票的一条记录）。  
  
> [!NOTE]
>  某些 BAM 视图没有与其相关联的聚合，因此可能没有要具体取决于如何创建视图访问信息。  
  
## <a name="see-also"></a>请参阅  
 [BAM 门户](../core/bam-portal.md)   
 [在 BAM 门户网站上的活动搜索页](../core/activity-search-on-the-bam-portal-page.md)   
 [“BAM 门户”页中的警报管理器](../core/alert-manager-on-the-bam-portal-page.md)