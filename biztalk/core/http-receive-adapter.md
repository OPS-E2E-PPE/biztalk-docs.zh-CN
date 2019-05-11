---
title: HTTP 接收适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9008833c-5a02-4fb4-a43e-09ca28a21eff
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea6731d6611d3cc2efbd374cd622b5fb239a3c9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332602"
---
# <a name="http-receive-adapter"></a><span data-ttu-id="7ed01-102">HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="7ed01-102">HTTP Receive Adapter</span></span>
<span data-ttu-id="7ed01-103">HTTP 接收适配器的接收位置是一个通过 BizTalk Server 管理控制台配置的独特 URL。</span><span class="sxs-lookup"><span data-stu-id="7ed01-103">The receive location for the HTTP receive adapter is a distinct URL configured through the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="7ed01-104">你可以配置 HTTP 接收适配器为异步提交或同步提交从客户端。</span><span class="sxs-lookup"><span data-stu-id="7ed01-104">You can configure the HTTP receive adapter for either asynchronous submission or synchronous submission from the client.</span></span> <span data-ttu-id="7ed01-105">异步提交为单向提交和同步提交为两个方法或请求-响应提交。</span><span class="sxs-lookup"><span data-stu-id="7ed01-105">Asynchronous submissions are one-way submissions and synchronous submissions are two way or request-response submissions.</span></span>  
  
 <span data-ttu-id="7ed01-106">IIS 安全用于身份验证和授权的传入请求。</span><span class="sxs-lookup"><span data-stu-id="7ed01-106">You use IIS security for authentication and authorization of incoming requests.</span></span>  
  
## <a name="http-get-and-http-post-requests"></a><span data-ttu-id="7ed01-107">HTTP GET 和 HTTP POST 请求</span><span class="sxs-lookup"><span data-stu-id="7ed01-107">HTTP GET and HTTP POST Requests</span></span>  
 <span data-ttu-id="7ed01-108">HTTP 接收适配器可以接收消息两个不同的方式 — 通过 HTTP POST 请求或 HTTP GET 请求。</span><span class="sxs-lookup"><span data-stu-id="7ed01-108">The HTTP receive adapter can receive messages in two different ways—by an HTTP POST request or an HTTP GET request.</span></span>  
  
 <span data-ttu-id="7ed01-109">当 HTTP 接收适配器获取消息上的 HTTP POST 请求时，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="7ed01-109">When an HTTP receive adapter gets messages on an HTTP POST request, the following sequence of events occurs:</span></span>  
  
1. <span data-ttu-id="7ed01-110">BizTalk Server 中配置的 URL 接收该接收位置中的新消息。</span><span class="sxs-lookup"><span data-stu-id="7ed01-110">The URL configured in BizTalk Server receives a new message on the receive location.</span></span>  
  
2. <span data-ttu-id="7ed01-111">接收适配器创建 BizTalk 消息对象，以便可以将消息提交到服务器。</span><span class="sxs-lookup"><span data-stu-id="7ed01-111">The receive adapter creates a BizTalk Message object so that the message can be submitted to the server.</span></span>  
  
3. <span data-ttu-id="7ed01-112">接收适配器仅具有一个部分中创建 BizTalk 消息对象，正文部分。</span><span class="sxs-lookup"><span data-stu-id="7ed01-112">The receive adapter creates the BizTalk Message object with only one part—the body part.</span></span>  
  
4. <span data-ttu-id="7ed01-113">读取消息并将其成功提交到服务器后，HTTP 接收适配器发送的 HTTP 代码 202 回客户端，该值指示已接受该请求。</span><span class="sxs-lookup"><span data-stu-id="7ed01-113">After the message has been read and successfully submitted to the server, the HTTP receive adapter sends an HTTP code 202 back to the client indicating that the request was accepted.</span></span>  
  
    <span data-ttu-id="7ed01-114">（可选） HTTP 接收适配器可在 HTTP 响应上发送消息相关标记。</span><span class="sxs-lookup"><span data-stu-id="7ed01-114">Optionally, the HTTP receive adapter can send a message correlation token on the HTTP response.</span></span> <span data-ttu-id="7ed01-115">此相关标记表示 BizTalk Server 中的消息。</span><span class="sxs-lookup"><span data-stu-id="7ed01-115">This correlation token represents the message within BizTalk Server.</span></span> <span data-ttu-id="7ed01-116">如果 HTTP 接收位置的请求-响应端口，该适配器返回成功代码 200，以及响应消息。</span><span class="sxs-lookup"><span data-stu-id="7ed01-116">If the HTTP receive location is in a request-response port, the adapter returns success code 200 along with the response message.</span></span>  
  
   <span data-ttu-id="7ed01-117">当 HTTP 接收适配器处理消息从 HTTP GET 请求时，接收适配器创建 BizTalk 消息对象，并将 HTTP GET 请求的解码的查询字符串放入 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="7ed01-117">When an HTTP receive adapter processes messages from an HTTP GET request, the receive adapter creates a BizTalk Message object and puts the decoded query string of the HTTP GET request into the BizTalk message body part.</span></span> <span data-ttu-id="7ed01-118">HTTP 适配器选择查询字符串放入 BizTalk 消息正文部分使用以下算法：</span><span class="sxs-lookup"><span data-stu-id="7ed01-118">The HTTP adapter selects the query string that is placed into the BizTalk message body part using the following algorithm:</span></span>  
  
