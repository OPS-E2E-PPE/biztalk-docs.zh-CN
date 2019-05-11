---
title: IBaseMessage 接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009c9df42e8dbce58f3b731932ef4077693f0f63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382812"
---
# <a name="ibasemessage-interface"></a><span data-ttu-id="726e1-102">IBaseMessage 接口</span><span class="sxs-lookup"><span data-stu-id="726e1-102">IBaseMessage Interface</span></span>
<span data-ttu-id="726e1-103">当接收适配器接受传入数据包通过其协议时，它使用**IBaseMessage**接口，以创建一条消息将传递给消息引擎。</span><span class="sxs-lookup"><span data-stu-id="726e1-103">When a receive adapter accepts an incoming data packet through its protocol, it uses the **IBaseMessage** interface to create a message to pass to the Messaging Engine.</span></span> <span data-ttu-id="726e1-104">使用此接口来表示所有消息。</span><span class="sxs-lookup"><span data-stu-id="726e1-104">All messages are represented by using this interface.</span></span>  
  
 <span data-ttu-id="726e1-105">一条消息有一个或多个消息部分由**IBaseMessagePart**接口。</span><span class="sxs-lookup"><span data-stu-id="726e1-105">A message has one or more message parts represented by the **IBaseMessagePart** interface.</span></span> <span data-ttu-id="726e1-106">每个消息部分已通过其数据的引用**IStream**接口指针。</span><span class="sxs-lookup"><span data-stu-id="726e1-106">Each message part has a reference to its data through an **IStream** interface pointer.</span></span> <span data-ttu-id="726e1-107">表示将消息上下文及其**IBaseMessageContext**接口。</span><span class="sxs-lookup"><span data-stu-id="726e1-107">The context of a message is represented by its **IBaseMessageContext** interface.</span></span> <span data-ttu-id="726e1-108">下图说明了 BizTalk 消息对象模型。</span><span class="sxs-lookup"><span data-stu-id="726e1-108">The following figure illustrates the BizTalk message object model.</span></span>  
  
 <span data-ttu-id="726e1-109">![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")</span><span class="sxs-lookup"><span data-stu-id="726e1-109">![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")</span></span>  
  
 <span data-ttu-id="726e1-110">消息上下文是一个字典，其中为键属性名称和属性命名空间的组合。</span><span class="sxs-lookup"><span data-stu-id="726e1-110">The message context is a dictionary that is keyed on a combination of the property name and the property namespace.</span></span> <span data-ttu-id="726e1-111">这会阻止来自不同源，例如，类似的命名属性之间的冲突[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统属性和自定义适配器属性。</span><span class="sxs-lookup"><span data-stu-id="726e1-111">This prevents collisions between similarly named properties from different sources, for example, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system properties and custom adapter properties.</span></span> <span data-ttu-id="726e1-112">这些属性的值是在.NET 类型的**对象**，但这些属性实际上是变体。</span><span class="sxs-lookup"><span data-stu-id="726e1-112">The values for these properties are of the .NET type **object**, but in fact these properties are VARIANTs.</span></span>  
  
 <span data-ttu-id="726e1-113">每个部分具有一个部分上下文，也是一个字典，但不支持命名空间的概念。</span><span class="sxs-lookup"><span data-stu-id="726e1-113">Each part has a part context that is also a dictionary but without the notion of a namespace.</span></span> <span data-ttu-id="726e1-114">部分上下文的值是指该部分数据的元数据。</span><span class="sxs-lookup"><span data-stu-id="726e1-114">The value of a part context is metadata referring to the data for that part.</span></span> <span data-ttu-id="726e1-115">这就**Charset**属性，它指定用于对消息编码的字符集。</span><span class="sxs-lookup"><span data-stu-id="726e1-115">An example of this is the **Charset** property that specifies the character set used for encoding the message.</span></span>  
  
 <span data-ttu-id="726e1-116">属性可能会写入到和从消息上下文中读取。</span><span class="sxs-lookup"><span data-stu-id="726e1-116">Properties may be written to and read from the message context.</span></span> <span data-ttu-id="726e1-117">它们还可能会提升要用于消息路由。</span><span class="sxs-lookup"><span data-stu-id="726e1-117">They may also be promoted to be used for message routing.</span></span> <span data-ttu-id="726e1-118">正在升级的意味着将其随消息流动的元数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="726e1-118">Being promoted means they are written as a part of metadata that flows with the message.</span></span> <span data-ttu-id="726e1-119">使用升级的属性，其值以在创建发送端口和业务流程的筛选器表达式中使用。</span><span class="sxs-lookup"><span data-stu-id="726e1-119">A promoted property allows its value to be used in the creation of filter expressions on send ports and orchestrations.</span></span> <span data-ttu-id="726e1-120">下游组件和业务流程中的用户代码可能会读取升级的属性，并还写入新值。</span><span class="sxs-lookup"><span data-stu-id="726e1-120">Downstream components and user code in orchestrations may read promoted properties and also write new values to them.</span></span>  
  
 <span data-ttu-id="726e1-121">与现有订阅匹配已提升的属性并将其用于将消息路由后，该属性被降级，以防止循环订阅匹配。</span><span class="sxs-lookup"><span data-stu-id="726e1-121">After a promoted property has been matched to an existing subscription and used to route a message, the property is demoted to prevent cyclic subscription matches.</span></span> <span data-ttu-id="726e1-122">降级的属性将保留在消息上下文，因为元数据但会失去升级的状态。</span><span class="sxs-lookup"><span data-stu-id="726e1-122">A demoted property remains on the message context as metadata but loses its promoted status.</span></span>  
  
 <span data-ttu-id="726e1-123">**实现提示：** 在运行时将消息上下文属性加载到内存。</span><span class="sxs-lookup"><span data-stu-id="726e1-123">**Implementation Tip:** Message context properties are loaded into memory at run time.</span></span> <span data-ttu-id="726e1-124">过大的数据应不会写入消息上下文因为这可能会影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持大消息。</span><span class="sxs-lookup"><span data-stu-id="726e1-124">Very large pieces of data should not be written to the message context because this could potentially break the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] large message support.</span></span> <span data-ttu-id="726e1-125">对象可能会被序列化到消息上下文中实现**IPersistStream**接口。</span><span class="sxs-lookup"><span data-stu-id="726e1-125">Objects may be serialized into the message context providing they implement the **IPersistStream** interface.</span></span> <span data-ttu-id="726e1-126">此外，升级的属性仅限于 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="726e1-126">Also, promoted properties are limited to 255 characters.</span></span>  
  
 <span data-ttu-id="726e1-127">始终应使用消息工厂来创建新消息。</span><span class="sxs-lookup"><span data-stu-id="726e1-127">The message factory should always be used to create new messages.</span></span>  <span data-ttu-id="726e1-128">下面的代码段演示了如何从适配器接收到的数据流中创建新的 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="726e1-128">The following code fragment illustrates how to create a new BizTalk message from the data stream received by the adapter.</span></span>  
  
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