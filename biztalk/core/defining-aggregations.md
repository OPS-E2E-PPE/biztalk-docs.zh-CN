---
title: 定义聚合 |Microsoft 文档
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
ms.openlocfilehash: 3412615d03fc9a9776d86fddfb062ab343c5aaeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238445"
---
# <a name="defining-aggregations"></a>定义聚合
Excel 定义**聚合**为预先计算摘要任务具有的改进查询响应时间的数据的情况下，答案就绪之前进行提问。 例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。 然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。  
  
 下图显示的是预先计算的聚合数据的示例。  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
预先计算的聚合数据  
  
 上图汇总了在两个月内发送到特定地点的各种产品的数量。 Excel 通常定义此类数据作为**度量值**。 用于筛选和分类的数据，Excel 将定义为**维度**。  
  
> [!NOTE]
>  BAM 不支持使用 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services 的命名实例。  
  
 浏览多维数据的用户体验，请参阅 Excel 帮助中的数据透视表主题。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何定义度量值](../core/how-to-define-measures.md)  
  
-   [定义维度](../core/defining-dimensions.md)  
  
-   [如何使用数据透视表](../core/how-to-use-the-pivottable.md)  
  
-   [定义实时聚合](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a>另请参阅  
 [定义 BAM 视图](../core/defining-a-bam-view.md)