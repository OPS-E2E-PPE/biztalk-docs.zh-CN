---
title: "HTTP 发送适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e69308b4-421f-4d7c-b9bb-ee086df03272
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8bfdfd380fac422f79ba175ae075a94f313dec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="http-send-adapter"></a>HTTP 发送适配器
HTTP 发送适配器用于从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 获取消息，并将其发送到 HTTP POST 请求的目标 URL。 HTTP 发送适配器获取消息内容从 BizTalk 消息对象的正文部分。 HTTP 发送适配器将忽略所有其他对象的部分 BizTalk 消息。  
  
 适配器将消息发送到目标 URL BizTalk Messaging Engine HTTP 成功状态代码后，收到 HTTP 发送适配器从 MessageBox 数据库中删除消息。  
  
 HTTP 消息的重定向支持，并且可以在发送端口上配置。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用作 HTTP 发送适配器的宿主，将其视为本地 BizTalk 应用程序。 它支持单向发送的消息以及请求-响应传输。 HTTP 发送适配器的发送位置是你通过发送端口配置的不同 URL。 此唯一 URL 可以包括查询字符串追加到基 URL。  
  
## <a name="batching-support-for-the-http-send-adapter"></a>批处理为 HTTP 发送适配器的支持  
 HTTP 发送适配器不支持批处理操作。  
  
## <a name="chunked-encoding-support-for-the-http-send-adapter"></a>Chunked 编码为 HTTP 发送适配器的支持  
 如果**启用 chunked 编码**已启用配置选项，则 HTTP 发送适配器将使用分块编码，如果请求大小超过 8 KB 的请求消息发送。 如果使用 HTTP 代理服务器，则 HTTP 发送适配器将不使用分块编码，并且始终在发送之前暂存数据。 **启用 chunked 编码**默认情况下已启用配置选项。  
  
 当发送适配器接收响应消息时，它可以接受具有分块编码的正文部分的响应消息。  
  
## <a name="client-authentication-for-the-http-send-adapter"></a>HTTP 发送适配器的客户端身份验证  
 HTTP 发送适配器进行身份验证的目标服务器通过使用以下身份验证类型之一：  
  
-   **匿名。** HTTP 适配器连接到目标服务器时，不会发送任何凭据。 如果目标服务器允许匿名身份验证使用目标服务器上配置的匿名帐户的凭据。  
  
-   **基本。** HTTP 适配器发送的用户名和密码通过 HTTP 连接以纯文本。  
  
-   **Digest。** HTTP 适配器发送的密码以加密格式通过 HTTP 连接。  
  
-   **Kerberos。** 用户名和密码都不是通过 HTTP 连接发送的。 HTTP 适配器将使用在其下 HTTP 所发送的此身份验证类型的适配器运行进程的凭据。  
  
 此外，HTTP 发送适配器可以提供客户端到 Web 服务器的安全套接字层 (SSL) 证书如果服务器需要或接受它。  
  
## <a name="client-certificates-for-the-http-send-adapter"></a>HTTP 发送适配器的客户端证书  
 HTTP 发送适配器可以建立与接受或需要客户端证书的服务器的安全连接。 如果指定客户端证书，则 HTTP 发送适配器将连接与服务器需要或不接受客户端证书时使用的证书。 如果未指定客户端证书，并且目标服务器需要客户端证书，HTTP 发送适配器无法发送消息，并遵循标准的重试逻辑。  
  
 HTTP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。 指定由其指纹的证书。 如果 HTTP 发送适配器无法正常工作，以加载证书出于任何原因，已发送的消息，则挂起。  
  
