---
title: 若要使用复杂全局类型的方式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddea1c7b-eb0e-4521-8576-0ea6f9460847
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf40f80a1c1353dc56b11c8e84e8d7d395beb37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393616"
---
# <a name="ways-to-use-complex-global-types"></a><span data-ttu-id="7afd1-102">使用复杂全局类型的方法</span><span class="sxs-lookup"><span data-stu-id="7afd1-102">Ways to Use Complex Global Types</span></span>
<span data-ttu-id="7afd1-103">复杂类型转换为全局复杂类型后，才可以在架构中其他位置中重用它。</span><span class="sxs-lookup"><span data-stu-id="7afd1-103">After you have converted a complex type to a global complex type, it becomes available for reuse in other locations within your schema.</span></span> <span data-ttu-id="7afd1-104">有关定义复杂类型并将其转换为全局复杂类型的详细信息，请参阅[复杂全局类型定义和命名](../core/complex-global-type-definition-and-naming.md)。</span><span class="sxs-lookup"><span data-stu-id="7afd1-104">For more information about defining a complex type and then converting it to a global complex type, see [Complex Global Type Definition and Naming](../core/complex-global-type-definition-and-naming.md).</span></span>  
  
 <span data-ttu-id="7afd1-105">首先，插入一个新**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="7afd1-105">First, you insert a new **Record** node.</span></span> <span data-ttu-id="7afd1-106">然后选择插入节点，并在属性窗口中，每个不同的效果设置了以下两个节点属性之一：</span><span class="sxs-lookup"><span data-stu-id="7afd1-106">Then you select the inserted node and set one of the following two node properties in the Properties window, each for a different effect:</span></span>  
  
-   <span data-ttu-id="7afd1-107">**Data Structure Type 属性**。</span><span class="sxs-lookup"><span data-stu-id="7afd1-107">**Data Structure Type property**.</span></span> <span data-ttu-id="7afd1-108">如果你想要使用的复杂全局类型而无需以任何方式修改它，将此属性设置为您提供给复杂全局类型，可作为下拉列表中的选项的类型名称。</span><span class="sxs-lookup"><span data-stu-id="7afd1-108">If you want to use the complex global type without modifying it in any way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="7afd1-109">在架构树中，将在新位置中，以图形方式复制所选全局节点结构和任何它在架构树中位置中的节点结构的任何后续更改会自动应用到使用该复杂全局类型的所有位置.</span><span class="sxs-lookup"><span data-stu-id="7afd1-109">In the schema tree, the chosen global node structure will be graphically duplicated in the new location, and any subsequent changes to the node structure in any of its locations in the schema tree are automatically made to all locations that use that complex global type.</span></span>  
  
-   <span data-ttu-id="7afd1-110">**Base Data Type 属性**。</span><span class="sxs-lookup"><span data-stu-id="7afd1-110">**Base Data Type property**.</span></span> <span data-ttu-id="7afd1-111">如果你想要使用复杂全局类型上的一种变体，其进行扩展或限制以某种方式，此属性设置为您提供给复杂全局类型，可作为下拉列表中的选项的类型名称。</span><span class="sxs-lookup"><span data-stu-id="7afd1-111">If you want to use a variation on the complex global type, either extending it or restricting it in some way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="7afd1-112">当设置此属性时**Derived By**节点属性更改为**扩展**(并**内容类型**属性更改为**ComplexContent**)，指示该扩展的复杂全局类型是默认的派生类型。</span><span class="sxs-lookup"><span data-stu-id="7afd1-112">When you set this property, the **Derived By** node property changes to **Extension** (and the **Content Type** property changes to **ComplexContent**), indicating that extending the complex global type is the default derivation type.</span></span> <span data-ttu-id="7afd1-113">您可以将其更改为**限制**如果您的修改的任务。</span><span class="sxs-lookup"><span data-stu-id="7afd1-113">You can change it to **Restriction** if your modifications are of that nature.</span></span> <span data-ttu-id="7afd1-114">对从其派生的基本复杂全局类型的更改会自动反映在派生类中，但派生类型中的更改将不会反映在基类型中。</span><span class="sxs-lookup"><span data-stu-id="7afd1-114">Changes to the base complex global type from which you are deriving are automatically reflected in the derived type, but changes in the derived type are never reflected in the base type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7afd1-115">自动设置这些属性之一会导致另一个具有删除现有设置。</span><span class="sxs-lookup"><span data-stu-id="7afd1-115">Setting either one of these properties automatically causes the other one to have any existing setting removed.</span></span> <span data-ttu-id="7afd1-116">此外，你会注意到相关属性，例如设置之间的其他自动交互**Derived By**属性设置为 **（默认）** 删除从任何现有设置**Base数据类型**属性。</span><span class="sxs-lookup"><span data-stu-id="7afd1-116">Further, you will notice other automatic interactions between the related properties, such as setting the **Derived By** property to **(Default)** removes any existing setting from the **Base Data Type** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7afd1-117">可以创建 test 架构，并观察 XSD 视图中的更改这些属性，使用不同的值。</span><span class="sxs-lookup"><span data-stu-id="7afd1-117">You can create a test schema and use different values for these properties, observing the changes in the XSD view.</span></span>  
  
 <span data-ttu-id="7afd1-118">本部分介绍使用复杂全局类型，如，和进行扩展和限制，如由本主题中所述的属性的设置控制。</span><span class="sxs-lookup"><span data-stu-id="7afd1-118">This section describes using complex global types, both as is, and by extending and restricting them, as controlled by the settings of the properties described in this topic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7afd1-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="7afd1-119">In This Section</span></span>  
  
-   [<span data-ttu-id="7afd1-120">复杂全局类型重用</span><span class="sxs-lookup"><span data-stu-id="7afd1-120">Complex Global Type Re-use</span></span>](../core/complex-global-type-re-use.md)  
  
-   [<span data-ttu-id="7afd1-121">复杂全局类型派生</span><span class="sxs-lookup"><span data-stu-id="7afd1-121">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)