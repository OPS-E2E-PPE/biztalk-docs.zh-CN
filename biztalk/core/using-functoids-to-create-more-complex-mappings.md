---
title: 使用 Functoid 创建更复杂的映射 |Microsoft 文档
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
ms.openlocfilehash: 736b6fa99844182c59db582182056faea1d3f322
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287157"
---
# <a name="using-functoids-to-create-more-complex-mappings"></a>使用 Functoid 创建更复杂的映射

## <a name="overview"></a>概述
Functoid 在许多映射方案中都起到非常重要的作用。 如果不使用 functoid，虽然可以复制元素数据和属性数据，但将无法有效地处理这些值本身。 使用 functoid，几乎可以执行任何转换。 例如，使用 functoid，您可以从完全不同的位置获取两个值，将这两个值相加，然后将所得的和置于目标架构中。  
  
 Functoid 出现在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱中，每个类别，当你编辑 BizTalk 映射时的一个工具箱选项卡。 在打开工具箱并通过单击相应的选项卡选择 functoid 类别后，即可将所需的 functoid 拖至网格页上。 然后，您可以在 functoid 与 schema 节点或其他 functoid 之间创建输入链接和输出链接。 输入链接对应于输入参数，从左侧进入 functoid；输出链接对应于输出参数，从 functoid 右侧引出。  
  
 与其他映射元素相似，functoid 也具有属性。 functoid 的最重要的属性之一是其输入参数集。 有关详细信息，请参阅[如何向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。  
  
 本部分提供有关在 BizTalk 映射内使用 functoid 的逐步说明。 有关 functoid 参考信息，请参阅**Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤 
  
-   [如何打开 Functoid 工具箱](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [如何在向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [编辑 Functoid 属性和输入的参数](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [如何选择多个 Functoid](../core/how-to-select-multiple-functoids.md)  
  
-   [如何删除 Functoid](../core/how-to-delete-functoids.md)  
  
-   [如何复制、 剪切和粘贴 Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md)