---
title: "消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, headers
- messages, acknowledgements
- messages, persisting
- messages
- examples, message headers
- properties
- message headers
- EMS messages
ms.assetid: 65bb3431-7186-4d4c-b004-932cdf070e73
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f7313e93029ca75d345aa4e9603699c50399230
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="messages"></a><span data-ttu-id="51c10-102">消息</span><span class="sxs-lookup"><span data-stu-id="51c10-102">Messages</span></span>
<span data-ttu-id="51c10-103">某个企业消息服务 (EMS) 消息，如 JMS 消息包含三个独立的部分： 标头、 属性和正文。</span><span class="sxs-lookup"><span data-stu-id="51c10-103">An Enterprise Message Service (EMS) message, like a JMS message, contains three separate parts: header, properties, and body.</span></span> <span data-ttu-id="51c10-104">标头是 EMS 消息中唯一必需的部分。</span><span class="sxs-lookup"><span data-stu-id="51c10-104">The header is the only required part of an EMS message.</span></span> <span data-ttu-id="51c10-105">本主题介绍如何在用于在 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器中处理消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-105">This topic describes how messages are treated in Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51c10-106">若要设置或检索一个标头字段 （例如，设置消息优先级或相关 ID） 或从业务流程的消息属性，必须添加对引用**Microsoft.BizTalk.Adapters.TIBCOEMSProperties.dll**中你使用解决方案资源管理器的项目。</span><span class="sxs-lookup"><span data-stu-id="51c10-106">To set or retrieve a header field (for example, set the Message Priority or Correlation ID) or a message property from the orchestration, you must add a reference to the **Microsoft.BizTalk.Adapters.TIBCOEMSProperties.dll** in your project using Solution Explorer.</span></span>  
  
## <a name="message-header"></a><span data-ttu-id="51c10-107">消息标头</span><span class="sxs-lookup"><span data-stu-id="51c10-107">Message Header</span></span>  
 <span data-ttu-id="51c10-108">消息标头包括一系列包含值的预定义字段。</span><span class="sxs-lookup"><span data-stu-id="51c10-108">The message header contains a series of predefined fields that contain values.</span></span> <span data-ttu-id="51c10-109">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器了解它在标头中可以设置和不可设置的内容。</span><span class="sxs-lookup"><span data-stu-id="51c10-109">BizTalk Adapter for TIBCO Enterprise Message Service knows what it can and cannot set in the header.</span></span> <span data-ttu-id="51c10-110">如果您尝试设置一个只读值，该适配器将在 Properties{} 部分中重定向或设置此值。</span><span class="sxs-lookup"><span data-stu-id="51c10-110">If you try to set a read-only value, the adapter redirects or sets your value in the Properties{} section.</span></span>  
  
### <a name="header-example"></a><span data-ttu-id="51c10-111">标头示例</span><span class="sxs-lookup"><span data-stu-id="51c10-111">Header Example</span></span>  
 <span data-ttu-id="51c10-112">在下面的示例，请注意，**属性 = {目标 = {字符串： 队列 [季 2 季]}}**。</span><span class="sxs-lookup"><span data-stu-id="51c10-112">In the following example, notice that **Properties= { Destination={String:Queue[Q2]} }**.</span></span> <span data-ttu-id="51c10-113">`Properties`是一个属性，包含一个字符串，字符串的内容是**季 2 季**。</span><span class="sxs-lookup"><span data-stu-id="51c10-113">`Properties` is a property that contains a string, and the contents of the string is **Q2**.</span></span> <span data-ttu-id="51c10-114">这与 Destination 部分无任何关系；该属性包含的所设置的字符串值无法转向其他任何位置，因此适配器将其保留在此部分中的此位置。</span><span class="sxs-lookup"><span data-stu-id="51c10-114">This has nothing to do with the Destination section; it contains strings of values that you set that could not go anywhere else, so the adapter has held them here in this section.</span></span>  
  
 <span data-ttu-id="51c10-115">`ReplyTo`属性可以设置在业务流程，以便告知最终的使用者发送响应的位置。</span><span class="sxs-lookup"><span data-stu-id="51c10-115">The `ReplyTo` property can be set in the orchestration to tell an eventual consumer where to send a response.</span></span> <span data-ttu-id="51c10-116">EMS 设置`Destination`属性时从 TIBCOEMS 收到的消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-116">EMS sets the `Destination` property when the message is received from TIBCOEMS.</span></span> <span data-ttu-id="51c10-117">业务流程中的上述第二个属性是只读的，用于接收来自 TIBCOEMS 的消息，该属性不能在业务流程中进行编辑。</span><span class="sxs-lookup"><span data-stu-id="51c10-117">This second property is read-only in the orchestration receiving the message from TIBCOEMS and cannot be edited in the orchestration.</span></span>  
  
 <span data-ttu-id="51c10-118">例如，业务流程无法在业务流程内部调度消息和动态设置目标。</span><span class="sxs-lookup"><span data-stu-id="51c10-118">For example, an orchestration cannot dispatch messages and set the destination dynamically inside an orchestration.</span></span> <span data-ttu-id="51c10-119">Destination 的值是由消息传输的目标端口设置的。</span><span class="sxs-lookup"><span data-stu-id="51c10-119">The value of Destination is set by the port to which the message is being transmitted.</span></span>  
  
 <span data-ttu-id="51c10-120">如果要将消息调度到不同队列，必须为每个队列创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="51c10-120">If you want to dispatch messages to different queues, you must create send ports for each queue.</span></span> <span data-ttu-id="51c10-121">然后，业务流程可确定应向哪些端口分配消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-121">The orchestration can then decide which port to assign the message.</span></span>  
  
 <span data-ttu-id="51c10-122">在下面的消息示例，目标 =`{Queue[Q1]}`是只读的。</span><span class="sxs-lookup"><span data-stu-id="51c10-122">In the following message example, the Destination= `{Queue[Q1]}` is read-only.</span></span> <span data-ttu-id="51c10-123">此值是在服务器收到消息时由 TIBCOEMS 设置的。</span><span class="sxs-lookup"><span data-stu-id="51c10-123">This value is set by TIBCOEMS when the server receives the message.</span></span> <span data-ttu-id="51c10-124">Destination 的值 Q1 来自于“传输属性”。</span><span class="sxs-lookup"><span data-stu-id="51c10-124">The value for Destination, Q1, comes from the Transport Properties.</span></span>  
  
