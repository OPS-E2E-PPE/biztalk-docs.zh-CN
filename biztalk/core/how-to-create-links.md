---
title: 如何创建链接 |Microsoft 文档
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
ms.openlocfilehash: 01171ddeaab8424087e8f04c29fb747e9479c1eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250189"
---
# <a name="how-to-create-links"></a>如何创建链接
创建从链接**记录**或**字段**到源架构中的节点**记录**或**字段**目标架构中的节点是最基本在创建地图的活动。 本主题为此活动的不同用法（包括创建指向和来自 functoid 的链接）提供了分步说明。 有关使用 functoid 的其他信息，请参阅[创建更复杂的映射到使用 Functoid](../core/using-functoids-to-create-more-complex-mappings.md)。  
  
 本主题中的说明假定您已经打开了一个 BizTalk 映射，并且已为该映射选择了源架构和目标架构。 有关打开地图和选择地图的架构的详细信息，请参阅[管理映射中项目](../core/managing-maps-within-projects.md)。  
  
### <a name="to-create-links-between-field-and-record-nodes"></a>创建“字段”与“记录”节点之间的链接  
  
1.  BizTalk 映射程序中，在将拖动**字段**或**记录**节点到将源架构树**字段**或**记录**目标架构中的节点树。  
  
     **-或者-**  
  
2.  BizTalk 映射程序中，在将拖动**字段**或**记录**节点从将目标架构树**字段**或**记录**源架构中的节点树。  
  
 创建链接时，应注意以下事项：  
  
-   数据类型**字段**或**记录**源架构树中的节点应与匹配的数据类型**字段**或**记录**它的节点在目标架构树的链接。  
  
-   如果**字段**或**记录**源架构中的节点是可选的和特定的源实例消息不包含相应元素或属性，不会创建 BizTalk 映射程序相应的元素或属性在目标实例消息中，即使**字段**或**记录**节点具有它们在映射中之间的直接链接。  
  
-   无法将链接到**字段**或**记录**具有常数值与之关联的目标架构中的节点。 另一方面，可以将链接到所需**字段**或**记录**具有与之关联的默认值的目标架构中的节点。 但是请注意，在测试映射时将使用该默认值。  
  
-   无法创建链接，或从**Any 元素**，**任何属性**，**序列组**，或**选项组**节点。 有关这些类型的节点的详细信息，请参阅以下主题，请参阅[任何元素节点](../core/any-element-nodes.md)，[序列组节点](../core/sequence-group-nodes.md)或[选择组节点](../core/choice-group-nodes.md)。  
  
-   可能需要展开架构树以查看要映射的字段。 有关详细信息，请参阅[如何展开和折叠架构树](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)。  
  
#### <a name="to-create-links-between-record-or-field-nodes-and-functoids"></a>创建“记录”或“字段”节点与 functoid 之间的链接  
  
1.  BizTalk 映射程序中，在将拖动**记录**或**字段**从源或目标架构中网格页 functoid 的节点。  
  
     **-或者-**  
  
2.  从网格页到拖动 functoid**记录**或**字段**源或目标架构中的节点。  
  
     当创建之间的链接**记录**或**字段**节点中的源架构和 functoid，创建该 functoid 的输入。 当创建之间的链接**记录**或**字段**节点中的目标架构和 functoid，您正从该 functoid 中创建一个输出。  
  
    > [!IMPORTANT]
    >  不能链接之间 functoid 和**Any 元素**节点或**任何属性**节点。  
  
    > [!NOTE]
    >  你必须首先将添加 functoid 到网格页添加之间的链接之前**记录**或**字段**节点和该 functoid。 有关将 functoid 添加到网格页的详细信息，请参阅[如何向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。 另请参阅[向地图添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)。  
  
    > [!NOTE]
    >  无法将链接到**字段**具有常数值与之关联的目标架构中的节点。 另一方面，可以将链接到所需**字段**具有与之关联的默认值的目标架构中的节点。 但是请注意，在测试映射时将使用该默认值。  
  
#### <a name="to-create-links-between-functoids"></a>创建 functoid 之间的链接  
  
-   在 BizTalk 映射器中，将一个 functoid 拖至网格页中的另一个 functoid。  
  
    > [!NOTE]
    >  链接在网格页中是按照从左到右的顺序进行处理的。 不能创建从一个 functoid 到直接位于其上方或下方的另一个 functoid 的链接。 functoid 之间的链接被解释为链接表示从左侧的 functoid 输出并输入到右侧的 functoid。  
  
### <a name="to-change-the-endpoint-of-a-link"></a>更改链接的终结点  
 在映射中，您可以将链接的终结点拖放到另一个节点或 functoid 上。  
  
 更改链接的终结点：  
  
1.  单击您要为其更改源或目标节点/functoid 的链接。 该链接的终结点变为粗体。  
  
2.  在任何粗体终结点上按下鼠标键并将该链接拖动到所需的节点/functoid。 这会将链接从以前的节点/functoid 更改为新节点/functoid。  
  
 但是，对于无效链接，您无法执行此操作，如：  
  
-   添加链接作为日期/时间 functoid 的输入链接。 日期/时间 functoid 不需要任何输入链接。  
  
-   复制中间 functoid 中的链接。  
  
     如果您将 Node1 链接到 Node2，并且还将 Node1 链接到 Node3，则不能拖动 Node2 上链接的终结点以进行更改并链接到 Node3。  
  
## <a name="see-also"></a>另请参阅  
 [使用链接以指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)