---
title: 使用确认 |Microsoft Docs
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
ms.openlocfilehash: ec79910977625c7e93bac1e70b0f482a0db67677
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399951"
---
# <a name="using-acknowledgments"></a>使用确认
BizTalk 消息引擎生成肯定确认 (ACK) 和否定确认 (NACK) 以响应通过端口的消息处理过程中遇到的条件。 BizTalk Server 发布肯定确认以指示成功的消息传输和否定确认来指明传输失败和消息挂起。  
  
## <a name="why-use-acknowledgments"></a>为什么使用确认？  
 正和负确认所提供的强有力的反馈，可用于确定消息是否到达其目标，或遇到了此过程的一个或多个问题。 例如，确认时很有用：  
  
- 你想要进行架构验证新的贸易合作伙伴和其他错误的监视器接收端口。  
  
- 你想要将标记为"进程内"发出，如果已成功发送给合作伙伴进行审批或"失败"如果传输失败 （例如，如果合作伙伴的服务器已关闭） 贷款申请的状态。  
  
- 处理的交换包含多个采购订单，并且想要跟踪对已传输或传输失败的订单数。  
  
  可以使用确认和基于内容的路由使用筛选器来完成这些方案的每个操作。  
  
## <a name="routing-acknowledgments"></a>路由确认  
 当发布 ACK 或 NACK 后时，所有从导致 ACK/NACK 的消息的消息上下文属性都将降级。 提升了任何属性不会流向确认。 若要确认路由，生成使用的以下属性的筛选器**BTS**命名空间：  
  
|属性名称|数据类型|Description|  
|-------------------|---------------|-----------------|  
|BTS.AckFailureCategory|xs:int|标识**ErrorCategory**，它可使位置和挂起的原因。|  
|BTS.AckFailureCode|xs:string|标识**ErrorCode**，它可使位置和挂起的原因。|  
|BTS.AckType|xs:string|值是 ACK 肯定确认和 NACK 对于否定确认。|  
|BTS.AckID|xs:string|标识**MessageID**的原始消息。|  
|BTS.AckOwnerID|xs:string|标识原始消息中的实例 ID。|  
|BTS.CorrelationToken|xs:string|如果不存在，请标识原始消息中的相关标记。|  
|BTS.AckDescription|xs:string|标识**ErrorDescription**，它可使位置和挂起的原因。|  
|BTS.AckSendPortID|xs:string|标识**SendPortID**原始消息中。|  
|BTS.AckSendPortName|xs:string|标识**SendPortName**原始消息中。|  
|BTS.AckOutboundTransportLocation|xs:string|标识**OutboundTransportLocation**原始消息中。|  
|BTS.AckReceivePortID|xs:string|标识**ReceivePortID**原始消息中。|  
|BTS.AckReceivePortName|xs:string|标识**ReceivePortName**原始消息中。|  
|BTS.AckInboundTransportLocation|xs:string|标识**InboundTransportLocation**原始消息中。|  
  
> [!NOTE]
>  包含错误信息的属性不出现在 Ack，因为它们表示传递成功。  
  
## <a name="negative-acknowledgment-message-body"></a>否定确认消息正文  
 很多有关肯定或否定确认的重要信息都包含在上下文属性。 除了上下文属性，Nack 还包含消息正文部分包含 SOAP 错误。 SOAP 错误的格式如下所示：  
  
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
  
 适配器引发的异常消息位于 ErrorDescription 元素中的 SOAP 详细信息部分。  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a>从业务流程中访问消息正文  
 如果您具有需要送达通知的业务流程端口，传输失败时引发的 DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化。 若要访问异常消息的字符串从业务流程中，将 DeliveryFailureException 转换为 SoapException，然后访问 InnerXml，如以下代码所示：  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 上面的代码示例将返回类似以下 XML 片段：  
  
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
 肯定 (确认 ACK) 和否定 (NACK) 确认发布到 MessageBox 数据库发生失败时提供至少一个相匹配的订阅。 例如，如果 BizTalk Server 找不到匹配的架构，从接收端口读取一个消息，并没有任何 NACK 订阅，它将挂起消息 （如果失败的消息路由尚未启用） 而不发布 NACK  
  
## <a name="see-also"></a>请参阅  
 [错误处理](../core/error-handling.md)   
 [使用失败的消息路由](../core/using-failed-message-routing.md)