#### <a name="example"></a><span data-ttu-id="51c10-125">示例</span><span class="sxs-lookup"><span data-stu-id="51c10-125">Example</span></span>  
  
```  
TextMessage={   
    Header={ MessageID={ID:EMS-SERVER.824437A58B11C75F4:1}   
    Destination={Queue[Q1]}   
  
        ' This is READONLY. It gets set by the server when the  
        ' message is received by the server (EMS). It is set in the  
        ' Transport Properties when you specify that you want to  
        ' listen for messages on Q1.  
    ReplyTo={}   
    DeliveryMode={Persistent}   
    Redelivered={False}   
    CorrelationID={}   
    MsgType={}   
    Timestamp={12/1/2005 11:59:01 PM}   
    Expiration={0}   
    Priority={1} }   
    Properties={ Destination={String:Queue[Q2]} }   
  
        ' This is a property that contains a string, and the   
        ' contents of the string is Q2. This has nothing to do with  
        ' the Destination section above – it is just another   
        ' property that is set.   
        ' This is in the schema. The adapter knows what it can and   
        ' cannot set in an EMS header. The values that the adapter   
        ' cannot set are put in the Properties section.   
    text={<?xml version="1.0" encoding="utf-16"?>  
    <ns0:Employees xmlns:ns0="http://BizTalk_Server_Project1.Employee">  
        <Emp Id="Id_0">  
            Name>Name_0</Name>  
        </Emp>  
    </ns0:Employees>  
    }  
```  
  
 <span data-ttu-id="51c10-126">标头包含一系列包含值的预定义字段，适配器将这些字段升级为 BizTalk Server 消息上下文，以便在业务流程中使用。</span><span class="sxs-lookup"><span data-stu-id="51c10-126">The header contains a series of predefined fields that contain values, which the adapter promotes to the BizTalk Server message context for use in the orchestration.</span></span> <span data-ttu-id="51c10-127">升级后的属性在定义上与 JMS 规范和 TIBCO Enterprise Message Service 扩展定义的标准标头属性相同。</span><span class="sxs-lookup"><span data-stu-id="51c10-127">The promoted properties are identical in definition to the standard header properties as defined by the JMS specification and the TIBCO Enterprise Message Service extensions.</span></span> <span data-ttu-id="51c10-128">除了两个的所有属性都均可用于业务流程从 EMS 接收到：`Destination`和`ReplyTo`描述不能在单个属性作为业务流程中使用正确映射的目标。</span><span class="sxs-lookup"><span data-stu-id="51c10-128">All properties except for two are available to the orchestration as received from EMS: `Destination` and `ReplyTo` describe a destination that cannot be correctly mapped for use in an orchestration as a single property.</span></span>  
  
 <span data-ttu-id="51c10-129">用于 TIBCO EMS 的 BizTalk 适配器将 TIBCOEMS 属性映射为字符串类型，并使用 Destination 的字符串表示形式，</span><span class="sxs-lookup"><span data-stu-id="51c10-129">BizTalk Adapter for TIBCO EMS maps the TIBCOEMS property to a string type and uses the Destination string representation.</span></span> <span data-ttu-id="51c10-130">这看起来像`StaticQueue[queuename]`或`StatisTopic[topicname]`。</span><span class="sxs-lookup"><span data-stu-id="51c10-130">This looks like `StaticQueue[queuename]` or `StatisTopic[topicname]`.</span></span> <span data-ttu-id="51c10-131">业务流程可以设置的值`ReplyTo`，并将该适配器替换它的标头中的有效目标对象。</span><span class="sxs-lookup"><span data-stu-id="51c10-131">The orchestration can set the value for `ReplyTo`, and the adapter replaces it with a valid destination object in the header.</span></span>  
  
 <span data-ttu-id="51c10-132">适配器提供了一个描述业务流程可使用的所有 TIBCO EMS 标头属性的架构和引用程序集。</span><span class="sxs-lookup"><span data-stu-id="51c10-132">The adapter provides a schema and reference assembly describing all TIBCO EMS header properties that can be used by orchestrations.</span></span> <span data-ttu-id="51c10-133">这些属性可用于筛选传入消息，也可用于添加到传出消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-133">These properties can be used to either filter incoming messages or to add to the outgoing message.</span></span> <span data-ttu-id="51c10-134">控制业务流程筛选器的规则不同于 EMS 服务器的消息选择器规则。</span><span class="sxs-lookup"><span data-stu-id="51c10-134">The rules governing the orchestration filter differs from those for the message selector for the EMS server.</span></span> <span data-ttu-id="51c10-135">例如，业务流程可以筛选在`TibcoEMS.ReplyTo`或`TibcoEMS.Destination`属性，但没有 JMS 规范来对此属性的消息选择器中不支持。</span><span class="sxs-lookup"><span data-stu-id="51c10-135">For example, orchestrations can filter on the `TibcoEMS.ReplyTo` or the `TibcoEMS.Destination` property, but there is no support in the JMS specification to allow message selector on this same property.</span></span>  
  
 <span data-ttu-id="51c10-136">当业务流程定义这些属性时，这些属性将包含在 JMS 消息的标头属性中。</span><span class="sxs-lookup"><span data-stu-id="51c10-136">When these properties are defined by the orchestration, they are included in the header properties of the JMS message.</span></span> <span data-ttu-id="51c10-137">或者在接收 EMS 消息时，这些标头属性将复制到 BizTalk Server 消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="51c10-137">Alternatively, when the EMS message is received, these header properties are copied to the BizTalk Server message context.</span></span>  
  
 <span data-ttu-id="51c10-138">如果某一属性与端口配置匹配，则消息的此属性值将优先于端口配置中的相应值。</span><span class="sxs-lookup"><span data-stu-id="51c10-138">When a property matches the port configuration, the value of the property on the message takes precedence on the port’s configuration.</span></span> <span data-ttu-id="51c10-139">例如，如果在端口中将优先级设置为 4，但在业务流程的逻辑中将消息的优先级设置为 9，那么该消息的优先级则为 9，并且将被发送到 TIBCO EMS。</span><span class="sxs-lookup"><span data-stu-id="51c10-139">For example, if the priority is set to 4 in the port, but you set the priority of the message to 9 in the logic of the orchestration, the message is received by TIBCO EMS as having a priority of 9.</span></span>  
  
