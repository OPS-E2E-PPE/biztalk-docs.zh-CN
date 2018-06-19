---
title: 如何修改聚合 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], modifying
- BAM portal, aggregations
ms.assetid: dd5ce211-32d3-4e1d-8ee0-1225ec2c45fb
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6f5f157da15cb53da41d6735524ed502cd35156
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254677"
---
# <a name="how-to-modify-an-aggregation"></a>如何修改聚合
在 Office Web 组件中使用数据透视表的方法与在 Excel 中使用数据透视表的方法相同。 可以添加和移除行、列及筛选器，以便生成可在聚合数据上创建警报的视图。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须拥有包含聚合的已部署视图。  
  
### <a name="to-modify-an-aggregation"></a>修改聚合  
  
1.  上**聚合**页上，从**数据透视表字段列表**窗口中，将与你想要在行中显示并将它们放要将行字段添加的网格左侧列的数据字段。 如果没有看到该字段列表，请在数据透视表放置区域的边框内单击，确保出现“显示字段列表”。 若要查看具有级别的字段的详细的可用级别，请单击相应字段旁的加号 (+)。  
  
2.  将与你想要在列标记为拖放区域上显示的数据的字段拖**将列字段拖至此处**。 只有指定为计数字段或进度字段的字段才能拖到此区域中。  
  
3.  如果添加多个数据字段，排列所需的顺序中的这些字段： 右键单击数据字段，指向**顺序**的快捷菜单上，并在使用命令**顺序**菜单可将字段。  
  
4.  若要重新排列字段，请将它们从一个区域拖放到另一个区域中。 若要删除字段，请将该字段拖出数据透视表，放到导航框架上。  
  
5.  从数据透视表的“汇总”列中，用鼠标右键单击要基于其汇总值设置警报的单元格。 选择**创建警报**以打开警报管理页。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 门户上的聚合页](../core/aggregations-on-the-bam-portal-page.md)   
 [如何设置警报](../core/how-to-set-an-alert.md)