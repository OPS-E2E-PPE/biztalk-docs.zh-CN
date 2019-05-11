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
# <a name="http-receive-adapter"></a>HTTP 接收适配器
HTTP 接收适配器的接收位置是一个通过 BizTalk Server 管理控制台配置的独特 URL。  
  
 你可以配置 HTTP 接收适配器为异步提交或同步提交从客户端。 异步提交为单向提交和同步提交为两个方法或请求-响应提交。  
  
 IIS 安全用于身份验证和授权的传入请求。  
  
## <a name="http-get-and-http-post-requests"></a>HTTP GET 和 HTTP POST 请求  
 HTTP 接收适配器可以接收消息两个不同的方式 — 通过 HTTP POST 请求或 HTTP GET 请求。  
  
 当 HTTP 接收适配器获取消息上的 HTTP POST 请求时，会发生以下事件序列：  
  
1. BizTalk Server 中配置的 URL 接收该接收位置中的新消息。  
  
2. 接收适配器创建 BizTalk 消息对象，以便可以将消息提交到服务器。  
  
3. 接收适配器仅具有一个部分中创建 BizTalk 消息对象，正文部分。  
  
4. 读取消息并将其成功提交到服务器后，HTTP 接收适配器发送的 HTTP 代码 202 回客户端，该值指示已接受该请求。  
  
    （可选） HTTP 接收适配器可在 HTTP 响应上发送消息相关标记。 此相关标记表示 BizTalk Server 中的消息。 如果 HTTP 接收位置的请求-响应端口，该适配器返回成功代码 200，以及响应消息。  
  
   当 HTTP 接收适配器处理消息从 HTTP GET 请求时，接收适配器创建 BizTalk 消息对象，并将 HTTP GET 请求的解码的查询字符串放入 BizTalk 消息正文部分。 HTTP 适配器选择查询字符串放入 BizTalk 消息正文部分使用以下算法：  
  
-   如果 HTTP 接收适配器收到的 HTTP GET 请求时，它将拆分传入 URI 字符串为两个部分，使用问号 （？） 符号作为分隔符。  
  
-   第一部分 URI 字符串，问号分隔符之前的部分复制到**InboundTransportLocation**消息上下文属性。 **InboundTransportLocation**属性唯一地标识 BizTalk Server 接收消息的位置。 引擎使用此属性来确定哪个接收位置运行的消息。  
  
-   HTTP 适配器采用 URI 字符串，问号分隔符之后的部分的其余部分和解码并将其复制到 BizTalk 消息正文部分。  
  
-   如果空的 HTTP GET 或 HTTP POST 操作接收 http 接收适配器，它将被拒绝。  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a>HTTP 接收适配器对 GET 请求的处理  
 以下是举例说明了 HTTP 接收适配器接收到的 HTTP GET 请求的进程消息。 这些示例假设 HTTP 接收适配器已配置以下两个接收位置：  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  为客户端提供以下 HTTP GET 请求：  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     通过 HTTP 执行的操作接收适配器是按如下所示：  
  
     设置**InboundTransportLocation**等于 /vroot/BTSHTTPReceive.dll，且等于将 BizTalk 消息对象正文部分的消息上下文属性 = 1。  
  
2.  为客户端提供以下 HTTP GET 请求：  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     通过 HTTP 执行的操作接收适配器是按如下所示：  
  
     设置**InboundTransportLocation**属性等于 /vroot/BTSHTTPReceive.dll 和 BizTalk 消息对象正文部分等于 = 1 和 MyParam = Value。  
  
3.  为客户端提供以下 HTTP GET 请求：  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     通过 HTTP 执行的操作接收适配器是 +，如下所示：  
  
     拒绝请求，因为 HTTP GET 请求的格式不正确。  
  
## <a name="batching-support-for-the-http-receive-adapter"></a>HTTP 接收适配器的批处理支持  
 HTTP 接收适配器将消息提交到批处理中的服务器。 用于提交到服务器的消息可以在 HTTP 适配器上配置的批的大小接收处理程序。  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a>HTTP 接收适配器支持对挂起失败的请求  
 BizTalk Server HTTP 接收适配器已配置设置，请**挂起失败的请求**，用于控制如果它由于接收管道故障、 映射故障的入站的处理失败的 HTTP 请求有什么影响或路由故障。 设置具有两个可能值：  
  
-   **如果为 false。** 这是默认设置。 HTTP 接收适配器将放弃由于接收管道故障、 映射故障或路由故障的入站的处理失败的消息。 此外，错误状态代码 401 或 500 是发送到客户端。 
  
-   **为 true。** HTTP 接收适配器将挂起由于接收管道故障、 映射故障或路由故障的入站的处理失败的消息。 对于单向接收端口**已接受**状态代码 202 发送到客户端。 对于双向接收端口**错误**状态代码 500 发送到客户端。  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a>Chunked 编码支持 http 接收适配器  
 HTTP 接收适配器接受使用 chunked 编码的正文消息的 HTTP 请求。 接收适配器使用 chunked 编码发送响应消息正文大小大于 4 KB。 Chunked 编码可关闭通过设置 DWORD 注册表项中所述[HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md)  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a>客户端证书的 HTTP 接收适配器  
 无论何时与客户端证书的安全连接使用 HTTP 接收位置，HTTP 接收适配器获取客户端证书指纹从 Microsoft Internet 信息服务 (IIS)，并将其添加到消息上下文的所有消息通过在该位置上的 HTTPS 接收的。 HTTP 接收适配器可设置以下系统属性：  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a>返回的 HTTP 状态代码接收适配器  
 以下列表包含状态代码返回的 HTTP 接收适配器。  
  
-   **200 确定。** 适配器已成功处理请求消息并生成响应。 适配器从 HTTP 请求-响应端口返回 HTTP 响应上的此状态代码。  
  
-   **202 消息已接受。** 该适配器将消息成功提交到服务器或已挂起单向请求。 适配器在 HTTP 响应从单向 HTTP 接收端口上返回此状态代码。  
  
-   **401 Access Denied.** 上收到的 HTTP 请求要求身份验证的接收端口和失败，该消息的安全检查。 例如，未解析的参与方或不解密消息。  
  
-   **500 内部服务器错误。** 常规失败以处理 HTTP 请求。 除非不通过 BizTalk Server 挂起该消息的配置设置**挂起失败的请求**设置为**True**双向接收端口。  
  
## <a name="see-also"></a>请参阅  
 [HTTP 适配器](../core/http-adapter.md)