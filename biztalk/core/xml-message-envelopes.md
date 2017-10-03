---
title: "XML 消息信封 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d01cd85d-7bf7-49fa-aa25-322213bce066
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3adb33866a3e6fdaee387934d2edededaab08aac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-message-envelopes"></a><span data-ttu-id="43446-102">XML 消息信封</span><span class="sxs-lookup"><span data-stu-id="43446-102">XML Message Envelopes</span></span>
<span data-ttu-id="43446-103">XML 包络线有两个用途在 XML 实例消息发送和接收的 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="43446-103">XML envelopes serve two purposes within XML instance messages sent and received by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="43446-104">XML 信封可包含用于补充 XML 文档中数据的数据。</span><span class="sxs-lookup"><span data-stu-id="43446-104">XML envelopes can contain data that supplements the data within the XML documents.</span></span> <span data-ttu-id="43446-105">XML 拆装器可以将此数据升级成消息上下文，以使其可更方便地被各种 BizTalk Server 组件访问。</span><span class="sxs-lookup"><span data-stu-id="43446-105">This data can be promoted into the message context by the XML disassembler to provide easier access from a variety of BizTalk Server components.</span></span> <span data-ttu-id="43446-106">对于出站 XML 实例消息，XML 组装器可以将值从消息上下文降级到信封中，以便在实例消息传输中包括这些值。</span><span class="sxs-lookup"><span data-stu-id="43446-106">For outbound XML instance messages, the XML assembler can demote values from the message context into an envelope for inclusion in the instance message transmission.</span></span>  
  
-   <span data-ttu-id="43446-107">可以使用 XML 信封将多个 XML 文档合并到单个有效的 XML 实例消息中。</span><span class="sxs-lookup"><span data-stu-id="43446-107">XML envelopes can be used to combine multiple XML documents into a single, valid XML instance message.</span></span> <span data-ttu-id="43446-108">如果不使用信封来将多个文档包装到单个根标记中，则不会将包含多个文档的 XML 实例消息认定为格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="43446-108">Without an envelope to wrap multiple documents within a single root tag, an XML instance message containing multiple documents would not qualify as well-formed XML.</span></span>  
  
 <span data-ttu-id="43446-109">典型的 XML 信封（以粗体显示）既包含数据，又包含用于分隔其包含的一个或多个 XML 文档（以常规字体显示）的标记。</span><span class="sxs-lookup"><span data-stu-id="43446-109">A typical XML envelope (shown in bold type) contains both data and a tag used to delimit the one or more XML documents (shown in regular font) that it contains.</span></span>  
  
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
  
 <span data-ttu-id="43446-110">XML 信封（以粗体显示）不必包含任何数据或用于分隔其包含的 XML 文档（以常规类型显示）的标记，这种情况比较少见，但仍然有效。</span><span class="sxs-lookup"><span data-stu-id="43446-110">Less common, but still valid, an XML envelope (shown in bold type) need not contain any data or a tag for delimiting the XML documents (shown in regular type) that it contains.</span></span>  
  
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
  
 <span data-ttu-id="43446-111">在这种情况下，XML 信封仅由开始信封标记和结束信封标记组成。</span><span class="sxs-lookup"><span data-stu-id="43446-111">In such cases, the XML envelope consists of nothing other than the starting and ending envelope tags.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43446-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43446-112">See Also</span></span>  
 <span data-ttu-id="43446-113">[嵌套的 XML 消息包络线](../core/nested-xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="43446-113">[Nested XML Message Envelopes](../core/nested-xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="43446-114">[XML 消息的结构](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="43446-114">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="43446-115">如何为包络线创建架构</span><span class="sxs-lookup"><span data-stu-id="43446-115">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)