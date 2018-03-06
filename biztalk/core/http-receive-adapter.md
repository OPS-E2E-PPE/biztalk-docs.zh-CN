---
title: "HTTP 接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9008833c-5a02-4fb4-a43e-09ca28a21eff
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f2f309a129c66d11d019b28b8ffc2b51d68e93d
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="http-receive-adapter"></a><span data-ttu-id="fcc65-102">HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="fcc65-102">HTTP Receive Adapter</span></span>
<span data-ttu-id="fcc65-103">HTTP 接收适配器的接收位置是一个通过 BizTalk Server 管理控制台配置的独特 URL。</span><span class="sxs-lookup"><span data-stu-id="fcc65-103">The receive location for the HTTP receive adapter is a distinct URL configured through the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="fcc65-104">您可为客户端的异步提交或同步提交配置 HTTP 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="fcc65-104">You can configure the HTTP receive adapter for either asynchronous submission or synchronous submission from the client.</span></span> <span data-ttu-id="fcc65-105">异步提交为单向提交，而同步提交为双向（或称为请求响应）提交。</span><span class="sxs-lookup"><span data-stu-id="fcc65-105">Asynchronous submissions are one-way submissions and synchronous submissions are two way or request-response submissions.</span></span>  
  
 <span data-ttu-id="fcc65-106">您可使用 IIS 安全性对传入请求进行验证和授权。</span><span class="sxs-lookup"><span data-stu-id="fcc65-106">You use IIS security for authentication and authorization of incoming requests.</span></span>  
  
## <a name="http-get-and-http-post-requests"></a><span data-ttu-id="fcc65-107">HTTP GET 请求和 HTTP POST 请求</span><span class="sxs-lookup"><span data-stu-id="fcc65-107">HTTP GET and HTTP POST Requests</span></span>  
 <span data-ttu-id="fcc65-108">HTTP 接收适配器可通过两种不同的方式接收消息，即通过 HTTP POST 请求或 HTTP GET 请求。</span><span class="sxs-lookup"><span data-stu-id="fcc65-108">The HTTP receive adapter can receive messages in two different ways—by an HTTP POST request or an HTTP GET request.</span></span>  
  
 <span data-ttu-id="fcc65-109">当 HTTP 接收适配器通过 HTTP POST 请求获取信息时，将按顺序发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="fcc65-109">When an HTTP receive adapter gets messages on an HTTP POST request, the following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="fcc65-110">在 BizTalk Server 中配置的 URL 在该接收位置上接收一条新消息。</span><span class="sxs-lookup"><span data-stu-id="fcc65-110">The URL configured in BizTalk Server receives a new message on the receive location.</span></span>  
  
2.  <span data-ttu-id="fcc65-111">接收适配器创建一个 BizTalk 消息对象，以便将该消息提交到服务器。</span><span class="sxs-lookup"><span data-stu-id="fcc65-111">The receive adapter creates a BizTalk Message object so that the message can be submitted to the server.</span></span>  
  
3.  <span data-ttu-id="fcc65-112">接收适配器创建仅具有一个部分（正文部分）的 BizTalk 消息对象。</span><span class="sxs-lookup"><span data-stu-id="fcc65-112">The receive adapter creates the BizTalk Message object with only one part—the body part.</span></span>  
  
4.  <span data-ttu-id="fcc65-113">在读取该消息并将其成功提交到服务器之后，HTTP 接收适配器会将 HTTP 代码 202 发送回客户端，指示已接受该请求。</span><span class="sxs-lookup"><span data-stu-id="fcc65-113">After the message has been read and successfully submitted to the server, the HTTP receive adapter sends an HTTP code 202 back to the client indicating that the request was accepted.</span></span>  
  
     <span data-ttu-id="fcc65-114">另外，HTTP 接收适配器也可以通过 HTTP 响应发送消息相关标记。</span><span class="sxs-lookup"><span data-stu-id="fcc65-114">Optionally, the HTTP receive adapter can send a message correlation token on the HTTP response.</span></span> <span data-ttu-id="fcc65-115">此相关标记表示 BizTalk Server 中的消息。</span><span class="sxs-lookup"><span data-stu-id="fcc65-115">This correlation token represents the message within BizTalk Server.</span></span> <span data-ttu-id="fcc65-116">如果 HTTP 接收位置位于请求响应端口，则适配器将随响应消息一起返回成功代码 200。</span><span class="sxs-lookup"><span data-stu-id="fcc65-116">If the HTTP receive location is in a request-response port, the adapter returns success code 200 along with the response message.</span></span>  
  
 <span data-ttu-id="fcc65-117">当 HTTP 接收适配器处理来自 HTTP GET 请求的消息时，接收适配器将创建 BizTalk 消息对象，并将该 HTTP GET 请求的解码查询字符串放入 BizTalk 消息正文部分中。</span><span class="sxs-lookup"><span data-stu-id="fcc65-117">When an HTTP receive adapter processes messages from an HTTP GET request, the receive adapter creates a BizTalk Message object and puts the decoded query string of the HTTP GET request into the BizTalk message body part.</span></span> <span data-ttu-id="fcc65-118">HTTP 适配器使用以下算法来选择放入 BizTalk 消息正文部分中的查询字符串：</span><span class="sxs-lookup"><span data-stu-id="fcc65-118">The HTTP adapter selects the query string that is placed into the BizTalk message body part using the following algorithm:</span></span>  
  
