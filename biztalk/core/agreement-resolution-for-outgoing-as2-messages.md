---
title: 对传出 AS2 消息的协议解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 578d7565-534c-4c13-b473-975f347f3a9b
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8329b2b80ca3b9bfd6b34379d936d6be1df3ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975854"
---
# <a name="agreement-resolution-for-outgoing-as2-messages"></a><span data-ttu-id="003a6-102">对传出 AS2 消息的协议解析</span><span class="sxs-lookup"><span data-stu-id="003a6-102">Agreement Resolution for Outgoing AS2 Messages</span></span>
<span data-ttu-id="003a6-103">当 AS2 发送管道处理通过 HTTP/HTTPS 传输传出的 EDIINT/AS2 编码的消息时，它会确定此消息将解析到的协议。</span><span class="sxs-lookup"><span data-stu-id="003a6-103">When an AS2 send pipeline processes an outgoing EDIINT/AS2-encoded message over HTTP/HTTPS transport, it determines the agreement that the message will resolve to.</span></span> <span data-ttu-id="003a6-104">然后，它将使用这些协议属性来处理此传出消息。</span><span class="sxs-lookup"><span data-stu-id="003a6-104">It will then use those agreement properties to process the outgoing message.</span></span> <span data-ttu-id="003a6-105">发送管道将使用以下条件来确定协议（按优先顺序）：</span><span class="sxs-lookup"><span data-stu-id="003a6-105">The send pipeline will use the following criteria to determine the agreement (in order of priority):</span></span>  
  
1. <span data-ttu-id="003a6-106">发送管道将尝试将 AS2From 和 AS2To 上下文属性与指定为协议属性的一部分的 AS2From 和 AS2To 的值匹配。</span><span class="sxs-lookup"><span data-stu-id="003a6-106">The send pipeline attempts to match the AS2From and AS2To context properties with the values of AS2From and AS2To specified as part of the agreement properties.</span></span>  
  
2. <span data-ttu-id="003a6-107">如果在上一步失败，发送管道将尝试匹配出站消息的 AS2To 上下文属性设置为中的其他协议解析程序的 AS2To 属性的值与**标识符**协议选项卡属性。</span><span class="sxs-lookup"><span data-stu-id="003a6-107">If the previous step fails, the send pipeline will attempt to match the AS2To context property of the outbound message with the value of AS2To property, which is set as additional agreement resolver in the **Identifiers** tab of agreement properties.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="003a6-108"> 不会将 AS2To 属性写入上下文。</span><span class="sxs-lookup"><span data-stu-id="003a6-108"> does not write the AS2To property to the context.</span></span> <span data-ttu-id="003a6-109">如果要对 AS2To 上下文属性执行协议解析，您必须并入一个自定义业务流程或自定义管道组件来执行此解析。</span><span class="sxs-lookup"><span data-stu-id="003a6-109">If you want to perform agreement resolution on the AS2To context property, you will have to incorporate a custom orchestration or a custom pipeline component to do so.</span></span> <span data-ttu-id="003a6-110">有关详细信息，请参阅[写入 AS2 上下文属性进行出站参与方解析](../core/writing-as2-context-properties-for-outbound-party-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="003a6-110">For more information, see [Writing AS2 Context Properties for Outbound Party Resolution](../core/writing-as2-context-properties-for-outbound-party-resolution.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="003a6-111">当您使用动态发送端口时，必须将 AS2To 属性写入上下文以进行协议解析。</span><span class="sxs-lookup"><span data-stu-id="003a6-111">When you are using a dynamic send port, the AS2To property must be written to the context for agreement resolution.</span></span>  
  
3. <span data-ttu-id="003a6-112">如果上一步失败，则发送管道将尝试将与协议关联的发送端口与订阅消息的发送端口匹配。</span><span class="sxs-lookup"><span data-stu-id="003a6-112">If the previous step fails, the send pipeline will attempt to match the send port that is associated with an agreement with the send port that subscribed to the message.</span></span> <span data-ttu-id="003a6-113">发送端口是与中的协议相关联**发送端口**页的单向 AS2 协议**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="003a6-113">The send port is associated with the agreement in the **Send Ports** page of the one-way AS2 agreement of the **Agreement Properties** dialog box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="003a6-114">与 EDI 处理过程不同，如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定协议，则它没有任何可以使用的后备 AS2 属性。</span><span class="sxs-lookup"><span data-stu-id="003a6-114">Unlike in EDI processing, there are no fallback AS2 properties that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can use if it cannot determine the agreement.</span></span> <span data-ttu-id="003a6-115">但存在用于发送 MDN 的默认协议。</span><span class="sxs-lookup"><span data-stu-id="003a6-115">There is, however, a default agreement used to send an MDN.</span></span> <span data-ttu-id="003a6-116">此外，发送端口和 Http.UserHttpHeaders 上下文属性都不用于解析 MDN 的协议。</span><span class="sxs-lookup"><span data-stu-id="003a6-116">In addition, neither the send port nor the Http.UserHttpHeaders context property is used to resolve the agreement for an MDN.</span></span> <span data-ttu-id="003a6-117">有关详细信息，请参阅的"协议解析 MDN 的"部分[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="003a6-117">For more information, see the "Agreement Resolution for an MDN" section of [Sending an Outgoing MDN](../core/sending-an-outgoing-mdn.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="003a6-118">如果 AS2-To 协议属性中**标识符**页的单向 AS2 协议的**协议属性**对话框中设置默认情况下为英文参与方名称，而值中 AS2-To 标头as2 消息设置为非英文名称，然后将找不到匹配项。</span><span class="sxs-lookup"><span data-stu-id="003a6-118">If the AS2-To agreement property in the **Identifiers** page of the one-way AS2 agreement of the **Agreement Properties** dialog box is set by default to an English party name, and the value in the AS2-To header of the AS2 message is set to a non-English name, then the match will not be found.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="003a6-119">当通过 AS2 发送 EDI 时，您需要为 EDI 和 AS2 使用单独的协议。</span><span class="sxs-lookup"><span data-stu-id="003a6-119">When sending EDI over AS2, you are required to use separate agreements for both EDI and AS2.</span></span>  
  
 <span data-ttu-id="003a6-120">有关发送过程的更多详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="003a6-120">For more details on the send process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003a6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="003a6-121">See Also</span></span>  
 [<span data-ttu-id="003a6-122">BizTalk Server 如何发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="003a6-122">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)