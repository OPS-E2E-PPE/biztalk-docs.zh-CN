---
title: 什么是聚合？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- OLAP cubes, BAM
- BAM, aggregations
- BAM, OLAP cubes
- aggregations [BAM], OLAP cubes
- aggregations [BAM], about aggregations
- aggregations [BAM]
ms.assetid: 77d40602-ef56-4a5b-a18f-56ccbff573a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24dced4d7075e85b8b002bf90b821ce745f91e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289157"
---
# <a name="what-is-an-aggregation"></a>什么是聚合？
Excel 将聚合定义为预先计算的数据汇总，通过在提问之前准备好答案的方式来提高查询响应时间。 例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。 然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。  
  
 下图显示的是预先计算的聚合数据的示例。  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
BAM OLAP 多维数据集  
  
 上图汇总了在两个月内发送到特定地点的各种产品的数量。 通常，Excel 将此数据定义为度量值。 Excel 将用于筛选和分类的数据定义为维度。  
  
 有关浏览多维数据的用户体验，请参阅 Excel 帮助中的透视表主题。  
  
 您可以基于特定视图中的可用数据创建多维活动聚合。 这些聚合包含度量值（要聚合的数据，如美元表示的金额）和维度（用于进行筛选或分组，如“州”和“城市”）。  
  
 可以创建联机分析处理 (OLAP) 多维数据集形式的聚合，用于表示特定时间的业务快照，也可以创建实时聚合，实时聚合由业务方案决定，您可以使用多维结构实时查看它。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [计划的聚合](../core/scheduled-aggregations.md)  
  
-   [实时聚合](../core/real-time-aggregations.md)