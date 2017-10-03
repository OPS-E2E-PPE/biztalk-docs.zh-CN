---
title: "如何使用复杂全局类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddea1c7b-eb0e-4521-8576-0ea6f9460847
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f84b8b872d047a62a913514a695b4bba2d482c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ways-to-use-complex-global-types"></a><span data-ttu-id="43ce8-102">使用复杂全局类型的方法</span><span class="sxs-lookup"><span data-stu-id="43ce8-102">Ways to Use Complex Global Types</span></span>
<span data-ttu-id="43ce8-103">将某一复杂类型转换为全局复杂类型之后，它就可以在您的架构的其他位置中重用。</span><span class="sxs-lookup"><span data-stu-id="43ce8-103">After you have converted a complex type to a global complex type, it becomes available for reuse in other locations within your schema.</span></span> <span data-ttu-id="43ce8-104">有关定义复杂类型，然后将它转换为全局复杂类型的详细信息，请参阅[复杂全局类型定义和命名](../core/complex-global-type-definition-and-naming.md)。</span><span class="sxs-lookup"><span data-stu-id="43ce8-104">For more information about defining a complex type and then converting it to a global complex type, see [Complex Global Type Definition and Naming](../core/complex-global-type-definition-and-naming.md).</span></span>  
  
 <span data-ttu-id="43ce8-105">首先，插入一个新**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="43ce8-105">First, you insert a new **Record** node.</span></span> <span data-ttu-id="43ce8-106">然后，选择所插入节点并在“属性”窗口中设置以下两个节点属性之一，每个将产生不同效果：</span><span class="sxs-lookup"><span data-stu-id="43ce8-106">Then you select the inserted node and set one of the following two node properties in the Properties window, each for a different effect:</span></span>  
  
-   <span data-ttu-id="43ce8-107">**数据结构类型属性**。</span><span class="sxs-lookup"><span data-stu-id="43ce8-107">**Data Structure Type property**.</span></span> <span data-ttu-id="43ce8-108">如果要使用复杂全局类型而不对其进行修改，则将此属性设置为您提供给复杂全局类型的类型名称，该类型名称作为下拉列表中的选项提供。</span><span class="sxs-lookup"><span data-stu-id="43ce8-108">If you want to use the complex global type without modifying it in any way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="43ce8-109">在架构树中，将在新位置中以图形方式复制所选的全局节点结构，如果对架构树中任何位置的节点结构进行后续更改，将自动对使用该复杂全局类型的所有位置进行相同更改。</span><span class="sxs-lookup"><span data-stu-id="43ce8-109">In the schema tree, the chosen global node structure will be graphically duplicated in the new location, and any subsequent changes to the node structure in any of its locations in the schema tree are automatically made to all locations that use that complex global type.</span></span>  
  
-   <span data-ttu-id="43ce8-110">**基数据类型属性**。</span><span class="sxs-lookup"><span data-stu-id="43ce8-110">**Base Data Type property**.</span></span> <span data-ttu-id="43ce8-111">如果要使用复杂全局类型的变体，以某种方式对其进行扩展或限制，则将此属性设置为您提供给复杂全局类型的类型名称，该类型名称作为下拉列表中的选项提供。</span><span class="sxs-lookup"><span data-stu-id="43ce8-111">If you want to use a variation on the complex global type, either extending it or restricting it in some way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="43ce8-112">当设置此属性，**派生源**节点属性更改为**扩展**(和**内容类型**属性更改为**ComplexContent**)，指示该扩展的复杂全局类型是默认的派生类型。</span><span class="sxs-lookup"><span data-stu-id="43ce8-112">When you set this property, the **Derived By** node property changes to **Extension** (and the **Content Type** property changes to **ComplexContent**), indicating that extending the complex global type is the default derivation type.</span></span> <span data-ttu-id="43ce8-113">你可以将其更改为**限制**如果您修改该性质的则。</span><span class="sxs-lookup"><span data-stu-id="43ce8-113">You can change it to **Restriction** if your modifications are of that nature.</span></span> <span data-ttu-id="43ce8-114">对从其派生的基本复杂全局类型的更改将自动反映在派生类型中，但在派生类型中所做的更改将不会反映在基本类型中。</span><span class="sxs-lookup"><span data-stu-id="43ce8-114">Changes to the base complex global type from which you are deriving are automatically reflected in the derived type, but changes in the derived type are never reflected in the base type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43ce8-115">设置上述属性之一将自动导致另一个属性删除现有设置。</span><span class="sxs-lookup"><span data-stu-id="43ce8-115">Setting either one of these properties automatically causes the other one to have any existing setting removed.</span></span> <span data-ttu-id="43ce8-116">此外，你将注意到相关的属性，例如设置之间的其他自动交互**派生源**属性**（默认）**中删除任何现有设置从**基数据类型**属性。</span><span class="sxs-lookup"><span data-stu-id="43ce8-116">Further, you will notice other automatic interactions between the related properties, such as setting the **Derived By** property to **(Default)** removes any existing setting from the **Base Data Type** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43ce8-117">您可以创建一个测试架构并为这些属性使用不同值，以观察 XSD 视图中的变化。</span><span class="sxs-lookup"><span data-stu-id="43ce8-117">You can create a test schema and use different values for these properties, observing the changes in the XSD view.</span></span>  
  
 <span data-ttu-id="43ce8-118">本部分将介绍按本主题中描述的属性设置来控制原样使用复杂全局类型，对其进行扩展和限制。</span><span class="sxs-lookup"><span data-stu-id="43ce8-118">This section describes using complex global types, both as is, and by extending and restricting them, as controlled by the settings of the properties described in this topic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43ce8-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="43ce8-119">In This Section</span></span>  
  
-   [<span data-ttu-id="43ce8-120">复杂全局类型重复使用</span><span class="sxs-lookup"><span data-stu-id="43ce8-120">Complex Global Type Re-use</span></span>](../core/complex-global-type-re-use.md)  
  
-   [<span data-ttu-id="43ce8-121">复杂全局类型派生</span><span class="sxs-lookup"><span data-stu-id="43ce8-121">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)