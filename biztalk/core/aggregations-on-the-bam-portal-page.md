---
title: BAM 门户上的聚合页 |Microsoft 文档
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
ms.openlocfilehash: a61df22bf5d07bd1b4d955f2baf884459de52998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230061"
---
# <a name="aggregations-on-the-bam-portal-page"></a>BAM 门户上的聚合页
当业务最终用户、开发人员和业务分析员需要显示聚合数据时可使用 BAM 门户页。聚合数据是某个数据集的预计算汇总，可以传达该数据集的典型特征。 使用 BAM 门户的“聚合”页，可以用图表形式以及随附的数据透视表显示聚合数据。  
  
## <a name="the-aggregations-page"></a>“聚合”页  
 “聚合”页显示传达流程或整个业务的总体运行情况的活动的结果。 例如，用户可能希望查看一个简单的饼图，其中显示 1,000 张发票按所在的处理阶段进行细分的结果（400 张仍在“评估”，400 张被拒绝，100 张已付款，还有 100 张仍处于“资金调拨”阶段）。  
  
### <a name="creating-alerts-for-aggregations"></a>创建聚合警报  
 可以将聚合作为创建警报的依据，例如，“当处于流程‘评估’阶段的发票超过 500 张时通知我”。 为此，右键单击任何数据透视表单元格，然后选择**设置警报**，或者单击单元格并单击**设置警报**数据透视表右侧的按钮。 有关创建警报的详细信息，请参阅[如何设置警报](../core/how-to-set-an-alert.md)。  
  
### <a name="viewing-individual-results-of-aggregations"></a>查看聚合的各个结果  
 还可以选择任意聚合数量（例如，仍在“评估”的 400 张发票），然后查看该聚合的各个结果。 右键单击任何数据透视表单元格并选择访问各个结果**显示结果**。 执行此操作后，您将进入“活动搜索”页，系统会自动构建搜索，然后显示出结果（对于此示例，400 张发票中的每张发票都有一条记录）。  
  
> [!NOTE]
>  某些 BAM 视图没有与之相关联的聚合，因此可能没有任何可访问的信息，这取决于视图的创建方式。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 门户](../core/bam-portal.md)   
 [BAM 门户上的活动搜索页](../core/activity-search-on-the-bam-portal-page.md)   
 [警报管理器上 BAM 门户页](../core/alert-manager-on-the-bam-portal-page.md)