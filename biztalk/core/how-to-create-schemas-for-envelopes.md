---
title: 如何为包络线创建架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae1c991c-447f-497e-803c-1cb8cad2846b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7308a093f9f95ce2342f268554deb67193aea053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249589"
---
# <a name="create-schemas-for-envelopes"></a><span data-ttu-id="c50db-102">为包络线创建架构</span><span class="sxs-lookup"><span data-stu-id="c50db-102">Create Schemas for Envelopes</span></span>

## <a name="overview"></a><span data-ttu-id="c50db-103">概述</span><span class="sxs-lookup"><span data-stu-id="c50db-103">Overview</span></span>
<span data-ttu-id="c50db-104">创建 XML 消息架构中所述之后[创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)，将其设置**信封**属性**架构**节点**是**.</span><span class="sxs-lookup"><span data-stu-id="c50db-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), set the **Envelope** property of the **Schema** node to **Yes**.</span></span> <span data-ttu-id="c50db-105">根据信封架构的某些特性（例如是否具有多个根节点），您将需要设置其他一些特定于信封的属性。</span><span class="sxs-lookup"><span data-stu-id="c50db-105">Depending on certain characteristics of your envelope schema, such as whether there are multiple root nodes, you will need to set several other envelope-specific properties.</span></span> <span data-ttu-id="c50db-106">有关详细信息，请参阅[信封架构](../core/envelope-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="c50db-106">For more information, see [Envelope Schemas](../core/envelope-schemas.md).</span></span>  
  
 <span data-ttu-id="c50db-107">信封的正文 XPath 属性指向包含文档元素的元素。</span><span class="sxs-lookup"><span data-stu-id="c50db-107">The body XPath property of the envelope points to the element that contains the document elements.</span></span> <span data-ttu-id="c50db-108">XPath 实际指向的元素不属于该文档。</span><span class="sxs-lookup"><span data-stu-id="c50db-108">The actual element where the XPath points to does not belong to the document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c50db-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c50db-109">See Also</span></span>  
-  [<span data-ttu-id="c50db-110">管理架构在项目中</span><span class="sxs-lookup"><span data-stu-id="c50db-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
-  <span data-ttu-id="c50db-111">**信封**属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c50db-111">**Envelope** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>