---
title: 如何优化架构树视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab4ad6b5-5bbd-443b-9041-6cddf9d64735
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3655e3bdf60aafc243c2d415f70da26224140a67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384470"
---
# <a name="how-to-optimize-the-schema-tree-view"></a>如何优化架构树视图
可以使用**关联视图**BizTalk 映射器以优化源和/或目标架构树中。 本主题提供有关如何执行该操作的说明。  
  
 关联视图使用同级合并来折叠非相关架构元素，以提供更精简的架构的视图。 这进一步降低滚动并可帮助你专注于使用架构和映射你的要求了。  
  
 下图显示了关联视图时的架构已关闭。 架构窗格显示所有节点，不管节点是否属于任何关系。  
  
 ![关联视图关闭时的架构](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")  
  
 单击![切换到关联视图](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")打开关联视图映射器实用工具功能区上的图标。 可以切换到的任何一个或源架构和目标架构中; 关联视图单击源和目标架构各自的图标。  
  
 当切换到关联视图的架构：  
  
-   没有为其任何链接的所有记录元素或其子字段元素处于折叠状态。  
  
-   不包含任何链接的所有后续节点都会合并并替换为![合并节点隐藏](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标。 BizTalk 映射器查找两个可合并的连续非关联节点的最小值。 可以将鼠标移到该图标可以查看合并节点的列表。 请注意，信息提示将仅列出的前三个合并节点，名称即使有更多合并的节点。 可以通过单击查看所有节点![合并节点隐藏](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标。  
  
    > [!NOTE]
    >  有关信息提示的详细信息，请参阅[如何查看信息提示和工具提示](../core/how-to-view-infotip-and-tooltip.md)。  
  
## <a name="prerequisites"></a>先决条件  
 此操作需要 BizTalk 映射器正在运行。  
  
## <a name="to-optimize-the-schema-tree-view"></a>若要优化架构树视图  
 在映射器实用工具功能区中，源和/或目标架构的关联视图通过单击来打开各自![切换到关联视图](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")图标。 下图显示了相同的架构关联视图时启用。 所有非关联节点替换为![合并节点隐藏](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标以提供更精简的架构的视图。  
  
 ![当关联视图为 ON 时的架构](../core/media/on-schema.gif "On_schema")  
  
 展开合并的节点在源和/或目标架构中，当![合并节点隐藏](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")更改为![合并节点显示](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence")图标。  
  
> [!NOTE]
>  可以按 CTRL + M、 CTRL + E 或 CTRL + M、 CTRL + C 将分别展开或折叠源架构中的树节点。 同样，可以按 CTRL + M、 CTRL + E 或 CTRL + M、 CTRL + C 将分别展开或折叠树节点在目标架构中。 此外可以按 Ctrl + M、 Ctrl + H 或 Ctrl + M、 Ctrl + D 的源或目标分别合并。 映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器中的增强功能](../core/using-enhanced-features-in-biztalk-mapper.md)