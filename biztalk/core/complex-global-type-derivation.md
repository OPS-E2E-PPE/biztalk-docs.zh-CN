---
title: "复杂全局类型派生 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fbf429d0-64f4-4c43-a5f7-e8af050803b9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee4e6235af62b2c08c08382b897632d15e34e0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="complex-global-type-derivation"></a><span data-ttu-id="c674f-102">复杂全局类型派生</span><span class="sxs-lookup"><span data-stu-id="c674f-102">Complex Global Type Derivation</span></span>
<span data-ttu-id="c674f-103">XSD 中有两种类型的继承：扩展和限制。</span><span class="sxs-lookup"><span data-stu-id="c674f-103">There are two types of inheritance in XSD: extension and restriction.</span></span> <span data-ttu-id="c674f-104">BizTalk 编辑器通过使用以下两个提供与此 XSD 功能的访问权限**记录**节点属性：</span><span class="sxs-lookup"><span data-stu-id="c674f-104">BizTalk Editor provides access to this XSD functionality by using the following two **Record** node properties:</span></span>  
  
-   <span data-ttu-id="c674f-105">**基数据类型**。</span><span class="sxs-lookup"><span data-stu-id="c674f-105">**Base Data Type**.</span></span> <span data-ttu-id="c674f-106">此属性提供可用作基本数据类型的所有全局复杂类型和简单类型的列表。</span><span class="sxs-lookup"><span data-stu-id="c674f-106">This property provides the list of all global complex types and simple types available for use as a base data type.</span></span> <span data-ttu-id="c674f-107">复杂全局类型可以在同一架构中，也可以在任何导入的架构中。</span><span class="sxs-lookup"><span data-stu-id="c674f-107">The complex global types can be in the same schema or in any imported schema.</span></span>  
  
-   <span data-ttu-id="c674f-108">**通过派生**。</span><span class="sxs-lookup"><span data-stu-id="c674f-108">**Derived By**.</span></span> <span data-ttu-id="c674f-109">此属性用于在通过扩展派生和通过限制派生之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="c674f-109">This property is used to choose between deriving by extension or by restriction.</span></span> <span data-ttu-id="c674f-110">此属性自动设置为**扩展**当设置**基数据类型**到列表中的任何类型的属性。</span><span class="sxs-lookup"><span data-stu-id="c674f-110">This property is automatically set to **Extension** when you set the **Base Data Type** property to any type in the list.</span></span> <span data-ttu-id="c674f-111">如果将此属性设置为**（默认）**中的任何类型**基数据类型**删除属性，则禁用节点继承。</span><span class="sxs-lookup"><span data-stu-id="c674f-111">If you set this property to **(Default)**, any type in the **Base Data Type** property is removed, disabling inheritance for the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c674f-112">**内容类型**属性也将自动为**ComplexContent**何时使用通过扩展或限制派生了。</span><span class="sxs-lookup"><span data-stu-id="c674f-112">The **Content Type** property is also set automatically to **ComplexContent** when derivation by extension or restriction is being used.</span></span>  
  
 <span data-ttu-id="c674f-113">本部分较详细地介绍了使用扩展和限制机制进行的复杂类型派生。</span><span class="sxs-lookup"><span data-stu-id="c674f-113">This section explains complex type derivation by using the extension and restriction mechanisms in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c674f-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="c674f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="c674f-115">使用扩展机制的复杂类型派生</span><span class="sxs-lookup"><span data-stu-id="c674f-115">Complex Type Derivation Using the Extension Mechanism</span></span>](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [<span data-ttu-id="c674f-116">使用限制机制的复杂类型派生</span><span class="sxs-lookup"><span data-stu-id="c674f-116">Complex Type Derivation Using the Restriction Mechanism</span></span>](../core/complex-type-derivation-using-the-restriction-mechanism.md)