### <a name="property-descriptions"></a><span data-ttu-id="51c10-140">属性说明</span><span class="sxs-lookup"><span data-stu-id="51c10-140">Property Descriptions</span></span>  
 <span data-ttu-id="51c10-141">下表说明了用于 TIBCO Enterprise Message Service 的 BizTalk 适配器如何使用每个属性。</span><span class="sxs-lookup"><span data-stu-id="51c10-141">The following table describes how each property is used by BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
|<span data-ttu-id="51c10-142">Name</span><span class="sxs-lookup"><span data-stu-id="51c10-142">Name</span></span>|<span data-ttu-id="51c10-143">类型</span><span class="sxs-lookup"><span data-stu-id="51c10-143">Type</span></span>|<span data-ttu-id="51c10-144">Description</span><span class="sxs-lookup"><span data-stu-id="51c10-144">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="51c10-145">TibcoEMS.MessageID</span><span class="sxs-lookup"><span data-stu-id="51c10-145">TibcoEMS.MessageID</span></span>|<span data-ttu-id="51c10-146">string</span><span class="sxs-lookup"><span data-stu-id="51c10-146">string</span></span>|<span data-ttu-id="51c10-147">发送调用向每个消息分配一个唯一 ID，并将其记录在标头中。</span><span class="sxs-lookup"><span data-stu-id="51c10-147">Sending calls assign a unique ID to each message and record it in the header.</span></span><br /><br /> <span data-ttu-id="51c10-148">所有消息 ID 的值均以包含三个字符的前缀 ID 开头（鉴于此原因而保留此前缀 ID）。</span><span class="sxs-lookup"><span data-stu-id="51c10-148">All message ID values start with the three-character prefix ID (which is reserved for this purpose).</span></span><br /><br /> <span data-ttu-id="51c10-149">只读。</span><span class="sxs-lookup"><span data-stu-id="51c10-149">Read-only.</span></span> <span data-ttu-id="51c10-150">更改此值不会对消息产生影响。</span><span class="sxs-lookup"><span data-stu-id="51c10-150">Changing the value does not affect the message.</span></span>|  
|<span data-ttu-id="51c10-151">TibcoEMS.Timestamp</span><span class="sxs-lookup"><span data-stu-id="51c10-151">TibcoEMS.Timestamp</span></span>|<span data-ttu-id="51c10-152">long</span><span class="sxs-lookup"><span data-stu-id="51c10-152">long</span></span>|<span data-ttu-id="51c10-153">发送调用在标头中记录 UTC 时间戳。</span><span class="sxs-lookup"><span data-stu-id="51c10-153">Sending calls record a UTC timestamp in the header.</span></span> <span data-ttu-id="51c10-154">该属性指示服务器接受消息的大致时间。</span><span class="sxs-lookup"><span data-stu-id="51c10-154">This indicates the approximate time that the server accepted the message.</span></span><br /><br /> <span data-ttu-id="51c10-155">该值是自 1970 年 1 月 1 日之后的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="51c10-155">The value is in milliseconds since January 1, 1970</span></span><br /><br /> <span data-ttu-id="51c10-156">只读。</span><span class="sxs-lookup"><span data-stu-id="51c10-156">Read-only.</span></span> <span data-ttu-id="51c10-157">更改此值不会对消息产生影响。</span><span class="sxs-lookup"><span data-stu-id="51c10-157">Changing the value does not affect the message.</span></span>|  
|<span data-ttu-id="51c10-158">TibcoEMS.Redelivered</span><span class="sxs-lookup"><span data-stu-id="51c10-158">TibcoEMS.Redelivered</span></span>|<span data-ttu-id="51c10-159">boolean</span><span class="sxs-lookup"><span data-stu-id="51c10-159">boolean</span></span>|<span data-ttu-id="51c10-160">服务器设置标头以指示某一消息是否与先前已传送的消息重复：</span><span class="sxs-lookup"><span data-stu-id="51c10-160">The server sets the header to indicate whether a message might duplicate a previously delivered message:</span></span><br /><br /> <span data-ttu-id="51c10-161">-false-服务器尚未以前尝试将此消息传递给使用者。</span><span class="sxs-lookup"><span data-stu-id="51c10-161">-   false—The server has not previously tried to deliver this message to the consumer.</span></span><br /><span data-ttu-id="51c10-162">-true-它是可能的但不是保证，服务器以前已尝试将此消息传递给使用者，但使用者未返回及时确认。</span><span class="sxs-lookup"><span data-stu-id="51c10-162">-   true—It is likely, but not guaranteed, that the server has previously tried to deliver this message to the consumer, but the consumer did not return timely acknowledgement.</span></span><br /><br /> <span data-ttu-id="51c10-163">只读。</span><span class="sxs-lookup"><span data-stu-id="51c10-163">Read-only.</span></span> <span data-ttu-id="51c10-164">更改此值不会对消息产生影响。</span><span class="sxs-lookup"><span data-stu-id="51c10-164">Changing the value does not affect the message.</span></span>|  
|<span data-ttu-id="51c10-165">TibcoEMS.Destination</span><span class="sxs-lookup"><span data-stu-id="51c10-165">TibcoEMS.Destination</span></span>|<span data-ttu-id="51c10-166">string</span><span class="sxs-lookup"><span data-stu-id="51c10-166">string</span></span>|<span data-ttu-id="51c10-167">发送调用在此标头中记录消息的目标（队列或主题）。</span><span class="sxs-lookup"><span data-stu-id="51c10-167">Sending calls record the destination (queue or topic) of the message in this header.</span></span> <span data-ttu-id="51c10-168">其格式已从目标形式改为字符串形式。</span><span class="sxs-lookup"><span data-stu-id="51c10-168">The format is adapted from a destination to a string.</span></span> <span data-ttu-id="51c10-169">之前已对此格式进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="51c10-169">The format is previously described.</span></span><br /><br /> <span data-ttu-id="51c10-170">只读。</span><span class="sxs-lookup"><span data-stu-id="51c10-170">Read-only.</span></span> <span data-ttu-id="51c10-171">更改此值不会对消息产生影响。</span><span class="sxs-lookup"><span data-stu-id="51c10-171">Changing the value does not affect the message.</span></span>|  
|<span data-ttu-id="51c10-172">TibcoEMS.DeliveryMode</span><span class="sxs-lookup"><span data-stu-id="51c10-172">TibcoEMS.DeliveryMode</span></span>|<span data-ttu-id="51c10-173">string</span><span class="sxs-lookup"><span data-stu-id="51c10-173">string</span></span>|<span data-ttu-id="51c10-174">有两个可能值： 持久和非持久。</span><span class="sxs-lookup"><span data-stu-id="51c10-174">Has two possible values: PERSISTENT and NON-PERSISTENT.</span></span> <span data-ttu-id="51c10-175">默认值为 PERSISTENT 模式。</span><span class="sxs-lookup"><span data-stu-id="51c10-175">Default value is PERSISTENT mode.</span></span><br /><br /> <span data-ttu-id="51c10-176">适配器在确认将消息发送到 BizTalk Server 之前将一直等待 EMS 服务器的确认。</span><span class="sxs-lookup"><span data-stu-id="51c10-176">The adapter waits for an acknowledgement from the EMS server before acknowledging the message sent to BizTalk Server.</span></span> <span data-ttu-id="51c10-177">此标头属性和端口配置项控制 EMS 向适配器发送此确认的时间，并控制消息传输的可靠性。</span><span class="sxs-lookup"><span data-stu-id="51c10-177">This header property and port configuration item controls the time EMS takes to send this acknowledgement to the adapter and control the reliability of message transmission.</span></span><br /><br /> <span data-ttu-id="51c10-178">使用 PERSISTENT 传送模式—在 EMS 服务器中成功持久化消息之前，EMS 服务器将一直等待。</span><span class="sxs-lookup"><span data-stu-id="51c10-178">Using PERSISTENT delivery mode—the EMS server waits until the message is successfully persisted in the EMS server.</span></span> <span data-ttu-id="51c10-179">此操作可保证消息已到达队列。</span><span class="sxs-lookup"><span data-stu-id="51c10-179">This action guarantees that the message has arrived in the queue.</span></span> <span data-ttu-id="51c10-180">使用 PERSISTENT 模式传送时，请考虑以下各项：</span><span class="sxs-lookup"><span data-stu-id="51c10-180">When you use PERSISTENT mode delivery, consider the following:</span></span><br /><br /> <span data-ttu-id="51c10-181">消息越大，则 BizTalk Server 用来确认该消息是否已发送的时间就越长。</span><span class="sxs-lookup"><span data-stu-id="51c10-181">The larger the messages, the longer it takes for BizTalk Server to consider the message as sent.</span></span><br /><br /> <span data-ttu-id="51c10-182">使用 NON-PERSISTENT 模式—EMS 服务器先返回确认，然后再对消息进行持久化处理。</span><span class="sxs-lookup"><span data-stu-id="51c10-182">Using NON-PERSISTENT mode—the EMS server returns the acknowledgement before persisting the message.</span></span> <span data-ttu-id="51c10-183">如果 EMS 服务器出现故障，则消息可能已丢失，而 BizTalk Server 认为已成功发送该消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-183">If a failure were to occur with the EMS server, the message might be lost when it is considered successfully sent by BizTalk Server.</span></span>|  
|<span data-ttu-id="51c10-184">TibcoEMS.Expiration</span><span class="sxs-lookup"><span data-stu-id="51c10-184">TibcoEMS.Expiration</span></span>|<span data-ttu-id="51c10-185">long</span><span class="sxs-lookup"><span data-stu-id="51c10-185">long</span></span>|<span data-ttu-id="51c10-186">消息在过期之前的生存时间长度。</span><span class="sxs-lookup"><span data-stu-id="51c10-186">Length of time that the message will live before expiration.</span></span> <span data-ttu-id="51c10-187">如果设置为 0，消息则不会过期。</span><span class="sxs-lookup"><span data-stu-id="51c10-187">If set to 0, message does not expire.</span></span><br /><br /> <span data-ttu-id="51c10-188">消息生存时间以毫秒为单位指定。</span><span class="sxs-lookup"><span data-stu-id="51c10-188">The time-to-live is specified in milliseconds.</span></span>|  
|<span data-ttu-id="51c10-189">TibcoEMS.Priority</span><span class="sxs-lookup"><span data-stu-id="51c10-189">TibcoEMS.Priority</span></span>|<span data-ttu-id="51c10-190">int</span><span class="sxs-lookup"><span data-stu-id="51c10-190">int</span></span>|<span data-ttu-id="51c10-191">使用 0 至 9 之间的某个数字级别将消息优先级定义为正常或加急。</span><span class="sxs-lookup"><span data-stu-id="51c10-191">Uses a numeric ranking, between 0 and 9, to define message priority as normal or expedited.</span></span> <span data-ttu-id="51c10-192">数字越大，表示的优先级越高。</span><span class="sxs-lookup"><span data-stu-id="51c10-192">Larger numbers represent higher priority.</span></span>|  
|<span data-ttu-id="51c10-193">TibcoEMS.CorrolationID</span><span class="sxs-lookup"><span data-stu-id="51c10-193">TibcoEMS.CorrolationID</span></span>|<span data-ttu-id="51c10-194">string</span><span class="sxs-lookup"><span data-stu-id="51c10-194">string</span></span>|<span data-ttu-id="51c10-195">可用于链接消息，例如将响应消息链接到请求消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-195">Can be used to link messages, such as linking a response message to a request message.</span></span><br /><br /> <span data-ttu-id="51c10-196">这通常是相同的值`EMS.JMSMessageID`。</span><span class="sxs-lookup"><span data-stu-id="51c10-196">Usually this is the same value as the `EMS.JMSMessageID`.</span></span> <span data-ttu-id="51c10-197">这通常用于连同`EMS.JMSReplyTo`属性。</span><span class="sxs-lookup"><span data-stu-id="51c10-197">This is usually used together with the `EMS.JMSReplyTo` property.</span></span>|  
|<span data-ttu-id="51c10-198">TibcoEMS.ReplyTo</span><span class="sxs-lookup"><span data-stu-id="51c10-198">TibcoEMS.ReplyTo</span></span>|<span data-ttu-id="51c10-199">string</span><span class="sxs-lookup"><span data-stu-id="51c10-199">string</span></span>|<span data-ttu-id="51c10-200">应接收消息答复的目标。</span><span class="sxs-lookup"><span data-stu-id="51c10-200">A destination to which a message reply should be sent.</span></span> <span data-ttu-id="51c10-201">格式等同于`EMS.JMSDestination`和也端口的配置。</span><span class="sxs-lookup"><span data-stu-id="51c10-201">Format is identical to the `EMS.JMSDestination` and also the port's configuration.</span></span>|  
|<span data-ttu-id="51c10-202">TibcoEMS.Type</span><span class="sxs-lookup"><span data-stu-id="51c10-202">TibcoEMS.Type</span></span>|<span data-ttu-id="51c10-203">string</span><span class="sxs-lookup"><span data-stu-id="51c10-203">string</span></span>|<span data-ttu-id="51c10-204">未描述消息类型（文本、字节、字符串…）。</span><span class="sxs-lookup"><span data-stu-id="51c10-204">Does not describe the message type (text, byte, string …).</span></span><br /><br /> <span data-ttu-id="51c10-205">某些 JMS 提供程序使用消息存储库来存储消息类型定义。</span><span class="sxs-lookup"><span data-stu-id="51c10-205">Some JMS providers use a message repository to store message type definitions.</span></span> <span data-ttu-id="51c10-206">客户端程序可在此字段中存储一个值，以便引用存储库中的定义。</span><span class="sxs-lookup"><span data-stu-id="51c10-206">Client programs can store a value in this field to reference a definition in the repository.</span></span> <span data-ttu-id="51c10-207">EMS 支持但不使用此标头。</span><span class="sxs-lookup"><span data-stu-id="51c10-207">EMS supports this header but does not use it.</span></span><br /><br /> <span data-ttu-id="51c10-208">JMS 规范没有定义标准的消息定义存储库，也没有定义消息类型定义的命名策略。</span><span class="sxs-lookup"><span data-stu-id="51c10-208">The JMS specification does not define a standard message definition repository, nor does it define a naming policy for message type definitions.</span></span><br /><br /> <span data-ttu-id="51c10-209">某些提供程序需要每个应用程序消息的消息类型定义。</span><span class="sxs-lookup"><span data-stu-id="51c10-209">Some providers require message type definitions for each application message.</span></span> <span data-ttu-id="51c10-210">为保证与此种提供程序兼容，即使客户端应用程序不使用此标头，客户端程序也可以对此标头进行设置。</span><span class="sxs-lookup"><span data-stu-id="51c10-210">To guarantee compatibility with such providers, client programs can set this header, even if the client application does not use it.</span></span><br /><br /> <span data-ttu-id="51c10-211">为保证可移植性，客户端可使用符号值（而非文本值）设置此标头，并将其配置为与提供程序的存储库匹配。</span><span class="sxs-lookup"><span data-stu-id="51c10-211">To guarantee portability, clients can set this header with symbolic values (instead of literals), and configure them to match the provider's repository.</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="51c10-212">属性</span><span class="sxs-lookup"><span data-stu-id="51c10-212">Properties</span></span>  
 <span data-ttu-id="51c10-213">集成器可定义一组属性，以便升级为 BizTalk Server 消息上下文，然后可将这些属性添加到 JMS 消息的属性部分。</span><span class="sxs-lookup"><span data-stu-id="51c10-213">The integrator can define a set of properties to promote to the BizTalk Server message context, after which the properties are added to the properties part of the JMS message.</span></span> <span data-ttu-id="51c10-214">创建架构时，集成器将负责定义属性的类型。</span><span class="sxs-lookup"><span data-stu-id="51c10-214">The integrator takes care when defining the type of the property while it is creating the schema.</span></span> <span data-ttu-id="51c10-215">如果在消息选择器中使用此属性的值，那么根据此属性的类型，某些操作是有效的。</span><span class="sxs-lookup"><span data-stu-id="51c10-215">If this property value is used in a message selector, certain operations are valid depending on the type of the property.</span></span> <span data-ttu-id="51c10-216">例如，如果消息选择器**myMessageProperty > 5**是使用，该属性必须定义为整数值，并适配器将值放入一个整数值形式的消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-216">For example, if a message selector **myMessageProperty > 5** is used, the property must be defined as an integer value, and the adapter puts the value in the message as an integer value.</span></span> <span data-ttu-id="51c10-217">对于要升级的属性，属性名称必须以 EMSX 开头，</span><span class="sxs-lookup"><span data-stu-id="51c10-217">For the properties to be promoted, the property names must start with EMSX.</span></span> <span data-ttu-id="51c10-218">此外，其名称不能与预定义属性的名称相同。</span><span class="sxs-lookup"><span data-stu-id="51c10-218">They must also not have the same name as the predefined properties.</span></span>  
  
 <span data-ttu-id="51c10-219">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器提供了一个架构和程序集，用于声明此部分中显示的特定 EMS 和 JMS 属性。</span><span class="sxs-lookup"><span data-stu-id="51c10-219">BizTalk Adapter for TIBCO Enterprise Message Service provides a schema and assembly, which declare the EMS- and JMS-specific properties that can appear in this section.</span></span> <span data-ttu-id="51c10-220">可扩充此架构和程序集，以包含任何遗漏项。</span><span class="sxs-lookup"><span data-stu-id="51c10-220">These can be augmented to include any omissions.</span></span> <span data-ttu-id="51c10-221">在消息上下文中引用的所有 EMSX 属性都将放置到 EMS 消息的消息属性部分中。</span><span class="sxs-lookup"><span data-stu-id="51c10-221">All EMSX properties referenced in the message context are put in the message property section of the EMS message.</span></span> <span data-ttu-id="51c10-222">有关详细信息，请参阅 TIBCO EMS 用户指南。</span><span class="sxs-lookup"><span data-stu-id="51c10-222">For more information, see the TIBCO EMS Users Guide.</span></span>  
  
