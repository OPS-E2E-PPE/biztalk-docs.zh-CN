---
title: 如何为信封创建架构 |Microsoft Docs
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
ms.openlocfilehash: 255236d6a28ee82fa4131b2189a97c9d0962c7d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338997"
---
# <a name="create-schemas-for-envelopes"></a><span data-ttu-id="0ddb1-102">为信封创建架构</span><span class="sxs-lookup"><span data-stu-id="0ddb1-102">Create Schemas for Envelopes</span></span>

## <a name="overview"></a><span data-ttu-id="0ddb1-103">概述</span><span class="sxs-lookup"><span data-stu-id="0ddb1-103">Overview</span></span>
<span data-ttu-id="0ddb1-104">创建 XML 消息架构中所述后[的 XML 消息创建架构](../core/how-to-create-schemas-for-xml-messages.md)，将**信封**属性**架构**节点到**是**.</span><span class="sxs-lookup"><span data-stu-id="0ddb1-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), set the **Envelope** property of the **Schema** node to **Yes**.</span></span> <span data-ttu-id="0ddb1-105">具体取决于某些特征的信封架构，如是否有多个根节点，你将需要设置多个其他特定于信封的属性。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-105">Depending on certain characteristics of your envelope schema, such as whether there are multiple root nodes, you will need to set several other envelope-specific properties.</span></span> <span data-ttu-id="0ddb1-106">有关详细信息，请参阅[信封架构](../core/envelope-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-106">For more information, see [Envelope Schemas](../core/envelope-schemas.md).</span></span>  

 <span data-ttu-id="0ddb1-107">正文信封的 XPath 属性指向包含文档元素的元素。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-107">The body XPath property of the envelope points to the element that contains the document elements.</span></span> <span data-ttu-id="0ddb1-108">XPath 指向的实际元素不属于该文档。</span><span class="sxs-lookup"><span data-stu-id="0ddb1-108">The actual element where the XPath points to does not belong to the document.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0ddb1-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ddb1-109">See Also</span></span>  
- [<span data-ttu-id="0ddb1-110">管理项目中的架构</span><span class="sxs-lookup"><span data-stu-id="0ddb1-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
- <span data-ttu-id="0ddb1-111">**信封**属性 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddb1-111">**Envelope** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
