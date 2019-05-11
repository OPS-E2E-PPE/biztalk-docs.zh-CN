---
title: 如何定义度量值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating measures
- aggregations [BAM], measures
- BAM views, measures
ms.assetid: fd3dfe6b-cc63-4306-8aad-a9d2a9af01e8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68b269cd333706978bb2ef2433f0e5703e72b37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338796"
---
# <a name="how-to-define-measures"></a>如何定义度量值
度量值定义如何计算活动。 创建 BAM 视图时您可以在视图中定义的度量值，该活动。 例如，对于采购订单活动，可以计算总 PO 金额、 Po 数量、 平均 PO 金额等。  
  
 BAM 支持度量值包括：  
  
-   Sum  
  
-   Count  
  
-   平均值  
  
-   最低要求  
  
-   最大值  
  
> [!NOTE]
>  BAM 实时聚合 (RTA) 功能目前不支持最小值和最大值的度量值。 可以使用这些度量值，但当标记为 RTA Excel 数据透视表时，将忽略最小值和最大值。  
  
### <a name="to-add-new-measures"></a>若要添加新度量值  
  
1. 在 BAM 视图向导中，单击**下一步**直到您看到**新建 BAM 视图：聚合维度和度量值**页。 单击**新的度量值**。  
  
2. 键入度量值的名称。  
  
3. 从下拉列表中，选择**基本数据项**。  
  
4. 单击**聚合类型**你想要使用。 选项包括：  
  
   -   Sum  
  
   -   Count  
  
   -   平均值  
  
   -   最小值 （Rta 不支持）。  
  
   -   最大值 （Rta 不支持）  
  
5. 单击“确定” 。 完成添加维度和度量值后，单击**下一步**。  
  
6. 在**新建 BAM 视图：摘要**页上，查看有关您的新视图的信息，然后单击**下一步**。  
  
7. 单击**完成**若要完成**BAM 视图向导**。  
  
   如果添加度量值和维度到 BAM 视图，您可以将这些项添加到 Excel 工作簿中数据透视表。 有关创建数据透视表的详细信息，请参阅[如何使用该数据透视表](../core/how-to-use-the-pivottable.md)。  
  
## <a name="see-also"></a>请参阅  
 [定义维度](../core/defining-dimensions.md)