---
title: 如何优化架构树视图 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab4ad6b5-5bbd-443b-9041-6cddf9d64735
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeeddd0893b80c1c7b37b2d0ee5f9f6cd68849d6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-optimize-the-schema-tree-view"></a>如何优化架构树视图
你可以使用 **相关性视图** BizTalk 映射程序来优化的源和/或目标架构树中。 本主题提供了有关如何执行该操作的说明。  
  
 关联视图使用同级合并来折叠非关联架构元素，以提供更全面的架构视图。 这进一步降低了滚动的需求，可帮助您专注于使用架构和映射。  
  
 下图显示了关联视图处于关闭状态时的架构。 该架构窗格显示所有节点，而不考虑这些节点是否属于任何关系。  
  
 ![架构相关性视图关闭时](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")  
  
 单击![切换到相关性视图](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")开启相关性视图映射器实用程序功能区上的图标。 您可以切换到源架构和/或目标架构的关联视图，单击源架构和目标架构各自的图标。  
  
 当切换到一个架构的关联视图时：  
  
-   所有不包含任何链接的记录元素或其子字段元素都将被折叠。  
  
-   不具有任何链接的所有后续节点合并和替换为![合并隐藏的节点](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标。 BizTalk 映射器可最少查找两个可合并的连续非关联节点。 您可以将鼠标移至图标上以查看合并节点的列表。 请注意，信息提示将只能列出头三个合并节点的名称，即使还存在更多的合并节点。 你可以通过单击查看所有节点![合并隐藏的节点](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标。  
  
    > [!NOTE]
    >  有关信息提示的详细信息，请参阅[视图信息提示和工具提示如何](../core/how-to-view-infotip-and-tooltip.md)。  
  
## <a name="prerequisites"></a>先决条件  
 此操作要求 BizTalk 映射器处于运行状态。  
  
## <a name="to-optimize-the-schema-tree-view"></a>若要优化架构树视图，请执行以下操作：  
 在映射器实用程序功能区中，打开用于源和/或目标架构的相关性视图上通过单击相应![切换到相关性视图](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")图标。 下图显示了在关联视图处于打开状态时的相同架构。 所有非相关节点替换为![合并隐藏的节点](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标以提供更紧凑视图的架构。  
  
 ![当相关性视图为 ON 时的架构](../core/media/on-schema.gif "On_schema")  
  
 当扩展在源和/或目标架构中，合并后的节点![合并隐藏的节点](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")更改为![合并所示节点](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence")图标。  
  
> [!NOTE]
>  可以按 Ctrl+M、Ctrl+E 或 Ctrl+M、Ctrl+C，分别展开或折叠源架构中的树节点。 同样，你可以按 CTRL + M、 CTRL + E 或 CTRL + M、 CTRL + C 以展开或折叠分别目标架构中的树节点。 此外可以按 Ctrl + M、 Ctrl + H 或 Ctrl + M、 Ctrl + D 有关源或目标分别合并。 映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在 BizTalk 映射程序中使用增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md)