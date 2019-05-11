---
title: 属性相互依存关系 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ed5b75e-db1c-43d4-a287-fc4cd1c529f5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a871fcccc61795569a3d93c0d558f91d13bb67f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398478"
---
# <a name="property-interdependencies"></a><span data-ttu-id="8bc1c-102">属性相互依存关系</span><span class="sxs-lookup"><span data-stu-id="8bc1c-102">Property Interdependencies</span></span>

## <a name="overview"></a><span data-ttu-id="8bc1c-103">概述</span><span class="sxs-lookup"><span data-stu-id="8bc1c-103">Overview</span></span>
<span data-ttu-id="8bc1c-104">使用 BizTalk 编辑器中，如，尤其是[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，若要更改属性的值，您将注意到属性之间是否存在大量相互依赖关系。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-104">As you use BizTalk Editor, and specifically the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, to change the values of properties, you will notice that there are extensive interdependencies between properties.</span></span> <span data-ttu-id="8bc1c-105">有时一个属性的特定设置将导致其他属性自动清除、 启用或禁用，或甚至出现或从属性窗口中完全消失。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-105">Sometimes a particular setting for one property will cause other properties to be automatically cleared, become enabled or disabled, or even appear or disappear entirely from the Properties window.</span></span> <span data-ttu-id="8bc1c-106">这些相互依存关系数不胜数。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-106">These interdependencies are too numerous to cover.</span></span> 

<span data-ttu-id="8bc1c-107">但是，以下列表提供了一些常见的示例，以便您了解它们的工作原理：</span><span class="sxs-lookup"><span data-stu-id="8bc1c-107">However, the following list provides some common examples to give you an idea of how they work:</span></span>  
  
- <span data-ttu-id="8bc1c-108">设置的属性时**Field 元素**节点或**字段属性**节点为其数据类型从派生简单类型的使用限制机制，一个新的类别属性可用：**限制**。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-108">When setting the properties of a **Field Element** node or **Field Attribute** node for which a data type is being derived from a simple type by using the restriction mechanism, an entire new category of properties becomes available: **Restriction**.</span></span> <span data-ttu-id="8bc1c-109">此外，此新类别中的属性启用或禁用基于的基本数据类型是否是字符串类型或数值类型。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-109">Further, the properties in this new category are enabled or disabled based on whether the base data type is of a string type or a numeric type.</span></span> <span data-ttu-id="8bc1c-110">有关这种形式的简单类型派生的详细信息，请参阅[简单类型派生使用限制机制](../core/simple-type-derivation-using-the-restriction-mechanism.md)。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-110">For more information about this form of simple type derivation, see [Simple Type Derivation Using the Restriction Mechanism](../core/simple-type-derivation-using-the-restriction-mechanism.md).</span></span>  
  
- <span data-ttu-id="8bc1c-111">设置的属性时**字段元素**节点或**Field 特性**节点为其数据类型派生自简单类型通过使用列表或联合机制**Base数据类型**属性改为**项类型**属性或**成员类型**属性，分别。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-111">When setting the properties of a **Field Element** node or **Field Attribute** node for which a data type is being derived from a simple type by using either the list or union mechanism, the **Base Data Type** property is changed to either the **Item Type** property or the **Member Types** property, respectively.</span></span> <span data-ttu-id="8bc1c-112">在后一种情况下，修改相应的下拉列表以包括复选框，允许选择多个类型。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-112">In the latter case, the corresponding drop-down list is modified to include check boxes, allowing multiple types to be selected.</span></span> <span data-ttu-id="8bc1c-113">有关这些形式的简单类型派生的详细信息，请参阅[简单类型派生使用列表机制](../core/simple-type-derivation-using-the-list-mechanism.md)并[简单类型派生使用联合机制](../core/simple-type-derivation-using-the-union-mechanism.md)。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-113">For more information about these forms of simple type derivation, see [Simple Type Derivation Using the List Mechanism](../core/simple-type-derivation-using-the-list-mechanism.md) and [Simple Type Derivation Using the Union Mechanism](../core/simple-type-derivation-using-the-union-mechanism.md).</span></span>  
  
- <span data-ttu-id="8bc1c-114">若要公开与平面文件架构相关联的属性，必须设置**架构编辑器扩展**的属性**架构**节点包括**平面文件扩展**.</span><span class="sxs-lookup"><span data-stu-id="8bc1c-114">To expose the properties associated with flat file schemas, you must set the **Schema Editor Extensions** property of the **Schema** node to include the **Flat File Extension**.</span></span> <span data-ttu-id="8bc1c-115">与其他编辑器扩展，例如 EDI 扩展相关联的自定义属性公开相同的方式： 通过选择相应的扩展使用**架构编辑器扩展**属性。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-115">The custom properties associated with other editor extensions, such as the EDI extension, are exposed in the same way: by choosing the corresponding extension using the **Schema Editor Extensions** property.</span></span>  
  
  <span data-ttu-id="8bc1c-116">此列表包含旨在说明属性相互依存关系，您将看到属性窗口中工作时的类型的示例，但它并不是这些相互依存关系的详尽列表。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-116">This list includes examples that are meant to illustrate the types of property interdependencies that you will see when working within the Properties window, but it is not meant to be an exhaustive list of such interdependencies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc1c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bc1c-117">See Also</span></span>  
- [<span data-ttu-id="8bc1c-118">节点属性</span><span class="sxs-lookup"><span data-stu-id="8bc1c-118">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="8bc1c-119">以下属性 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="8bc1c-119">The following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
   -  <span data-ttu-id="8bc1c-120">节点属性按字母顺序排列列表</span><span class="sxs-lookup"><span data-stu-id="8bc1c-120">Node Properties Alphabetical Listings</span></span>
   -  <span data-ttu-id="8bc1c-121">所有架构的节点属性</span><span class="sxs-lookup"><span data-stu-id="8bc1c-121">Node Properties of All Schemas</span></span> 
   -  <span data-ttu-id="8bc1c-122">架构编辑器扩展</span><span class="sxs-lookup"><span data-stu-id="8bc1c-122">Schema Editor Extensions</span></span>