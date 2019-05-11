---
title: 传入 AS2 消息的协议解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 746d01af-de6a-4d5d-9433-b0e1a2b41861
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf569721a2a97aeb93b8b753599c64ae0ef890ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359877"
---
# <a name="agreement-resolution-for-incoming-as2-messages"></a><span data-ttu-id="d5684-102">传入 AS2 消息的协议解析</span><span class="sxs-lookup"><span data-stu-id="d5684-102">Agreement Resolution for Incoming AS2 Messages</span></span>
<span data-ttu-id="d5684-103">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDIINT/AS2 编码的消息通过 HTTP/HTTPS 传输，它会尝试确定发送消息的贸易合作伙伴的业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="d5684-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDIINT/AS2-encoded message over HTTP/HTTPS transport, it attempts to determine the trading partner’s business profile that sent the message.</span></span> <span data-ttu-id="d5684-104">这是通过尝试执行以下 （按所示的顺序）：</span><span class="sxs-lookup"><span data-stu-id="d5684-104">It does so by attempting to do the following (in the order shown):</span></span>  
  
1. <span data-ttu-id="d5684-105">使匹配 AS2-From 的值与传入消息中的标头**AS2-从**中**标识符**中的单向 AS2 协议页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="d5684-105">Make a match between the AS2-From header in the incoming message with the value for **AS2-From** in the **Identifiers** page of the one-way AS2 agreement in the **Agreement Properties** dialog box.</span></span>  
  
2. <span data-ttu-id="d5684-106">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定协议，它将尝试匹配 AS2-From 上下文属性设置为将传入消息与贸易合作伙伴的名称。</span><span class="sxs-lookup"><span data-stu-id="d5684-106">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement, it will attempt to match the AS2-From context property that is set for the incoming message with the name of a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5684-107">由于 AS2-从标头只能包含 ASCII 字符，则必须确保贸易合作伙伴名称和 AS2-From 别名也只包含 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="d5684-107">Since the AS2-From header can only contain ASCII characters, you must ensure that your trading partner name and the AS2-From alias also contain only ASCII characters.</span></span> <span data-ttu-id="d5684-108">如果完全匹配项不会发生，BizTalk 将无法确定传入消息标头所基于的协议。</span><span class="sxs-lookup"><span data-stu-id="d5684-108">If an exact match does not occur, BizTalk will be unable to determine the agreement based on the incoming message headers.</span></span>  
  
 <span data-ttu-id="d5684-109">AS2 接收管道将处理该消息，仅当确定了协议。</span><span class="sxs-lookup"><span data-stu-id="d5684-109">The AS2 receive pipeline will process the message only if an agreement is determined.</span></span> <span data-ttu-id="d5684-110">不同于在 EDI 处理中，没有回退 AS2 属性的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果它无法确定协议，可以使用。</span><span class="sxs-lookup"><span data-stu-id="d5684-110">Unlike in EDI processing, there are no fallback AS2 properties that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can use if it cannot determine the agreement.</span></span>  
  
 <span data-ttu-id="d5684-111">一旦管道确定了协议，它将检查的设置**使用协议设置用于验证和 MDN 而非消息标头**属性中的**验证**页的单向 AS2中的协议**协议设置**对话框。</span><span class="sxs-lookup"><span data-stu-id="d5684-111">Once the pipeline has determined the agreement, it will check the setting of the **Use agreement settings for validation and MDN instead message header** property in the **Validation** page of the one-way AS2 agreement in the **Agreement Settings** dialog box.</span></span> <span data-ttu-id="d5684-112">如果该属性为选中状态，接收管道将使用协议属性来处理该消息。</span><span class="sxs-lookup"><span data-stu-id="d5684-112">If that property is checked, the receive pipeline will use the agreement properties to process the message.</span></span> <span data-ttu-id="d5684-113">如果清除该属性，则接收管道将使用值的消息的 AS2 头部中要对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="d5684-113">If the property is cleared, the receive pipeline will use the values in the AS2 header of the message to process it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5684-114">在协议解析过程中确定的 AS2 协议可能不是 EDI 负载的形式相同的协议。</span><span class="sxs-lookup"><span data-stu-id="d5684-114">The AS2 agreement that is determined during agreement resolution may not be the same agreement as the EDI payload.</span></span> <span data-ttu-id="d5684-115">没有要求，AS2 和 EDI 必须共享相同的协议，因为 AS2 协议可能代表将路由从多个参与方的 EDI 文档交换所。</span><span class="sxs-lookup"><span data-stu-id="d5684-115">There is no requirement that AS2 and EDI must share the same agreement, as the AS2 agreement may represent a clearinghouse that routes EDI documents from multiple parties.</span></span>  
  
 <span data-ttu-id="d5684-116">有关接收过程的更多详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="d5684-116">For more details on the receive process, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5684-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5684-117">See Also</span></span>  
 [<span data-ttu-id="d5684-118">BizTalk Server 如何接收 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="d5684-118">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)