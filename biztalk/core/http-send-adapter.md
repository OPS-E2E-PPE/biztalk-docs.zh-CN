---
title: HTTP 发送适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e69308b4-421f-4d7c-b9bb-ee086df03272
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 012ae1302571355e56adda51714bd9206cf51fb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382883"
---
# <a name="http-send-adapter"></a>HTTP 发送适配器
HTTP 发送适配器获取来自消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并将它们发送到 HTTP POST 请求的目标 URL。 HTTP 发送适配器获取消息内容从 BizTalk 消息对象正文部分。 HTTP 发送适配器将忽略 BizTalk 消息对象的所有其他部分。  
  
 该适配器将消息发送到目标 URL 和 BizTalk 消息引擎接收 HTTP 成功状态代码后，HTTP 发送适配器从 MessageBox 数据库中删除该消息。  
  
 HTTP 消息的重定向支持，并且可以配置发送端口上。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机 HTTP 发送适配器作为本机 BizTalk 应用程序。 它支持单向发送的消息以及要求-响应传输。 HTTP 发送适配器的发送位置是一个通过发送端口配置的独特 URL。 此唯一 URL 可以包括查询字符串追加到基 URL。  
  
## <a name="batching-support-for-the-http-send-adapter"></a>HTTP 发送适配器的批处理支持  
 HTTP 发送适配器不支持批处理操作。  
  
## <a name="chunked-encoding-support-for-the-http-send-adapter"></a>HTTP 发送适配器的 chunked 编码支持  
 如果**启用 chunked 编码**已启用配置选项，则 HTTP 发送适配器将使用 chunked 编码，如果请求大小超过 8 KB 的请求消息发送。 如果使用 HTTP 代理服务器，则 HTTP 发送适配器将不使用 chunked 编码，并始终将数据暂存在发送之前。 **启用 chunked 编码**默认情况下已启用配置选项。  
  
 当发送适配器收到的响应消息时，它可以接受使用 chunked 编码的正文部分的响应消息。  
  
## <a name="client-authentication-for-the-http-send-adapter"></a>HTTP 发送适配器的客户端身份验证  
 HTTP 发送适配器使用进行身份验证目标服务器通过使用以下身份验证类型之一：  
  
- **匿名。** 连接到目标服务器时，HTTP 适配器不发送任何凭据。 如果目标服务器允许匿名身份验证使用目标服务器上配置的匿名帐户的凭据。  
  
- **基本。** HTTP 适配器通过 HTTP 连接以纯文本格式发送用户名和密码。  
  
- **摘要。** HTTP 适配器通过 HTTP 连接以加密格式发送密码。  
  
- **Kerberos。** 用户名和密码都不会通过 HTTP 连接发送。 HTTP 适配器将使用在其下 HTTP 适配器运行发送此身份验证类型的进程的凭据。  
  
  此外，HTTP 发送适配器可以提供客户端到 Web 服务器的安全套接字层 (SSL) 证书如果服务器要求或接受它。  
  
## <a name="client-certificates-for-the-http-send-adapter"></a>HTTP 发送适配器的客户端证书  
 HTTP 发送适配器可以建立与接受或不需要客户端证书的服务器的安全连接。 如果指定客户端证书，则 HTTP 发送适配器将连接与服务器的要求或接受客户端证书时使用该证书。 如果未指定客户端证书和目标服务器需要客户端证书，HTTP 发送适配器无法发送消息，并按照标准的重试逻辑。  
  
 HTTP 发送适配器使用的客户端证书所用的帐户的个人存储中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程正在运行。 证书的指纹来指定。 如果 HTTP 发送适配器无法加载证书出于任何原因，已发送的消息被挂起。  
  
