---
title: SOAP 发送适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d65218d-516b-4e45-a824-272ef6ef298c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2051cff7fcffc0876bfc45ad59578d08d538265f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002934"
---
# <a name="soap-send-adapter"></a>SOAP 发送适配器
使用 SOAP 发送适配器可调用 Web Services。 SOAP 发送适配器读取 BizTalk 消息对象上的消息上下文以获取代理名，并调用关联的外部 Web Services 代理。  
  
## <a name="client-authentication-for-the-soap-send-adapter"></a>SOAP 发送适配器的客户端验证  
 SOAP 发送适配器使用以下验证类型之一对目标服务器进行验证：  
  
- **匿名。** 默认设置。  
  
- **基本。** SOAP 连接以纯文本格式发送用户名和密码。  
  
- **摘要。** SOAP 连接以加密格式发送用户名和密码。  
  
- **Kerberos 或 NTLM。** 用户名和密码都不通过 SOAP 连接发送。 SOAP 适配器始终为此验证类型使用运行 SOAP 发送适配器的进程的凭据。  
  
  另外，如果 Web 服务器要求或接受客户端安全套接字层 (SSL) 证书，SOAP 发送适配器还可为其提供该证书。  
  
  如果 SOAP 发送适配器接收到请求的消息时，在启用了企业单一登录 (SSO)， **SSOTicket**属性，该适配器连接到 SSO 服务器以验证并兑换票证。 在 SOAP 适配器验证票证后，将对其进行解密，并从凭据存储中检索关联系统的凭据。 然后，SOAP 适配器将使用这些凭据连接到关联系统，并处理 SOAP 请求。  
  
## <a name="client-certificates-for-the-soap-send-adapter"></a>SOAP 发送适配器的客户端证书  
 SOAP 发送适配器可与接受或要求使用客户端证书的服务器建立安全连接。 如果指定了客户端证书，则在连接要求或接受客户端证书的服务器时，SOAP 发送适配器将使用该证书。 如果未指定客户端证书，并且目标服务器要求客户端证书，则 SOAP 发送适配器将无法发送消息，并会遵循标准的重试逻辑。  
  
 SOAP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。 SOAP 适配器根据证书的指纹来指定证书。 如果 SOAP 发送适配器由于某种原因无法加载证书，则会挂起该适配器正在发送的消息。  
  
## <a name="negative-acknowledgement-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapters"></a>HTTP 或 SOAP 适配器对于失败的传输将生成否定确认 (NACK) 消息  
 如果启用了送达通知，则在消息传输成功时，BizTalk 消息引擎将向 MessageBox 数据库发布一个关联的确认 (ACK) 消息。 同样，当 BizTalk 消息引擎挂起消息或业务流程引擎挂起业务流程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]向 MessageBox 发布一个关联的否定确认 (NACK) 消息。 NACK 消息包含上下文属性以及一个由 SOAP 错误构成的消息正文部分。 如果 NACK 消息由于 HTTP 或 SOAP 适配器的传输失败而生成的包含 SOAP 错误**标头**元素并**正文**来自目标 Web 响应的元素服务器。 下面列出了一个由于 SOAP 传输失败而生成的 NACK 中的 SOAP 错误示例：  
  
```  
<SOAP:Envelope xmlns:SOAP="http://schemas.xmlsoap.org/soap/envelope/" SOAP:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
   <SOAP:Body>  
      <SOAP:Fault>  
         <faultcode>Microsoft BizTalk Server Negative Acknowledgment</faultcode>   
         <faultstring>An error occurred while processing the message, refer to the details section for more information</faultstring>   
         <faultactor>http://localhost/receivestandard.asp</faultactor>   
         <detail>  
            <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
            <NAckID>{4E646707-03AA-4493-95C7-A64B09E2987D}</NAckID>  
            <ErrorCode>0x80131600</ErrorCode>  
            <ErrorCategory>0</ErrorCategory>  
            <ErrorDescription>The remote server returned an error: (404) Not Found.</ErrorDescription>  
            <ErrorDetail>  
            <HttpErrorDetail xmlns="http://schema.microsoft.com/BizTalk/2006/HttpErrorDetails.xsd">  
               <Headers>Server: Microsoft-IIS/5.1 Date: Wed, 21 Apr 2005 00:27:47 GMT X-Powered-By: ASP.NET Connection: close Content-Type: text/html Content-Length: 67 </Headers>  
               <Body>We could not locate the page you requested. Please check the URL.</Body>  
            </HttpErrorDetail>  
            </ErrorDetail>  
            </ns0:NACK>  
         </detail>  
      </SOAP:Fault>  
   </SOAP:Body>  
</SOAP:Envelope>  
```  
  
> [!NOTE]
>  **标头**元素并**正文**元素仅限于 48 KB。 **标头**元素舍入为最接近完整的标头值对不超出该限制。 **正文**元素将被截至 48 kb。  
  
> [!NOTE]
>  如果没有匹配的订阅，则会放弃 NACK 和 ACK 消息。 消息引擎不会挂起 NACK 和 ACK 消息。  
  
 若要订阅 NACK 消息，可执行以下操作之一：  
  
1. 创建带有相应消息上下文属性筛选器的发送端口。 请参阅**消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]有关系统消息上下文属性的列表，包括那些与消息确认相关。  
  
2. 从标记为业务流程端口发送**送达通知 = 传输**。 如果业务流程端口标有**送达通知 = 传输**，业务流程将等待，直到收到 ACK 或 NACK 消息与已传输。 如果生成了 NACK，则会将其路由到业务流程，然后业务流程将引发 DeliveryFailureException。 DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化而来的。 若要从返回到业务流程的 SOAP 错误中检索异常消息字符串，请将 DeliveryFailureException 转换为 SoapException，然后访问“SOAP 详细信息”部分中的 InnerXml。 下面的代码示例演示了如何执行此操作：  
  
   ```  
   // Cast the DeliveryFailureException to a SoapException…  
   System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
   System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
   //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
   //object type created in an Exception handler  
   ```  
  
    上面的代码示例返回的 XML 片断类似于以下形式：  
  
   ```  
   <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
   <NAckID>{4E646707-03AA-4493-95C7-A64B09E2987D}</NAckID>  
   <ErrorCode>0x80131600</ErrorCode>  
   <ErrorCategory>0</ErrorCategory>  
   <ErrorDescription>The remote server returned an error: (404) Not Found.</ErrorDescription>  
   <ErrorDetail>  
   <HttpErrorDetail xmlns="http://schema.microsoft.com/BizTalk/2006/HttpErrorDetails.xsd">  
      <Headers>Server: Microsoft-IIS/5.1 Date: Wed, 21 Apr 2005 00:27:47 GMT X-Powered-By: ASP.NET Connection: close Content-Type: text/html Content-Length: 67 </Headers>  
      <Body>We could not locate the page you requested. Please check the URL.</Body>  
   </HttpErrorDetail>  
   </ErrorDetail>  
   </ns0:NACK>  
   ```  
  
## <a name="see-also"></a>请参阅  
 [SOAP 适配器是什么？](../core/what-is-the-soap-adapter.md)   
 [SOAP 适配器的安全建议](../core/soap-adapter-security-recommendations.md)