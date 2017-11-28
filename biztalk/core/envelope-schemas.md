---
title: "信封架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af296c30-95dc-4fef-9aa3-bea2f2cd8caf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c44f1a5d9797ec09cc164789148287c98b4399
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="envelope-schemas"></a><span data-ttu-id="7b728-102">信封架构</span><span class="sxs-lookup"><span data-stu-id="7b728-102">Envelope Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="7b728-103">概述</span><span class="sxs-lookup"><span data-stu-id="7b728-103">Overview</span></span>
<span data-ttu-id="7b728-104">你可以在所有你可以创建针对业务文档的 XML 架构的相同方式创建信封架构。</span><span class="sxs-lookup"><span data-stu-id="7b728-104">You can create an envelope schema in all of the same ways that you can create an XML schema for a business document.</span></span> <span data-ttu-id="7b728-105">你可以创建架构，从格式正确的 XML 信封实例消息，或从文档类型定义 (DTD) 或 XML 数据缩减 (XDR) 表示形式的信封架构。</span><span class="sxs-lookup"><span data-stu-id="7b728-105">You can create a schema from a well-formed XML envelope instance message, or from Document Type Definition (DTD) or XML-Data reduced (XDR) representations of the envelope schema.</span></span> <span data-ttu-id="7b728-106">或者，可以创建新的架构，或者结合其他架构。</span><span class="sxs-lookup"><span data-stu-id="7b728-106">Or, you can create a new schema, either in conjunction with other schemas or not.</span></span> <span data-ttu-id="7b728-107">因为信封架构是小得多，并且小于比大多数的业务文档架构复杂，通常多创建新的信封架构是可行的替代方案。</span><span class="sxs-lookup"><span data-stu-id="7b728-107">Because envelope schemas are generally much smaller and less complicated than most business document schemas, creating new envelope schemas is usually a viable alternative.</span></span>  
  
 <span data-ttu-id="7b728-108">若要为信封架构中定义的架构，你需要设置**信封**属性**架构**的值的节点**是**。</span><span class="sxs-lookup"><span data-stu-id="7b728-108">To define a schema as an envelope schema, you need to set the **Envelope** property of the **Schema** node to the value **Yes**.</span></span> <span data-ttu-id="7b728-109">在定义信封架构时，您应该指向的信封**正文 XPath**向父节点只包含\<任何 > 子元素。</span><span class="sxs-lookup"><span data-stu-id="7b728-109">When you define an envelope schema, you should point the envelope's **Body XPath** to the parent node that contains only the \<any> child element.</span></span> <span data-ttu-id="7b728-110">为了使 XML 汇编程序，若要使用信封的情况下，父节点不能包含任何其他元素。</span><span class="sxs-lookup"><span data-stu-id="7b728-110">In order for the XML assembler to use the envelope, the parent node must not contain any other elements.</span></span>  
  
 <span data-ttu-id="7b728-111">当你将设置**信封**属性**是**，这意味着实际消息内容的 XML 实例消息 （称为消息的正文） 是否存在某个位置内根**记录**此架构，由指定的节点**正文 XPath**该节点的属性。</span><span class="sxs-lookup"><span data-stu-id="7b728-111">When you set **Envelope** property to **Yes**, it means that the actual message content of the XML instance message (called the body of the message) is present somewhere inside the root **Record** node of this schema, as specified by the **Body XPath** property of that node.</span></span> <span data-ttu-id="7b728-112">因此，您还必须根据不同条件设置其他属性：</span><span class="sxs-lookup"><span data-stu-id="7b728-112">Therefore, you must also set additional properties based on a variety of conditions:</span></span>  
  
-   <span data-ttu-id="7b728-113">如果信封架构具有一个根，则必须设置**正文 XPath**该根的属性。</span><span class="sxs-lookup"><span data-stu-id="7b728-113">If an envelope schema has a single root, you must set the **Body XPath** property for that root.</span></span>  
  
-   <span data-ttu-id="7b728-114">如果信封架构具有多个根和**根引用**未设置属性，则必须设置**正文 XPath**所有根的属性。</span><span class="sxs-lookup"><span data-stu-id="7b728-114">If an envelope schema has multiple roots and the **Root Reference** property is not set, you must set the **Body XPath** property for all roots.</span></span>  
  
-   <span data-ttu-id="7b728-115">如果信封架构具有多个根和**根引用**属性时，必须设置**正文 XPath**属性的相应根**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="7b728-115">If an envelope schema has multiple roots and the **Root Reference** property is set, you must set the **Body XPath** property of the corresponding root **Record** node.</span></span> <span data-ttu-id="7b728-116">你可以选择性地设置**正文 XPath**剩余的根的属性。</span><span class="sxs-lookup"><span data-stu-id="7b728-116">You can optionally set the **Body XPath** property for the remaining roots.</span></span>  
  
-   <span data-ttu-id="7b728-117">无论是否信封架构具有单个根或多个根，设置**[根引用**属性不是必需。</span><span class="sxs-lookup"><span data-stu-id="7b728-117">Regardless of whether an envelope schema has a single root or multiple roots, setting the **[Root Reference** property is not required.</span></span>  

<span data-ttu-id="7b728-118">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b728-118">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7b728-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b728-119">See Also</span></span>  
 <span data-ttu-id="7b728-120">[不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="7b728-120">[Different Types of BizTalk Schemas](../core/different-types-of-biztalk-schemas.md) </span></span>  
 [<span data-ttu-id="7b728-121">如何为包络线创建架构</span><span class="sxs-lookup"><span data-stu-id="7b728-121">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)