-   <span data-ttu-id="fcc65-119">如果 HTTP 接收适配器接收到 HTTP GET 请求，该适配器会使用问号 (?) 作为分隔符，将传入 URI 字符串拆分为两部分。</span><span class="sxs-lookup"><span data-stu-id="fcc65-119">If the HTTP receive adapter receives an HTTP GET request, it splits the incoming URI string into two parts, using the question mark (?) symbol as a delimiter.</span></span>  
  
-   <span data-ttu-id="fcc65-120">URI 字符串，问号分隔符之前, 的部分的第一部分复制到 **InboundTransportLocation** 消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="fcc65-120">The first part of the URI string, the part before the question mark delimiter, is copied into the **InboundTransportLocation** property on the message context.</span></span> <span data-ttu-id="fcc65-121">**InboundTransportLocation** 属性唯一地标识 BizTalk Server 从中接收消息的位置。</span><span class="sxs-lookup"><span data-stu-id="fcc65-121">The **InboundTransportLocation** property uniquely identifies the location where BizTalk Server received the message.</span></span> <span data-ttu-id="fcc65-122">引擎使用此属性来确定应为该消息运行哪个接收位置。</span><span class="sxs-lookup"><span data-stu-id="fcc65-122">The engine uses this property to determine which receive location to run for the message.</span></span>  
  
-   <span data-ttu-id="fcc65-123">HTTP 适配器获取问号分隔符后面的其余 URI 字符串，然后将其解码并复制到 BizTalk 消息正文部分中。</span><span class="sxs-lookup"><span data-stu-id="fcc65-123">The HTTP adapter takes the rest of the URI string, the part after the question mark delimiter, and decodes and copies it into the BizTalk message body part.</span></span>  
  
-   <span data-ttu-id="fcc65-124">如果 HTTP 接收适配器接收到空 HTTP GET 或 HTTP POST 操作，将拒绝该操作。</span><span class="sxs-lookup"><span data-stu-id="fcc65-124">If an empty HTTP GET or HTTP POST operation is received by the HTTP receive adapter, it is rejected.</span></span>  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a><span data-ttu-id="fcc65-125">HTTP 接收适配器对 GET 请求的处理</span><span class="sxs-lookup"><span data-stu-id="fcc65-125">HTTP Receive Adapter Processing of a GET Request</span></span>  
 <span data-ttu-id="fcc65-126">以下示例说明了 HTTP 接收适配器如何处理通过 HTTP GET 请求接收的消息。</span><span class="sxs-lookup"><span data-stu-id="fcc65-126">The following are examples of how the HTTP receive adapter processes messages received by HTTP GET requests.</span></span> <span data-ttu-id="fcc65-127">这些示例假设 HTTP 接收适配器配置了以下两个接收位置：</span><span class="sxs-lookup"><span data-stu-id="fcc65-127">These examples assume that the HTTP receive adapter is configured with the following two receive locations:</span></span>  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  <span data-ttu-id="fcc65-128">假设收到客户端的以下 HTTP GET 请求：</span><span class="sxs-lookup"><span data-stu-id="fcc65-128">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     <span data-ttu-id="fcc65-129">HTTP 接收适配器将执行如下操作：</span><span class="sxs-lookup"><span data-stu-id="fcc65-129">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="fcc65-130">设置 **InboundTransportLocation** 等于 /vroot/BTSHTTPReceive.dll，且等于 LocationID BizTalk 消息对象正文部分的消息上下文属性 = 1。</span><span class="sxs-lookup"><span data-stu-id="fcc65-130">Set the **InboundTransportLocation** property on the message context equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1.</span></span>  
  
2.  <span data-ttu-id="fcc65-131">假设收到客户端的以下 HTTP GET 请求：</span><span class="sxs-lookup"><span data-stu-id="fcc65-131">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     <span data-ttu-id="fcc65-132">HTTP 接收适配器将执行如下操作：</span><span class="sxs-lookup"><span data-stu-id="fcc65-132">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="fcc65-133">设置 **InboundTransportLocation** 属性等于 /vroot/BTSHTTPReceive.dll 和 BizTalk 消息对象主体部件等于 LocationID = 1 MyParam = 我的值。</span><span class="sxs-lookup"><span data-stu-id="fcc65-133">Set the **InboundTransportLocation** property equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1&MyParam=My Value.</span></span>  
  
