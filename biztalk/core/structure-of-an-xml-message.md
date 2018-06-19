---
title: XML 消息的结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bba81-2f2b-41f3-b8b2-c2fb9c15ea5a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f35e48e90ffb089342c268b7b6a45069e2f9869
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278477"
---
# <a name="structure-of-an-xml-message"></a><span data-ttu-id="8afd6-102">XML 消息的结构</span><span class="sxs-lookup"><span data-stu-id="8afd6-102">Structure of an XML Message</span></span>
<span data-ttu-id="8afd6-103">在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中，XML 实例消息是一个有效的 XML 标记层次结构，这些标记共同构成零个或多个 XML 信封和一个或多个 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="8afd6-103">In the context of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], an XML instance message is a valid hierarchy of XML tags that together constitute zero or more XML envelopes and one or more XML documents.</span></span> <span data-ttu-id="8afd6-104">例如，以下 XML 实例消息由包含单个 XML 文档（以粗体显示）的单个 XML 信封（使用常规字体）组成。</span><span class="sxs-lookup"><span data-stu-id="8afd6-104">For example, the following XML instance message consists of a single XML envelope (in regular font) that contains a single XML document (shown in bold type).</span></span>  
  
```  
<ns0:envelope xmlns:ns0="http://myEnvelopeNamespaceURI.org">  
    <header>  
        <firstName>John</firstName>  
        <lastName>Scott</lastName>  
    </header>  
    <body>  
        <ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">            <message>Hello</message>        </ns1:document>  
    </body>  
</ns0:envelope>  
```  
  
 <span data-ttu-id="8afd6-105">可以使用多种方式将 XML 信封和所包含的 XML 文档组合成有效的 XML 实例消息。</span><span class="sxs-lookup"><span data-stu-id="8afd6-105">XML envelopes and the XML documents that they contain can be combined into valid XML instance messages in several different ways.</span></span> <span data-ttu-id="8afd6-106">本主题的其余部分将介绍这些不同的组合。</span><span class="sxs-lookup"><span data-stu-id="8afd6-106">The remainder of this section describes these different combinations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8afd6-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="8afd6-107">In This Section</span></span>  
  
-   [<span data-ttu-id="8afd6-108">XML 消息包络线</span><span class="sxs-lookup"><span data-stu-id="8afd6-108">XML Message Envelopes</span></span>](../core/xml-message-envelopes.md)  
  
-   [<span data-ttu-id="8afd6-109">嵌套的 XML 消息包络线</span><span class="sxs-lookup"><span data-stu-id="8afd6-109">Nested XML Message Envelopes</span></span>](../core/nested-xml-message-envelopes.md)