## <a name="body"></a><span data-ttu-id="51c10-223">正文</span><span class="sxs-lookup"><span data-stu-id="51c10-223">Body</span></span>  
 <span data-ttu-id="51c10-224">EMS 支持枚举 JMS 规范中的所有消息： 文本、 字节、 流、 地图中和对象。</span><span class="sxs-lookup"><span data-stu-id="51c10-224">EMS supports all messages enumerated in the JMS specification: text, byte, stream, map, and object.</span></span> <span data-ttu-id="51c10-225">用于 TIBCO EMS 的 BizTalk 适配器仅支持文本消息类型。</span><span class="sxs-lookup"><span data-stu-id="51c10-225">The BizTalk Adapter for TIBCO EMS supports only the text message type.</span></span>  
  
 <span data-ttu-id="51c10-226">JMS 并未要求文本类型的消息应包含 XML 格式的正文。</span><span class="sxs-lookup"><span data-stu-id="51c10-226">JMS does not require that messages of type text contain XML-formatted bodies.</span></span> <span data-ttu-id="51c10-227">适配器不处理消息; 的正文它提供给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收到。</span><span class="sxs-lookup"><span data-stu-id="51c10-227">The adapter does not process the body of the message; it is provided to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as received.</span></span>  <span data-ttu-id="51c10-228">因此，消息提交到 BizTalk 适配器可能不始终解析为 XML 数据中。</span><span class="sxs-lookup"><span data-stu-id="51c10-228">Therefore, messages submitted to BizTalk by the adapter may not always parse as XML data.</span></span>  
  
