---
title: 等效的节点和及其子节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a85c6a1-6121-4849-b958-7c4bd1c7c552
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82c58b477130431ce2b115cb141af759b6614b57
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012046"
---
# <a name="equivalent-nodes-and-their-child-nodes"></a><span data-ttu-id="4c91b-102">等效的节点和及其子节点</span><span class="sxs-lookup"><span data-stu-id="4c91b-102">Equivalent Nodes and Their Child Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="4c91b-103">概述</span><span class="sxs-lookup"><span data-stu-id="4c91b-103">Overview</span></span>
<span data-ttu-id="4c91b-104">**\<等效\>** 节点及其子级中使用架构树以显示出现的复杂数据类型多形性。</span><span class="sxs-lookup"><span data-stu-id="4c91b-104">The **\<Equivalent\>** node and its children are used in the schema tree to display occurrences of complex data type polymorphism.</span></span> <span data-ttu-id="4c91b-105">在从其他复杂数据类型派生一个复杂数据类型时，XSD 内的多形性允许这些数据类型之一出现在已为其指定基本复杂数据类型的位置的实例消息中。</span><span class="sxs-lookup"><span data-stu-id="4c91b-105">When you derive one complex data type from another complex data type, polymorphism within XSD allows either of these data types to occur in instance messages in locations for which the base complex data type has been specified.</span></span> <span data-ttu-id="4c91b-106">在架构验证期间在特定位置允许多个可能的复杂数据类型之一这一事实是隐式地表示与关联的基本复杂数据类型名**基**属性**扩展**或**限制**派生的复杂数据类型的元素。</span><span class="sxs-lookup"><span data-stu-id="4c91b-106">During schema validation, the fact that one of multiple possible complex data types is allowed at a particular location is represented implicitly by the base complex data type name associated with the **base** attribute of the **extension** or **restriction** elements of the derived complex data types.</span></span> <span data-ttu-id="4c91b-107">若要使此多形性在架构树中，更显而易见**\<等效\>** 显式显示节点和子节点。</span><span class="sxs-lookup"><span data-stu-id="4c91b-107">To make this polymorphism more obvious in the schema tree, the **\<Equivalent\>** node and its child nodes are displayed explicitly.</span></span>  

 <span data-ttu-id="4c91b-108">**\<等效\>** 节点显示为子节点的基本复杂数据类型，指示有多个实例中的该位置可能会发生的复杂数据类型的出现次数消息。</span><span class="sxs-lookup"><span data-stu-id="4c91b-108">The **\<Equivalent\>** node is displayed as a child node of occurrences of the base complex data type, indicating that there are multiple complex data types that could occur at that position in an instance message.</span></span> <span data-ttu-id="4c91b-109">子节点**\<等效\>** 节点显示的值为**名称**的相应属性**complexType**显示在尖括号内的多形性的 XSD 表示形式中的元素 (\<名称\>)。</span><span class="sxs-lookup"><span data-stu-id="4c91b-109">The child nodes of the **\<Equivalent\>** node are displayed as the value of the **name** attribute of the corresponding **complexType** element in the XSD representation of the polymorphism, displayed within angle brackets (\<name\>).</span></span>  

 <span data-ttu-id="4c91b-110">**\<等效\>** 节点及其子级具有与之关联的只有两个属性：</span><span class="sxs-lookup"><span data-stu-id="4c91b-110">The **\<Equivalent\>** node and its children each have only two properties associated with them:</span></span>  

-   <span data-ttu-id="4c91b-111">**\<等效\>** 节点：**节点名称**和**基类型**</span><span class="sxs-lookup"><span data-stu-id="4c91b-111">**\<Equivalent\>** node: **Node Name** and **Base Type**</span></span>

-   <span data-ttu-id="4c91b-112">子节点：**节点名称**和**派生类型**</span><span class="sxs-lookup"><span data-stu-id="4c91b-112">Child nodes: **Node Name** and **Derivation Type**</span></span>

<span data-ttu-id="4c91b-113">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c91b-113">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="xsd-representation"></a><span data-ttu-id="4c91b-114">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="4c91b-114">XSD representation</span></span>  
 <span data-ttu-id="4c91b-115">没有任何直接 XSD 表示形式**\<等效\>** 节点及其子级。</span><span class="sxs-lookup"><span data-stu-id="4c91b-115">There is no direct XSD representation of the **\<Equivalent\>** node and its children.</span></span> <span data-ttu-id="4c91b-116">在架构树中使用此节点，可使复杂数据类型多形性表现的更为直观和明显。</span><span class="sxs-lookup"><span data-stu-id="4c91b-116">This node is used within the schema tree to make complex data type polymorphism more visible and obvious.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4c91b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c91b-117">See Also</span></span>  
- [<span data-ttu-id="4c91b-118">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="4c91b-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="4c91b-119">节点属性</span><span class="sxs-lookup"><span data-stu-id="4c91b-119">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="4c91b-120">**序列组节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4c91b-120">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
- [<span data-ttu-id="4c91b-121">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="4c91b-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
