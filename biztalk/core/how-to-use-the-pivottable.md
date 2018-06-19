---
title: 如何使用数据透视表 |Microsoft 文档
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
ms.openlocfilehash: aed416f7a04392804c4c031a69940c4229eabe99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256653"
---
# <a name="how-to-use-the-pivottable"></a>如何使用透视表
当您定义了包含维度和度量的 BAM 视图后，您需要更新与该视图相关联的一个或多个透视表。  
  
 Excel 中的透视表报告是一个交互式表，使用它可以轻松地合并和比较大量的数据。 表中的行值和列值可以循环滚动，以查看所显示数据的不同摘要。 您还可以使用透视表对数据执行计算，例如求聚合计数或平均数。  
  
 创建透视表后，要使用透视表，请执行以下过程中的步骤。 有关使用透视表的详细信息，请参阅 Microsoft Excel 文档。  
  
> [!NOTE]
>  创建实时聚合透视表时，它最多可以包含 14 个维度级别。  
  
> [!IMPORTANT]
>  如果在 Excel 工作表上定义多个透视表，且活动返回大的数据集，则最终的表可能增大并相互重叠。 在这种情况下，在刷新数据时将收到“数据透视表不能覆盖另一个数据透视表”错误消息。 通过在透视表间添加列或行以允许表增大而不发生重叠，可以更正此错误。  
  
### <a name="to-use-the-pivottable"></a>使用透视表  
  
1.  创建一个要与透视表一起使用的 BAM 视图。 有关创建 BAM 视图的详细信息，请参阅[定义业务活动视图](../core/defining-a-bam-view.md)  
  
2.  使用**数据透视表字段列表**，拖放一个或多个可用维度到的列和行区域的数据透视表模板。  
  
3.  使用**数据透视表字段列表**，拖放一个或多个可用度量值数据项区域的数据透视表模板。  
  
     更新透视表时，您将看到该表中填充了示例数据。 这可帮助您确定如何配置透视表。  
  
4.  使用**数据透视表**工具栏上，一个数据透视表与图表相关联。  
  
5.  保存您的 Excel 工作簿。