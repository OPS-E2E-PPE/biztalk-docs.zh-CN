---
title: 节点的控制实例消息结构和变体 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af8e6ce-282d-4318-a538-046b423ef033
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14be46a217bae51a31b785d4ad60700ecd7f30d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263352"
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a><span data-ttu-id="e98cd-102">控制实例消息结构和变体的节点</span><span class="sxs-lookup"><span data-stu-id="e98cd-102">Nodes That Control Instance Message Structure and Variations</span></span>
<span data-ttu-id="e98cd-103">一些用于创建在 BizTalk 编辑器中的架构的节点类型控制结构和实例消息中的变体。</span><span class="sxs-lookup"><span data-stu-id="e98cd-103">Some of the node types that you use to create schemas in BizTalk Editor control the structure of, and variations within, instance messages.</span></span> <span data-ttu-id="e98cd-104">您使用**序列组**节点指定一系列元素必须出现在实例消息中的相应位置特定的顺序。</span><span class="sxs-lookup"><span data-stu-id="e98cd-104">You use **Sequence Group** nodes to specify that a sequence of elements must occur in a specific order in the corresponding location in an instance message.</span></span> <span data-ttu-id="e98cd-105">您使用**选择组**节点指定集合中的元素的一个元素可以出现在实例消息中的相应位置。</span><span class="sxs-lookup"><span data-stu-id="e98cd-105">You use **Choice Group** nodes to specify that one element from a collection of elements can occur in the corresponding location in an instance message.</span></span> <span data-ttu-id="e98cd-106">您使用**全部组**节点指定所有指定的元素可以在实例消息中的相应位置出现在任何顺序，但仅出现一次。</span><span class="sxs-lookup"><span data-stu-id="e98cd-106">You use **All Group** nodes to specify that all of the specified elements can occur in any order, but only once, at the corresponding location in an instance message.</span></span> <span data-ttu-id="e98cd-107">**\<等效\>** 节点及其子节点显示在架构树中以指示其中基于派生的多态性是起作用，允许一种许多相关复杂数据类型出现在实例消息中的位置实例消息中的相应位置。</span><span class="sxs-lookup"><span data-stu-id="e98cd-107">**\<Equivalent\>** nodes and their child nodes are displayed in the schema tree to indicate locations in instance messages where derivation-based polymorphism is in effect, allowing one of many related complex data types to occur in the corresponding location in an instance message.</span></span>  
  
 <span data-ttu-id="e98cd-108">本部分的其余部分提供有关此类节点的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e98cd-108">The remainder of this section provides additional information about this class of nodes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e98cd-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="e98cd-109">In This Section</span></span>  
  
-   [<span data-ttu-id="e98cd-110">“顺序组”节点</span><span class="sxs-lookup"><span data-stu-id="e98cd-110">Sequence Group Nodes</span></span>](../core/sequence-group-nodes.md)  
  
-   [<span data-ttu-id="e98cd-111">“选择组”节点</span><span class="sxs-lookup"><span data-stu-id="e98cd-111">Choice Group Nodes</span></span>](../core/choice-group-nodes.md)  
  
-   [<span data-ttu-id="e98cd-112">“全部组”节点</span><span class="sxs-lookup"><span data-stu-id="e98cd-112">All Group Nodes</span></span>](../core/all-group-nodes.md)  
  
-   [<span data-ttu-id="e98cd-113">\<等效\>节点和及其子节点</span><span class="sxs-lookup"><span data-stu-id="e98cd-113">\<Equivalent\> Nodes and Their Child Nodes</span></span>](../core/equivalent-nodes-and-their-child-nodes.md)