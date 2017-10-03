---
title: "如何使用 MessageBox 直接绑定端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1839184b-408e-4ac6-94a4-a0eb708183f6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82fbe52d46847bdaa7caffbb4402ce8d380a73f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-messagebox-direct-bound-ports"></a><span data-ttu-id="7bc3d-102">如何使用 MessageBox 直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="7bc3d-102">How to Use MessageBox Direct Bound Ports</span></span>
<span data-ttu-id="7bc3d-103">MessageBox 直接绑定的端口，可以直接在没有显式的接收方 MessageBox 数据库丢弃的消息并订阅满足特定条件的消息，而不是来自特定发件人的消息。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-103">MessageBox direct bound ports enable you to drop messages directly into the MessageBox database without an explicit recipient, and to subscribe to messages that meet certain criteria rather than messages that come from a particular sender.</span></span>  
  
 <span data-ttu-id="7bc3d-104">在消息框上发送消息直接绑定的端口是等效于将消息发布到消息总线 — 在这种情况下，到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-104">Sending a message on a MessageBox direct bound port is equivalent to publishing the message to a message bus—in this case, to the MessageBox database.</span></span> <span data-ttu-id="7bc3d-105">对于任何已发布的消息，可存在任意数目的订户；并且，如果在您发布消息时没有任何订户对此消息感兴趣，将引发“找不到订阅”异常。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-105">There can be any number of subscribers for any published message, and if there are no subscribers interested in the message at the time you publish it, a "subscription not found" exception will be thrown.</span></span> <span data-ttu-id="7bc3d-106">如果你在使用特定的接收人的需求的 MessageBox 直接绑定端口通过发送消息，你可能想要将属性设置为中的特定值**消息分配**你预期的订阅服务器，若要寻找的形状。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-106">If you send a message through a MessageBox direct bound port with a particular recipient in mind, you may want to set properties to particular values in the **Message Assignment** shape for your intended subscriber to look for.</span></span> <span data-ttu-id="7bc3d-107">你可以设置基于预定义的 BizTalk Server 属性定义或你自己的属性定义的属性。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-107">You can set the properties based on BizTalk Server predefined property definitions or on your own property definitions.</span></span> <span data-ttu-id="7bc3d-108">例如：</span><span class="sxs-lookup"><span data-stu-id="7bc3d-108">For example:</span></span>  
  
```  
myMessage(PropertyNamespace.PropertyName) = "My Property")  
```  
  
 <span data-ttu-id="7bc3d-109">接收任何消息通过 MessageBox 直接绑定端口相当于使用筛选器条件消息总线订阅。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-109">Receiving a message through a MessageBox direct bound port is equivalent to subscribing to a message bus with filter criteria.</span></span> <span data-ttu-id="7bc3d-110">消息的收件人可以是服务的任何类型的消息，可以订阅其中包括业务流程，并发送端口。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-110">Recipients of the message can be any type of service that can subscribe to messages, which includes orchestrations and send ports.</span></span> <span data-ttu-id="7bc3d-111">激活**接收**形状订阅是消息类型和筛选器表达式中，和非激活**接收**形状订阅是消息类型和相关设置。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-111">For an activating **Receive** shape the subscription is the message type and the filter expression, and for a non-activating **Receive** shape the subscription is the message type and the correlation set.</span></span> <span data-ttu-id="7bc3d-112">每个**接收**形状始终包括作为其订阅的一部分的消息类型。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-112">Every **Receive** shape always includes the message type as part of its subscription.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bc3d-113">如果已激活，则必须使用筛选器表达式**接收**接收的消息的类型的形状**System.Xml.XmlDocument**或**Microsoft.XLANGs.BaseTypes.Any**与订阅定义的路由直接绑定的端口。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-113">You must use a filter expression if you have an activating **Receive** shape receiving a message of type **System.Xml.XmlDocument** or **Microsoft.XLANGs.BaseTypes.Any** on a direct bound port with subscription-defined routing.</span></span>  
  
 <span data-ttu-id="7bc3d-114">如果你未指定任何筛选器条件中激活**接收**形状连接到 MessageBox 直接绑定端口，则订阅将类似于以下：</span><span class="sxs-lookup"><span data-stu-id="7bc3d-114">If you did not specify any filter criteria in the activating **Receive** shape connected to a MessageBox direct bound port, then the subscription will look similar to the following:</span></span>  
  
```  
http://schemas.microsoft.com/BizTalk/2003/system-properties.ReceivePortID == {2F6A80E1-2518-4A69-9C28-401C2DB1CBF6} And  
http://schemas.microsoft.com/BizTalk/2003/system-properties.MessageType == http://MyMessageType  
```  
  
 <span data-ttu-id="7bc3d-115">在前面的示例中，MessageBox 直接绑定接收端口将接收每条消息为配置的端口的操作的消息类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-115">In the preceding example, the MessageBox direct bound receive port will receive every message that matches the message type that the port’s operation is configured for.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bc3d-116">当使用 MessageBox 直接绑定接收端口时，您应使筛选尽可能具体。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-116">When using MessageBox direct bound receive ports, you should make the filter as specific as possible.</span></span> <span data-ttu-id="7bc3d-117">如果你不一定要筛选器足够具体，您的业务流程可能会收到不需要的消息。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-117">If you do not make the filter specific enough, your orchestration may receive unwanted messages.</span></span>  
  
 <span data-ttu-id="7bc3d-118">若要配置的 MessageBox 直接绑定的端口，选择**端口之间的路由将定义消息框数据库中的传入消息的筛选器表达式**在端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-118">To configure a MessageBox direct bound port, select **Routing between ports will be defined by filter expressions on incoming messages in the Message Box database** in the Port Configuration Wizard.</span></span>  
  
 <span data-ttu-id="7bc3d-119">如何使用 MessageBox 直接绑定的端口的示例，请参阅"直接绑定到 MessageBox 数据库中业务流程"中的 SDK 示例在[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="7bc3d-119">For an example of how to use MessageBox direct bound ports, see the SDK sample "Direct Binding to the MessageBox Database in Orchestrations" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc3d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bc3d-120">See Also</span></span>  
 <span data-ttu-id="7bc3d-121">[如何使用自关联 Direct 绑定端口](../core/how-to-use-self-correlating-direct-bound-ports.md) </span><span class="sxs-lookup"><span data-stu-id="7bc3d-121">[How to Use Self-Correlating Direct Bound Ports](../core/how-to-use-self-correlating-direct-bound-ports.md) </span></span>  
 [<span data-ttu-id="7bc3d-122">如何直接使用合作伙伴业务流程绑定端口</span><span class="sxs-lookup"><span data-stu-id="7bc3d-122">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)