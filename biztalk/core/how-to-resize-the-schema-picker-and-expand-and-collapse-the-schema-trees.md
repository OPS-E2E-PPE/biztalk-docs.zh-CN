---
title: 如何调整大小架构选取器，以及展开和折叠架构树 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 267ea17d-54fe-4031-a044-719606489f24
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972be8ca5f412c39e1eb6fa2c81ccd9a21e65a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254813"
---
# <a name="how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees"></a>如何调整大小架构选取器，以及展开和折叠架构树
开发 BizTalk 映射时，可能需要展开和折叠源架构树及目标架构树，以显示或隐藏各 schema 节点。 本主题提供了分步说明，若要调整大小架构选取器，并可展开和折叠架构树。  

## <a name="resize-the-schema-picker"></a>调整大小架构选取器

在创建地图时，你可以添加一个源架构和目标架构。 当你添加或替换架构时，BizTalk 类型选取器窗口将打开，并且你选择您的架构。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，则可以调整此类型选取器窗口。 此功能允许你查看您的架构的完整名称。

1. 在映射中，选择**打开目标架构**，或**打开源架构**。
2. 在**BizTalk 类型选取器**窗口中，拖动右下角来增加或减少的窗口大小。
  
## <a name="expand-all-or-part-of-a-schema-tree"></a>展开所有或部分架构树  
  
1.  选择希望完全展开其下级架构树的节点。  
  
     所选节点必须是旁边有加号 (+) 或减号 (-) 图标的节点。  
  
2.  上**BizTalk**菜单上，或者在该节点的快捷菜单，单击**展开树节点**。 此时，所选节点的所有下级节点均将完全展开。  
  
     如果已完全展开所选节点下面的架构树，**展开树节点**菜单项被禁用。  
  
    > [!NOTE]
    >  此外，还可以按 Ctrl+M、E 来展开架构树节点。 键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
    > [!NOTE]
    >  在大型和复杂架构中，当你单击**展开树节点**包含复杂类型的节点，架构中的某些节点中可能会保留折叠状态。 其原因在于，递归进程只展开当前视图中出现的第一个给定复杂类型。 您必须手动展开之后出现的同一类型。 设计此行为是为了优化在复杂的大型架构中展开节点时的性能。  
  
## <a name="collapse-all-or-part-of-a-schema-tree"></a>折叠所有或部分架构树  
  
1.  选择希望完全折叠其下级架构树的节点。  
  
     所选节点必须是旁边有加号 (+) 或减号 (-) 图标的节点。  
  
2.  上**BizTalk**菜单上，或者在该节点的快捷菜单，单击**折叠树节点**。  
  
     此时，所选节点的所有下级节点均将完全折叠。  
  
    > [!NOTE]
    >  此外，还可以按 Ctrl+M、C 来折叠架构树节点。 键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
     如果所选节点下面的架构树已处于折叠状态，**折叠树节点**菜单项被禁用。  
  
 此操作不会记忆所选节点的各个下级节点的展开和折叠设置。 重新展开折叠的节点时，以前的设置会丢失，您必须按节点逐级展开该节点的下级架构树，或将其完全展开。  
  
### <a name="expand-a-node"></a>展开节点
  
-   单击要展开的节点旁边的加号 (+) 图标。  
  
 展开所选的节点。 及其子代节点是展开还是折叠取决于所选的节点已折叠的方式和其以前的展开和折叠设置。  
  
### <a name="collapse-a-node"></a>折叠节点
  
-   单击要折叠的节点旁边的减号 (-) 图标。  
  
 所选的节点处于折叠状态。  
  
 此操作将记住单个展开和折叠的所选节点下的节点的设置。 通过使用加号 (+) 图标重新展开折叠的节点时，各个下级节点以前的设置不会丢失，该节点的下级架构树将恢复为以前的状态。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 映射程序](../core/using-biztalk-mapper.md)