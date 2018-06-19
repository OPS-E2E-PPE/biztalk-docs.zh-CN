---
title: 键入重用和派生 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 240145ea-be41-40ce-8edd-3d4d00e2baec
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2982fdf5e46f813669ff74b513615637aa699bd4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286613"
---
# <a name="type-reuse-and-derivations"></a><span data-ttu-id="5618e-102">类型重用和派生</span><span class="sxs-lookup"><span data-stu-id="5618e-102">Type Reuse and Derivations</span></span>
<span data-ttu-id="5618e-103">在 XML 架构定义 (XSD) 语言中，复杂的全局类型提供了定义可在架构中各个位置重用并可能进行重新定义的结构化数据类型的机制。</span><span class="sxs-lookup"><span data-stu-id="5618e-103">Within XML Schema definition (XSD) language, complex global types provide a mechanism for defining a structured data type that can be reused, and potentially redefined, at various locations within your schema.</span></span> <span data-ttu-id="5618e-104">例如，最传统的示例之一是包含姓名、街道、城市、省/自治区等信息的地址结构。</span><span class="sxs-lookup"><span data-stu-id="5618e-104">Perhaps the most classic example is an address structure that includes a name, street, city, state, and so on.</span></span> <span data-ttu-id="5618e-105">此外，姓名本身可能是包含名字、中名和姓氏字符串的结构。</span><span class="sxs-lookup"><span data-stu-id="5618e-105">Further, the name itself might be a structure that includes first, middle, and last name strings.</span></span> <span data-ttu-id="5618e-106">如果对此复杂结构进行全局定义，则可以在架构中的多个位置使用该结构，例如用于发货地址和帐单邮寄地址。</span><span class="sxs-lookup"><span data-stu-id="5618e-106">If this complex structure is defined globally, you can use it in multiple locations within your schema, such as for both a shipping address and a billing address.</span></span>  
  
 <span data-ttu-id="5618e-107">XSD 还提供了从一个类型派生另一个类型的机制。</span><span class="sxs-lookup"><span data-stu-id="5618e-107">XSD also provides mechanisms for deriving one type from another.</span></span> <span data-ttu-id="5618e-108">此机制既包括简单内容类型，也包括复杂内容类型。</span><span class="sxs-lookup"><span data-stu-id="5618e-108">This includes both simple content types and complex content types.</span></span> <span data-ttu-id="5618e-109">例如，可以从简单字符串类型（例如，xs:string）派生新的类型，以便该新类型只允许将几个特定字符串作为合法值。</span><span class="sxs-lookup"><span data-stu-id="5618e-109">For example, a new type can be derived from a simple string type (such as, xs:string) such that the new type allows only a few particular strings as legal values.</span></span> <span data-ttu-id="5618e-110">此类派生在 XSD 中称为通过限制派生，因为所派生类型的允许值比基本类型的允许值具有更高的限制性。</span><span class="sxs-lookup"><span data-stu-id="5618e-110">This type of derivation is known within XSD as derivation by restriction because the values allowed by the derived type are more restrictive than the values allowed by the base type.</span></span>  
  
 <span data-ttu-id="5618e-111">在上述建议的地址类型中，可以提供涉及复杂类型的派生示例。</span><span class="sxs-lookup"><span data-stu-id="5618e-111">An example of a derivation involving a complex type can be seen in the address type previously suggested.</span></span> <span data-ttu-id="5618e-112">假设该地址类型被设计为包含特定国家/地区内的地址，该地址中已假定了国家/地区本身。</span><span class="sxs-lookup"><span data-stu-id="5618e-112">Suppose that the address type is designed to accommodate the addresses within a particular country/region, where the country/region itself is assumed in the address.</span></span> <span data-ttu-id="5618e-113">若要扩展此类地址类型，以便能够处理国际地址，则可以从原始地址类型派生新的类型，然后在所派生的类型中包括诸如国家/地区之类的其他信息。</span><span class="sxs-lookup"><span data-stu-id="5618e-113">To extend such an address type to handle international addresses, you can derive a new type from the original address type and then include additional information in the derived type, such as the country/region.</span></span> <span data-ttu-id="5618e-114">此类派生在 XSD 中称为通过扩展派生，因为所派生的类型已扩展了基本类型。</span><span class="sxs-lookup"><span data-stu-id="5618e-114">This type of derivation is known within XSD as derivation by extension because the derived type has extended the base type.</span></span>  
  
 <span data-ttu-id="5618e-115">本部分介绍了类型重用以及在重用类型时使用派生对其进行重新定义的方式。</span><span class="sxs-lookup"><span data-stu-id="5618e-115">This section describes type reuse and the ways in which you can use derivation to redefine types as they are reused.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5618e-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="5618e-116">In This Section</span></span>  
  
-   [<span data-ttu-id="5618e-117">复杂全局类型定义和命名</span><span class="sxs-lookup"><span data-stu-id="5618e-117">Complex Global Type Definition and Naming</span></span>](../core/complex-global-type-definition-and-naming.md)  
  
-   [<span data-ttu-id="5618e-118">如何使用复杂全局类型</span><span class="sxs-lookup"><span data-stu-id="5618e-118">Ways to Use Complex Global Types</span></span>](../core/ways-to-use-complex-global-types.md)  
  
-   [<span data-ttu-id="5618e-119">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="5618e-119">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)