---
title: 定义聚合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], creating
- Excel add-in [BAM], creating aggregations
- aggregations [BAM], Excel add-in
- aggregations [BAM], about aggregations
ms.assetid: d5bf22d5-f491-4b08-a604-c7158e6e282f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a379e27e7805aa7e4b67ad3c94afba65b546c7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352471"
---
# <a name="defining-aggregations"></a>定义聚合
Excel 将定义**聚合**预先计算的数据汇总，通过缩短查询响应时间作为答案就绪问题提出之前。 例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。 然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。  
  
 下图显示的是预先计算的聚合数据的示例。  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
预先计算的聚合数据  
  
 上图汇总了在两个月内发送到特定地点的各种产品的数量。 通常，Excel 将定义此类数据作为**度量值**。 用于筛选和分类的数据，Excel 将定义为**维度**。  
  
> [!NOTE]
>  BAM 不支持使用的命名的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services。  
  
 有关浏览多维数据的用户体验，请参阅 Excel 帮助中的数据透视表主题。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何定义度量值](../core/how-to-define-measures.md)  
  
-   [定义维度](../core/defining-dimensions.md)  
  
-   [如何使用该数据透视表](../core/how-to-use-the-pivottable.md)  
  
-   [定义实时聚合](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a>请参阅  
 [定义 BAM 视图](../core/defining-a-bam-view.md)