---
title: 使用确认 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, publishing
- messages, acknowledgements
- BTS.AckSendPortID property
- BTS.AckSendPortName property
- BTS.AckType property
- BTS.AckFailureCode property
- BTS.AckID property
- acknowledgements, positive
- SOAP fault
- BTS.AckReceivePortID property
- BTS.AckReceivePortName property
- BTS.AckInboundTransportLocation property
- BTS.AckOutboundTransportLocation property
- messages, successful transmission
- BTS.AckDescription property
- orchestrations, messages
- acknowledgements, negative
- BTS.CorrelationToken property
- BTS.AckFailureCategory property
- positive acknowledgements (ACK)
- BTS.AckOwnerID property
ms.assetid: 2e5986d4-9633-4b7b-8ff3-fa3da93c5400
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c3a5363ee70a67c5882088af9fa3d2f4b805823
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288181"
---
# <a name="using-acknowledgments"></a><span data-ttu-id="962e4-102">使用确认</span><span class="sxs-lookup"><span data-stu-id="962e4-102">Using Acknowledgments</span></span>
<span data-ttu-id="962e4-103">在对通过端口处理消息期间所遇到的情况作出响应时，BizTalk 消息引擎将生成肯定确认 (ACK) 和否定确认 (NACK)。</span><span class="sxs-lookup"><span data-stu-id="962e4-103">The BizTalk Messaging Engine generates positive acknowledgments (ACK) and negative acknowledgments (NACK) in response to conditions encountered during the processing of a message through a port.</span></span> <span data-ttu-id="962e4-104">BizTalk Server 发布肯定确认以指示消息传输成功，发布否定确认以指示传输失败并挂起消息。</span><span class="sxs-lookup"><span data-stu-id="962e4-104">BizTalk Server publishes a positive acknowledgment to indicate successful transmission of a message and a negative acknowledgment to indicate transmission failure and suspension of a message.</span></span>  
  
## <a name="why-use-acknowledgments"></a><span data-ttu-id="962e4-105">为什么使用确认？</span><span class="sxs-lookup"><span data-stu-id="962e4-105">Why Use Acknowledgments?</span></span>  
 <span data-ttu-id="962e4-106">肯定确认和否定确认所提供的强有力的反馈信息可以用来确定消息是否到达其目标，或是否在传输过程中遇到一个或多个问题。</span><span class="sxs-lookup"><span data-stu-id="962e4-106">Positive and negative acknowledgments provide strong feedback that you can use to determine if a message arrived at its destination or encountered one or more problems along the way.</span></span> <span data-ttu-id="962e4-107">例如，确认在以下情况下非常有用：</span><span class="sxs-lookup"><span data-stu-id="962e4-107">For example, acknowledgments are useful when:</span></span>  
  
-   <span data-ttu-id="962e4-108">您希望监视新贸易合作伙伴的接收端口，以查看架构验证信息和其他错误。</span><span class="sxs-lookup"><span data-stu-id="962e4-108">You want to monitor a receive port for a new trading partner for schema validation and other errors.</span></span>  
  
