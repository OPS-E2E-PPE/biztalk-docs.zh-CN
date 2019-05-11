---
title: 查询计划的聚合数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, scheduled data
- queries [BAM], scheduled data
ms.assetid: fb785ec0-7862-4d83-bb6f-0ebd69a28ce6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d088f0affe630ecf2df727cc89ceffc6f82855d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398271"
---
# <a name="querying-scheduled-aggregated-data"></a>查询计划的聚合数据
可通过 BAM 分析数据库中的动态创建 OLAP 多维数据集的查询计划的聚合数据。  
  
 此多维数据集的名称是相同的 BAM 定义 XML 中 View 元素的 Name 属性与在 Excel 向导中输入的视图名称相同。 BAM 将刷新此多维数据集时运行数据转换服务 (DTS) 包 BAM_AN_\<*ViewName*\>，其中\< *ViewName* \>是的名称描述你在 Excel 向导中使用。  
  
 请务必在查询计划的聚合的数据时注意下列情况：  
  
-   这是业务的虚拟多维数据集包含快照，在开始执行 DTS 包的确切时间。 它包含聚合已完成的活动以及与仍在进行中。 您可以使用进度维度对筛选器或组聚合相应地。  
  
-   如果您不感兴趣的当前活动 （例如，如果他们完成非常快） 可以查询相应的真实多维数据集\< *ViewName*\>#Completed。  
  
-   如果此外还有实时聚合，安排 DTS 包，比为实时聚合设置联机时段更频繁地刷新多维数据集。 否则，将有一个没有聚合的时段。  
  
## <a name="see-also"></a>请参阅  
 [查询 BAM 数据](../core/querying-bam-data.md)