---
title: 如何创建链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 670b831f-be03-4612-93d5-a894f7bb3c11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4309e806d81427c0c8003300de27f346c229c5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339438"
---
# <a name="how-to-create-links"></a>如何创建链接
创建从链接**记录**或**字段**节点在源架构中的**记录**或**字段**目标架构中的节点是最基本创建映射过程中的活动。 本主题提供有关此活动，包括创建指向和来自 functoid 的链接的多个变体的分步说明。 有关使用 functoid 的其他信息，请参阅[使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)。  
  
 本主题中的说明假定你已打开，BizTalk 映射，但选择映射源和目标架构。 有关打开映射和选择的映射架构的详细信息，请参阅[管理映射中的项目](../core/managing-maps-within-projects.md)。  
  
### <a name="to-create-links-between-field-and-record-nodes"></a>若要创建字段和记录节点之间的链接  
  
1. 在 BizTalk 映射器中拖动**字段**或**记录**到源架构树中的节点**字段**或**记录**目标架构中的节点树。  
  
    **- Or -**  
  
2. 在 BizTalk 映射器中拖动**字段**或**记录**到目标架构树中的节点**字段**或**记录**源架构中的节点树。  
  
   有几种方法创建链接时要考虑：  
  
-   数据类型**字段**或**记录**源架构树中的节点应与匹配的数据类型**字段**或者**记录**它的节点链接的目标架构树中。  
  
-   如果**字段**或**记录**源架构中的节点是可选的和特定的源实例消息不包含相应元素或属性，BizTalk 映射器不会创建相应元素或属性在目标实例消息中，即使**字段**或**记录**节点具有相互映射中的直接链接。  
  
-   不能链接到**字段**或**记录**具有与之关联的常数值的目标架构中的节点。 但是，你可以链接到所需**字段**或**记录**有与之关联的默认值的目标架构中的节点。 但是，请注意，测试映射时，将使用默认值。  
  
-   不能创建一个链接，面向或源自**任何元素**，**任何属性**，**序列组**，或者**选择组**节点。 有关这些类型的节点的详细信息，请参阅以下主题，请参阅[Any 元素节点](../core/any-element-nodes.md)，[序列组节点](../core/sequence-group-nodes.md)或[所选组节点](../core/choice-group-nodes.md)。  
  
-   您可能需要展开架构树以查看要映射的字段。 有关详细信息，请参阅[如何展开和折叠架构树](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)。  
  
#### <a name="to-create-links-between-record-or-field-nodes-and-functoids"></a>若要创建记录或字段节点和 functoid 之间的链接  
  
1.  在 BizTalk 映射器中拖动**记录**或**字段**到网格页的 functoid 将源或目标架构中的节点。  
  
     **- Or -**  
  
2.  将提取 functoid 拖至网格页中**记录**或**字段**源或目标架构中的节点。  
  
     当创建之间的链接**记录**或**字段**源架构和 functoid 中的节点，创建该 functoid 的输入。 当创建之间的链接**记录**或**字段**目标架构和 functoid 中的节点，您要从该 functoid 创建输出。  
  
    > [!IMPORTANT]
    >  您不能 functoid 之间的链接和一个**Any 元素**节点或**任何属性**节点。  
  
    > [!NOTE]
    >  必须首先添加一个 functoid 到网格页后，才能添加之间的链接**记录**或**字段**节点与该 functoid。 有关将 functoid 添加到网格页的详细信息，请参阅[如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。 另请参阅[向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)。  
  
    > [!NOTE]
    >  不能链接到**字段**具有与之关联的常数值的目标架构中的节点。 但是，你可以链接到所需**字段**有与之关联的默认值的目标架构中的节点。 但是，请注意，测试映射时，将使用默认值。  
  
#### <a name="to-create-links-between-functoids"></a>若要创建 functoid 之间的链接  
  
-   在 BizTalk 映射器中，将一个 functoid 拖至网格页中的另一个 functoid。  
  
    > [!NOTE]
    >  链接是已处理从左到右的网格页中。 不能进行从一个 functoid 到另一个 functoid 的正上方或下方的链接。 Functoid 之间的链接被解释为链接表示输出从 functoid 到左侧和右侧 functoid 的输入。  
  
### <a name="to-change-the-endpoint-of-a-link"></a>若要更改链接的终结点  
 在映射中，您可以拖动链接的终结点，并将它放通过另一个节点或 functoid。  
  
 若要更改链接的终结点：  
  
1. 单击你想要更改源或目标节点 /functoid 的链接。 链接的终结点变为粗体。  
  
2. 按下鼠标键在任何粗体终结点，并将链接拖到所需的节点 /functoid。 这会更改从上一节点 functoid 链接到新节点 /functoid。  
  
   但是，无法执行此操作对于无效链接，例如：  
  
-   添加链接作为日期/时间 functoid 的输入。 日期/时间 functoid 不需要任何输入的链接。  
  
-   复制中间 functoid 中的链接。  
  
     如果到 Node2，并且还从节点 1 到 Node3 链接节点 1，不能拖动 Node2 更改并将链接到 Node3 上链接的终结点。  
  
## <a name="see-also"></a>请参阅  
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)