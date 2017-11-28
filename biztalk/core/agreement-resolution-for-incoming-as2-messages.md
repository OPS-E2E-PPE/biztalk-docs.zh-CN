---
title: "为传入 AS2 消息的协议解析 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 746d01af-de6a-4d5d-9433-b0e1a2b41861
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e5e9795979ddf0a8b8f13fe7ab53bd4e783bd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="agreement-resolution-for-incoming-as2-messages"></a><span data-ttu-id="2159c-102">传入 AS2 消息的协议解析</span><span class="sxs-lookup"><span data-stu-id="2159c-102">Agreement Resolution for Incoming AS2 Messages</span></span>
<span data-ttu-id="2159c-103">当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通过 HTTP/HTTPS 传输接收 EDIINT/AS2 编码消息时，它会尝试确定发送该消息的贸易合作伙伴的业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="2159c-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDIINT/AS2-encoded message over HTTP/HTTPS transport, it attempts to determine the trading partner’s business profile that sent the message.</span></span> <span data-ttu-id="2159c-104">它通过尝试执行以下操作（按照所示顺序）来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="2159c-104">It does so by attempting to do the following (in the order shown):</span></span>  
  
1.  <span data-ttu-id="2159c-105">请 AS2 之间的匹配项的从标头中将传入消息的值与**AS2-从**中**标识符**中的单向 AS2 协议页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2159c-105">Make a match between the AS2-From header in the incoming message with the value for **AS2-From** in the **Identifiers** page of the one-way AS2 agreement in the **Agreement Properties** dialog box.</span></span>  
  
2.  <span data-ttu-id="2159c-106">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定协议，则它会尝试将为传入的消息设置的 AS2-From 上下文属性与贸易合作伙伴的名称进行匹配。</span><span class="sxs-lookup"><span data-stu-id="2159c-106">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement, it will attempt to match the AS2-From context property that is set for the incoming message with the name of a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2159c-107">由于 AS2-From 标头只能包含 ASCII 字符，因此必须确保贸易合作伙伴名称和 AS2-From 别名也只包含 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="2159c-107">Since the AS2-From header can only contain ASCII characters, you must ensure that your trading partner name and the AS2-From alias also contain only ASCII characters.</span></span> <span data-ttu-id="2159c-108">如果不是完全匹配，BizTalk 将无法基于传入消息标头确定协议。</span><span class="sxs-lookup"><span data-stu-id="2159c-108">If an exact match does not occur, BizTalk will be unable to determine the agreement based on the incoming message headers.</span></span>  
  
 <span data-ttu-id="2159c-109">只有在确定了协议的情况下，AS2 接收管道才会处理该消息。</span><span class="sxs-lookup"><span data-stu-id="2159c-109">The AS2 receive pipeline will process the message only if an agreement is determined.</span></span> <span data-ttu-id="2159c-110">与 EDI 处理过程不同，如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定协议，则它没有任何可以使用的后备 AS2 属性。</span><span class="sxs-lookup"><span data-stu-id="2159c-110">Unlike in EDI processing, there are no fallback AS2 properties that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can use if it cannot determine the agreement.</span></span>  
  
 <span data-ttu-id="2159c-111">一旦管道已确定该协议，它将检查断言的设置**使用协议的验证和 MDN 设置改为消息标头**中的属性**验证**单向 AS2 页中的协议**协议设置**对话框。</span><span class="sxs-lookup"><span data-stu-id="2159c-111">Once the pipeline has determined the agreement, it will check the setting of the **Use agreement settings for validation and MDN instead message header** property in the **Validation** page of the one-way AS2 agreement in the **Agreement Settings** dialog box.</span></span> <span data-ttu-id="2159c-112">如果该属性处于选中状态，接收管道将使用协议属性处理消息。</span><span class="sxs-lookup"><span data-stu-id="2159c-112">If that property is checked, the receive pipeline will use the agreement properties to process the message.</span></span> <span data-ttu-id="2159c-113">如果未选中该属性，接收管道将使用消息的 AS2 标头中的值处理消息。</span><span class="sxs-lookup"><span data-stu-id="2159c-113">If the property is cleared, the receive pipeline will use the values in the AS2 header of the message to process it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2159c-114">在协议解析过程中确定的 AS2 协议可能不是作为 EDI 负载相同的协议。</span><span class="sxs-lookup"><span data-stu-id="2159c-114">The AS2 agreement that is determined during agreement resolution may not be the same agreement as the EDI payload.</span></span> <span data-ttu-id="2159c-115">AS2 协议可能表示将路由从多个方 EDI 文档 clearinghouse 是 EDI 和 AS2 必须共享相同的协议，不要求。</span><span class="sxs-lookup"><span data-stu-id="2159c-115">There is no requirement that AS2 and EDI must share the same agreement, as the AS2 agreement may represent a clearinghouse that routes EDI documents from multiple parties.</span></span>  
  
 <span data-ttu-id="2159c-116">接收过程的更多详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="2159c-116">For more details on the receive process, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2159c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2159c-117">See Also</span></span>  
 [<span data-ttu-id="2159c-118">BizTalk Server 接收 AS2 消息的方式</span><span class="sxs-lookup"><span data-stu-id="2159c-118">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)