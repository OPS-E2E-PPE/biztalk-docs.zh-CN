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
ms.openlocfilehash: 7bd63c7ad8c121cbbaf086be4bff9dd1fbc1becc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244363"
---
# <a name="soap-send-adapter"></a>SOAP 发送适配器
使用 SOAP 发送适配器来调用 Web 服务。 SOAP 发送适配器读取 BizTalk 消息对象，若要获取代理名称上的消息上下文，并调用关联的外部 Web 服务代理。  
  
## <a name="client-authentication-for-the-soap-send-adapter"></a>客户端身份验证为 SOAP 发送适配器  
 SOAP 发送适配器使用进行身份验证目标服务器通过使用以下身份验证类型之一：  
  
- **匿名。** 默认设置。  
  
- **基本。** SOAP 连接以纯文本格式发送用户名和密码。  
  
- **摘要。** SOAP 连接以加密格式发送用户名和密码。  
  
- **Kerberos 或 NTLM。** 用户名和密码都不通过 SOAP 连接发送。 SOAP 适配器始终使用的进程在其下运行 SOAP 发送适配器的此身份验证类型的凭据。  
  
  此外，SOAP 发送适配器可以提供客户端到 Web 服务器的安全套接字层 (SSL) 证书如果服务器要求或接受它。  
  
  如果 SOAP 发送适配器接收到请求的消息时，在启用了企业单一登录 (SSO)， **SSOTicket**属性，该适配器连接到 SSO 服务器以验证并兑换票证。 SOAP 适配器验证票证后，它解密，并从凭据存储区检索关联系统的凭据。 SOAP 适配器然后使用凭据连接到关联系统，并处理 SOAP 请求。  
  
## <a name="client-certificates-for-the-soap-send-adapter"></a>客户端证书，为 SOAP 发送适配器  
 SOAP 发送适配器可以建立与接受或不需要客户端证书的服务器的安全连接。 如果指定的客户端证书，SOAP 发送适配器使用的证书使用要求或接受客户端证书的服务器进行连接时。 如果未指定客户端证书，并且目标服务器需要客户端证书，SOAP 发送适配器将无法发送消息，并按照标准的重试逻辑。  
  
 SOAP 发送适配器使用的客户端证书所用的帐户的个人存储中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程正在运行。 SOAP 适配器指定由其指纹的证书。 如果 SOAP 发送适配器无法加载证书出于任何原因，已发送的消息被挂起。  
  
## <a name="negative-acknowledgement-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapters"></a>对于失败的传输生成的 HTTP 或 SOAP 适配器的否定确认 (NACK) 消息  
 当已成功传输一条消息时，BizTalk 消息引擎发布到 MessageBox 数据库相关联的确认 (ACK) 消息，如果启用了送达通知。 同样，当 BizTalk 消息引擎挂起消息或业务流程引擎挂起业务流程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]向 MessageBox 发布一个关联的否定确认 (NACK) 消息。 NACK 消息包含上下文属性和消息正文部分包含的 SOAP 错误。 如果 NACK 消息由于 HTTP 或 SOAP 适配器的传输失败而生成的包含 SOAP 错误**标头**元素并**正文**来自目标 Web 响应的元素服务器。 以下是 SOAP 错误而失败的 SOAP 传输生成的 NACK 中的示例：  
  
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
  
 若要订阅 NACK 消息，可以执行下列任一操作：  
  
1. 使用相应的消息上下文属性的筛选器创建发送端口。 请参阅**消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]有关系统消息上下文属性的列表，包括那些与消息确认相关。  
  
2. 从标记为业务流程端口发送**送达通知 = 传输**。 如果业务流程端口标有**送达通知 = 传输**，业务流程将等待，直到收到 ACK 或 NACK 消息与已传输。 如果生成了 NACK，然后它将路由到业务流程和业务流程将引发 DeliveryFailureException。 DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化。 若要检索从返回到业务流程的 SOAP 错误的异常消息字符串，将 DeliveryFailureException 转换为 SoapException，然后访问 InnerXml，从 SOAP 详细信息部分。 下面的代码示例演示如何执行此操作：  
  
   ```  
   // Cast the DeliveryFailureException to a SoapException…  
   System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
   System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
   //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
   //object type created in an Exception handler  
   ```  
  
    上面的代码示例将返回类似于以下 XML 片段：  
  
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