## <a name="single-sign-on-support-for-the-http-adapter"></a>HTTP 适配器的单一登录支持  
 用于 HTTP 接收位置或发送端口使用 BizTalk 管理控制台中，可以配置企业单一登录 (SSO)。 本主题介绍使用 HTTP 适配器的 SSO 工作原理。  
  
 **接收位置用于 HTTP 的单一登录支持**  
  
 当由 Microsoft Internet 信息服务 (IIS) 从 Web 客户端收到的 HTTP 请求时，IIS 进行用户身份验证。 Internet 服务器应用程序编程接口 (ISAPI) 扩展将模拟的 Microsoft Windows 用户，然后调用 SSO 凭据存储区获取加密的票证。 此票证将被视为**SSOTicket**中消息的上下文属性。  
  
 在直通方案中，BizTalk 消息引擎将定向到 MessageBox 数据库的消息。 当适配器从 MessageBox 数据库接收消息时，HTTP 适配器调用**ISSOTicket.RedeemTicket 方法**使用加密票证和要检索从后端凭据的应用程序名称SSO 存储区。 HTTP 适配器使用的外部凭据连接到后端系统并处理该请求。 有关关联应用程序的详细信息，请参阅[SSO 关联应用程序](../core/sso-affiliate-applications.md)。  
  
 在方案中在业务流程调用该适配器，BizTalk 消息引擎将此消息发送到 MessageBox 数据库。 业务流程应确保同时**SSOTicket**上下文属性和**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**是包含该票证在消息上下文属性维护。 当适配器从 MessageBox 数据库接收此消息时，适配器调用**RedeemTicket**使用加密票证以从 SSO 存储中检索后端凭据。 具体而言，设计计划的用户应将此属性复制到消息。  
  
 **HTTP 发送适配器的单一登录支持**  
  
 如果启用 SSO，则当 HTTP 发送端口收到的消息**Secure**属性，它将调用 SSO 服务器以验证并兑换票证关联应用程序。 管理应用程序、 关联管理员或 SSO 关联应用程序的管理员可调用 SSO 以兑换票证。 然后，SSO 对票证进行解密，并获取后端凭据。 直通和业务流程方案是与 HTTP 发送端口相同。  
  
 默认情况下，为 HTTP 发送端口已禁用 SSO。 有关为 HTTP 发送端口启用 SSO 的详细信息，请参阅[配置 HTTP 发送端口](../core/configuring-an-http-send-port.md)。  
  
> [!NOTE]
>  仅可以使用单一登录使用基本和摘要式身份验证。  
  
 若要正确实现单一登录支持 HTTP 接收和发送适配器的以下条件必须满足：  
  
-   必须在以下位置中指定相同的用户帐户：  
  
    -   应用程序池标识 (IIS 7.0) 或宿主 COM + 应用程序标识为通过 HTTP 进行监视的 IIS 虚拟目录接收适配器。 有关配置 IIS 以实现 HTTP 接收位置，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
    -   用于 HTTP 适配器运行在独立主机实例的登录凭据。 有关如何配置主机实例的登录凭据的信息，请参阅[如何修改主机实例属性](../core/how-to-modify-host-instance-properties.md)。  
  
-   使用 HTTP 适配器的独立主机必须配置为受信任的身份验证。 有关如何将主机配置为受信任验证的信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="negative-acknowledgment-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapter"></a>对于失败的传输生成的 HTTP 或 SOAP 适配器的否定确认 (NACK) 消息  
 当已成功传输一条消息时，BizTalk 消息引擎发布到 MessageBox 相关联的确认 (ACK) 消息，如果启用了送达通知。 同样，当 BizTalk 消息引擎挂起消息或业务流程引擎挂起业务流程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将关联的否定确认 (NACK) 消息发布到 MessageBox。 NACK 消息包含上下文属性和消息正文部分组成的 SOAP 错误。 如果因 HTTP 或 SOAP 适配器的传输失败而生成的 NACK 消息，则 SOAP 错误将包含标头元素和来自目标 Web 服务器的响应的正文元素。 以下是 SOAP 错误而失败的 HTTP 传输生成的 NACK 中的示例：  
  
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
>  限制为 48 KB 的标头元素和 Body 元素。 标头元素是舍入为最接近完整的标头值对不超出该限制。 正文元素将被截至 48 KB。  
  
> [!NOTE]
>  如果没有匹配的订阅，则会放弃 NACK 和 ACK 消息。 BizTalk 消息引擎不会挂起 NACK 和 ACK 消息。  
  
 若要订阅 NACK 消息，可以执行下列任一操作：  
  
- 使用相应的消息上下文属性的筛选器创建发送端口。 请参阅**消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]有关系统消息上下文属性的列表，包括那些与消息确认相关。  
  
- 从标记为业务流程端口发送**送达通知 = 传输**。 如果业务流程端口标有**送达通知 = 传输**，业务流程将等待，直到收到 ACK 或 NACK 消息与已传输。 如果生成了 NACK，然后它将路由到业务流程和业务流程将引发 DeliveryFailureException。 DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化。 若要检索从返回到业务流程的 SOAP 错误的异常消息字符串，将 DeliveryFailureException 转换为 SoapException，然后访问 InnerXml，从 SOAP 详细信息部分。 下面的代码示例演示如何执行此操作：  
  
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
 [HTTP 适配器](../core/http-adapter.md)  
**SSO COM 对象** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]