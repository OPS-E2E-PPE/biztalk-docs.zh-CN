---
title: 控制实例的节点消息结构和变体 |Microsoft 文档
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
ms.openlocfilehash: baa82def3f62c6a603ef67e098e53b48a49013a3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970923"
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a><span data-ttu-id="a9e9e-102">控制实例消息结构和变体的节点</span><span class="sxs-lookup"><span data-stu-id="a9e9e-102">Nodes That Control Instance Message Structure and Variations</span></span>
<span data-ttu-id="a9e9e-103">在 BizTalk 编辑器中用于创建架构的某些节点类型控制着实例消息的结构和实例消息中的变体。</span><span class="sxs-lookup"><span data-stu-id="a9e9e-103">Some of the node types that you use to create schemas in BizTalk Editor control the structure of, and variations within, instance messages.</span></span> <span data-ttu-id="a9e9e-104">你使用**序列组**节点若要指定的元素序列必须对实例消息中的对应位置中的特定顺序发生。</span><span class="sxs-lookup"><span data-stu-id="a9e9e-104">You use **Sequence Group** nodes to specify that a sequence of elements must occur in a specific order in the corresponding location in an instance message.</span></span> <span data-ttu-id="a9e9e-105">你使用**选项组**节点指定的元素集合中的一个元素会在实例消息中的对应位置。</span><span class="sxs-lookup"><span data-stu-id="a9e9e-105">You use **Choice Group** nodes to specify that one element from a collection of elements can occur in the corresponding location in an instance message.</span></span> <span data-ttu-id="a9e9e-106">你使用**所有组**节点指定的所有指定的元素可能发生的任何顺序，但一次，在实例消息中的相应位置。</span><span class="sxs-lookup"><span data-stu-id="a9e9e-106">You use **All Group** nodes to specify that all of the specified elements can occur in any order, but only once, at the corresponding location in an instance message.</span></span> <span data-ttu-id="a9e9e-107">**\<等效\>** 节点及其子节点显示在架构树，以指示的位置实例消息中基于派生的多态性起作用，并允许之一很多相关的复杂数据类型出现在实例消息中的对应位置。</span><span class="sxs-lookup"><span data-stu-id="a9e9e-107">**\<Equivalent\>** nodes and their child nodes are displayed in the schema tree to indicate locations in instance messages where derivation-based polymorphism is in effect, allowing one of many related complex data types to occur in the corresponding location in an instance message.</span></span>  
  
 <span data-ttu-id="a9e9e-108">本部分的其余部分将提供有关此类节点的其他信息。</span><span class="sxs-lookup"><span data-stu-id="a9e9e-108">The remainder of this section provides additional information about this class of nodes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9e9e-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="a9e9e-109">In This Section</span></span>  
  
-   [<span data-ttu-id="a9e9e-110">“顺序组”节点</span><span class="sxs-lookup"><span data-stu-id="a9e9e-110">Sequence Group Nodes</span></span>](../core/sequence-group-nodes.md)  
  
-   [<span data-ttu-id="a9e9e-111">“选择组”节点</span><span class="sxs-lookup"><span data-stu-id="a9e9e-111">Choice Group Nodes</span></span>](../core/choice-group-nodes.md)  
  
-   [<span data-ttu-id="a9e9e-112">“全部组”节点</span><span class="sxs-lookup"><span data-stu-id="a9e9e-112">All Group Nodes</span></span>](../core/all-group-nodes.md)  
  
-   [<span data-ttu-id="a9e9e-113">\<等效\>节点和它们的子节点</span><span class="sxs-lookup"><span data-stu-id="a9e9e-113">\<Equivalent\> Nodes and Their Child Nodes</span></span>](../core/equivalent-nodes-and-their-child-nodes.md)