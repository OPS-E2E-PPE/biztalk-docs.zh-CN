---
title: 如何修改聚合 |Microsoft Docs
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
ms.openlocfilehash: a073b454a270de2e7ac4f78c421513936d8f7ecd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336150"
---
# <a name="how-to-modify-an-aggregation"></a>如何修改聚合
在使用数据透视表的相同方式报告在 Excel 中的 Office Web 组件中使用数据透视表报表。 您可以添加和删除行、 列和筛选器，以生成可以在其创建警报的聚合数据的视图。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须具有一个包含聚合的已部署的视图。  
  
### <a name="to-modify-an-aggregation"></a>若要修改聚合  
  
1.  上**聚合**页上，从**数据透视表字段列表**窗口中，将使用你想要在行中显示它们放到左侧网格以添加行字段的列的数据字段。 如果看不到字段列表中，在数据透视表放置区域，边框内单击，并确保显示字段列表会显示。 若要查看具有级别的字段中提供了哪些级别的详细信息，请单击相应字段旁的加号 （+）。  
  
2.  将与你想要显示在标记为拖放区域的列的数据字段拖**将列字段拖至此处**。 可被指定为计数或进度字段的唯一字段拖动到此区域。  
  
3.  如果添加多个数据字段，排列这些字段中所需的顺序： 右键单击数据字段，指向**顺序**快捷菜单上，并在使用命令**顺序**菜单移动这些字段。  
  
4.  若要重新排列字段，将它们从一个区域到另一个。 若要删除字段，将其拖出拖到导航框架数据透视表报表。  
  
5.  从数据透视表报表中的总计列中，右键单击包含要设置警报的总的单元格。 选择**创建警报**打开警报管理页。  
  
## <a name="see-also"></a>请参阅  
 [BAM 门户上的聚合页](../core/aggregations-on-the-bam-portal-page.md)   
 [如何设置警报](../core/how-to-set-an-alert.md)