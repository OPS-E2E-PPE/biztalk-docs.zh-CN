---
title: 如何调整架构选取器，并展开和折叠架构树 |Microsoft Docs
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
ms.openlocfilehash: 682077ffc044c3f293d5bf7f2d3c2a1d81a4c918
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993046"
---
# <a name="how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees"></a>如何调整架构选取器，并展开和折叠架构树
开发 BizTalk 映射时，可能需要展开和折叠源架构树及目标架构树，以显示或隐藏各 schema 节点。 本主题提供分步说明来调整架构选取器，并可展开和折叠架构树。  

## <a name="resize-the-schema-picker"></a>调整架构选取器大小

在创建映射时，添加源架构和目标架构。 当添加或替换架构时，此时会打开 BizTalk 类型选取器窗口中，并选择您的架构。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，可以调整此类型选择器窗口的大小。 此功能，可查看您的架构的完整名称。

1. 在映射中，选择**打开目标架构**，或**打开源架构**。
2. 在中**BizTalk 类型选取器**窗口中，拖动右下角以增加或减少的窗口大小。
  
## <a name="expand-all-or-part-of-a-schema-tree"></a>展开所有或部分架构树  
  
1.  选择希望完全展开其下级架构树的节点。  
  
     所选节点必须是旁边有加号 (+) 或减号 (-) 图标的节点。  
  
2.  上**BizTalk**菜单中，或在该节点的快捷菜单，单击**展开树节点**。 此时，所选节点的所有下级节点均将完全展开。  
  
     如果所选节点的下级架构树已经完全展开，**展开树节点**菜单项被禁用。  
  
    > [!NOTE]
    >  此外，还可以按 Ctrl+M、E 来展开架构树节点。 键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
    > [!NOTE]
    >  在大型和复杂架构中，单击时**展开树节点**上包含复杂类型的节点，该架构中的某些节点可能仍会保持折叠状态。 其原因在于，递归进程只展开当前视图中出现的第一个给定复杂类型。 您必须手动展开之后出现的同一类型。 设计此行为是为了优化在复杂的大型架构中展开节点时的性能。  
  
## <a name="collapse-all-or-part-of-a-schema-tree"></a>折叠所有或部分架构树  
  
1. 选择希望完全折叠其下级架构树的节点。  
  
    所选节点必须是旁边有加号 (+) 或减号 (-) 图标的节点。  
  
2. 上**BizTalk**菜单中，或在该节点的快捷菜单，单击**折叠树节点**。  
  
    此时，所选节点的所有下级节点均将完全折叠。  
  
   > [!NOTE]
   >  此外，还可以按 Ctrl+M、C 来折叠架构树节点。 键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
    如果所选节点的下级架构树已经完全折叠，**折叠树节点**菜单项被禁用。  
  
   此操作不会记忆所选节点的各个下级节点的展开和折叠设置。 重新展开折叠的节点时，以前的设置会丢失，您必须按节点逐级展开该节点的下级架构树，或将其完全展开。  
  
### <a name="expand-a-node"></a>展开某一节点
  
- 单击要展开的节点旁边的加号 (+) 图标。  
  
  展开所选的节点。 及其子代节点是展开还是折叠取决于所选的节点的折叠方式以及其以前的展开和折叠设置。  
  
### <a name="collapse-a-node"></a>折叠节点
  
- 单击要折叠的节点旁边的减号 (-) 图标。  
  
  所选的节点处于折叠状态。  
  
  此操作将记住单个展开和折叠所选节点的下级节点的设置。 通过使用加号 (+) 图标重新展开折叠的节点时，各个下级节点以前的设置不会丢失，该节点的下级架构树将恢复为以前的状态。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器](../core/using-biztalk-mapper.md)