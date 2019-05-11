---
title: 接收适配器的交换模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e505559e-66be-4c32-a2a8-a242cba10000
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856200bbd511f580f8ef58fd0be78ee1fb6718b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388275"
---
# <a name="exchange-patterns-for-receive-adapters"></a><span data-ttu-id="d7c0d-102">接收适配器的交换模式</span><span class="sxs-lookup"><span data-stu-id="d7c0d-102">Exchange Patterns for Receive Adapters</span></span>
<span data-ttu-id="d7c0d-103">接收适配器接收从"网络"的数据，并将其作为消息提交[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-103">Receive adapters receive data from the "wire" and submit it as a message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d7c0d-104">这一提交过程可以是单向或双向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-104">This submittal process can be a one-way or a two-way message exchange pattern.</span></span>  
  
## <a name="one-way-submit"></a><span data-ttu-id="d7c0d-105">单向提交</span><span class="sxs-lookup"><span data-stu-id="d7c0d-105">One-Way Submit</span></span>  
 <span data-ttu-id="d7c0d-106">接收适配器将消息提交到 BizTalk 消息引擎，它首先需要创建新的 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-106">For a receive adapter to submit a message into the BizTalk Messaging Engine, it first needs to create a new BizTalk message.</span></span> <span data-ttu-id="d7c0d-107">IBaseMessage 主题中的代码示例演示如何做到这一点。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-107">The code sample in the IBaseMessage topic shows how this is done.</span></span> <span data-ttu-id="d7c0d-108">适配器设置为消息正文的流通常应为只进流，这意味着它不应该缓存先前已读入内存的数据。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-108">The stream that the adapter sets as the message body should typically be a forward-only stream, meaning that it should not cache the data that it has previously read into memory.</span></span>  
  
 <span data-ttu-id="d7c0d-109">该适配器将消息提交到引擎之前，它必须编写**InboundTransportLocation**消息上下文属性在 BizTalk 消息将系统命名空间中的。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-109">Before the adapter submits the message into the engine, it must write the **InboundTransportLocation** message context property in the system namespace onto the BizTalk message.</span></span> <span data-ttu-id="d7c0d-110">下面的代码段所示：</span><span class="sxs-lookup"><span data-stu-id="d7c0d-110">This is illustrated in the following code fragment:</span></span>  
  
 `Assembly References:`  
  
 `Microsoft.XLANGs.BaseTypes.dll`  
  
 `Microsoft.BizTalk.Pipeline.dll`  
  
 `Microsoft.BizTalk.GlobalPropertySchemas.dll`  
  
```  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.XLANGs.BaseTypes;  
  
private static readonly PropertyBase InboundTransportLocationProp =   
new BTS.InboundTransportLocation();  
  
private void StampMsgCtxProps(  
IBaseMessage msg, string uri, string adapterType)  
{  
msg.Context.Write(  
 InboundTransportLocationProp.Name.Name,   
 InboundTransportLocationProperty.Name.Namespace,   
  uri);  
}  
```  
  
 <span data-ttu-id="d7c0d-111">此外，适配器可以定义其自己的属性架构并写入与对其接收消息的终结点相关的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-111">In addition, the adapter may define its own property schemas and write message context properties pertaining to the endpoint over which it received the message.</span></span> <span data-ttu-id="d7c0d-112">例如，HTTP 适配器可能会将 HTTP 标头写入消息上下文，并且 SMTP 接收方可能会将邮件的主题写入消息上下文。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-112">For example, an HTTP adapter might write the HTTP headers to the message context, and an SMTP receiver might write the subject of the mail to the message context.</span></span> <span data-ttu-id="d7c0d-113">此信息可能非常有用到下游组件，如管道组件、 业务流程调度或发送适配器。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-113">This information may be useful to downstream components such as pipeline components, orchestration schedules, or a send adapter.</span></span>  
  
 <span data-ttu-id="d7c0d-114">消息准备好后，它们可以提交到消息引擎。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-114">After the messages are prepared, they can be submitted into the Messaging Engine.</span></span> <span data-ttu-id="d7c0d-115">若要查看如何的单向接收适配器可能会将消息提交到引擎，请参阅代码示例[SubmitDirect （BizTalk Server 示例）](../core/submitdirect-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-115">To see how a one-way receive adapter might submit a message into the engine, see the code sample [SubmitDirect (BizTalk Server Sample)](../core/submitdirect-biztalk-server-sample.md).</span></span>  
  
## <a name="request-response"></a><span data-ttu-id="d7c0d-116">请求-响应</span><span class="sxs-lookup"><span data-stu-id="d7c0d-116">Request-Response</span></span>  
 <span data-ttu-id="d7c0d-117">双向接收适配器通常应用于单向或双向接收端口。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-117">Two-way receive adapters are typically used on one-way or two-way receive ports.</span></span> <span data-ttu-id="d7c0d-118">适配器可以确定它所服务的接收位置是否为单向或双向端口通过检查[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置属性包。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-118">The adapter determines whether the receive location it is servicing is a one-way or two-way port by inspecting the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration property bag.</span></span> <span data-ttu-id="d7c0d-119">此过程所述**IBTTransportConfig.AddReceiveEndpoint 方法 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-119">This process is explained in the **IBTTransportConfig.AddReceiveEndpoint Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="d7c0d-120">以下对象交互图说明了执行请求-响应消息交换的过程。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-120">The following object interaction diagram illustrates the process of performing a request-response message exchange.</span></span> <span data-ttu-id="d7c0d-121">适配器从传输代理请求一个新的批处理，并将传递到它的引用**IBTTransmitter**接口通过**SubmitRequestMessage**方法。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-121">The adapter requests a new batch from the transport proxy and passes in its reference to the **IBTTransmitter** interface through the **SubmitRequestMessage** method.</span></span> <span data-ttu-id="d7c0d-122">消息引擎通过使用提供此接口上的响应消息**TransmitMessage**方法。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-122">The Messaging Engine delivers the response message on this interface by using the **TransmitMessage** method.</span></span>  
  
 <span data-ttu-id="d7c0d-123">该引擎以异步方式处理消息，因为很可能出现下列情况：</span><span class="sxs-lookup"><span data-stu-id="d7c0d-123">Because the engine is processing messages asynchronously, it is possible for the following to happen:</span></span>  
  
- <span data-ttu-id="d7c0d-124">**BatchComplete**回调可能会发生之前**完成**已返回。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-124">The **BatchComplete** callback might occur before **Done** has returned.</span></span>  
  
- <span data-ttu-id="d7c0d-125">TransmitMessage 调用可能会在 BatchComplete 之前所做和甚至之前完成。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-125">The call to TransmitMessage might be made before BatchComplete and even before Done.</span></span>  
  
  <span data-ttu-id="d7c0d-126">虽然这两个方案都很少见，适配器应保护自身免遭这。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-126">While both of these scenarios are rare, the adapter should protect itself against this.</span></span>  
  
  <span data-ttu-id="d7c0d-127">建议使用异步非阻止调用传输响应消息。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-127">It is recommended that the response message is transmitted using an asynchronous non-blocking call.</span></span>  
  
  <span data-ttu-id="d7c0d-128">BaseAdapter 项目有一个实用工具类， **StandardRequestResponseHandler**，它封装了本主题中所述的请求-响应语义。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-128">The BaseAdapter project has a utility class, **StandardRequestResponseHandler**, that encapsulates the request-response semantics explained in this topic.</span></span>  
  
## <a name="request-response-message-time-outs"></a><span data-ttu-id="d7c0d-129">请求-响应消息超时</span><span class="sxs-lookup"><span data-stu-id="d7c0d-129">Request-Response Message Time-Outs</span></span>  
 <span data-ttu-id="d7c0d-130">当适配器提交请求-响应消息时，需要在指定的请求消息的超时值**IBTTransportBatch.SubmitRequestMessage 方法 (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-130">When an adapter submits a request-request message, it needs to specify the time-out of the request message on the **IBTTransportBatch.SubmitRequestMessage Method (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="d7c0d-131">此超时期间内仅响应消息将传送到适配器。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-131">A response message will be delivered to the adapter only within this time-out period.</span></span> <span data-ttu-id="d7c0d-132">超时过期后，会将一个否定确认 (NACK) 传递到而不是响应消息的适配器。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-132">After the time-out expires, a negative acknowledgment (NACK) will be delivered to the adapter instead of the response message.</span></span> <span data-ttu-id="d7c0d-133">如果适配器未指定超时值，引擎将使用默认值 20 分钟。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-133">If the adapter does not specify a time-out value, the engine uses the default value of 20 minutes.</span></span>  
  
 <span data-ttu-id="d7c0d-134">请求-响应消息的默认超时值可能会受为进程内接收适配器使用以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="d7c0d-134">The default time-out for request-response messages may be controlled by using the following registry key for in-process receive adapters:</span></span>  
  
 <span data-ttu-id="d7c0d-135">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="d7c0d-135">**DWORD**</span></span>  
  
 <span data-ttu-id="d7c0d-136">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingReqRespTTL**</span><span class="sxs-lookup"><span data-stu-id="d7c0d-136">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingReqRespTTL**</span></span>  
  
 <span data-ttu-id="d7c0d-137">注册表项是在不同的位置，对于独立接收适配器：</span><span class="sxs-lookup"><span data-stu-id="d7c0d-137">The registry key is in a different location for isolated receive adapters:</span></span>  
  
 <span data-ttu-id="d7c0d-138">**DWORD**</span><span class="sxs-lookup"><span data-stu-id="d7c0d-138">**DWORD**</span></span>  
  
 <span data-ttu-id="d7c0d-139">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**</span><span class="sxs-lookup"><span data-stu-id="d7c0d-139">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**</span></span>  
  
 <span data-ttu-id="d7c0d-140">Nack （否定确认） 是 SOAP 错误，有两种方法来处理它们。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-140">NACKs (Negative ACKnowledgements) are SOAP faults and there are two ways to handle them.</span></span> <span data-ttu-id="d7c0d-141">通常，适配器将 NACK 返回给客户端和客户端处理 NACK。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-141">Typically the adapter returns the NACK to the client and the client handles the NACK.</span></span> <span data-ttu-id="d7c0d-142">或者可能将处理响应消息的传输管道配置为使用映射或自定义管道组件中更改响应消息的内容。</span><span class="sxs-lookup"><span data-stu-id="d7c0d-142">Alternatively the transmit pipeline handling the response message may be configured to change the contents of the response message, by using either a map or a custom pipeline component.</span></span>