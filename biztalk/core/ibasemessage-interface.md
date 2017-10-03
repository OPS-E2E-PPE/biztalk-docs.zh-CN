---
title: "IBaseMessage 接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de478b27105ee6c01d582aa9b728bd0496d0487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ibasemessage-interface"></a><span data-ttu-id="5da0a-102">IBaseMessage 接口</span><span class="sxs-lookup"><span data-stu-id="5da0a-102">IBaseMessage Interface</span></span>
<span data-ttu-id="5da0a-103">当接收适配器接受传入的数据包通过其协议时，它会使用**IBaseMessage**接口可创建要传递给 the Messaging Engine 一条消息。</span><span class="sxs-lookup"><span data-stu-id="5da0a-103">When a receive adapter accepts an incoming data packet through its protocol, it uses the **IBaseMessage** interface to create a message to pass to the Messaging Engine.</span></span> <span data-ttu-id="5da0a-104">所有消息都是使用这个接口传递的。</span><span class="sxs-lookup"><span data-stu-id="5da0a-104">All messages are represented by using this interface.</span></span>  
  
 <span data-ttu-id="5da0a-105">一条消息具有一个或多个消息部分由**IBaseMessagePart**接口。</span><span class="sxs-lookup"><span data-stu-id="5da0a-105">A message has one or more message parts represented by the **IBaseMessagePart** interface.</span></span> <span data-ttu-id="5da0a-106">每个消息部分有对通过其数据的引用**IStream**接口指针。</span><span class="sxs-lookup"><span data-stu-id="5da0a-106">Each message part has a reference to its data through an **IStream** interface pointer.</span></span> <span data-ttu-id="5da0a-107">一条消息的上下文都由其**IBaseMessageContext**接口。</span><span class="sxs-lookup"><span data-stu-id="5da0a-107">The context of a message is represented by its **IBaseMessageContext** interface.</span></span> <span data-ttu-id="5da0a-108">下图阐释了 BizTalk 消息对象模型。</span><span class="sxs-lookup"><span data-stu-id="5da0a-108">The following figure illustrates the BizTalk message object model.</span></span>  
  
 ![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")  
  
 <span data-ttu-id="5da0a-109">消息上下文是一个字典，以属性名称和属性命名空间的组合为键。</span><span class="sxs-lookup"><span data-stu-id="5da0a-109">The message context is a dictionary that is keyed on a combination of the property name and the property namespace.</span></span> <span data-ttu-id="5da0a-110">这会阻止来自不同源，例如，类似名称的属性之间的冲突[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统属性和自定义适配器属性。</span><span class="sxs-lookup"><span data-stu-id="5da0a-110">This prevents collisions between similarly named properties from different sources, for example, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system properties and custom adapter properties.</span></span> <span data-ttu-id="5da0a-111">这些属性的值是.NET 类型的**对象**，但这些属性实际上是变体。</span><span class="sxs-lookup"><span data-stu-id="5da0a-111">The values for these properties are of the .NET type **object**, but in fact these properties are VARIANTs.</span></span>  
  
 <span data-ttu-id="5da0a-112">每个部分均有一个部分上下文，同样也是字典，但没有命名空间这个概念。</span><span class="sxs-lookup"><span data-stu-id="5da0a-112">Each part has a part context that is also a dictionary but without the notion of a namespace.</span></span> <span data-ttu-id="5da0a-113">部分上下文的值为元数据，指向该部分数据。</span><span class="sxs-lookup"><span data-stu-id="5da0a-113">The value of a part context is metadata referring to the data for that part.</span></span> <span data-ttu-id="5da0a-114">此示例是**Charset**指定用于编码消息的字符集的属性。</span><span class="sxs-lookup"><span data-stu-id="5da0a-114">An example of this is the **Charset** property that specifies the character set used for encoding the message.</span></span>  
  
 <span data-ttu-id="5da0a-115">属性可以写入消息上下文，也可以从消息上下文中读取。</span><span class="sxs-lookup"><span data-stu-id="5da0a-115">Properties may be written to and read from the message context.</span></span> <span data-ttu-id="5da0a-116">还可以升级属性，以用于消息路由。</span><span class="sxs-lookup"><span data-stu-id="5da0a-116">They may also be promoted to be used for message routing.</span></span> <span data-ttu-id="5da0a-117">升级意味着将其作为元数据的一部分随消息流动。</span><span class="sxs-lookup"><span data-stu-id="5da0a-117">Being promoted means they are written as a part of metadata that flows with the message.</span></span> <span data-ttu-id="5da0a-118">属性经升级后，其值可用于对发送端口和业务流程创建筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="5da0a-118">A promoted property allows its value to be used in the creation of filter expressions on send ports and orchestrations.</span></span> <span data-ttu-id="5da0a-119">业务流程中的下游组件和用户代码可读取升级属性，还可以对属性赋新值。</span><span class="sxs-lookup"><span data-stu-id="5da0a-119">Downstream components and user code in orchestrations may read promoted properties and also write new values to them.</span></span>  
  
 <span data-ttu-id="5da0a-120">升级属性与现有订阅匹配完毕并用于路由消息后，该属性将被降级，以防止发生循环订阅匹配。</span><span class="sxs-lookup"><span data-stu-id="5da0a-120">After a promoted property has been matched to an existing subscription and used to route a message, the property is demoted to prevent cyclic subscription matches.</span></span> <span data-ttu-id="5da0a-121">降级属性仍作为元数据留在消息上下文中，但会失去升级状态。</span><span class="sxs-lookup"><span data-stu-id="5da0a-121">A demoted property remains on the message context as metadata but loses its promoted status.</span></span>  
  
 <span data-ttu-id="5da0a-122">**实现提示：**消息上下文属性都在运行时加载到内存。</span><span class="sxs-lookup"><span data-stu-id="5da0a-122">**Implementation Tip:** Message context properties are loaded into memory at run time.</span></span> <span data-ttu-id="5da0a-123">非常大片的数据应不会写入消息上下文因为这可能会中断[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持大消息。</span><span class="sxs-lookup"><span data-stu-id="5da0a-123">Very large pieces of data should not be written to the message context because this could potentially break the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] large message support.</span></span> <span data-ttu-id="5da0a-124">可能将对象序列化到消息上下文提供其实现**IPersistStream**接口。</span><span class="sxs-lookup"><span data-stu-id="5da0a-124">Objects may be serialized into the message context providing they implement the **IPersistStream** interface.</span></span> <span data-ttu-id="5da0a-125">同样，升级属性的长度也限制在 255 个字符之内。</span><span class="sxs-lookup"><span data-stu-id="5da0a-125">Also, promoted properties are limited to 255 characters.</span></span>  
  
 <span data-ttu-id="5da0a-126">应始终应当使用消息工厂来创建新消息。</span><span class="sxs-lookup"><span data-stu-id="5da0a-126">The message factory should always be used to create new messages.</span></span>  <span data-ttu-id="5da0a-127">下面的代码段演示了如何用适配器接收的数据流来创建新的 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="5da0a-127">The following code fragment illustrates how to create a new BizTalk message from the data stream received by the adapter.</span></span>  
  
```  
using Microsoft.BizTalk.Message.Interop;  
  
IBaseMessage CreateMessage( Stream s, IBaseMessageFactory msgFactory )  
{  
IBaseMessage msg = null;  
IBaseMessagePart part = msgFactory.CreateMessagePart();  
part.Data = s;  
msg = msgFactory.CreateMessage();  
msg.AddPart("body", part, true);  
return msg;  
}  
```