## <a name="single-sign-on-support-for-the-http-adapter"></a>HTTP 适配器的的单一登录支持  
 用于 HTTP 中使用的接收位置或发送端口使用 BizTalk 管理控制台，你可以配置企业单一登录 (SSO)。 本主题介绍 SSO 与 HTTP 适配器的工作方式。  
  
 **用于 HTTP 的单一登录支持接收位置**  
  
 当从 Web 客户端可以收到由 Microsoft Internet 信息服务 (IIS) 的 HTTP 请求时，IIS 进行用户身份验证。 Internet 服务器应用程序编程接口 (ISAPI) 扩展模拟的 Microsoft Windows 用户，然后调用要获得加密的票证的 SSO 凭据存储区。 此票证已存储为**SSOTicket**消息的上下文中的属性。  
  
 在直通方案中，BizTalk 消息引擎将把消息引入 MessageBox 数据库中。 当适配器从 MessageBox 数据库收到消息时，HTTP 适配器将调用**ISSOTicket.RedeemTicket 方法**与加密票证以及从中检索后端凭据的应用程序名称SSO 存储。 然后，HTTP 适配器使用的外部凭据连接到后端系统并处理该请求。 有关关联应用程序的详细信息，请参阅[SSO Affiliate 应用程序](../core/sso-affiliate-applications.md)。  
  
 在其中业务流程将调用该适配器方案中，BizTalk 消息引擎将此消息发送到 MessageBox 数据库。 业务流程应确保同时**SSOTicket**上下文属性和**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**包含票证的消息的上下文属性维护。 当适配器从 MessageBox 数据库收到此消息时，该适配器调用**RedeemTicket**与加密的票证，以从 SSO 存储中检索后端凭据。 具体而言，设计计划的用户应将此属性复制到消息。  
  
 **HTTP 发送适配器的单一登录支持**  
  
 如果启用了 SSO，当 HTTP 发送端口收到的消息**Secure**属性，它调用的 SSO 服务器验证和兑换关联应用程序的票证。 关联应用程序的管理应用程序、关联管理员或 SSO 管理员可调用 SSO 以兑换票证。 然后，SSO 将对票证进行解密，并获取后端凭据。 传递和业务流程方案都是与 HTTP 发送端口相同。  
  
 默认情况下，为 HTTP 发送端口被禁用 SSO。 有关为 HTTP 发送端口启用 SSO 的详细信息，请参阅[配置 HTTP 发送端口](../core/configuring-an-http-send-port.md)。  
  
> [!NOTE]
>  你只能使用单一登录用基本和摘要式身份验证。  
  
 若要正确实现单一登录支持对 HTTP 接收和发送以下条件的适配器必须满足：  
  
-   必须在以下位置中指定相同的用户帐户：  
  
    -   应用程序池标识 (IIS 7.0) 或承载通过 HTTP 进行监视的 IIS 虚拟目录的 COM + 应用程序标识接收适配器。 接收位置的有关配置用于 HTTP 的 IIS 的详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
    -   用于 HTTP 适配器运行中的独立主机实例的登录凭据。 有关如何配置主机实例的登录凭据的信息，请参阅[如何修改主机实例属性](../core/how-to-modify-host-instance-properties.md)。  
  
-   HTTP 适配器将使用的独立主机必须配置为“受信任验证”。 有关如何将主机配置为受信任的身份验证的信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="negative-acknowledgment-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapter"></a>对于失败的传输生成的 HTTP 或 SOAP 适配器的否定确认 (NACK) 消息  
 当成功传输一条消息时，BizTalk Messaging Engine 发布到 MessageBox 关联的确认 (ACK) 消息，当启用了传递通知。 同样，当 BizTalk 消息引擎挂起消息或业务流程引擎挂起业务流程时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 也会向 MessageBox 发布一个关联的否定确认 (NACK) 消息。 NACK 消息包含上下文属性和消息正文部分组成的 SOAP 错误。 如果由于失败的传输从 HTTP 或 SOAP 适配器生成 NACK 消息，则 SOAP 错误将包含的标头元素和来自目标 Web 服务器的响应的正文元素。 下面是在生成针对失败的 HTTP 传输 NACK SOAP 错误的示例：  
  
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
>  Headers 元素和 Body 元素限制在 48 KB 之内。 Headers 元素将舍入为不超出该限制的最接近完整形式的标头值对。 Body 元素将被截至 48 KB。  
  
> [!NOTE]
>  如果没有匹配的订阅，则会放弃 NACK 和 ACK 消息。 NACK 和 ACK 消息不会挂起 BizTalk 消息传送引擎。  
  
 若要订阅 NACK 消息，可执行以下操作之一：  
  
-   创建带有相应消息上下文属性筛选器的发送端口。 请参阅**消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]有关系统消息上下文属性的列表包括那些与消息确认。  
  
-   从标记为业务流程端口发送**传递通知 = 传输**。 如果使用标记的业务流程端口**传递通知 = 传输**，业务流程将等待直至其收到 ACK 或已传输的消息 NACK。 如果生成了 NACK，则会将其路由到业务流程，然后业务流程将引发 DeliveryFailureException。 DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化而来的。 若要从返回到业务流程的 SOAP 错误中检索异常消息字符串，请将 DeliveryFailureException 转换为 SoapException，然后访问“SOAP 详细信息”部分中的 InnerXml。 下面的代码示例演示了如何执行此操作：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [HTTP 适配器](../core/http-adapter.md)  
**SSO COM 对象**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]