---
title: 使用 Functoid 创建更复杂的映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d53e3a3-5ccd-4733-8c2f-3101e41fca61
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e16b692f3f91aff47e978080be124220db68a89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247227"
---
# <a name="using-functoids-to-create-more-complex-mappings"></a>使用 Functoid 创建更复杂的映射

## <a name="overview"></a>概述
Functoid 在许多映射方案中扮演着重要角色。 如果不使用 functoid，您可以复制元素和属性数据，但您不能有效地，处理这些值本身。 使用 functoid，则有可能的几乎任何转换。 例如，functoid 您利用两个值从完全不同的位置，将它们相加，以及将其放在目标架构中。  
  
 Functoid 显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱中，每个类别，编辑 BizTalk 映射时的对应一个工具箱选项卡。 在打开工具箱并通过单击相应的选项卡选择 functoid 类别后，您的 functoid 拖到网格页上。 然后，您将创建输入和输出之间 functoid 与 schema 节点或另一个 functoid 的链接。 输入的链接对应于输入参数，并且会导致 functoid 从左;输出链接对应于输出参数，并使 functoid 右侧。  
  
 像其他地图元素，functoid 也具有属性。 Functoid 的最重要属性之一是其组的输入参数。 有关详细信息，请参阅[如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。  
  
 本部分提供使用 BizTalk 映射内 functoid 的分步说明。 有关 functoid 的参考信息，请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤 
  
-   [如何打开 Functoid 工具箱](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [如何选择多个 Functoid](../core/how-to-select-multiple-functoids.md)  
  
-   [如何删除 Functoid](../core/how-to-delete-functoids.md)  
  
-   [如何复制、 剪切和粘贴 Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md)