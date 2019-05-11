---
title: 定义维度 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- BAM, dimensions
- BAM views, dimensions
- Excel add-in [BAM], creating dimensions
- dimensions [BAM]
ms.assetid: c00e0c45-eef2-42d9-832c-4be08d79203f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 538310883b4c8167cea40be4799160e67a1e1fa2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352379"
---
# <a name="defining-dimensions"></a>定义维度
Microsoft Excel 将维度定义为类别用于将表中的数据组织到将用于分析的级别。 例如，位置数据维度可能包含如市/县、 州/省和国家/地区的级别。 创建 BAM 视图时在 BAM 视图向导中，可以添加一个或多个以下的维度类型：  
  
- [进度维度](../core/progress-dimension.md)  
  
- [数据维度](../core/data-dimension.md)  
  
- [时间维度](../core/time-dimension.md)  
  
- [数值范围维度](../core/numeric-range-dimension.md)  
  
  ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
  预先计算的聚合数据  
  
  在 BAM 视图向导中添加新的维度。 在添加维度之前，需要使用该向导创建业务活动视图。 有关使用向导的详细信息，请参阅[定义业务活动和在 Excel 中的视图](../core/defining-business-activities-and-views-in-excel.md)。  
  
### <a name="to-add-new-dimensions"></a>若要添加新维度  
  
1.  在 BAM 视图向导中，单击**下一步**直到您看到**新建 BAM 视图：聚合维度和度量值**页。 单击**新维度**。  
  
2.  键入该维度的名称。  
  
3.  从下拉列表中，选择维度类型。  
  
4.  根据所选的维度类型，填写适当的数据，然后依次**确定**。  
  
## <a name="see-also"></a>请参阅  
 [进度维度](../core/progress-dimension.md)