3.  <span data-ttu-id="fcc65-134">假设收到客户端的以下 HTTP GET 请求：</span><span class="sxs-lookup"><span data-stu-id="fcc65-134">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     <span data-ttu-id="fcc65-135">通过 HTTP 执行的操作接收适配器是 +，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="fcc65-135">The action taken by the HTTP receive adapter is+ as follows:</span></span>  
  
     <span data-ttu-id="fcc65-136">拒绝该请求，因为 HTTP GET 请求的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="fcc65-136">Reject the request due to incorrect formatting of the HTTP GET request.</span></span>  
  
## <a name="batching-support-for-the-http-receive-adapter"></a><span data-ttu-id="fcc65-137">HTTP 接收适配器的批处理支持</span><span class="sxs-lookup"><span data-stu-id="fcc65-137">Batching Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="fcc65-138">HTTP 接收适配器将消息分批提交给服务器。</span><span class="sxs-lookup"><span data-stu-id="fcc65-138">The HTTP receive adapter submits messages to the server in batches.</span></span> <span data-ttu-id="fcc65-139">用于向服务器提交消息的批的大小可在 HTTP 适配器接收处理程序中进行配置。</span><span class="sxs-lookup"><span data-stu-id="fcc65-139">The size of the batch used to submit messages to the server can be configured on the HTTP adapter receive handler.</span></span>  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a><span data-ttu-id="fcc65-140">HTTP 接收适配器对挂起失败请求的支持</span><span class="sxs-lookup"><span data-stu-id="fcc65-140">HTTP Receive Adapter Support for Suspending Failed Requests</span></span>  
 <span data-ttu-id="fcc65-141">BizTalk Server HTTP 接收适配器已配置设置，**挂起失败的请求**、 控制如果仍然失败，因为接收管道失败，映射失败，入站的处理，如何操作使用 HTTP 请求或路由失败。</span><span class="sxs-lookup"><span data-stu-id="fcc65-141">The BizTalk Server HTTP receive adapter has a configuration setting, **Suspend Failed Requests**, to control what happens with an HTTP request if it fails inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="fcc65-142">该设置有两个可能的值：</span><span class="sxs-lookup"><span data-stu-id="fcc65-142">The setting has two possible values:</span></span>  
  
-   <span data-ttu-id="fcc65-143">**如果为 false。**</span><span class="sxs-lookup"><span data-stu-id="fcc65-143">**False.**</span></span> <span data-ttu-id="fcc65-144">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="fcc65-144">This is the default setting.</span></span> <span data-ttu-id="fcc65-145">HTTP 接收适配器将放弃由于接收管道故障、映射故障或路由故障而导致入站处理失败的消息。</span><span class="sxs-lookup"><span data-stu-id="fcc65-145">The HTTP receive adapter discards messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="fcc65-146">另外，将向客户端发送错误状态代码 401 或 500。</span><span class="sxs-lookup"><span data-stu-id="fcc65-146">Additionally, an error status code 401 or 500 is sent to the client.</span></span> 
  
