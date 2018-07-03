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
ms.openlocfilehash: f2ddd2a3fa4b8bb2f97e25809121fa11b1f473f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999638"
---
# <a name="http-send-adapter"></a><span data-ttu-id="64067-102">HTTP 发送适配器</span><span class="sxs-lookup"><span data-stu-id="64067-102">HTTP Send Adapter</span></span>
<span data-ttu-id="64067-103">HTTP 发送适配器用于从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 获取消息，并将其发送到 HTTP POST 请求的目标 URL。</span><span class="sxs-lookup"><span data-stu-id="64067-103">The HTTP send adapter gets messages from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and sends them to a destination URL on an HTTP POST request.</span></span> <span data-ttu-id="64067-104">HTTP 发送适配器获取消息内容从 BizTalk 消息对象正文部分。</span><span class="sxs-lookup"><span data-stu-id="64067-104">The HTTP send adapter gets the message content from the body part of the BizTalk Message object.</span></span> <span data-ttu-id="64067-105">HTTP 发送适配器将忽略 BizTalk 消息对象的所有其他部分。</span><span class="sxs-lookup"><span data-stu-id="64067-105">The HTTP send adapter ignores all other parts of the BizTalk Message object.</span></span>  
  
 <span data-ttu-id="64067-106">该适配器将消息发送到目标 URL 和 BizTalk 消息引擎接收 HTTP 成功状态代码后，HTTP 发送适配器从 MessageBox 数据库中删除该消息。</span><span class="sxs-lookup"><span data-stu-id="64067-106">After the adapter sends the message to a destination URL and the BizTalk Messaging Engine receives the HTTP success status code, the HTTP send adapter deletes the message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="64067-107">HTTP 消息的重定向支持，并且可以配置发送端口上。</span><span class="sxs-lookup"><span data-stu-id="64067-107">Redirection of HTTP messages is supported and can be configured on the send port.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="64067-108"> 用作 HTTP 发送适配器的宿主，将其视为本地 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="64067-108"> hosts the HTTP send adapter as a native BizTalk application.</span></span> <span data-ttu-id="64067-109">它支持单向发送的消息以及要求-响应传输。</span><span class="sxs-lookup"><span data-stu-id="64067-109">It supports one-way sending of messages as well a solicit-response transmission.</span></span> <span data-ttu-id="64067-110">HTTP 发送适配器的发送位置是一个通过发送端口配置的独特 URL。</span><span class="sxs-lookup"><span data-stu-id="64067-110">The send location for the HTTP send adapter is a distinct URL that you configure through the send port.</span></span> <span data-ttu-id="64067-111">此唯一 URL 可以包括查询字符串追加到基 URL。</span><span class="sxs-lookup"><span data-stu-id="64067-111">This unique URL can include query strings appended to the base URL.</span></span>  
  
## <a name="batching-support-for-the-http-send-adapter"></a><span data-ttu-id="64067-112">HTTP 发送适配器的批处理支持</span><span class="sxs-lookup"><span data-stu-id="64067-112">Batching Support for the HTTP Send Adapter</span></span>  
 <span data-ttu-id="64067-113">HTTP 发送适配器不支持批处理操作。</span><span class="sxs-lookup"><span data-stu-id="64067-113">The HTTP send adapter does not support batching operations.</span></span>  
  
## <a name="chunked-encoding-support-for-the-http-send-adapter"></a><span data-ttu-id="64067-114">HTTP 发送适配器的 chunked 编码支持</span><span class="sxs-lookup"><span data-stu-id="64067-114">Chunked Encoding Support for the HTTP Send Adapter</span></span>  
 <span data-ttu-id="64067-115">如果**启用 chunked 编码**已启用配置选项，则 HTTP 发送适配器将使用 chunked 编码，如果请求大小超过 8 KB 的请求消息发送。</span><span class="sxs-lookup"><span data-stu-id="64067-115">If the **Enable chunked encoding** configuration option is enabled, then the HTTP send adapter sends request messages using chunked encoding if the request size exceeds 8 KB.</span></span> <span data-ttu-id="64067-116">如果使用 HTTP 代理服务器，则 HTTP 发送适配器将不使用 chunked 编码，并始终将数据暂存在发送之前。</span><span class="sxs-lookup"><span data-stu-id="64067-116">If the HTTP proxy server is used, the HTTP send adapter does not use chunked encoding and always stages the data before sending.</span></span> <span data-ttu-id="64067-117">**启用 chunked 编码**默认情况下已启用配置选项。</span><span class="sxs-lookup"><span data-stu-id="64067-117">The **Enable chunked encoding** configuration option is enabled by default.</span></span>  
  
 <span data-ttu-id="64067-118">当发送适配器收到的响应消息时，它可以接受使用 chunked 编码的正文部分的响应消息。</span><span class="sxs-lookup"><span data-stu-id="64067-118">When the send adapter receives a response message, it can accept response messages with a chunked encoded body part.</span></span>  
  
