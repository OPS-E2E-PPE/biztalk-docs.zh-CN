---
title: 如何使用该数据透视表 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM views, pivot tables
- BAM views, previewing data
ms.assetid: af34494b-f577-4d36-9a9e-5d6e9c5fafbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b0400dd5cf1c21aa0c24ac54e2a72ded2e20fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333212"
---
# <a name="how-to-use-the-pivottable"></a>如何使用透视表
定义 BAM 视图，其中包括维度和度量值后，你需要更新与该视图相关联的一个或多个数据透视表。  
  
 在 Excel 中的数据透视表报表是一个交互式表，使您能够轻松地合并和比较大量数据。 可以旋转其行和列中的值，若要查看显示的数据的不同摘要。 数据透视表，还可以执行计算的数据，例如求聚合计数或平均值。  
  
 若要在创建后，请使用该数据透视表，请执行此过程中的步骤。 有关使用数据透视表的详细信息，请参阅 Microsoft Excel 文档。  
  
> [!NOTE]
>  创建实时聚合透视表时，它可以包含最多为 14 个维度级别。  
  
> [!IMPORTANT]
>  如果在 Excel 工作表上定义多个数据透视表，就可以生成的表可能增大并相互重叠，如果活动返回大型数据集。 在此方案中，你将收到"数据透视表不能重叠另一个数据透视表报表"时刷新数据。 可以通过添加列或数据透视表，以允许表增大而不重叠的之间的行来更正此错误。  
  
### <a name="to-use-the-pivottable"></a>若要使用该数据透视表  
  
1.  创建要与数据透视表一起使用的 BAM 视图。 有关创建 BAM 视图的详细信息，请参阅[定义业务活动视图。](../core/defining-a-bam-view.md)  
  
2.  使用**数据透视表字段列表**，拖放一个或多个可用维度到数据透视表模板的列和行区域。  
  
3.  使用**数据透视表字段列表**，拖放一个或多个可用度量值拖动到数据的项区域的数据透视表模板。  
  
     要更新该数据透视表，您会发现用示例数据填充。 这有助于确定应如何配置该数据透视表。  
  
4.  使用**数据透视表**工具栏中，某个图表与该数据透视表的关联。  
  
5.  保存 Excel 工作簿。