-   <span data-ttu-id="7ed01-119">如果 HTTP 接收适配器收到的 HTTP GET 请求时，它将拆分传入 URI 字符串为两个部分，使用问号 （？） 符号作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="7ed01-119">If the HTTP receive adapter receives an HTTP GET request, it splits the incoming URI string into two parts, using the question mark (?) symbol as a delimiter.</span></span>  
  
-   <span data-ttu-id="7ed01-120">第一部分 URI 字符串，问号分隔符之前的部分复制到**InboundTransportLocation**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="7ed01-120">The first part of the URI string, the part before the question mark delimiter, is copied into the **InboundTransportLocation** property on the message context.</span></span> <span data-ttu-id="7ed01-121">**InboundTransportLocation**属性唯一地标识 BizTalk Server 接收消息的位置。</span><span class="sxs-lookup"><span data-stu-id="7ed01-121">The **InboundTransportLocation** property uniquely identifies the location where BizTalk Server received the message.</span></span> <span data-ttu-id="7ed01-122">引擎使用此属性来确定哪个接收位置运行的消息。</span><span class="sxs-lookup"><span data-stu-id="7ed01-122">The engine uses this property to determine which receive location to run for the message.</span></span>  
  
-   <span data-ttu-id="7ed01-123">HTTP 适配器采用 URI 字符串，问号分隔符之后的部分的其余部分和解码并将其复制到 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="7ed01-123">The HTTP adapter takes the rest of the URI string, the part after the question mark delimiter, and decodes and copies it into the BizTalk message body part.</span></span>  
  
-   <span data-ttu-id="7ed01-124">如果空的 HTTP GET 或 HTTP POST 操作接收 http 接收适配器，它将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="7ed01-124">If an empty HTTP GET or HTTP POST operation is received by the HTTP receive adapter, it is rejected.</span></span>  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a><span data-ttu-id="7ed01-125">HTTP 接收适配器对 GET 请求的处理</span><span class="sxs-lookup"><span data-stu-id="7ed01-125">HTTP Receive Adapter Processing of a GET Request</span></span>  
 <span data-ttu-id="7ed01-126">以下是举例说明了 HTTP 接收适配器接收到的 HTTP GET 请求的进程消息。</span><span class="sxs-lookup"><span data-stu-id="7ed01-126">The following are examples of how the HTTP receive adapter processes messages received by HTTP GET requests.</span></span> <span data-ttu-id="7ed01-127">这些示例假设 HTTP 接收适配器已配置以下两个接收位置：</span><span class="sxs-lookup"><span data-stu-id="7ed01-127">These examples assume that the HTTP receive adapter is configured with the following two receive locations:</span></span>  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  <span data-ttu-id="7ed01-128">为客户端提供以下 HTTP GET 请求：</span><span class="sxs-lookup"><span data-stu-id="7ed01-128">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     <span data-ttu-id="7ed01-129">通过 HTTP 执行的操作接收适配器是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ed01-129">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="7ed01-130">设置**InboundTransportLocation**等于 /vroot/BTSHTTPReceive.dll，且等于将 BizTalk 消息对象正文部分的消息上下文属性 = 1。</span><span class="sxs-lookup"><span data-stu-id="7ed01-130">Set the **InboundTransportLocation** property on the message context equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1.</span></span>  
  
2.  <span data-ttu-id="7ed01-131">为客户端提供以下 HTTP GET 请求：</span><span class="sxs-lookup"><span data-stu-id="7ed01-131">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     <span data-ttu-id="7ed01-132">通过 HTTP 执行的操作接收适配器是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ed01-132">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="7ed01-133">设置**InboundTransportLocation**属性等于 /vroot/BTSHTTPReceive.dll 和 BizTalk 消息对象正文部分等于 = 1 和 MyParam = Value。</span><span class="sxs-lookup"><span data-stu-id="7ed01-133">Set the **InboundTransportLocation** property equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1&MyParam=My Value.</span></span>  
  
