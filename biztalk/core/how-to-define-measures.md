---
title: "如何定义度量值 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating measures
- aggregations [BAM], measures
- BAM views, measures
ms.assetid: fd3dfe6b-cc63-4306-8aad-a9d2a9af01e8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56fea736baaec3f259fc8831a7256e28eaabc9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-define-measures"></a>如何定义度量值
度量值定义如何计算活动。 创建 BAM 视图时，可以为该视图中的活动定义度量值。 例如，对于一项采购订单活动，可以计算总 PO 金额、PO 数量、平均 PO 金额等。  
  
 BAM 支持的度量值包括：  
  
-   Sum  
  
-   Count  
  
-   平均值  
  
-   最低要求  
  
-   最大值  
  
> [!NOTE]
>  BAM 实时聚合 (RTA) 功能目前不支持“最小值”和“最大值”度量值。 您可以使用这些度量值，但将 Excel 透视表标记为 RTA 时，“最小值”和“最大值”将被忽略。  
  
### <a name="to-add-new-measures"></a>若要添加新度量值  
  
1.  在 BAM 视图向导中，单击**下一步**直到你看到**新 BAM 视图： 聚合维度和度量值**页。 单击**新度量值**。  
  
2.  键入你的度量值的名称。  
  
3.  从下拉列表中选择**基本数据项**。  
  
4.  单击**聚合类型**你想要使用。 可选类型包括：  
  
    -   Sum  
  
    -   Count  
  
    -   平均值  
  
    -   最小值 （不支持 Rta）。  
  
    -   最大值（RTA 不支持）  
  
5.  单击 **“确定”**。 在你完成添加维度和度量值后，单击**下一步**。  
  
6.  上**新 BAM 视图： 摘要**页上，查看有关您的新视图的信息，然后单击**下一步**。  
  
7.  单击**完成**完成**BAM 视图向导**。  
  
 将度量值和维度添加到 BAM 视图后，就可以将这些项添加到 Excel 工作簿的透视表中。 有关创建数据透视表的详细信息，请参阅[如何使用数据透视表](../core/how-to-use-the-pivottable.md)。  
  
## <a name="see-also"></a>另请参阅  
 [定义维度](../core/defining-dimensions.md)