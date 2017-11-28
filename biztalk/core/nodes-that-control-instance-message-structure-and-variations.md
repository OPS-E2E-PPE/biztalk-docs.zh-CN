---
title: "控制实例的节点消息结构和变体 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af8e6ce-282d-4318-a538-046b423ef033
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0733be2e3331e02bff38a7b93d31b8cafd5ec582
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a><span data-ttu-id="4e584-102">控制实例消息结构和变体的节点</span><span class="sxs-lookup"><span data-stu-id="4e584-102">Nodes That Control Instance Message Structure and Variations</span></span>
<span data-ttu-id="4e584-103">在 BizTalk 编辑器中用于创建架构的某些节点类型控制着实例消息的结构和实例消息中的变体。</span><span class="sxs-lookup"><span data-stu-id="4e584-103">Some of the node types that you use to create schemas in BizTalk Editor control the structure of, and variations within, instance messages.</span></span> <span data-ttu-id="4e584-104">你使用**序列组**节点若要指定的元素序列必须对实例消息中的对应位置中的特定顺序发生。</span><span class="sxs-lookup"><span data-stu-id="4e584-104">You use **Sequence Group** nodes to specify that a sequence of elements must occur in a specific order in the corresponding location in an instance message.</span></span> <span data-ttu-id="4e584-105">你使用**选项组**节点指定的元素集合中的一个元素会在实例消息中的对应位置。</span><span class="sxs-lookup"><span data-stu-id="4e584-105">You use **Choice Group** nodes to specify that one element from a collection of elements can occur in the corresponding location in an instance message.</span></span> <span data-ttu-id="4e584-106">你使用**所有组**节点指定的所有指定的元素可能发生的任何顺序，但一次，在实例消息中的相应位置。</span><span class="sxs-lookup"><span data-stu-id="4e584-106">You use **All Group** nodes to specify that all of the specified elements can occur in any order, but only once, at the corresponding location in an instance message.</span></span> <span data-ttu-id="4e584-107">**\<等效 >**节点及其子节点显示在指示的位置实例消息中基于派生的多态性起作用，并允许之一很多相关的复杂数据类型出现在相应的架构树实例消息中的位置。</span><span class="sxs-lookup"><span data-stu-id="4e584-107">**\<Equivalent>** nodes and their child nodes are displayed in the schema tree to indicate locations in instance messages where derivation-based polymorphism is in effect, allowing one of many related complex data types to occur in the corresponding location in an instance message.</span></span>  
  
 <span data-ttu-id="4e584-108">本部分的其余部分将提供有关此类节点的其他信息。</span><span class="sxs-lookup"><span data-stu-id="4e584-108">The remainder of this section provides additional information about this class of nodes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e584-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="4e584-109">In This Section</span></span>  
  
-   [<span data-ttu-id="4e584-110">序列组节点</span><span class="sxs-lookup"><span data-stu-id="4e584-110">Sequence Group Nodes</span></span>](../core/sequence-group-nodes.md)  
  
-   [<span data-ttu-id="4e584-111">选择组节点</span><span class="sxs-lookup"><span data-stu-id="4e584-111">Choice Group Nodes</span></span>](../core/choice-group-nodes.md)  
  
-   [<span data-ttu-id="4e584-112">所有组节点</span><span class="sxs-lookup"><span data-stu-id="4e584-112">All Group Nodes</span></span>](../core/all-group-nodes.md)  
  
-   [<span data-ttu-id="4e584-113">\<等效 > 节点和它们的子节点</span><span class="sxs-lookup"><span data-stu-id="4e584-113">\<Equivalent> Nodes and Their Child Nodes</span></span>](../core/equivalent-nodes-and-their-child-nodes.md)