3.  <span data-ttu-id="7ed01-134">为客户端提供以下 HTTP GET 请求：</span><span class="sxs-lookup"><span data-stu-id="7ed01-134">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     <span data-ttu-id="7ed01-135">通过 HTTP 执行的操作接收适配器是 +，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ed01-135">The action taken by the HTTP receive adapter is+ as follows:</span></span>  
  
     <span data-ttu-id="7ed01-136">拒绝请求，因为 HTTP GET 请求的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="7ed01-136">Reject the request due to incorrect formatting of the HTTP GET request.</span></span>  
  
## <a name="batching-support-for-the-http-receive-adapter"></a><span data-ttu-id="7ed01-137">HTTP 接收适配器的批处理支持</span><span class="sxs-lookup"><span data-stu-id="7ed01-137">Batching Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="7ed01-138">HTTP 接收适配器将消息提交到批处理中的服务器。</span><span class="sxs-lookup"><span data-stu-id="7ed01-138">The HTTP receive adapter submits messages to the server in batches.</span></span> <span data-ttu-id="7ed01-139">用于提交到服务器的消息可以在 HTTP 适配器上配置的批的大小接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="7ed01-139">The size of the batch used to submit messages to the server can be configured on the HTTP adapter receive handler.</span></span>  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a><span data-ttu-id="7ed01-140">HTTP 接收适配器支持对挂起失败的请求</span><span class="sxs-lookup"><span data-stu-id="7ed01-140">HTTP Receive Adapter Support for Suspending Failed Requests</span></span>  
 <span data-ttu-id="7ed01-141">BizTalk Server HTTP 接收适配器已配置设置，请**挂起失败的请求**，用于控制如果它由于接收管道故障、 映射故障的入站的处理失败的 HTTP 请求有什么影响或路由故障。</span><span class="sxs-lookup"><span data-stu-id="7ed01-141">The BizTalk Server HTTP receive adapter has a configuration setting, **Suspend Failed Requests**, to control what happens with an HTTP request if it fails inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="7ed01-142">设置具有两个可能值：</span><span class="sxs-lookup"><span data-stu-id="7ed01-142">The setting has two possible values:</span></span>  
  
-   <span data-ttu-id="7ed01-143">**如果为 false。**</span><span class="sxs-lookup"><span data-stu-id="7ed01-143">**False.**</span></span> <span data-ttu-id="7ed01-144">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="7ed01-144">This is the default setting.</span></span> <span data-ttu-id="7ed01-145">HTTP 接收适配器将放弃由于接收管道故障、 映射故障或路由故障的入站的处理失败的消息。</span><span class="sxs-lookup"><span data-stu-id="7ed01-145">The HTTP receive adapter discards messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="7ed01-146">此外，错误状态代码 401 或 500 是发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="7ed01-146">Additionally, an error status code 401 or 500 is sent to the client.</span></span> 
  
-   <span data-ttu-id="7ed01-147">**为 true。**</span><span class="sxs-lookup"><span data-stu-id="7ed01-147">**True.**</span></span> <span data-ttu-id="7ed01-148">HTTP 接收适配器将挂起由于接收管道故障、 映射故障或路由故障的入站的处理失败的消息。</span><span class="sxs-lookup"><span data-stu-id="7ed01-148">The HTTP receive adapter suspends messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="7ed01-149">对于单向接收端口**已接受**状态代码 202 发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="7ed01-149">For one-way receive ports an **Accepted** status code 202 is sent to the client.</span></span> <span data-ttu-id="7ed01-150">对于双向接收端口**错误**状态代码 500 发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="7ed01-150">For two-way receive ports an **Error** status code 500 is sent to the client.</span></span>  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a><span data-ttu-id="7ed01-151">Chunked 编码支持 http 接收适配器</span><span class="sxs-lookup"><span data-stu-id="7ed01-151">Chunked Encoding Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="7ed01-152">HTTP 接收适配器接受使用 chunked 编码的正文消息的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="7ed01-152">The HTTP receive adapter accepts HTTP requests with chunked encoded body messages.</span></span> <span data-ttu-id="7ed01-153">接收适配器使用 chunked 编码发送响应消息正文大小大于 4 KB。</span><span class="sxs-lookup"><span data-stu-id="7ed01-153">The receive adapter uses chunked encoding to send response messages when the body size is larger than 4 KB.</span></span> <span data-ttu-id="7ed01-154">Chunked 编码可关闭通过设置 DWORD 注册表项中所述[HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md)</span><span class="sxs-lookup"><span data-stu-id="7ed01-154">Chunked encoding can be turned off by setting the DWORD registry entry described in [HTTP Adapter Configuration and Tuning Parameters](../core/http-adapter-configuration-and-tuning-parameters.md)</span></span>  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a><span data-ttu-id="7ed01-155">客户端证书的 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="7ed01-155">Client Certificates for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="7ed01-156">无论何时与客户端证书的安全连接使用 HTTP 接收位置，HTTP 接收适配器获取客户端证书指纹从 Microsoft Internet 信息服务 (IIS)，并将其添加到消息上下文的所有消息通过在该位置上的 HTTPS 接收的。</span><span class="sxs-lookup"><span data-stu-id="7ed01-156">Whenever a secure connection with a client certificate is used for the HTTP receive location, the HTTP receive adapter obtains the client certificate thumbprint from Microsoft Internet Information Services (IIS) and adds it to the message context of all messages that were received over HTTPS on that location.</span></span> <span data-ttu-id="7ed01-157">HTTP 接收适配器可设置以下系统属性：</span><span class="sxs-lookup"><span data-stu-id="7ed01-157">The HTTP receive adapter sets the following system properties:</span></span>  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a><span data-ttu-id="7ed01-158">返回的 HTTP 状态代码接收适配器</span><span class="sxs-lookup"><span data-stu-id="7ed01-158">Status Codes Returned by the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="7ed01-159">以下列表包含状态代码返回的 HTTP 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="7ed01-159">The following list contains status codes returned by the HTTP receive adapter.</span></span>  
  