-   <span data-ttu-id="fcc65-147">**为 true。**</span><span class="sxs-lookup"><span data-stu-id="fcc65-147">**True.**</span></span> <span data-ttu-id="fcc65-148">HTTP 接收适配器将挂起由于接收管道故障、映射故障或路由故障而导致入站处理失败的消息。</span><span class="sxs-lookup"><span data-stu-id="fcc65-148">The HTTP receive adapter suspends messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="fcc65-149">对于单向接收端口 **已接受** 状态代码 202 发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="fcc65-149">For one-way receive ports an **Accepted** status code 202 is sent to the client.</span></span> <span data-ttu-id="fcc65-150">对于双向接收端口 **错误** 状态代码 500 发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="fcc65-150">For two-way receive ports an **Error** status code 500 is sent to the client.</span></span>  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a><span data-ttu-id="fcc65-151">HTTP 接收适配器的 Chunked 编码支持</span><span class="sxs-lookup"><span data-stu-id="fcc65-151">Chunked Encoding Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="fcc65-152">HTTP 接收适配器可接受带有使用 Chunked 编码的正文消息的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="fcc65-152">The HTTP receive adapter accepts HTTP requests with chunked encoded body messages.</span></span> <span data-ttu-id="fcc65-153">当正文大小超过 4 KB 时，接收适配器将使用 Chunked 编码来发送响应消息。</span><span class="sxs-lookup"><span data-stu-id="fcc65-153">The receive adapter uses chunked encoding to send response messages when the body size is larger than 4 KB.</span></span> <span data-ttu-id="fcc65-154">分块编码可关闭通过设置中所述的 DWORD 注册表项[HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md)</span><span class="sxs-lookup"><span data-stu-id="fcc65-154">Chunked encoding can be turned off by setting the DWORD registry entry described in [HTTP Adapter Configuration and Tuning Parameters](../core/http-adapter-configuration-and-tuning-parameters.md)</span></span>  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a><span data-ttu-id="fcc65-155">HTTP 接收适配器的客户端证书</span><span class="sxs-lookup"><span data-stu-id="fcc65-155">Client Certificates for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="fcc65-156">HTTP 接收位置使用具有客户端证书的安全连接时，HTTP 接收适配器会从 Microsoft Internet 信息服务 (IIS) 获取该客户端证书的指纹，然后将其添加到在该位置通过 HTTPS 接收的所有消息的消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="fcc65-156">Whenever a secure connection with a client certificate is used for the HTTP receive location, the HTTP receive adapter obtains the client certificate thumbprint from Microsoft Internet Information Services (IIS) and adds it to the message context of all messages that were received over HTTPS on that location.</span></span> <span data-ttu-id="fcc65-157">HTTP 接收适配器可设置以下系统属性：</span><span class="sxs-lookup"><span data-stu-id="fcc65-157">The HTTP receive adapter sets the following system properties:</span></span>  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a><span data-ttu-id="fcc65-158">HTTP 接收适配器返回的状态代码</span><span class="sxs-lookup"><span data-stu-id="fcc65-158">Status Codes Returned by the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="fcc65-159">下面列出了 HTTP 接收适配器返回的各种状态代码：</span><span class="sxs-lookup"><span data-stu-id="fcc65-159">The following list contains status codes returned by the HTTP receive adapter.</span></span>  
  
-   <span data-ttu-id="fcc65-160">**200 确定。**</span><span class="sxs-lookup"><span data-stu-id="fcc65-160">**200 OK.**</span></span> <span data-ttu-id="fcc65-161">适配器已成功处理请求消息并生成响应。</span><span class="sxs-lookup"><span data-stu-id="fcc65-161">The adapter successfully processed the request message and generated a response.</span></span> <span data-ttu-id="fcc65-162">适配器通过 HTTP 响应从 HTTP 请求响应端口返回此状态代码。</span><span class="sxs-lookup"><span data-stu-id="fcc65-162">The adapter returns this status code on the HTTP response from the HTTP request-response port.</span></span>  
  
-   <span data-ttu-id="fcc65-163">**接受 202 的消息。**</span><span class="sxs-lookup"><span data-stu-id="fcc65-163">**202 Message Accepted.**</span></span> <span data-ttu-id="fcc65-164">适配器已将消息成功提交到服务器中，或已挂起单向请求。</span><span class="sxs-lookup"><span data-stu-id="fcc65-164">The adapter successfully submitted the message into the server or a one-way request is suspended.</span></span> <span data-ttu-id="fcc65-165">适配器通过 HTTP 响应从单向 HTTP 接收端口返回此状态代码。</span><span class="sxs-lookup"><span data-stu-id="fcc65-165">The adapter returns this status code on the HTTP response from a one way HTTP receive port.</span></span>  
  
-   <span data-ttu-id="fcc65-166">**401 访问被拒绝。**</span><span class="sxs-lookup"><span data-stu-id="fcc65-166">**401 Access Denied.**</span></span> <span data-ttu-id="fcc65-167">HTTP 请求被要求验证的接收端口接收，但对该消息的安全检查失败。</span><span class="sxs-lookup"><span data-stu-id="fcc65-167">The HTTP request is received on an authentication-required receive port and the security check for that message failed.</span></span> <span data-ttu-id="fcc65-168">例如，参与方未解析或消息未解密。</span><span class="sxs-lookup"><span data-stu-id="fcc65-168">For example, the party was not resolved or the message was not decrypted.</span></span>  
  
-   <span data-ttu-id="fcc65-169">**500 内部服务器错误。**</span><span class="sxs-lookup"><span data-stu-id="fcc65-169">**500 Internal Server Error.**</span></span> <span data-ttu-id="fcc65-170">处理 HTTP 请求时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="fcc65-170">A general failure to process the HTTP request.</span></span> <span data-ttu-id="fcc65-171">消息未挂起 BizTalk server，除非配置设置 **挂起失败的请求** 设置为 **True** 对于双向收到端口。</span><span class="sxs-lookup"><span data-stu-id="fcc65-171">The message is not suspended by BizTalk Server unless the configuration setting **Suspend Failed Requests** is set to **True** for a two-way receive port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc65-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcc65-172">See Also</span></span>  
 [<span data-ttu-id="fcc65-173">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="fcc65-173">HTTP Adapter</span></span>](../core/http-adapter.md)