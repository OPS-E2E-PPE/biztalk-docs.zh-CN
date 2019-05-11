---
title: 复杂全局类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbf429d0-64f4-4c43-a5f7-e8af050803b9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b82c7482204195010cf4d1177c4e6ccad4713df2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356713"
---
# <a name="complex-global-type-derivation"></a><span data-ttu-id="015ef-102">复杂全局类型派生</span><span class="sxs-lookup"><span data-stu-id="015ef-102">Complex Global Type Derivation</span></span>
<span data-ttu-id="015ef-103">有两种类型的 XSD 中的继承： 扩展和限制。</span><span class="sxs-lookup"><span data-stu-id="015ef-103">There are two types of inheritance in XSD: extension and restriction.</span></span> <span data-ttu-id="015ef-104">BizTalk 编辑器中通过使用以下两个提供访问此 XSD 功能**记录**节点属性：</span><span class="sxs-lookup"><span data-stu-id="015ef-104">BizTalk Editor provides access to this XSD functionality by using the following two **Record** node properties:</span></span>  
  
-   <span data-ttu-id="015ef-105">**基本数据类型**。</span><span class="sxs-lookup"><span data-stu-id="015ef-105">**Base Data Type**.</span></span> <span data-ttu-id="015ef-106">此属性提供的所有全局复杂类型的列表，并可用于简单类型将用作基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="015ef-106">This property provides the list of all global complex types and simple types available for use as a base data type.</span></span> <span data-ttu-id="015ef-107">复杂全局类型可以是同一架构中或在任何导入的架构。</span><span class="sxs-lookup"><span data-stu-id="015ef-107">The complex global types can be in the same schema or in any imported schema.</span></span>  
  
-   <span data-ttu-id="015ef-108">**通过派生**。</span><span class="sxs-lookup"><span data-stu-id="015ef-108">**Derived By**.</span></span> <span data-ttu-id="015ef-109">此属性用于通过扩展或限制派生之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="015ef-109">This property is used to choose between deriving by extension or by restriction.</span></span> <span data-ttu-id="015ef-110">此属性自动设置为**扩展**设置时**Base Data Type**到列表中的任何类型的属性。</span><span class="sxs-lookup"><span data-stu-id="015ef-110">This property is automatically set to **Extension** when you set the **Base Data Type** property to any type in the list.</span></span> <span data-ttu-id="015ef-111">如果此属性设置为 **（默认值）**，在任何类型**Base Data Type**属性会被删除，禁用节点继承。</span><span class="sxs-lookup"><span data-stu-id="015ef-111">If you set this property to **(Default)**, any type in the **Base Data Type** property is removed, disabling inheritance for the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="015ef-112">**内容类型**属性也设置自动向**ComplexContent**时正在使用通过扩展或限制进行派生。</span><span class="sxs-lookup"><span data-stu-id="015ef-112">The **Content Type** property is also set automatically to **ComplexContent** when derivation by extension or restriction is being used.</span></span>  
  
 <span data-ttu-id="015ef-113">本部分介绍通过使用更详细地扩展和限制机制进行复杂类型派生。</span><span class="sxs-lookup"><span data-stu-id="015ef-113">This section explains complex type derivation by using the extension and restriction mechanisms in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="015ef-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="015ef-114">In This Section</span></span>  
  
-   [<span data-ttu-id="015ef-115">使用扩展机制进行复杂类型派生</span><span class="sxs-lookup"><span data-stu-id="015ef-115">Complex Type Derivation Using the Extension Mechanism</span></span>](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [<span data-ttu-id="015ef-116">使用限制机制进行复杂类型派生</span><span class="sxs-lookup"><span data-stu-id="015ef-116">Complex Type Derivation Using the Restriction Mechanism</span></span>](../core/complex-type-derivation-using-the-restriction-mechanism.md)