## <a name="client-authentication-for-the-http-send-adapter"></a><span data-ttu-id="64067-119">HTTP 发送适配器的客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="64067-119">Client Authentication for the HTTP Send Adapter</span></span>  
 <span data-ttu-id="64067-120">HTTP 发送适配器使用进行身份验证目标服务器通过使用以下身份验证类型之一：</span><span class="sxs-lookup"><span data-stu-id="64067-120">The HTTP send adapter authenticates with the destination server by using one of the following authentication types:</span></span>  
  
- <span data-ttu-id="64067-121">**匿名。**</span><span class="sxs-lookup"><span data-stu-id="64067-121">**Anonymous.**</span></span> <span data-ttu-id="64067-122">连接到目标服务器时，HTTP 适配器不发送任何凭据。</span><span class="sxs-lookup"><span data-stu-id="64067-122">The HTTP adapter does not send any credentials when connecting to the destination server.</span></span> <span data-ttu-id="64067-123">如果目标服务器允许匿名身份验证使用目标服务器上配置的匿名帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="64067-123">If the destination server permits anonymous authentication then the credentials of the configured anonymous account on the destination server are used.</span></span>  
  
- <span data-ttu-id="64067-124">**基本。**</span><span class="sxs-lookup"><span data-stu-id="64067-124">**Basic.**</span></span> <span data-ttu-id="64067-125">HTTP 适配器通过 HTTP 连接以纯文本格式发送用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="64067-125">The HTTP adapter sends the user name and password over an HTTP connection in plain text.</span></span>  
  
- <span data-ttu-id="64067-126">**摘要。**</span><span class="sxs-lookup"><span data-stu-id="64067-126">**Digest.**</span></span> <span data-ttu-id="64067-127">HTTP 适配器通过 HTTP 连接以加密格式发送密码。</span><span class="sxs-lookup"><span data-stu-id="64067-127">The HTTP adapter sends passwords in an encrypted format over the HTTP connection.</span></span>  
  
- <span data-ttu-id="64067-128">**Kerberos。**</span><span class="sxs-lookup"><span data-stu-id="64067-128">**Kerberos.**</span></span> <span data-ttu-id="64067-129">用户名和密码都不会通过 HTTP 连接发送。</span><span class="sxs-lookup"><span data-stu-id="64067-129">Neither the user name nor the password is sent over an HTTP connection.</span></span> <span data-ttu-id="64067-130">HTTP 适配器将使用在其下 HTTP 适配器运行发送此身份验证类型的进程的凭据。</span><span class="sxs-lookup"><span data-stu-id="64067-130">The HTTP adapter uses the credentials of the process under which the HTTP send adapter runs for this authentication type.</span></span>  
  
  <span data-ttu-id="64067-131">此外，HTTP 发送适配器可以提供客户端到 Web 服务器的安全套接字层 (SSL) 证书如果服务器要求或接受它。</span><span class="sxs-lookup"><span data-stu-id="64067-131">Additionally, the HTTP send adapter can provide a client Secure Sockets Layer (SSL) certificate to the Web server if the server requires or accepts it.</span></span>  
  
