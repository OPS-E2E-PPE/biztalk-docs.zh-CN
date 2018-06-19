---
title: SOAP 发送适配器 |Microsoft 文档
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
ms.openlocfilehash: f59babb164458f7a5d072809d038fb253482553d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278853"
---
# <a name="soap-send-adapter"></a><span data-ttu-id="ddb36-102">SOAP 发送适配器</span><span class="sxs-lookup"><span data-stu-id="ddb36-102">SOAP Send Adapter</span></span>
<span data-ttu-id="ddb36-103">使用 SOAP 发送适配器可调用 Web Services。</span><span class="sxs-lookup"><span data-stu-id="ddb36-103">You use the SOAP send adapter to call a Web service.</span></span> <span data-ttu-id="ddb36-104">SOAP 发送适配器读取 BizTalk 消息对象上的消息上下文以获取代理名，并调用关联的外部 Web Services 代理。</span><span class="sxs-lookup"><span data-stu-id="ddb36-104">The SOAP send adapter reads the message context on the BizTalk Message object to get the proxy name and calls the associated external Web service proxy.</span></span>  
  
## <a name="client-authentication-for-the-soap-send-adapter"></a><span data-ttu-id="ddb36-105">SOAP 发送适配器的客户端验证</span><span class="sxs-lookup"><span data-stu-id="ddb36-105">Client Authentication for the SOAP Send Adapter</span></span>  
 <span data-ttu-id="ddb36-106">SOAP 发送适配器使用以下验证类型之一对目标服务器进行验证：</span><span class="sxs-lookup"><span data-stu-id="ddb36-106">The SOAP send adapter authenticates with the destination server by using one of the following authentication types:</span></span>  
  
-   <span data-ttu-id="ddb36-107">**匿名。**</span><span class="sxs-lookup"><span data-stu-id="ddb36-107">**Anonymous.**</span></span> <span data-ttu-id="ddb36-108">默认设置。</span><span class="sxs-lookup"><span data-stu-id="ddb36-108">The default setting.</span></span>  
  
-   <span data-ttu-id="ddb36-109">**基本。**</span><span class="sxs-lookup"><span data-stu-id="ddb36-109">**Basic.**</span></span> <span data-ttu-id="ddb36-110">SOAP 连接以纯文本格式发送用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="ddb36-110">The SOAP connection sends the user name and password in plain text.</span></span>  
  
-   <span data-ttu-id="ddb36-111">**Digest。**</span><span class="sxs-lookup"><span data-stu-id="ddb36-111">**Digest.**</span></span> <span data-ttu-id="ddb36-112">SOAP 连接以加密格式发送用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="ddb36-112">The SOAP connection sends the user name and password in an encrypted format.</span></span>  
  
-   <span data-ttu-id="ddb36-113">**Kerberos 或 NTLM。**</span><span class="sxs-lookup"><span data-stu-id="ddb36-113">**Kerberos or NTLM.**</span></span> <span data-ttu-id="ddb36-114">用户名和密码都不通过 SOAP 连接发送。</span><span class="sxs-lookup"><span data-stu-id="ddb36-114">Neither the user name nor the password is sent over a SOAP connection.</span></span> <span data-ttu-id="ddb36-115">SOAP 适配器始终为此验证类型使用运行 SOAP 发送适配器的进程的凭据。</span><span class="sxs-lookup"><span data-stu-id="ddb36-115">The SOAP adapter always uses the credentials of the process under which the SOAP send adapter runs for this authentication type.</span></span>  
  
 <span data-ttu-id="ddb36-116">另外，如果 Web 服务器要求或接受客户端安全套接字层 (SSL) 证书，SOAP 发送适配器还可为其提供该证书。</span><span class="sxs-lookup"><span data-stu-id="ddb36-116">Additionally, the SOAP send adapter can provide a client Secure Sockets Layer (SSL) certificate to the Web server if the server requires or accepts it.</span></span>  
  
 <span data-ttu-id="ddb36-117">如果你启用企业单一登录 (SSO)，当收到与请求消息时 SOAP 发送适配器**SSOTicket**属性，该适配器已连接到 SSO 服务器验证和兑换票证。</span><span class="sxs-lookup"><span data-stu-id="ddb36-117">If you enabled Enterprise Single Sign-On (SSO), when the SOAP send adapter receives a message with the request to the **SSOTicket** property, the adapter connects to an SSO server to validate and redeem the ticket.</span></span> <span data-ttu-id="ddb36-118">在 SOAP 适配器验证票证后，将对其进行解密，并从凭据存储中检索关联系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="ddb36-118">After the SOAP adapter validates the ticket, it is decrypted and the credentials for the affiliate system are retrieved from the credential store.</span></span> <span data-ttu-id="ddb36-119">然后，SOAP 适配器将使用这些凭据连接到关联系统，并处理 SOAP 请求。</span><span class="sxs-lookup"><span data-stu-id="ddb36-119">The SOAP adapter then uses the credentials to connect to the affiliate system, and the SOAP request is processed.</span></span>  
  
