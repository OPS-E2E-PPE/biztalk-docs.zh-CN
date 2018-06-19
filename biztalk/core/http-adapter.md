---
title: HTTP 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, receive adapters
- HTTP adapters, send adapters
- HTTP adapters
- receive adapters, HTTP adapters
- send adapters, HTTP adapters
- HTTP adapters, about HTTP adapters
ms.assetid: a9423052-8392-4006-ab46-79834169c796
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d9be9fac6fdb65c4516c671b6c0e30096e83a27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256045"
---
# <a name="http-adapter"></a><span data-ttu-id="ea4c5-102">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="ea4c5-102">HTTP Adapter</span></span>
<span data-ttu-id="ea4c5-103">使用 HTTP 适配器可以通过 HTTP 协议在 Microsoft BizTalk Server 和应用程序之间交换信息。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-103">You use the HTTP adapter to exchange information between Microsoft BizTalk Server and an application by means of the HTTP protocol.</span></span> <span data-ttu-id="ea4c5-104">HTTP 是企业间进行消息交换的主要协议。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-104">HTTP is the primary protocol for interbusiness message exchange.</span></span> <span data-ttu-id="ea4c5-105">通过向指定的 HTTP URL 发送 HTTP POST 或 HTTP GET 请求，应用程序可以向服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-105">Applications can send messages to a server by sending HTTP POST or HTTP GET requests to a specified HTTP URL.</span></span> <span data-ttu-id="ea4c5-106">HTTP 适配器接收 HTTP 请求，并将其提交到 BizTalk Server 进行处理。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-106">The HTTP adapter receives the HTTP requests and submits them to BizTalk Server for processing.</span></span> <span data-ttu-id="ea4c5-107">同样，通过向指定的 HTTP URL 发送 HTTP POST 请求，BizTalk Server 可以将消息传输给远程应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-107">Similarly, BizTalk Server can transmit messages to remote applications by sending HTTP POST requests to a specified HTTP URL.</span></span>  
  
 <span data-ttu-id="ea4c5-108">HTTP 适配器由两个适配器组成：一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-108">The HTTP adapter consists of two adapters—a receive adapter and a send adapter.</span></span> <span data-ttu-id="ea4c5-109">HTTP 接收适配器是 Microsoft Internet 信息服务 (IIS) Internet 服务器应用程序编程接口 (ISAPI) 扩展，IIS 进程将作为该适配器的接收位置的宿主并控制这些接收位置。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-109">The HTTP receive adapter is a Microsoft Internet Information Services (IIS) Internet Server Application Programming Interface (ISAPI) extension that the IIS process hosts, and controls the receive locations that use the HTTP adapter.</span></span> <span data-ttu-id="ea4c5-110">HTTP 发送适配器控制使用 HTTP 适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-110">The HTTP send adapter controls the send ports that use the HTTP adapter.</span></span>  
  
 <span data-ttu-id="ea4c5-111">本部分将介绍 HTTP 接收适配器和 HTTP 发送适配器的工作流和批处理支持。</span><span class="sxs-lookup"><span data-stu-id="ea4c5-111">This section discusses the workflow and batching support for both the HTTP receive adapter and the HTTP send adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea4c5-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="ea4c5-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ea4c5-113">HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="ea4c5-113">HTTP Receive Adapter</span></span>](../core/http-receive-adapter.md)  
  
-   [<span data-ttu-id="ea4c5-114">HTTP 发送适配器</span><span class="sxs-lookup"><span data-stu-id="ea4c5-114">HTTP Send Adapter</span></span>](../core/http-send-adapter.md)  
  
-   [<span data-ttu-id="ea4c5-115">配置 HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="ea4c5-115">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)  
  
-   [<span data-ttu-id="ea4c5-116">HTTP 适配器安全建议</span><span class="sxs-lookup"><span data-stu-id="ea4c5-116">HTTP Adapter Security Recommendations</span></span>](../core/http-adapter-security-recommendations.md)