## <a name="persistent-messages"></a><span data-ttu-id="51c10-229">持久性消息</span><span class="sxs-lookup"><span data-stu-id="51c10-229">Persistent Messages</span></span>  
 <span data-ttu-id="51c10-230">消息可持久保留在 EMS 服务器中，以保证对订户进行一次性传送；但是，这可能会严重影响适配器的性能。</span><span class="sxs-lookup"><span data-stu-id="51c10-230">Messages can be persisted on the EMS server to guarantee exactly one-time delivery to a subscriber; however, this can have a significant impact on the adapter's performance.</span></span> <span data-ttu-id="51c10-231">发送消息时，EMS 会将此消息存储在本地存储区，然后再向适配器确认已收到此消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-231">When you send messages, EMS stores the message in local storage before acknowledging reception of the message to the adapter.</span></span> <span data-ttu-id="51c10-232">您可以在业务流程中针对每条消息设置此属性，也可以针对端口处理的所有消息设置此属性。</span><span class="sxs-lookup"><span data-stu-id="51c10-232">You can set this property on a per-message basis in the orchestration or for all messages processed by the port.</span></span>  
  
 <span data-ttu-id="51c10-233">从接收方面而言，如果适配器未订阅到主题，则可能丢失消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-233">From the receiving aspect, the adapter can miss messages when it is not subscribed to the topic.</span></span> <span data-ttu-id="51c10-234">对于发布为主题的消息，如果没有任何订阅，EMS 将不会持久保留这些消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-234">Messages posted to topics when there are no subscriptions are not persisted by EMS.</span></span> <span data-ttu-id="51c10-235">适配器需要即使当前没有订阅也仍会接收消息发布的机制；但是，此机制与使用持久性消息一样，会对 EMS 性能产生重大影响，因此此机制并非总是必需的。</span><span class="sxs-lookup"><span data-stu-id="51c10-235">The adapter needs a mechanism to receive message postings even when not currently subscribed; however, like the use of persistent messages, this has a significant impact on the EMS performance, and it is not always required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51c10-236">从 EMS 角度而言，存在一个接收机制，实际上此接收机制并不是所需的，因此并未实现。</span><span class="sxs-lookup"><span data-stu-id="51c10-236">There is a mechanism for receive from the point of view of EMS, but it is not implemented, nor is it really desired.</span></span> <span data-ttu-id="51c10-237">此问题仅与主题相关；并不影响队列。</span><span class="sxs-lookup"><span data-stu-id="51c10-237">This is only an issue with topic; queues are not affected.</span></span> <span data-ttu-id="51c10-238">主题通常用于特定于时间的数据，如股票行情。</span><span class="sxs-lookup"><span data-stu-id="51c10-238">A topic is generally used for time-specific data -- stock quotes, for example.</span></span> <span data-ttu-id="51c10-239">如果股票价格丢失，如您所知，稍后将再次发布价格。</span><span class="sxs-lookup"><span data-stu-id="51c10-239">If the price of a stock is missed, you know that it will be posted again later.</span></span>  
  
 <span data-ttu-id="51c10-240">鉴于以上原因，端口配置允许您在 EMS 服务器上启用或禁用消息持久化功能。</span><span class="sxs-lookup"><span data-stu-id="51c10-240">For these reasons the port configuration lets you enable or disable message persistence on the EMS server.</span></span>  
  
