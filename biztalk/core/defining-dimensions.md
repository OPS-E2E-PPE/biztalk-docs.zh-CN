---
title: "定义维度 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- BAM, dimensions
- BAM views, dimensions
- Excel add-in [BAM], creating dimensions
- dimensions [BAM]
ms.assetid: c00e0c45-eef2-42d9-832c-4be08d79203f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916e8f29d7f1e48a7bab5f9ad78e65cb78e51802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="defining-dimensions"></a>定义维度
Microsoft Excel 将维度定义为类别，这些类别用于将表中的数据组织成若干级别以供分析之用。 例如，位置数据维度可能包含下级别：县/市、省/市/自治区和国家/地区。 在 BAM 视图向导中创建 BAM 视图时，您可以添加以下维度类型中的一个或多个：  
  
-   [进度维度](../core/progress-dimension.md)  
  
-   [数据维度](../core/data-dimension.md)  
  
-   [时间维度](../core/time-dimension.md)  
  
-   [数值范围维度](../core/numeric-range-dimension.md)  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
预先计算的聚合数据  
  
 您可以在“BAM 视图”向导中添加新的维度。 在添加维度之前，您需要使用该向导来创建业务活动视图。 有关使用向导的详细信息，请参阅[定义业务活动和在 Excel 中的视图](../core/defining-business-activities-and-views-in-excel.md)。  
  
### <a name="to-add-new-dimensions"></a>添加新维度  
  
1.  在 BAM 视图向导中，单击**下一步**直到你看到**新 BAM 视图： 聚合维度和度量值**页。 单击**新维度**。  
  
2.  键入该维度的名称。  
  
3.  从下拉列表中选择一个维度类型。  
  
4.  根据你选择的维度类型，填写适当的数据，并依次**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [进度维度](../core/progress-dimension.md)