## <a name="client-certificates-for-the-soap-send-adapter"></a><span data-ttu-id="ddb36-120">SOAP 发送适配器的客户端证书</span><span class="sxs-lookup"><span data-stu-id="ddb36-120">Client Certificates for the SOAP Send Adapter</span></span>  
 <span data-ttu-id="ddb36-121">SOAP 发送适配器可与接受或要求使用客户端证书的服务器建立安全连接。</span><span class="sxs-lookup"><span data-stu-id="ddb36-121">The SOAP send adapter can establish a secure connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="ddb36-122">如果指定了客户端证书，则在连接要求或接受客户端证书的服务器时，SOAP 发送适配器将使用该证书。</span><span class="sxs-lookup"><span data-stu-id="ddb36-122">If you specify a client certificate, the SOAP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="ddb36-123">如果未指定客户端证书，并且目标服务器要求客户端证书，则 SOAP 发送适配器将无法发送消息，并会遵循标准的重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="ddb36-123">If you do not specify a client certificate and the destination server requires client certificates, the SOAP send adapter fails to send the message and follows the standard retry logic.</span></span>  
  
 <span data-ttu-id="ddb36-124">SOAP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。</span><span class="sxs-lookup"><span data-stu-id="ddb36-124">The SOAP send adapter uses the client certificate from the Personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="ddb36-125">SOAP 适配器根据证书的指纹来指定证书。</span><span class="sxs-lookup"><span data-stu-id="ddb36-125">The SOAP adapter specifies the certificate by its thumbprint.</span></span> <span data-ttu-id="ddb36-126">如果 SOAP 发送适配器由于某种原因无法加载证书，则会挂起该适配器正在发送的消息。</span><span class="sxs-lookup"><span data-stu-id="ddb36-126">If the SOAP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  
  
## <a name="negative-acknowledgement-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapters"></a><span data-ttu-id="ddb36-127">HTTP 或 SOAP 适配器对于失败的传输将生成否定确认 (NACK) 消息</span><span class="sxs-lookup"><span data-stu-id="ddb36-127">Negative Acknowledgement (NACK) Messages Generated for Failed Transmissions by the HTTP or SOAP Adapters</span></span>  
 <span data-ttu-id="ddb36-128">如果启用了送达通知，则在消息传输成功时，BizTalk 消息引擎将向 MessageBox 数据库发布一个关联的确认 (ACK) 消息。</span><span class="sxs-lookup"><span data-stu-id="ddb36-128">When a message is successfully transmitted, the BizTalk Messaging Engine publishes an associated Acknowledgement (ACK) message to the MessageBox database if delivery notifications are enabled.</span></span> <span data-ttu-id="ddb36-129">同样，当由 BizTalk 消息传送引擎挂起消息或业务流程挂起业务流程引擎[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将关联的否定确认 (NACK) 消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="ddb36-129">Likewise, when a message is suspended by the BizTalk Messaging Engine or an orchestration is suspended by the orchestration engine, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publishes an associated Negative Acknowledgement (NACK) message to the MessageBox.</span></span> <span data-ttu-id="ddb36-130">NACK 消息包含上下文属性以及一个由 SOAP 错误构成的消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="ddb36-130">The NACK message contains context properties and a message body part consisting of a SOAP fault.</span></span> <span data-ttu-id="ddb36-131">如果由于失败的传输从 HTTP 或 SOAP 适配器生成 NACK 消息，则包含 SOAP 错误**标头**元素和**正文**目标 Web 响应的元素服务器。</span><span class="sxs-lookup"><span data-stu-id="ddb36-131">If the NACK message is generated due to a failed transmission from the HTTP or SOAP adapters, the SOAP fault contains the **Headers** element and the **Body** element of the response from the destination Web server.</span></span> <span data-ttu-id="ddb36-132">下面列出了一个由于 SOAP 传输失败而生成的 NACK 中的 SOAP 错误示例：</span><span class="sxs-lookup"><span data-stu-id="ddb36-132">The following is an example of the SOAP fault in a NACK generated for a failed SOAP transmission:</span></span>  
  
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
>  <span data-ttu-id="ddb36-133">**标头**元素和**正文**元素仅限于 48 KB。</span><span class="sxs-lookup"><span data-stu-id="ddb36-133">The **Headers** element and the **Body** element are limited to 48 KB.</span></span> <span data-ttu-id="ddb36-134">**标头**元素舍入为最近的完整的标头值对不超出限制的情况下。</span><span class="sxs-lookup"><span data-stu-id="ddb36-134">The **Headers** element is rounded to the nearest complete header value pair without exceeding the limit.</span></span> <span data-ttu-id="ddb36-135">**正文**元素截断为 48 KB。</span><span class="sxs-lookup"><span data-stu-id="ddb36-135">The **Body** element is truncated to 48 KB.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddb36-136">如果没有匹配的订阅，则会放弃 NACK 和 ACK 消息。</span><span class="sxs-lookup"><span data-stu-id="ddb36-136">NACK and ACK messages are discarded if there are no matching subscriptions for them.</span></span> <span data-ttu-id="ddb36-137">消息引擎不会挂起 NACK 和 ACK 消息。</span><span class="sxs-lookup"><span data-stu-id="ddb36-137">NACK and ACK messages are not suspended by the Messaging Engine.</span></span>  
  
 <span data-ttu-id="ddb36-138">若要订阅 NACK 消息，可执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ddb36-138">To subscribe to a NACK message, you can do one of the following:</span></span>  
  
1.  <span data-ttu-id="ddb36-139">创建带有相应消息上下文属性筛选器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="ddb36-139">Create a send port with a filter for the appropriate message context property.</span></span> <span data-ttu-id="ddb36-140">请参阅**消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]有关系统消息上下文属性的列表包括那些与消息确认。</span><span class="sxs-lookup"><span data-stu-id="ddb36-140">See **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for a listing of system message context properties including those related to message acknowledgment.</span></span>  
  
