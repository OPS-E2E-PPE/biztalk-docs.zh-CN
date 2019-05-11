---
title: 如何使用 MessageBox 直接绑定端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1839184b-408e-4ac6-94a4-a0eb708183f6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a37717639b12d3394ae3fc9e5de421c971fc2e73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333419"
---
# <a name="how-to-use-messagebox-direct-bound-ports"></a><span data-ttu-id="c9855-102">如何使用 MessageBox 直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="c9855-102">How to Use MessageBox Direct Bound Ports</span></span>
<span data-ttu-id="c9855-103">MessageBox 直接绑定的端口，可以删除直接到 MessageBox 数据库中没有显式的接收方的消息并订阅符合特定条件的消息而不是来自特定发件人的消息。</span><span class="sxs-lookup"><span data-stu-id="c9855-103">MessageBox direct bound ports enable you to drop messages directly into the MessageBox database without an explicit recipient, and to subscribe to messages that meet certain criteria rather than messages that come from a particular sender.</span></span>  
  
 <span data-ttu-id="c9855-104">消息的发送上一个消息框直接绑定的端口是等效于将消息发布到消息总线 — 在这种情况下，到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="c9855-104">Sending a message on a MessageBox direct bound port is equivalent to publishing the message to a message bus—in this case, to the MessageBox database.</span></span> <span data-ttu-id="c9855-105">可以有任意数量的订阅服务器的任何已发布的消息，并且如果没有任何订户关注该消息将其发布时，将引发"找不到订阅"异常。</span><span class="sxs-lookup"><span data-stu-id="c9855-105">There can be any number of subscribers for any published message, and if there are no subscribers interested in the message at the time you publish it, a "subscription not found" exception will be thrown.</span></span> <span data-ttu-id="c9855-106">如果您在特定的收件人记住通过 MessageBox 直接绑定端口发送消息，你可能想要将属性设置为中的特定值**消息赋值**预期订阅者要查找的形状。</span><span class="sxs-lookup"><span data-stu-id="c9855-106">If you send a message through a MessageBox direct bound port with a particular recipient in mind, you may want to set properties to particular values in the **Message Assignment** shape for your intended subscriber to look for.</span></span> <span data-ttu-id="c9855-107">可以设置基于 BizTalk Server 预定义的属性定义或您自己的属性定义的属性。</span><span class="sxs-lookup"><span data-stu-id="c9855-107">You can set the properties based on BizTalk Server predefined property definitions or on your own property definitions.</span></span> <span data-ttu-id="c9855-108">例如：</span><span class="sxs-lookup"><span data-stu-id="c9855-108">For example:</span></span>  
  
```  
myMessage(PropertyNamespace.PropertyName) = "My Property")  
```  
  
 <span data-ttu-id="c9855-109">接收的消息通过 MessageBox 直接绑定端口相当于使用筛选器条件的消息总线订阅。</span><span class="sxs-lookup"><span data-stu-id="c9855-109">Receiving a message through a MessageBox direct bound port is equivalent to subscribing to a message bus with filter criteria.</span></span> <span data-ttu-id="c9855-110">消息的收件人可以是服务的任何类型的消息，可以订阅其中包括业务流程和发送端口。</span><span class="sxs-lookup"><span data-stu-id="c9855-110">Recipients of the message can be any type of service that can subscribe to messages, which includes orchestrations and send ports.</span></span> <span data-ttu-id="c9855-111">对于激活**接收**形状，订阅是消息类型和筛选器表达式中，对于非激活**接收**形状，订阅是消息类型和相关设置。</span><span class="sxs-lookup"><span data-stu-id="c9855-111">For an activating **Receive** shape the subscription is the message type and the filter expression, and for a non-activating **Receive** shape the subscription is the message type and the correlation set.</span></span> <span data-ttu-id="c9855-112">每个**接收**形状都始终包括消息类型作为其订阅的一部分。</span><span class="sxs-lookup"><span data-stu-id="c9855-112">Every **Receive** shape always includes the message type as part of its subscription.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9855-113">如果已激活，则必须使用筛选器表达式**接收**接收的消息类型的形状**System.Xml.XmlDocument**或**Microsoft.XLANGs.BaseTypes.Any**在直接绑定端口与订阅定义的路由。</span><span class="sxs-lookup"><span data-stu-id="c9855-113">You must use a filter expression if you have an activating **Receive** shape receiving a message of type **System.Xml.XmlDocument** or **Microsoft.XLANGs.BaseTypes.Any** on a direct bound port with subscription-defined routing.</span></span>  
  
 <span data-ttu-id="c9855-114">如果未指定任何筛选器条件中的激活**接收**形状连接到 MessageBox 直接绑定端口，则订阅将如下所示：</span><span class="sxs-lookup"><span data-stu-id="c9855-114">If you did not specify any filter criteria in the activating **Receive** shape connected to a MessageBox direct bound port, then the subscription will look similar to the following:</span></span>  
  
```  
http://schemas.microsoft.com/BizTalk/2003/system-properties.ReceivePortID == {2F6A80E1-2518-4A69-9C28-401C2DB1CBF6} And  
http://schemas.microsoft.com/BizTalk/2003/system-properties.MessageType == http://MyMessageType  
```  
  
 <span data-ttu-id="c9855-115">在前面的示例中，MessageBox 直接绑定接收端口将接收每条消息为配置的端口操作的消息类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="c9855-115">In the preceding example, the MessageBox direct bound receive port will receive every message that matches the message type that the port’s operation is configured for.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9855-116">使用 MessageBox 直接绑定接收端口，您应使筛选尽可能具体。</span><span class="sxs-lookup"><span data-stu-id="c9855-116">When using MessageBox direct bound receive ports, you should make the filter as specific as possible.</span></span> <span data-ttu-id="c9855-117">如果您没有进行筛选器足够具体，您的业务流程可能会收到不需要的消息。</span><span class="sxs-lookup"><span data-stu-id="c9855-117">If you do not make the filter specific enough, your orchestration may receive unwanted messages.</span></span>  
  
 <span data-ttu-id="c9855-118">若要配置 MessageBox 直接绑定的端口，请选择**端口之间的路由将由 Messagebox 数据库中的传入消息的筛选器表达式定义**端口配置向导中。</span><span class="sxs-lookup"><span data-stu-id="c9855-118">To configure a MessageBox direct bound port, select **Routing between ports will be defined by filter expressions on incoming messages in the Message Box database** in the Port Configuration Wizard.</span></span>  
  
 <span data-ttu-id="c9855-119">有关如何使用 MessageBox 直接绑定的端口的示例，请参阅 SDK 示例"直接绑定到 MessageBox 数据库中的业务流程"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="c9855-119">For an example of how to use MessageBox direct bound ports, see the SDK sample "Direct Binding to the MessageBox Database in Orchestrations" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9855-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9855-120">See Also</span></span>  
 <span data-ttu-id="c9855-121">[如何使用自相关直接绑定端口](../core/how-to-use-self-correlating-direct-bound-ports.md) </span><span class="sxs-lookup"><span data-stu-id="c9855-121">[How to Use Self-Correlating Direct Bound Ports](../core/how-to-use-self-correlating-direct-bound-ports.md) </span></span>  
 [<span data-ttu-id="c9855-122">如何使用合作伙伴业务流程直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="c9855-122">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)