## <a name="client-certificates-for-the-http-send-adapter"></a><span data-ttu-id="64067-132">HTTP 发送适配器的客户端证书</span><span class="sxs-lookup"><span data-stu-id="64067-132">Client Certificates for the HTTP Send Adapter</span></span>  
 <span data-ttu-id="64067-133">HTTP 发送适配器可以建立与接受或不需要客户端证书的服务器的安全连接。</span><span class="sxs-lookup"><span data-stu-id="64067-133">The HTTP send adapter can establish a secure connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="64067-134">如果指定客户端证书，则 HTTP 发送适配器将连接与服务器的要求或接受客户端证书时使用该证书。</span><span class="sxs-lookup"><span data-stu-id="64067-134">If a client certificate is specified, the HTTP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="64067-135">如果未指定客户端证书和目标服务器需要客户端证书，HTTP 发送适配器无法发送消息，并按照标准的重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="64067-135">If the client certificate is not specified and the destination server requires client certificates, the HTTP send adapter fails to send the message and follows the standard retry logic.</span></span>  
  
 <span data-ttu-id="64067-136">HTTP 发送适配器使用的客户端证书位于运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程的帐户的个人存储中。</span><span class="sxs-lookup"><span data-stu-id="64067-136">The HTTP send adapter uses the client certificate from the personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="64067-137">证书的指纹来指定。</span><span class="sxs-lookup"><span data-stu-id="64067-137">The certificate is specified by its thumbprint.</span></span> <span data-ttu-id="64067-138">如果 HTTP 发送适配器无法加载证书出于任何原因，已发送的消息被挂起。</span><span class="sxs-lookup"><span data-stu-id="64067-138">If the HTTP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  
  
