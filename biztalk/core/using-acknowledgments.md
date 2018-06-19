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
# <a name="using-acknowledgments"></a>使用确认
在对通过端口处理消息期间所遇到的情况作出响应时，BizTalk 消息引擎将生成肯定确认 (ACK) 和否定确认 (NACK)。 BizTalk Server 发布肯定确认以指示消息传输成功，发布否定确认以指示传输失败并挂起消息。  
  
## <a name="why-use-acknowledgments"></a>为什么使用确认？  
 肯定确认和否定确认所提供的强有力的反馈信息可以用来确定消息是否到达其目标，或是否在传输过程中遇到一个或多个问题。 例如，确认在以下情况下非常有用：  
  
-   您希望监视新贸易合作伙伴的接收端口，以查看架构验证信息和其他错误。  
  
-   如果您希望将已发出的贷款申请的状态标记为“正在处理”（如果该申请已成功发送给合作伙伴进行审批）或“失败”（如果传输失败。例如，合作伙伴的服务器停机）。  
  
-   所处理的交换包含多个采购订单，您希望对已传输或传输失败的订单数进行跟踪。  
  
 通过使用确认和利用筛选器的基于内容的路由，可以完成以下各个方案：  
  
## <a name="routing-acknowledgments"></a>路由确认  
 在发布 ACK 或 NACK 后，引发 ACK/NACK 的消息内的所有消息上下文属性都将降级。 已升级的任何属性都不会流向确认。 若要将路由确认时，生成使用中的以下属性的筛选器**BTS**命名空间：  
  
|属性名称|数据类型|Description|  
|-------------------|---------------|-----------------|  
|BTS.AckFailureCategory|xs:int|标识**ErrorCategory**，后者提供的位置和将其挂起的原因。|  
|BTS.AckFailureCode|xs:string|标识**ErrorCode**，后者提供的位置和将其挂起的原因。|  
|BTS.AckType|xs:string|对于肯定确认，值为 ACK；对于否定确认，值为 NACK。|  
|BTS.AckID|xs:string|标识**MessageID**的原始消息。|  
|BTS.AckOwnerID|xs:string|标识原始消息中的实例 ID。|  
|BTS.CorrelationToken|xs:string|标识原始消息（如果出现一个）中的相关标记。|  
|BTS.AckDescription|xs:string|标识**ErrorDescription**，后者提供的位置和将其挂起的原因。|  
|BTS.AckSendPortID|xs:string|标识**SendPortID**原始消息中。|  
|BTS.AckSendPortName|xs:string|标识**SendPortName**原始消息中。|  
|BTS.AckOutboundTransportLocation|xs:string|标识**OutboundTransportLocation**原始消息中。|  
|BTS.AckReceivePortID|xs:string|标识**ReceivePortID**原始消息中。|  
|BTS.AckReceivePortName|xs:string|标识**ReceivePortName**原始消息中。|  
|BTS.AckInboundTransportLocation|xs:string|标识**InboundTransportLocation**原始消息中。|  
  
> [!NOTE]
>  包含错误信息的属性不会出现在 ACK 中，因为它们表示传递成功。  
  
## <a name="negative-acknowledgment-message-body"></a>否定确认消息正文  
 有关肯定确认或否定确认的很多重要信息都包含在上下文属性中。 除上下文属性之外，NACK 还包含消息正文部分，其中包含 SOAP 错误。 SOAP 错误的格式如下：  
  
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
  
 适配器引发的异常消息位于 ErrorDescription 元素的“SOAP 详细信息”部分中。  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a>在业务流程中访问消息正文  
 如果具有需要送达通知的业务流程端口，则传输失败时引发的 DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化而来的。 若要在业务流程中访问异常消息字符串，请将 DeliveryFailureException 转换为 SoapException，然后访问 InnerXml，如以下代码所示：  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 上面的代码示例返回的 XML 片段类似如下：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
  <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
  <ErrorCode>0xc0c01658</ErrorCode>  
  <ErrorCategory>0</ErrorCategory>  
  <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".</ErrorDescription>  
</ns0:NACK>  
```  
  
## <a name="when-is-an-acknowledgment-published"></a>何时发布确认？  
 肯定确认 (ACK) 和否定确认 (NACK) 都是在失败时向 MessageBox 数据库发布的（假设至少有一个匹配订阅）。 例如，如果 BizTalk Server 找不到与从接收端口读取的消息相匹配的架构，并且没有任何 NACK 订阅，则将会挂起该消息（如果尚未启用失败消息路由），并且不发布 NACK。  
  
## <a name="see-also"></a>另请参阅  
 [错误处理](../core/error-handling.md)   
 [使用失败的邮件路由](../core/using-failed-message-routing.md)