## <a name="message-acknowledgement"></a><span data-ttu-id="51c10-241">消息确认</span><span class="sxs-lookup"><span data-stu-id="51c10-241">Message Acknowledgement</span></span>  
 <span data-ttu-id="51c10-242">将消息正确调度到 BizTalk Server 时，用于 TIBCO Enterprise Message Service 的 BizTalk 适配器将始终确认已收到此消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-242">BizTalk Adapter for TIBCO Enterprise Message Service always acknowledges reception of a message when that message was correctly dispatched to BizTalk Server.</span></span> <span data-ttu-id="51c10-243">这表示 EMS 将向适配器重新发送未经确认的消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-243">This means that unacknowledged messages are resent from EMS to the adapter.</span></span> <span data-ttu-id="51c10-244">适配器无法控制 EMS 重新发送消息的次数，这是因为这是目标自身的配置；但是，适配器可控制是否向 MessageBox 发送消息。</span><span class="sxs-lookup"><span data-stu-id="51c10-244">The adapter cannot control the number of times the message is resent by EMS because this is a configuration of the destination itself; however, the adapter can control if the message is sent to the MessageBox or not.</span></span> <span data-ttu-id="51c10-245">EMS 服务器控制向队列发送失败消息的最大次数。</span><span class="sxs-lookup"><span data-stu-id="51c10-245">The EMS server controls the maximum number of times a failed message is sent to a queue.</span></span>  
  
 <span data-ttu-id="51c10-246">对于将被重新传送的消息，EMS 服务器设置`JMSRedelivered`属性设置为 True、 增量`JMSXDeliveryCount`。</span><span class="sxs-lookup"><span data-stu-id="51c10-246">For messages that are redelivered, the EMS server sets the `JMSRedelivered` property to True and increments the `JMSXDeliveryCount`.</span></span> <span data-ttu-id="51c10-247">业务流程可使用上述两个属性值。</span><span class="sxs-lookup"><span data-stu-id="51c10-247">Both property values are available to the orchestration.</span></span> <span data-ttu-id="51c10-248">在未在 EMS 服务器中传送消息的情况下，您不能将此消息移动到 EMS 的未传送队列中。</span><span class="sxs-lookup"><span data-stu-id="51c10-248">You cannot move a message to the EMS un-delivered queue without delivering it there.</span></span> <span data-ttu-id="51c10-249">否则将更改消息属性。</span><span class="sxs-lookup"><span data-stu-id="51c10-249">Doing this would change the message properties.</span></span>  
  
 <span data-ttu-id="51c10-250">如果消息达到其配置的最大重新传送计数，EMS 服务器将确定是否应删除此消息，或将其放置到 $sys.undelivered 队列中。</span><span class="sxs-lookup"><span data-stu-id="51c10-250">When a message reaches its configured maximum redelivery count, the EMS server determines whether the message should be deleted or put on the $sys.undelivered queue.</span></span> <span data-ttu-id="51c10-251">EMS 服务器所做的决策基于`JMS_TIBCO_PRESERVE_UNDELIVERED`属性; 如果为 True，消息将发送到未传递队列，或它已被删除。</span><span class="sxs-lookup"><span data-stu-id="51c10-251">The EMS server makes the decision based on the `JMS_TIBCO_PRESERVE_UNDELIVERED` property; if True, the message goes to the undelivered queue, or it is deleted.</span></span> <span data-ttu-id="51c10-252">在发送消息之前，您可以在业务流程中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="51c10-252">This property can be set in the orchestration before sending the message.</span></span> <span data-ttu-id="51c10-253">传送之后则无法更改此消息属性。</span><span class="sxs-lookup"><span data-stu-id="51c10-253">After delivery, the message property cannot be changed.</span></span> <span data-ttu-id="51c10-254">消息成功发送到 EMS 时，BizTalk Server 将对此消息进行确认。</span><span class="sxs-lookup"><span data-stu-id="51c10-254">Messages sent to EMS are acknowledged to BizTalk Server when they are successful.</span></span> <span data-ttu-id="51c10-255">如果发送到 EMS 失败，消息将挂起并标记为可重试。</span><span class="sxs-lookup"><span data-stu-id="51c10-255">If there is a failure sending theme to EMS, they are suspended and marked as retryable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c10-256">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51c10-256">See Also</span></span>  
 [<span data-ttu-id="51c10-257">入门</span><span class="sxs-lookup"><span data-stu-id="51c10-257">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)