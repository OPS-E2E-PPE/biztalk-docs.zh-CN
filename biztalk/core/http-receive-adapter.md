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
ms.openlocfilehash: d2a21679c2000f85d8fa4ae32f4959b79bd8c55f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977054"
---
# <a name="http-receive-adapter"></a>HTTP 接收适配器
HTTP 接收适配器的接收位置是一个通过 BizTalk Server 管理控制台配置的独特 URL。  
  
 您可为客户端的异步提交或同步提交配置 HTTP 接收适配器。 异步提交为单向提交，而同步提交为双向（或称为请求响应）提交。  
  
 您可使用 IIS 安全性对传入请求进行验证和授权。  
  
## <a name="http-get-and-http-post-requests"></a>HTTP GET 请求和 HTTP POST 请求  
 HTTP 接收适配器可通过两种不同的方式接收消息，即通过 HTTP POST 请求或 HTTP GET 请求。  
  
 当 HTTP 接收适配器通过 HTTP POST 请求获取信息时，将按顺序发生以下事件：  
  
1. 在 BizTalk Server 中配置的 URL 在该接收位置上接收一条新消息。  
  
2. 接收适配器创建一个 BizTalk 消息对象，以便将该消息提交到服务器。  
  
3. 接收适配器创建仅具有一个部分（正文部分）的 BizTalk 消息对象。  
  
4. 在读取该消息并将其成功提交到服务器之后，HTTP 接收适配器会将 HTTP 代码 202 发送回客户端，指示已接受该请求。  
  
    另外，HTTP 接收适配器也可以通过 HTTP 响应发送消息相关标记。 此相关标记表示 BizTalk Server 中的消息。 如果 HTTP 接收位置位于请求响应端口，则适配器将随响应消息一起返回成功代码 200。  
  
   当 HTTP 接收适配器处理来自 HTTP GET 请求的消息时，接收适配器将创建 BizTalk 消息对象，并将该 HTTP GET 请求的解码查询字符串放入 BizTalk 消息正文部分中。 HTTP 适配器使用以下算法来选择放入 BizTalk 消息正文部分中的查询字符串：  
  
-   如果 HTTP 接收适配器接收到 HTTP GET 请求，该适配器会使用问号 (?) 作为分隔符，将传入 URI 字符串拆分为两部分。  
  
-   第一部分 URI 字符串，问号分隔符之前的部分复制到**InboundTransportLocation**消息上下文属性。 **InboundTransportLocation**属性唯一地标识 BizTalk Server 接收消息的位置。 引擎使用此属性来确定应为该消息运行哪个接收位置。  
  
-   HTTP 适配器获取问号分隔符后面的其余 URI 字符串，然后将其解码并复制到 BizTalk 消息正文部分中。  
  
-   如果 HTTP 接收适配器接收到空 HTTP GET 或 HTTP POST 操作，将拒绝该操作。  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a>HTTP 接收适配器对 GET 请求的处理  
 以下示例说明了 HTTP 接收适配器如何处理通过 HTTP GET 请求接收的消息。 这些示例假设 HTTP 接收适配器配置了以下两个接收位置：  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  假设收到客户端的以下 HTTP GET 请求：  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     HTTP 接收适配器将执行如下操作：  
  
     设置**InboundTransportLocation**等于 /vroot/BTSHTTPReceive.dll，且等于将 BizTalk 消息对象正文部分的消息上下文属性 = 1。  
  
2.  假设收到客户端的以下 HTTP GET 请求：  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     HTTP 接收适配器将执行如下操作：  
  
     设置**InboundTransportLocation**属性等于 /vroot/BTSHTTPReceive.dll 和 BizTalk 消息对象正文部分等于 = 1 和 MyParam = Value。  
  
3.  假设收到客户端的以下 HTTP GET 请求：  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     通过 HTTP 执行的操作接收适配器是 +，如下所示：  
  
     拒绝该请求，因为 HTTP GET 请求的格式不正确。  
  
## <a name="batching-support-for-the-http-receive-adapter"></a>HTTP 接收适配器的批处理支持  
 HTTP 接收适配器将消息分批提交给服务器。 用于向服务器提交消息的批的大小可在 HTTP 适配器接收处理程序中进行配置。  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a>HTTP 接收适配器对挂起失败请求的支持  
 BizTalk Server HTTP 接收适配器已配置设置，请**挂起失败的请求**，用于控制如果它由于接收管道故障、 映射故障的入站的处理失败的 HTTP 请求有什么影响或路由故障。 该设置有两个可能的值：  
  
-   **如果为 false。** 这是默认设置。 HTTP 接收适配器将放弃由于接收管道故障、映射故障或路由故障而导致入站处理失败的消息。 另外，将向客户端发送错误状态代码 401 或 500。 
  
-   **为 true。** HTTP 接收适配器将挂起由于接收管道故障、映射故障或路由故障而导致入站处理失败的消息。 对于单向接收端口**已接受**状态代码 202 发送到客户端。 对于双向接收端口**错误**状态代码 500 发送到客户端。  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a>HTTP 接收适配器的 Chunked 编码支持  
 HTTP 接收适配器可接受带有使用 Chunked 编码的正文消息的 HTTP 请求。 当正文大小超过 4 KB 时，接收适配器将使用 Chunked 编码来发送响应消息。 Chunked 编码可关闭通过设置 DWORD 注册表项中所述[HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md)  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a>HTTP 接收适配器的客户端证书  
 HTTP 接收位置使用具有客户端证书的安全连接时，HTTP 接收适配器会从 Microsoft Internet 信息服务 (IIS) 获取该客户端证书的指纹，然后将其添加到在该位置通过 HTTPS 接收的所有消息的消息上下文中。 HTTP 接收适配器可设置以下系统属性：  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a>HTTP 接收适配器返回的状态代码  
 下面列出了 HTTP 接收适配器返回的各种状态代码：  
  
-   **200 确定。** 适配器已成功处理请求消息并生成响应。 适配器通过 HTTP 响应从 HTTP 请求响应端口返回此状态代码。  
  
-   **202 消息已接受。** 适配器已将消息成功提交到服务器中，或已挂起单向请求。 适配器通过 HTTP 响应从单向 HTTP 接收端口返回此状态代码。  
  
-   **401 访问被拒绝。** HTTP 请求被要求验证的接收端口接收，但对该消息的安全检查失败。 例如，参与方未解析或消息未解密。  
  
-   **500 内部服务器错误。** 处理 HTTP 请求时的常见错误。 除非不通过 BizTalk Server 挂起该消息的配置设置**挂起失败的请求**设置为**True**双向接收端口。  
  
## <a name="see-also"></a>请参阅  
 [HTTP 适配器](../core/http-adapter.md)