-   <span data-ttu-id="962e4-109">如果您希望将已发出的贷款申请的状态标记为“正在处理”（如果该申请已成功发送给合作伙伴进行审批）或“失败”（如果传输失败。例如，合作伙伴的服务器停机）。</span><span class="sxs-lookup"><span data-stu-id="962e4-109">You want to mark the status of a loan request sent out for approval as "in process" if it is successfully sent to a partner for approval or "failed" if transmission fails (for example, if the partner's server is down).</span></span>  
  
-   <span data-ttu-id="962e4-110">所处理的交换包含多个采购订单，您希望对已传输或传输失败的订单数进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="962e4-110">You process interchanges containing multiple purchase orders and want to track the number of orders that are transmitted or fail transmission.</span></span>  
  
 <span data-ttu-id="962e4-111">通过使用确认和利用筛选器的基于内容的路由，可以完成以下各个方案：</span><span class="sxs-lookup"><span data-stu-id="962e4-111">You can accomplish each of these scenarios by using acknowledgments and content-based routing that uses filters.</span></span>  
  
## <a name="routing-acknowledgments"></a><span data-ttu-id="962e4-112">路由确认</span><span class="sxs-lookup"><span data-stu-id="962e4-112">Routing Acknowledgments</span></span>  
 <span data-ttu-id="962e4-113">在发布 ACK 或 NACK 后，引发 ACK/NACK 的消息内的所有消息上下文属性都将降级。</span><span class="sxs-lookup"><span data-stu-id="962e4-113">When an ACK or NACK is published, all of the message context properties from the message that caused the ACK/NACK are demoted.</span></span> <span data-ttu-id="962e4-114">已升级的任何属性都不会流向确认。</span><span class="sxs-lookup"><span data-stu-id="962e4-114">Any properties that were promoted do not flow to the acknowledgment.</span></span> <span data-ttu-id="962e4-115">若要将路由确认时，生成使用中的以下属性的筛选器**BTS**命名空间：</span><span class="sxs-lookup"><span data-stu-id="962e4-115">To route an acknowledgment, build a filter using the following properties from the **BTS** namespace:</span></span>  
  
|<span data-ttu-id="962e4-116">属性名称</span><span class="sxs-lookup"><span data-stu-id="962e4-116">Property name</span></span>|<span data-ttu-id="962e4-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="962e4-117">Data type</span></span>|<span data-ttu-id="962e4-118">Description</span><span class="sxs-lookup"><span data-stu-id="962e4-118">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="962e4-119">BTS.AckFailureCategory</span><span class="sxs-lookup"><span data-stu-id="962e4-119">BTS.AckFailureCategory</span></span>|<span data-ttu-id="962e4-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="962e4-120">xs:int</span></span>|<span data-ttu-id="962e4-121">标识**ErrorCategory**，后者提供的位置和将其挂起的原因。</span><span class="sxs-lookup"><span data-stu-id="962e4-121">Identifies the **ErrorCategory**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="962e4-122">BTS.AckFailureCode</span><span class="sxs-lookup"><span data-stu-id="962e4-122">BTS.AckFailureCode</span></span>|<span data-ttu-id="962e4-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-123">xs:string</span></span>|<span data-ttu-id="962e4-124">标识**ErrorCode**，后者提供的位置和将其挂起的原因。</span><span class="sxs-lookup"><span data-stu-id="962e4-124">Identifies the **ErrorCode**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="962e4-125">BTS.AckType</span><span class="sxs-lookup"><span data-stu-id="962e4-125">BTS.AckType</span></span>|<span data-ttu-id="962e4-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-126">xs:string</span></span>|<span data-ttu-id="962e4-127">对于肯定确认，值为 ACK；对于否定确认，值为 NACK。</span><span class="sxs-lookup"><span data-stu-id="962e4-127">Value is ACK for a positive acknowledgment and NACK for a negative acknowledgment.</span></span>|  
|<span data-ttu-id="962e4-128">BTS.AckID</span><span class="sxs-lookup"><span data-stu-id="962e4-128">BTS.AckID</span></span>|<span data-ttu-id="962e4-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-129">xs:string</span></span>|<span data-ttu-id="962e4-130">标识**MessageID**的原始消息。</span><span class="sxs-lookup"><span data-stu-id="962e4-130">Identifies the **MessageID** of the original message.</span></span>|  
|<span data-ttu-id="962e4-131">BTS.AckOwnerID</span><span class="sxs-lookup"><span data-stu-id="962e4-131">BTS.AckOwnerID</span></span>|<span data-ttu-id="962e4-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-132">xs:string</span></span>|<span data-ttu-id="962e4-133">标识原始消息中的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="962e4-133">Identifies the instance ID from the original message.</span></span>|  
|<span data-ttu-id="962e4-134">BTS.CorrelationToken</span><span class="sxs-lookup"><span data-stu-id="962e4-134">BTS.CorrelationToken</span></span>|<span data-ttu-id="962e4-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-135">xs:string</span></span>|<span data-ttu-id="962e4-136">标识原始消息（如果出现一个）中的相关标记。</span><span class="sxs-lookup"><span data-stu-id="962e4-136">Identifies the correlation token from the original message if one is present.</span></span>|  
|<span data-ttu-id="962e4-137">BTS.AckDescription</span><span class="sxs-lookup"><span data-stu-id="962e4-137">BTS.AckDescription</span></span>|<span data-ttu-id="962e4-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-138">xs:string</span></span>|<span data-ttu-id="962e4-139">标识**ErrorDescription**，后者提供的位置和将其挂起的原因。</span><span class="sxs-lookup"><span data-stu-id="962e4-139">Identifies the **ErrorDescription**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="962e4-140">BTS.AckSendPortID</span><span class="sxs-lookup"><span data-stu-id="962e4-140">BTS.AckSendPortID</span></span>|<span data-ttu-id="962e4-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-141">xs:string</span></span>|<span data-ttu-id="962e4-142">标识**SendPortID**原始消息中。</span><span class="sxs-lookup"><span data-stu-id="962e4-142">Identifies the **SendPortID** from the original message.</span></span>|  
|<span data-ttu-id="962e4-143">BTS.AckSendPortName</span><span class="sxs-lookup"><span data-stu-id="962e4-143">BTS.AckSendPortName</span></span>|<span data-ttu-id="962e4-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-144">xs:string</span></span>|<span data-ttu-id="962e4-145">标识**SendPortName**原始消息中。</span><span class="sxs-lookup"><span data-stu-id="962e4-145">Identifies the **SendPortName** from the original message.</span></span>|  
|<span data-ttu-id="962e4-146">BTS.AckOutboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="962e4-146">BTS.AckOutboundTransportLocation</span></span>|<span data-ttu-id="962e4-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-147">xs:string</span></span>|<span data-ttu-id="962e4-148">标识**OutboundTransportLocation**原始消息中。</span><span class="sxs-lookup"><span data-stu-id="962e4-148">Identifies the **OutboundTransportLocation** from the original message.</span></span>|  
|<span data-ttu-id="962e4-149">BTS.AckReceivePortID</span><span class="sxs-lookup"><span data-stu-id="962e4-149">BTS.AckReceivePortID</span></span>|<span data-ttu-id="962e4-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-150">xs:string</span></span>|<span data-ttu-id="962e4-151">标识**ReceivePortID**原始消息中。</span><span class="sxs-lookup"><span data-stu-id="962e4-151">Identifies the **ReceivePortID** from the original message.</span></span>|  
|<span data-ttu-id="962e4-152">BTS.AckReceivePortName</span><span class="sxs-lookup"><span data-stu-id="962e4-152">BTS.AckReceivePortName</span></span>|<span data-ttu-id="962e4-153">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-153">xs:string</span></span>|<span data-ttu-id="962e4-154">标识**ReceivePortName**原始消息中。</span><span class="sxs-lookup"><span data-stu-id="962e4-154">Identifies the **ReceivePortName** from the original message.</span></span>|  
|<span data-ttu-id="962e4-155">BTS.AckInboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="962e4-155">BTS.AckInboundTransportLocation</span></span>|<span data-ttu-id="962e4-156">xs:string</span><span class="sxs-lookup"><span data-stu-id="962e4-156">xs:string</span></span>|<span data-ttu-id="962e4-157">标识**InboundTransportLocation**原始消息中。</span><span class="sxs-lookup"><span data-stu-id="962e4-157">Identifies the **InboundTransportLocation** from the original message.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="962e4-158">包含错误信息的属性不会出现在 ACK 中，因为它们表示传递成功。</span><span class="sxs-lookup"><span data-stu-id="962e4-158">The properties that contain error information are not present in ACKs because they signal a positive delivery.</span></span>  
  
## <a name="negative-acknowledgment-message-body"></a><span data-ttu-id="962e4-159">否定确认消息正文</span><span class="sxs-lookup"><span data-stu-id="962e4-159">Negative Acknowledgment Message Body</span></span>  
 <span data-ttu-id="962e4-160">有关肯定确认或否定确认的很多重要信息都包含在上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="962e4-160">Much of the important information about a positive or negative acknowledgment is contained in the context properties.</span></span> <span data-ttu-id="962e4-161">除上下文属性之外，NACK 还包含消息正文部分，其中包含 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="962e4-161">In addition to the context properties, NACKs also contain a message body part containing a SOAP fault.</span></span> <span data-ttu-id="962e4-162">SOAP 错误的格式如下：</span><span class="sxs-lookup"><span data-stu-id="962e4-162">The format of the SOAP fault is as follows:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<SOAP:Envelope xmlns:SOAP="http://schemas.xmlsoap.org/soap/envelope/" SOAP:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
  <SOAP:Body>  
    <SOAP:Fault>  
      <faultcode>Microsoft BizTalk Server Negative Acknowledgment </faultcode>  
      <faultstring>An error occurred while processing the message, refer to the details section for more information </faultstring>  
      <faultactor>C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml</faultactor>  
      <detail>  
        <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
          <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
          <ErrorCode>0xc0c01658</ErrorCode>  
          <ErrorCategory>0</ErrorCategory>  
          <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".  </ErrorDescription>  
        </ns0:NACK>  
      </detail>  
    </SOAP:Fault>  
  </SOAP:Body>  
</SOAP:Envelope>  
```  
  
 <span data-ttu-id="962e4-163">适配器引发的异常消息位于 ErrorDescription 元素的“SOAP 详细信息”部分中。</span><span class="sxs-lookup"><span data-stu-id="962e4-163">The exception message raised by the adapter is in the SOAP Detail section in the ErrorDescription element.</span></span>  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a><span data-ttu-id="962e4-164">在业务流程中访问消息正文</span><span class="sxs-lookup"><span data-stu-id="962e4-164">Accessing the Message Body from an Orchestration</span></span>  
 <span data-ttu-id="962e4-165">如果具有需要送达通知的业务流程端口，则传输失败时引发的 DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化而来的。</span><span class="sxs-lookup"><span data-stu-id="962e4-165">If you have an orchestration port that requires delivery notification, the DeliveryFailureException that is thrown on a transmission failure is deserialized from the SOAP fault that is contained in the NACK message body.</span></span> <span data-ttu-id="962e4-166">若要在业务流程中访问异常消息字符串，请将 DeliveryFailureException 转换为 SoapException，然后访问 InnerXml，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="962e4-166">To access the exception message string from within your orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml as shown in the following code:</span></span>  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 <span data-ttu-id="962e4-167">上面的代码示例返回的 XML 片段类似如下：</span><span class="sxs-lookup"><span data-stu-id="962e4-167">The preceding code sample returns an XML fragment similar to the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
  <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
  <ErrorCode>0xc0c01658</ErrorCode>  
  <ErrorCategory>0</ErrorCategory>  
  <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".</ErrorDescription>  
</ns0:NACK>  
```  
  
## <a name="when-is-an-acknowledgment-published"></a><span data-ttu-id="962e4-168">何时发布确认？</span><span class="sxs-lookup"><span data-stu-id="962e4-168">When Is an Acknowledgment Published?</span></span>  
 <span data-ttu-id="962e4-169">肯定确认 (ACK) 和否定确认 (NACK) 都是在失败时向 MessageBox 数据库发布的（假设至少有一个匹配订阅）。</span><span class="sxs-lookup"><span data-stu-id="962e4-169">Both positive (ACK) and negative (NACK) acknowledgments are published to the MessageBox database at the point of failure provided there is at least one matching subscription.</span></span> <span data-ttu-id="962e4-170">例如，如果 BizTalk Server 找不到与从接收端口读取的消息相匹配的架构，并且没有任何 NACK 订阅，则将会挂起该消息（如果尚未启用失败消息路由），并且不发布 NACK。</span><span class="sxs-lookup"><span data-stu-id="962e4-170">For example, if BizTalk Server cannot find a matching schema for a message read from a receive port and there are no NACK subscriptions, it suspends the message (if failed message routing has not been enabled) and does not publish a NACK</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="962e4-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="962e4-171">See Also</span></span>  
 <span data-ttu-id="962e4-172">[错误处理](../core/error-handling.md) </span><span class="sxs-lookup"><span data-stu-id="962e4-172">[Error Handling](../core/error-handling.md) </span></span>  
 [<span data-ttu-id="962e4-173">使用失败的邮件路由</span><span class="sxs-lookup"><span data-stu-id="962e4-173">Using Failed Message Routing</span></span>](../core/using-failed-message-routing.md)