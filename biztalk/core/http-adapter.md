---
title: HTTP 适配器 |Microsoft Docs
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
ms.openlocfilehash: 7d9bfc533222dad9411c6c56e67c37b5c9a37212
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382872"
---
# <a name="http-adapter"></a><span data-ttu-id="894fa-102">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="894fa-102">HTTP Adapter</span></span>
<span data-ttu-id="894fa-103">使用 HTTP 适配器通过 HTTP 协议交换 Microsoft BizTalk Server 和应用程序之间的信息。</span><span class="sxs-lookup"><span data-stu-id="894fa-103">You use the HTTP adapter to exchange information between Microsoft BizTalk Server and an application by means of the HTTP protocol.</span></span> <span data-ttu-id="894fa-104">HTTP 是企业间进行消息交换的主要协议。</span><span class="sxs-lookup"><span data-stu-id="894fa-104">HTTP is the primary protocol for interbusiness message exchange.</span></span> <span data-ttu-id="894fa-105">应用程序可以通过将 HTTP POST 或 HTTP GET 请求发送到指定的 HTTP URL 向服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="894fa-105">Applications can send messages to a server by sending HTTP POST or HTTP GET requests to a specified HTTP URL.</span></span> <span data-ttu-id="894fa-106">HTTP 适配器接收 HTTP 请求，并将其提交给 BizTalk Server 进行处理。</span><span class="sxs-lookup"><span data-stu-id="894fa-106">The HTTP adapter receives the HTTP requests and submits them to BizTalk Server for processing.</span></span> <span data-ttu-id="894fa-107">同样，BizTalk Server 可以将 HTTP POST 请求发送到指定的 HTTP URL 传输给远程应用程序的消息。</span><span class="sxs-lookup"><span data-stu-id="894fa-107">Similarly, BizTalk Server can transmit messages to remote applications by sending HTTP POST requests to a specified HTTP URL.</span></span>  
  
 <span data-ttu-id="894fa-108">HTTP 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="894fa-108">The HTTP adapter consists of two adapters—a receive adapter and a send adapter.</span></span> <span data-ttu-id="894fa-109">HTTP 接收适配器是 Microsoft Internet 信息服务 (IIS) Internet 服务器应用程序编程接口 (ISAPI) 扩展的 IIS 进程的宿主并控制使用 HTTP 适配器的接收位置。</span><span class="sxs-lookup"><span data-stu-id="894fa-109">The HTTP receive adapter is a Microsoft Internet Information Services (IIS) Internet Server Application Programming Interface (ISAPI) extension that the IIS process hosts, and controls the receive locations that use the HTTP adapter.</span></span> <span data-ttu-id="894fa-110">HTTP 发送适配器控制使用 HTTP 适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="894fa-110">The HTTP send adapter controls the send ports that use the HTTP adapter.</span></span>  
  
 <span data-ttu-id="894fa-111">本部分讨论了工作流和批处理支持 HTTP 接收适配器和 HTTP 发送适配器。</span><span class="sxs-lookup"><span data-stu-id="894fa-111">This section discusses the workflow and batching support for both the HTTP receive adapter and the HTTP send adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="894fa-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="894fa-112">In This Section</span></span>  
  
-   [<span data-ttu-id="894fa-113">HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="894fa-113">HTTP Receive Adapter</span></span>](../core/http-receive-adapter.md)  
  
-   [<span data-ttu-id="894fa-114">HTTP 发送适配器</span><span class="sxs-lookup"><span data-stu-id="894fa-114">HTTP Send Adapter</span></span>](../core/http-send-adapter.md)  
  
-   [<span data-ttu-id="894fa-115">配置 HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="894fa-115">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)  
  
-   [<span data-ttu-id="894fa-116">HTTP 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="894fa-116">HTTP Adapter Security Recommendations</span></span>](../core/http-adapter-security-recommendations.md)