2.  <span data-ttu-id="ddb36-141">从标记为业务流程端口发送**传递通知 = 传输**。</span><span class="sxs-lookup"><span data-stu-id="ddb36-141">Send from an orchestration port marked with **Delivery Notification = Transmitted**.</span></span> <span data-ttu-id="ddb36-142">如果使用标记的业务流程端口**传递通知 = 传输**，业务流程将等待直至其收到 ACK 或已传输的消息 NACK。</span><span class="sxs-lookup"><span data-stu-id="ddb36-142">If an orchestration port is marked with **Delivery Notification = Transmitted**, the orchestration will wait until it receives either an ACK or a NACK for the message that was transmitted.</span></span> <span data-ttu-id="ddb36-143">如果生成了 NACK，则会将其路由到业务流程，然后业务流程将引发 DeliveryFailureException。</span><span class="sxs-lookup"><span data-stu-id="ddb36-143">If a NACK is generated then it will be routed to the orchestration and the orchestration will throw a DeliveryFailureException.</span></span> <span data-ttu-id="ddb36-144">DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化而来的。</span><span class="sxs-lookup"><span data-stu-id="ddb36-144">The DeliveryFailureException is deserialized from the SOAP fault that is contained within the NACK message body.</span></span> <span data-ttu-id="ddb36-145">若要从返回到业务流程的 SOAP 错误中检索异常消息字符串，请将 DeliveryFailureException 转换为 SoapException，然后访问“SOAP 详细信息”部分中的 InnerXml。</span><span class="sxs-lookup"><span data-stu-id="ddb36-145">To retrieve the exception message string from the SOAP fault that is returned to the orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml from the SOAP Detail section.</span></span> <span data-ttu-id="ddb36-146">下面的代码示例演示了如何执行此操作：</span><span class="sxs-lookup"><span data-stu-id="ddb36-146">The following code sample demonstrates how to do this:</span></span>  
  
    ```  
    // Cast the DeliveryFailureException to a SoapException…  
    System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
    System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
    //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
    //object type created in an Exception handler  
    ```  
  
     <span data-ttu-id="ddb36-147">上面的代码示例返回的 XML 片断类似于以下形式：</span><span class="sxs-lookup"><span data-stu-id="ddb36-147">The code sample above will return an XML fragment similar to the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ddb36-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddb36-148">See Also</span></span>  
 <span data-ttu-id="ddb36-149">[什么是 SOAP 适配器？](../core/what-is-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ddb36-149">[What Is the SOAP Adapter?](../core/what-is-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="ddb36-150">SOAP 适配器安全建议</span><span class="sxs-lookup"><span data-stu-id="ddb36-150">SOAP Adapter Security Recommendations</span></span>](../core/soap-adapter-security-recommendations.md)