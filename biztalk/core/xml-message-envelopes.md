---
title: XML 消息信封 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d01cd85d-7bf7-49fa-aa25-322213bce066
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8276e2986231c391479112b25e01bea778566093
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246412"
---
# <a name="xml-message-envelopes"></a><span data-ttu-id="f6e28-102">XML 消息信封</span><span class="sxs-lookup"><span data-stu-id="f6e28-102">XML Message Envelopes</span></span>
<span data-ttu-id="f6e28-103">在由 Microsoft 发送和接收的 XML 实例消息中的两个用途，XML 信封具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f6e28-103">XML envelopes serve two purposes within XML instance messages sent and received by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
- <span data-ttu-id="f6e28-104">XML 信封可包含补充 XML 文档中的数据的数据。</span><span class="sxs-lookup"><span data-stu-id="f6e28-104">XML envelopes can contain data that supplements the data within the XML documents.</span></span> <span data-ttu-id="f6e28-105">此数据可以升级到消息上下文中，XML 拆装器以便更容易访问不同的 BizTalk Server 组件。</span><span class="sxs-lookup"><span data-stu-id="f6e28-105">This data can be promoted into the message context by the XML disassembler to provide easier access from a variety of BizTalk Server components.</span></span> <span data-ttu-id="f6e28-106">对于出站 XML 实例消息，XML 组装器可以将值从消息上下文降级到信封中，以包含在实例消息传输。</span><span class="sxs-lookup"><span data-stu-id="f6e28-106">For outbound XML instance messages, the XML assembler can demote values from the message context into an envelope for inclusion in the instance message transmission.</span></span>  
  
- <span data-ttu-id="f6e28-107">XML 信封可以用于将多个 XML 文档合并到单个有效的 XML 实例消息。</span><span class="sxs-lookup"><span data-stu-id="f6e28-107">XML envelopes can be used to combine multiple XML documents into a single, valid XML instance message.</span></span> <span data-ttu-id="f6e28-108">如果不使用信封来包装到单个根标记中的多个文档，包含多个文档的 XML 实例消息将不适合作为格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="f6e28-108">Without an envelope to wrap multiple documents within a single root tag, an XML instance message containing multiple documents would not qualify as well-formed XML.</span></span>  
  
  <span data-ttu-id="f6e28-109">典型的 XML 信封 （以粗体显示） 包含数据和用于分隔 （以常规字体显示），它包含一个或多个 XML 文档的标记。</span><span class="sxs-lookup"><span data-stu-id="f6e28-109">A typical XML envelope (shown in bold type) contains both data and a tag used to delimit the one or more XML documents (shown in regular font) that it contains.</span></span>  
  
```  
  
  <envelope fieldAttrib1="..." fieldAttrib2="..." ...>     <fieldElem1>...</fieldElem1>     <fieldElem2>...</fieldElem2>     ...     <body>  
    <document1>  
        ...  
    </document1>  
    <document2>  
        ...  
    </document2>  
    ...  
</body>    ...</envelope>  
```  
  
 <span data-ttu-id="f6e28-110">不太常见，但仍然有效，XML 信封 （以粗体显示） 不需要包含任何数据或分隔的 XML 文档 （以常规类型显示），它包含的标记。</span><span class="sxs-lookup"><span data-stu-id="f6e28-110">Less common, but still valid, an XML envelope (shown in bold type) need not contain any data or a tag for delimiting the XML documents (shown in regular type) that it contains.</span></span>  
  
```  
  
      <envelope>  
    <document1>  
        ...  
    </document1>  
    <document2>  
        ...  
    </document2>  
    ...  
</envelope>  
```  
  
 <span data-ttu-id="f6e28-111">在这种情况下，XML 信封包含开始和结束信封标记以外的任何内容。</span><span class="sxs-lookup"><span data-stu-id="f6e28-111">In such cases, the XML envelope consists of nothing other than the starting and ending envelope tags.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e28-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6e28-112">See Also</span></span>  
 <span data-ttu-id="f6e28-113">[嵌套的 XML 消息信封](../core/nested-xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="f6e28-113">[Nested XML Message Envelopes](../core/nested-xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="f6e28-114">[XML 消息的结构](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="f6e28-114">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="f6e28-115">如何为信封创建架构</span><span class="sxs-lookup"><span data-stu-id="f6e28-115">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)