-   <span data-ttu-id="7ed01-160">**200 确定。**</span><span class="sxs-lookup"><span data-stu-id="7ed01-160">**200 OK.**</span></span> <span data-ttu-id="7ed01-161">适配器已成功处理请求消息并生成响应。</span><span class="sxs-lookup"><span data-stu-id="7ed01-161">The adapter successfully processed the request message and generated a response.</span></span> <span data-ttu-id="7ed01-162">适配器从 HTTP 请求-响应端口返回 HTTP 响应上的此状态代码。</span><span class="sxs-lookup"><span data-stu-id="7ed01-162">The adapter returns this status code on the HTTP response from the HTTP request-response port.</span></span>  
  
-   <span data-ttu-id="7ed01-163">**202 消息已接受。**</span><span class="sxs-lookup"><span data-stu-id="7ed01-163">**202 Message Accepted.**</span></span> <span data-ttu-id="7ed01-164">该适配器将消息成功提交到服务器或已挂起单向请求。</span><span class="sxs-lookup"><span data-stu-id="7ed01-164">The adapter successfully submitted the message into the server or a one-way request is suspended.</span></span> <span data-ttu-id="7ed01-165">适配器在 HTTP 响应从单向 HTTP 接收端口上返回此状态代码。</span><span class="sxs-lookup"><span data-stu-id="7ed01-165">The adapter returns this status code on the HTTP response from a one way HTTP receive port.</span></span>  
  
-   <span data-ttu-id="7ed01-166">**401 Access Denied.**</span><span class="sxs-lookup"><span data-stu-id="7ed01-166">**401 Access Denied.**</span></span> <span data-ttu-id="7ed01-167">上收到的 HTTP 请求要求身份验证的接收端口和失败，该消息的安全检查。</span><span class="sxs-lookup"><span data-stu-id="7ed01-167">The HTTP request is received on an authentication-required receive port and the security check for that message failed.</span></span> <span data-ttu-id="7ed01-168">例如，未解析的参与方或不解密消息。</span><span class="sxs-lookup"><span data-stu-id="7ed01-168">For example, the party was not resolved or the message was not decrypted.</span></span>  
  
-   <span data-ttu-id="7ed01-169">**500 内部服务器错误。**</span><span class="sxs-lookup"><span data-stu-id="7ed01-169">**500 Internal Server Error.**</span></span> <span data-ttu-id="7ed01-170">常规失败以处理 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="7ed01-170">A general failure to process the HTTP request.</span></span> <span data-ttu-id="7ed01-171">除非不通过 BizTalk Server 挂起该消息的配置设置**挂起失败的请求**设置为**True**双向接收端口。</span><span class="sxs-lookup"><span data-stu-id="7ed01-171">The message is not suspended by BizTalk Server unless the configuration setting **Suspend Failed Requests** is set to **True** for a two-way receive port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed01-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ed01-172">See Also</span></span>  
 [<span data-ttu-id="7ed01-173">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="7ed01-173">HTTP Adapter</span></span>](../core/http-adapter.md)