## <a name="single-sign-on-support-for-the-http-adapter"></a><span data-ttu-id="64067-139">HTTP 适配器的单一登录支持</span><span class="sxs-lookup"><span data-stu-id="64067-139">Single Sign-On Support for the HTTP Adapter</span></span>  
 <span data-ttu-id="64067-140">用于 HTTP 接收位置或发送端口使用 BizTalk 管理控制台中，可以配置企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="64067-140">You can configure Enterprise Single Sign-On (SSO) for use with the HTTP receive location or send port by using BizTalk Administration console.</span></span> <span data-ttu-id="64067-141">本主题介绍使用 HTTP 适配器的 SSO 工作原理。</span><span class="sxs-lookup"><span data-stu-id="64067-141">This topic describes how SSO works with the HTTP adapter.</span></span>  
  
 <span data-ttu-id="64067-142">**接收位置用于 HTTP 的单一登录支持**</span><span class="sxs-lookup"><span data-stu-id="64067-142">**Single Sign-On Support for the HTTP Receive Location**</span></span>  
  
 <span data-ttu-id="64067-143">当由 Microsoft Internet 信息服务 (IIS) 从 Web 客户端收到的 HTTP 请求时，IIS 进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="64067-143">When an HTTP request is received by Microsoft Internet Information Services (IIS) from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="64067-144">Internet 服务器应用程序编程接口 (ISAPI) 扩展将模拟的 Microsoft Windows 用户，然后调用 SSO 凭据存储区获取加密的票证。</span><span class="sxs-lookup"><span data-stu-id="64067-144">The Internet Server Application Programming Interface (ISAPI) extension impersonates the Microsoft Windows user and then calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="64067-145">此票证将被视为**SSOTicket**中消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="64067-145">This ticket is stored as the **SSOTicket** property in the context of the message.</span></span>  
  
 <span data-ttu-id="64067-146">在直通方案中，BizTalk 消息引擎将把消息引入 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="64067-146">In the pass-through scenario, the BizTalk Messaging Engine directs the message to the MessageBox database.</span></span> <span data-ttu-id="64067-147">当适配器从 MessageBox 数据库接收消息时，HTTP 适配器调用**ISSOTicket.RedeemTicket 方法**使用加密票证和要检索从后端凭据的应用程序名称SSO 存储区。</span><span class="sxs-lookup"><span data-stu-id="64067-147">When the adapter receives the message from the MessageBox database, the HTTP adapter calls the **ISSOTicket.RedeemTicket Method** with the encrypted ticket along with the application name to retrieve the back-end credentials from the SSO store.</span></span> <span data-ttu-id="64067-148">HTTP 适配器使用的外部凭据连接到后端系统并处理该请求。</span><span class="sxs-lookup"><span data-stu-id="64067-148">The HTTP adapter then uses the external credentials to connect to the back-end system and process the request.</span></span> <span data-ttu-id="64067-149">有关关联应用程序的详细信息，请参阅[SSO 关联应用程序](../core/sso-affiliate-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="64067-149">For more information about the affiliate applications, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="64067-150">在方案中在业务流程调用该适配器，BizTalk 消息引擎将此消息发送到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="64067-150">In the scenario where an orchestration invokes the adapter, the BizTalk Messaging Engine sends this message to the MessageBox database.</span></span> <span data-ttu-id="64067-151">业务流程应确保同时**SSOTicket**上下文属性和**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**是包含该票证在消息上下文属性维护。</span><span class="sxs-lookup"><span data-stu-id="64067-151">The orchestration should ensure that both the **SSOTicket** context property and the **Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID** context property of the message that contains the ticket are maintained.</span></span> <span data-ttu-id="64067-152">当适配器从 MessageBox 数据库接收此消息时，适配器调用**RedeemTicket**使用加密票证以从 SSO 存储中检索后端凭据。</span><span class="sxs-lookup"><span data-stu-id="64067-152">When the adapter receives this message from the MessageBox database, the adapter calls **RedeemTicket** with the encrypted ticket to retrieve the back-end credentials from the SSO store.</span></span> <span data-ttu-id="64067-153">具体而言，设计计划的用户应将此属性复制到消息。</span><span class="sxs-lookup"><span data-stu-id="64067-153">The user designing the schedule should specifically copy this property to the message.</span></span>  
  
 <span data-ttu-id="64067-154">**HTTP 发送适配器的单一登录支持**</span><span class="sxs-lookup"><span data-stu-id="64067-154">**Single Sign-On Support for the HTTP Send Adapters**</span></span>  
  
 <span data-ttu-id="64067-155">如果启用 SSO，则当 HTTP 发送端口收到的消息**Secure**属性，它将调用 SSO 服务器以验证并兑换票证关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="64067-155">If SSO is enabled, when an HTTP send port receives a message with the **Secure** property, it calls the SSO server to validate and redeem the ticket for an affiliate application.</span></span> <span data-ttu-id="64067-156">关联应用程序的管理应用程序、关联管理员或 SSO 管理员可调用 SSO 以兑换票证。</span><span class="sxs-lookup"><span data-stu-id="64067-156">The administration application, affiliate administrators, or SSO administrators for the affiliate application can call SSO to redeem a ticket.</span></span> <span data-ttu-id="64067-157">然后，SSO 将对票证进行解密，并获取后端凭据。</span><span class="sxs-lookup"><span data-stu-id="64067-157">SSO then decrypts the ticket and obtains the back-end credentials.</span></span> <span data-ttu-id="64067-158">直通和业务流程方案是与 HTTP 发送端口相同。</span><span class="sxs-lookup"><span data-stu-id="64067-158">The pass-through and orchestration scenario are the same as for the HTTP send port.</span></span>  
  
 <span data-ttu-id="64067-159">默认情况下，为 HTTP 发送端口已禁用 SSO。</span><span class="sxs-lookup"><span data-stu-id="64067-159">By default, SSO is disabled for the HTTP send port.</span></span> <span data-ttu-id="64067-160">有关为 HTTP 发送端口启用 SSO 的详细信息，请参阅[配置 HTTP 发送端口](../core/configuring-an-http-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="64067-160">For more information about enabling SSO for the HTTP send port, see [Configuring an HTTP Send Port](../core/configuring-an-http-send-port.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64067-161">仅可以使用单一登录使用基本和摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="64067-161">You can only use Single Sign-On with basic and digest authentication.</span></span>  
  
 <span data-ttu-id="64067-162">若要正确实现单一登录支持 HTTP 接收和发送适配器的以下条件必须满足：</span><span class="sxs-lookup"><span data-stu-id="64067-162">To correctly implement Single Sign On support for the HTTP receive and send adapter the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="64067-163">必须在以下位置中指定相同的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="64067-163">The same user account must be specified in the following places:</span></span>  
  
    -   <span data-ttu-id="64067-164">应用程序池标识 (IIS 7.0) 或宿主 COM + 应用程序标识为通过 HTTP 进行监视的 IIS 虚拟目录接收适配器。</span><span class="sxs-lookup"><span data-stu-id="64067-164">The application pool identity (IIS 7.0) or hosting COM+ application identity for the IIS virtual directory that is monitored by the HTTP receive adapter.</span></span> <span data-ttu-id="64067-165">有关配置 IIS 以实现 HTTP 接收位置，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="64067-165">For more information about configuring IIS for HTTP receive locations, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
    -   <span data-ttu-id="64067-166">用于 HTTP 适配器运行在独立主机实例的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="64067-166">The logon credentials used for the isolated host instance that the HTTP adapter is running in.</span></span> <span data-ttu-id="64067-167">有关如何配置主机实例的登录凭据的信息，请参阅[如何修改主机实例属性](../core/how-to-modify-host-instance-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="64067-167">For information about how to configure the logon credentials for a host instance, see [How to Modify Host Instance Properties](../core/how-to-modify-host-instance-properties.md).</span></span>  
  
-   <span data-ttu-id="64067-168">HTTP 适配器将使用的独立主机必须配置为“受信任验证”。</span><span class="sxs-lookup"><span data-stu-id="64067-168">The isolated host that the HTTP adapter is using must be configured as Authentication Trusted.</span></span> <span data-ttu-id="64067-169">有关如何将主机配置为受信任验证的信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="64067-169">For information about how to configure a host as Authentication Trusted, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="negative-acknowledgment-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapter"></a><span data-ttu-id="64067-170">对于失败的传输生成的 HTTP 或 SOAP 适配器的否定确认 (NACK) 消息</span><span class="sxs-lookup"><span data-stu-id="64067-170">Negative Acknowledgment (NACK) Messages Generated for Failed Transmissions by the HTTP or SOAP Adapter</span></span>  
 <span data-ttu-id="64067-171">当已成功传输一条消息时，BizTalk 消息引擎发布到 MessageBox 相关联的确认 (ACK) 消息，如果启用了送达通知。</span><span class="sxs-lookup"><span data-stu-id="64067-171">When a message is successfully transmitted, the BizTalk Messaging Engine publishes an associated acknowledgment (ACK) message to the MessageBox if delivery notifications are enabled.</span></span> <span data-ttu-id="64067-172">同样，当 BizTalk 消息引擎挂起消息或业务流程引擎挂起业务流程时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 也会向 MessageBox 发布一个关联的否定确认 (NACK) 消息。</span><span class="sxs-lookup"><span data-stu-id="64067-172">Likewise, when a message is suspended by the BizTalk Messaging Engine or an orchestration is suspended by the orchestration engine, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publishes an associated negative acknowledgment (NACK) message to the MessageBox.</span></span> <span data-ttu-id="64067-173">NACK 消息包含上下文属性和消息正文部分组成的 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="64067-173">The NACK message contains context properties and a message body part that consists of a SOAP fault.</span></span> <span data-ttu-id="64067-174">如果因 HTTP 或 SOAP 适配器的传输失败而生成的 NACK 消息，则 SOAP 错误将包含标头元素和来自目标 Web 服务器的响应的正文元素。</span><span class="sxs-lookup"><span data-stu-id="64067-174">If the NACK message is generated due to a failed transmission from the HTTP or SOAP adapter, the SOAP fault contains the Headers element and the Body element of the response from the destination Web server.</span></span> <span data-ttu-id="64067-175">以下是 SOAP 错误而失败的 HTTP 传输生成的 NACK 中的示例：</span><span class="sxs-lookup"><span data-stu-id="64067-175">The following is an example of the SOAP fault in a NACK generated for a failed HTTP transmission:</span></span>  
  
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
>  <span data-ttu-id="64067-176">Headers 元素和 Body 元素限制在 48 KB 之内。</span><span class="sxs-lookup"><span data-stu-id="64067-176">The Headers element and the Body element are limited to 48 KB.</span></span> <span data-ttu-id="64067-177">Headers 元素将舍入为不超出该限制的最接近完整形式的标头值对。</span><span class="sxs-lookup"><span data-stu-id="64067-177">The Headers element is rounded to the nearest complete header value pair without exceeding the limit.</span></span> <span data-ttu-id="64067-178">Body 元素将被截至 48 KB。</span><span class="sxs-lookup"><span data-stu-id="64067-178">The Body element is truncated to 48 KB.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64067-179">如果没有匹配的订阅，则会放弃 NACK 和 ACK 消息。</span><span class="sxs-lookup"><span data-stu-id="64067-179">NACK and ACK messages are discarded if there are no matching subscriptions for them.</span></span> <span data-ttu-id="64067-180">BizTalk 消息引擎不会挂起 NACK 和 ACK 消息。</span><span class="sxs-lookup"><span data-stu-id="64067-180">NACK and ACK messages are not suspended by the BizTalk Messaging Engine.</span></span>  
  
 <span data-ttu-id="64067-181">若要订阅 NACK 消息，可执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="64067-181">To subscribe to a NACK message, you can do one of the following:</span></span>  
  
- <span data-ttu-id="64067-182">创建带有相应消息上下文属性筛选器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="64067-182">Create a send port with a filter for the appropriate message context property.</span></span> <span data-ttu-id="64067-183">请参阅**消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]有关系统消息上下文属性的列表，包括那些与消息确认相关。</span><span class="sxs-lookup"><span data-stu-id="64067-183">See **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for a listing of system message context properties including those related to message acknowledgment.</span></span>  
  
- <span data-ttu-id="64067-184">从标记为业务流程端口发送**送达通知 = 传输**。</span><span class="sxs-lookup"><span data-stu-id="64067-184">Send from an orchestration port marked with **Delivery Notification = Transmitted**.</span></span> <span data-ttu-id="64067-185">如果业务流程端口标有**送达通知 = 传输**，业务流程将等待，直到收到 ACK 或 NACK 消息与已传输。</span><span class="sxs-lookup"><span data-stu-id="64067-185">If an orchestration port is marked with **Delivery Notification = Transmitted**, the orchestration will wait until it receives either an ACK or a NACK for the message that was transmitted.</span></span> <span data-ttu-id="64067-186">如果生成了 NACK，则会将其路由到业务流程，然后业务流程将引发 DeliveryFailureException。</span><span class="sxs-lookup"><span data-stu-id="64067-186">If a NACK is generated then it will be routed to the orchestration and the orchestration will throw a DeliveryFailureException.</span></span> <span data-ttu-id="64067-187">DeliveryFailureException 是从 NACK 消息正文中包含的 SOAP 错误反序列化而来的。</span><span class="sxs-lookup"><span data-stu-id="64067-187">The DeliveryFailureException is deserialized from the SOAP fault that is contained within the NACK message body.</span></span> <span data-ttu-id="64067-188">若要从返回到业务流程的 SOAP 错误中检索异常消息字符串，请将 DeliveryFailureException 转换为 SoapException，然后访问“SOAP 详细信息”部分中的 InnerXml。</span><span class="sxs-lookup"><span data-stu-id="64067-188">To retrieve the exception message string from the SOAP fault that is returned to the orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml from the SOAP Detail section.</span></span> <span data-ttu-id="64067-189">下面的代码示例演示了如何执行此操作：</span><span class="sxs-lookup"><span data-stu-id="64067-189">The following code sample demonstrates how to do this:</span></span>  
  
  ```  
  // Cast the DeliveryFailureException to a SoapException…  
  System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
  System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
  //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
  //object type created in an Exception handler  
  
  ```  
  
   <span data-ttu-id="64067-190">上面的代码示例返回的 XML 片断类似于以下形式：</span><span class="sxs-lookup"><span data-stu-id="64067-190">The code sample above will return an XML fragment similar to the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64067-191">请参阅</span><span class="sxs-lookup"><span data-stu-id="64067-191">See Also</span></span>  
 [<span data-ttu-id="64067-192">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="64067-192">HTTP Adapter</span></span>](../core/http-adapter.md)  
<span data-ttu-id="64067-193">**SSO COM 对象** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="64067-193">**SSO COM objects** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>