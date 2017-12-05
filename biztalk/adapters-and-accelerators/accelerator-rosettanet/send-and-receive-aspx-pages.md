---
title: "发送和接收 ASPX 页 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, ASPX pages
- ASPX pages, initiator
- HTTP adapters
- connections, HTTP adapters
- connections, single-action
- ASPX pages, responder
- single-action connections
- RNIFSend.aspx
- connections, asynchronous
- ASPX pages, about ASPX pages
- double-action connections
- connections, synchronous
- connections, double-action
- ASPX pages
- HTTP adapters, connections
- asynchronous connections
- RNIFReceive.aspx
- synchronous connections
ms.assetid: 21e52390-35d8-44b1-a5cd-1cd60cfe6e61
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0782c421dfe771cd024b5ce4df893e2aaa45721d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="send-and-receive-aspx-pages"></a><span data-ttu-id="8ea9c-102">发送和接收 ASPX 页</span><span class="sxs-lookup"><span data-stu-id="8ea9c-102">Send and Receive ASPX Pages</span></span>
<span data-ttu-id="8ea9c-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX 页是间的直接接口[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]和 Internet。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX pages are the direct interfaces between [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] and the Internet.</span></span> <span data-ttu-id="8ea9c-104">两个 ASPX 页分别是接收页 (RNIFReceive.aspx) 和发送页 (RNIFSend.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-104">The two ASPX pages are the receive page (RNIFReceive.aspx) and the send page (RNIFSend.aspx).</span></span> <span data-ttu-id="8ea9c-105">每个 ASPX 页都是相应 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管道的扩展。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-105">Each ASPX page is an extension to the corresponding [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline.</span></span> <span data-ttu-id="8ea9c-106">该管道需要 ASPX 页来处理 RosettaNet 实现框架 (RNIF) 头。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-106">The pipeline requires the ASPX page to handle RosettaNet Implementation Framework (RNIF) headers.</span></span> <span data-ttu-id="8ea9c-107">管道执行大部分 HTTP 处理，而每个 ASPX 页执行 RNIF 头的 HTTP 处理。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-107">The pipeline performs most of the HTTP processing; however, each ASPX page performs the HTTP processing of the RNIF headers.</span></span> <span data-ttu-id="8ea9c-108">这些 ASPX 页对 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP 适配器的功能进行了补充。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-108">The pages augment the functionality in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP adapter.</span></span>  
  
 <span data-ttu-id="8ea9c-109">每个 ASPX 页都是一个没有用户界面的 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-109">Each ASPX page is an ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web application with no user interface.</span></span> <span data-ttu-id="8ea9c-110">它们使用 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web 安全以确保与外部参与方的安全连接。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-110">They use ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web security to ensure a secure connection with external parties.</span></span> <span data-ttu-id="8ea9c-111">这些 ASPX 页提供了一个层，您可以在该层实现容错、可伸缩性和高可用性的服务。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-111">They provide a layer in which you can implement fault tolerance, scalability, and highly available services.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="8ea9c-112"> 安装程序在部署了 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 的每台计算机上安装一个 RNIFSend.aspx 页和一个 RNIFReceive.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-112"> setup installs an RNIFSend.aspx page and an RNIFReceive.aspx page on each deployment of [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="8ea9c-113">当发起方或响应方与贸易合作伙伴交换消息时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用 ASPX 页将消息发送到该贸易伙伴 URL，或从该贸易伙伴 URL 接收消息。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-113">When the initiator or responder exchanges messages with the trading partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] uses the ASPX pages to send messages to, or receive messages from, the partner URL.</span></span> <span data-ttu-id="8ea9c-114">如果发起方和响应方都使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，则发起方的两个 ASPX 页将与响应方的两个 ASPX 页交换消息。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-114">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the two ASPX pages on the initiator exchange messages with the two ASPX pages on the responder.</span></span> <span data-ttu-id="8ea9c-115">有关详细信息，请参阅下面的子节“发起方和响应方 ASPX 页的交互方式”。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-115">For more information, see the "How Initiator and Responder ASPX Pages Interact" subsection below.</span></span>  
  
## <a name="send-aspx-page"></a><span data-ttu-id="8ea9c-116">发送 ASPX 页</span><span class="sxs-lookup"><span data-stu-id="8ea9c-116">Send ASPX Page</span></span>  
 <span data-ttu-id="8ea9c-117">RNIFSend.aspx 页从 BizTalk HTTP 适配器接收消息。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-117">The RNIFSend.aspx page receives a message from the BizTalk HTTP adapter.</span></span> <span data-ttu-id="8ea9c-118">该页创建 RNIF 头并将其添加到消息中，然后通过 Internet 将消息发送给合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-118">It creates and adds RNIF headers to the message, and then sends the message to the partner over the Internet.</span></span> <span data-ttu-id="8ea9c-119">HTTP 适配器使用以下命令调用 RNIFSend.aspx：</span><span class="sxs-lookup"><span data-stu-id="8ea9c-119">The HTTP adapter calls RNIFSend.aspx with the following command:</span></span>  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 <span data-ttu-id="8ea9c-120">查询字符串包括下列数据，分别是发送页向合作伙伴发送消息所需数据，以及合作伙伴处理消息所需数据：</span><span class="sxs-lookup"><span data-stu-id="8ea9c-120">The query string includes the following data that the send page needs to send the message to the partner, and the data that the partner must have to process the message:</span></span>  
  
-   <span data-ttu-id="8ea9c-121">贸易合作伙伴 URL: http://www。\<*地址*\>.com/RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="8ea9c-121">The trading-partner URL: http://www.\<*address*\>.com/RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="8ea9c-122">响应类型： 同步或异步</span><span class="sxs-lookup"><span data-stu-id="8ea9c-122">The response type: sync or async</span></span>  
  
-   <span data-ttu-id="8ea9c-123">RNIF 版本： 1.1 或 2.0。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-123">The RNIF version: 1.1 or 2.0.</span></span>  
  
 <span data-ttu-id="8ea9c-124">BizTalk HTTP 适配器将 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送管道生成的一个 MIME 消息发送到发起方的 RNIFSend.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-124">The BizTalk HTTP adapter sends a MIME message produced by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline to the initiator RNIFSend.aspx page.</span></span> <span data-ttu-id="8ea9c-125">RNIFSend.aspx 按以下方式处理该消息：</span><span class="sxs-lookup"><span data-stu-id="8ea9c-125">RNIFSend.aspx processes the message as follows:</span></span>  
  
1.  <span data-ttu-id="8ea9c-126">发送页对消息进行验证。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-126">The send page performs validation on the message.</span></span>  
  
2.  <span data-ttu-id="8ea9c-127">发送页根据消息的内容类型、长度、ID 和多用途 Internet 邮件扩展 (MIME) 版本创建 MIME 头。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-127">The send page creates a Multipurpose Internet Mail Extensions (MIME) header based upon the content type, the length, the ID, and the MIME version.</span></span> <span data-ttu-id="8ea9c-128">该页将 MIME 头和 MIME 上下边界添加到消息中。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-128">It adds the MIME header, and upper and lower MIME boundaries, to the message.</span></span>  
  
3.  <span data-ttu-id="8ea9c-129">对于 RNIF 2.01，发送页按以下方式设置 HTTP 标头的属性：</span><span class="sxs-lookup"><span data-stu-id="8ea9c-129">For RNIF 2.01, the send page sets properties of the HTTP header as follows:</span></span>  
  
    1.  <span data-ttu-id="8ea9c-130">它将 X-RN-Version 属性设置为流程配置设置的“版本”属性中输入的版本。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-130">It sets the X-RN-Version property to the version entered in the Version property of the process configuration settings.</span></span>  
  
    2.  <span data-ttu-id="8ea9c-131">它将 X-RN-ResponseType 属性设置为 sync 或 async，具体取决于流程配置设置中 IsSynchronous 属性的设置。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-131">It sets the X-RN-ResponseType property to either sync or async, depending upon the setting of the IsSynchronous property in the process configuration settings.</span></span>  
  
    3.  <span data-ttu-id="8ea9c-132">它将 Content-Length 属性设置为完整消息的大小。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-132">It sets the Content-Length property to the size of the full message.</span></span>  
  
4.  <span data-ttu-id="8ea9c-133">发送页使用 HTTP Post 按照贸易合作伙伴协议中操作 URL 或信号 URL 设置设定的位置将消息发送到合作伙伴的目标 URL。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-133">Using an HTTP Post, the send page sends the message to the partner's destination URL, as set in the Action URL or Signal URL settings in the trading partner agreement.</span></span>  
  
5.  <span data-ttu-id="8ea9c-134">然后发送页等待 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-134">The send page waits for the HTTP response.</span></span> <span data-ttu-id="8ea9c-135">接收到响应后，它将该响应路由到 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-135">When it receives the response, it routes it to the HTTP adapter.</span></span>  
  
6.  <span data-ttu-id="8ea9c-136">如果连接是异步的，发送页将关闭连接，处理过程完成。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-136">If the connection is asynchronous, the send page closes the connection, and its processing is complete.</span></span>  
  
7.  <span data-ttu-id="8ea9c-137">如果连接是同步的，发送页将保持连接的开通以接收返回的消息。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-137">If the connection is synchronous, the send page keeps the connection open for a returned message.</span></span> <span data-ttu-id="8ea9c-138">发送页在收到消息以后执行的处理与 RNIFReceive.aspx 对所收到消息的处理相同，然后，发送页将收到的消息发送到 HTTP 适配器，最后关闭连接。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-138">After it receives the message, it performs the same processing that an RNIFReceive.aspx page performs on a received message, sends the received message to the HTTP adapter, and then closes the connection.</span></span>  
  
## <a name="receive-aspx-page"></a><span data-ttu-id="8ea9c-139">接收 ASPX 页</span><span class="sxs-lookup"><span data-stu-id="8ea9c-139">Receive ASPX Page</span></span>  
 <span data-ttu-id="8ea9c-140">RNIFReceive.aspx 页通过 Internet 接收合作伙伴的 HTTP 消息。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-140">The RNIFReceive.aspx page receives an HTTP message from the partner over the Internet.</span></span> <span data-ttu-id="8ea9c-141">该页处理、验证并删除 RNIF 头，然后将该消息提交到 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-141">It processes, validates, and then removes the RNIF headers, and submits the message to the HTTP adapter.</span></span> <span data-ttu-id="8ea9c-142">接收页收到的消息必须与 RNIF HTTP 传输兼容。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-142">The message received by the receive page must be RNIF HTTP transport-compliant.</span></span> <span data-ttu-id="8ea9c-143">接收页处理消息的方式如下：</span><span class="sxs-lookup"><span data-stu-id="8ea9c-143">The receive page processes messages as follows:</span></span>  
  
1.  <span data-ttu-id="8ea9c-144">响应方 RNIFReceive.aspx 页接收来自发起方消息，</span><span class="sxs-lookup"><span data-stu-id="8ea9c-144">The responder RNIFReceive.aspx page receives the message from the initiator.</span></span> <span data-ttu-id="8ea9c-145">该消息包含 MIME 头和上下边界。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-145">The message contains the MIME header and upper and lower boundaries.</span></span>  
  
2.  <span data-ttu-id="8ea9c-146">接收页验证 MIME 头。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-146">The receive page validates the MIME header.</span></span>  
  
3.  <span data-ttu-id="8ea9c-147">接收页删除消息中的 MIME 头和边界。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-147">The receive page removes the MIME header and boundaries from the message.</span></span>  
  
4.  <span data-ttu-id="8ea9c-148">接收页使用 HTTP 接收位置将消息发布到 HTTP 适配器，</span><span class="sxs-lookup"><span data-stu-id="8ea9c-148">The receive page posts the message to the HTTP adapter using the HTTP receive location.</span></span> <span data-ttu-id="8ea9c-149">并接收 HTTP 响应，然后将其返回给发起方发送页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-149">The receive page receives an HTTP response, and returns the HTTP response to the send page of the initiator.</span></span>  
  
5.  <span data-ttu-id="8ea9c-150">如果连接是异步的，接收页将关闭连接。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-150">If the connection is asynchronous, the receive page closes the connection.</span></span>  
  
6.  <span data-ttu-id="8ea9c-151">如果连接是同步的，接收页将保持连接的开通状态以等待返回的消息。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-151">If the connection is synchronous, the receive page keeps the connection open, waiting for a returned message.</span></span>  
  
7.  <span data-ttu-id="8ea9c-152">接收页在收到 HTTP 适配器返回的消息以后，执行与 RNIFSend.aspx 页相同的处理，然后将返回消息发送给发起方发送页；</span><span class="sxs-lookup"><span data-stu-id="8ea9c-152">After it receives the returned message from the HTTP adapter, the receive page performs the same processing that an RNIFSend.aspx page does, and sends the returned message to the initiator send page.</span></span> <span data-ttu-id="8ea9c-153">在收到 HTTP 响应以后，关闭连接。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-153">After it receives the HTTP response, it closes the connection.</span></span>  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a><span data-ttu-id="8ea9c-154">发起方 ASPX 页和响应方 ASPX 页的交互方式</span><span class="sxs-lookup"><span data-stu-id="8ea9c-154">How Initiator and Responder ASPX Pages Interact</span></span>  
 <span data-ttu-id="8ea9c-155">如果发起方和响应方都使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，则双方的四个 ASPX 页将根据连接是同步还是异步、消息是单操作还是双操作分别进行不同的交互。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-155">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the four ASPX pages on the initiator and responder interact differently depending on whether the connections are asynchronous or synchronous, and whether the messages are single-action or double-action.</span></span> <span data-ttu-id="8ea9c-156">以下各个子节对全部交互方案进行说明。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-156">The following subsections describe the complete set of interactions.</span></span>  
  
 <span data-ttu-id="8ea9c-157">**异步双操作**</span><span class="sxs-lookup"><span data-stu-id="8ea9c-157">**Double-Action Asynchronous**</span></span>  
  
 <span data-ttu-id="8ea9c-158">此方案涉及四个单独的 HTTP 连接，每步一个连接：</span><span class="sxs-lookup"><span data-stu-id="8ea9c-158">This scenario involves four separate HTTP connections, one for each step:</span></span>  
  
1.  <span data-ttu-id="8ea9c-159">发起方发送页将操作请求消息发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-159">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ea9c-160">根据系统负载情况，下面的步骤 2 和步骤 3 的次序可能会颠倒。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-160">Steps 2 and 3 below may occur in the reverse order, depending upon system load.</span></span>  
  
2.  <span data-ttu-id="8ea9c-161">响应方发送页将请求信号消息发送到发起方接收页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-161">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
3.  <span data-ttu-id="8ea9c-162">响应方发送页将操作响应消息发送到发起方接收页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-162">The responder send page sends an action response message to the initiator receive page.</span></span>  
  
4.  <span data-ttu-id="8ea9c-163">发起方发送页将响应信号消息发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-163">The initiator send page sends a response signal message to the responder receive page.</span></span>  
  
 <span data-ttu-id="8ea9c-164">**异步单操作**</span><span class="sxs-lookup"><span data-stu-id="8ea9c-164">**Single-Action Asynchronous**</span></span>  
  
 <span data-ttu-id="8ea9c-165">此方案涉及两个单独的 HTTP 连接，每步一个连接。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-165">This scenario involves two separate HTTP connections, one for each step.</span></span> <span data-ttu-id="8ea9c-166">请注意，此方案由双操作异步方案的步骤 1 和步骤 2 组成。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-166">Note that this scenario consists of step 1 and 2 of the double-action asynchronous scenario.</span></span>  
  
1.  <span data-ttu-id="8ea9c-167">发起方发送页将操作请求消息发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-167">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
2.  <span data-ttu-id="8ea9c-168">响应方发送页将请求信号消息发送到发起方接收页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-168">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
 <span data-ttu-id="8ea9c-169">**同步双操作**</span><span class="sxs-lookup"><span data-stu-id="8ea9c-169">**Double-Action Synchronous**</span></span>  
  
 <span data-ttu-id="8ea9c-170">此方案涉及一个 HTTP 连接：</span><span class="sxs-lookup"><span data-stu-id="8ea9c-170">This scenario involves one HTTP connection:</span></span>  
  
1.  <span data-ttu-id="8ea9c-171">发起方发送页将操作请求消息发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-171">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
2.  <span data-ttu-id="8ea9c-172">响应方接收页将操作响应消息（如果出现问题则为异常消息）发送到与步骤 1 所用连接相同的发起方发送页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-172">The responder receive page sends an action response message (or an exception, if there is a problem) to the initiator send page on the same connection used in step 1.</span></span>  
  
 <span data-ttu-id="8ea9c-173">**同步单操作**</span><span class="sxs-lookup"><span data-stu-id="8ea9c-173">**Single-Action Synchronous**</span></span>  
  
 <span data-ttu-id="8ea9c-174">此方案涉及一个 HTTP 连接：</span><span class="sxs-lookup"><span data-stu-id="8ea9c-174">This scenario involves one HTTP connection:</span></span>  
  
1.  <span data-ttu-id="8ea9c-175">发起方发送页将操作请求消息发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-175">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
2.  <span data-ttu-id="8ea9c-176">响应方接收页将请求信号消息（如果出现问题则为异常消息）发送到同一连接的发起方发送页。</span><span class="sxs-lookup"><span data-stu-id="8ea9c-176">The responder receive page sends a request signal message (or an exception, if there is a problem) to the initiator send page on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea9c-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ea9c-177">See Also</span></span>  
 <span data-ttu-id="8ea9c-178">[消息处理在 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="8ea9c-178">[Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span></span>  
 <span data-ttu-id="8ea9c-179">[BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="8ea9c-179">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="8ea9c-180">BTARN 发送管道</span><span class="sxs-lookup"><span data-stu-id="8ea9c-180">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)