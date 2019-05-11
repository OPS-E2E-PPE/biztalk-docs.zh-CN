---
title: 发送和接收 ASPX 页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d93c41a87465a75adc2047889ff6cb80cdf629fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281967"
---
# <a name="send-and-receive-aspx-pages"></a><span data-ttu-id="19757-102">发送和接收 ASPX 页</span><span class="sxs-lookup"><span data-stu-id="19757-102">Send and Receive ASPX Pages</span></span>
<span data-ttu-id="19757-103">在 Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX 页是之间的直接接口[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]和 Internet。</span><span class="sxs-lookup"><span data-stu-id="19757-103">The Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX pages are the direct interfaces between [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] and the Internet.</span></span> <span data-ttu-id="19757-104">两个 ASPX 页是接收页 (RNIFReceive.aspx) 和发送页 (RNIFSend.aspx)。</span><span class="sxs-lookup"><span data-stu-id="19757-104">The two ASPX pages are the receive page (RNIFReceive.aspx) and the send page (RNIFSend.aspx).</span></span> <span data-ttu-id="19757-105">每个 ASPX 页都是相应的扩展[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管道。</span><span class="sxs-lookup"><span data-stu-id="19757-105">Each ASPX page is an extension to the corresponding [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline.</span></span> <span data-ttu-id="19757-106">该管道需要 ASPX 页来处理 RosettaNet 实现框架 (RNIF) 标头。</span><span class="sxs-lookup"><span data-stu-id="19757-106">The pipeline requires the ASPX page to handle RosettaNet Implementation Framework (RNIF) headers.</span></span> <span data-ttu-id="19757-107">管道执行大部分 HTTP 处理;但是，每个 ASPX 页执行 RNIF 头的 HTTP 处理。</span><span class="sxs-lookup"><span data-stu-id="19757-107">The pipeline performs most of the HTTP processing; however, each ASPX page performs the HTTP processing of the RNIF headers.</span></span> <span data-ttu-id="19757-108">页增强功能中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="19757-108">The pages augment the functionality in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP adapter.</span></span>  
  
 <span data-ttu-id="19757-109">每个 ASPX 页都是 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web 应用程序没有用户界面。</span><span class="sxs-lookup"><span data-stu-id="19757-109">Each ASPX page is an ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web application with no user interface.</span></span> <span data-ttu-id="19757-110">它们使用 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web 安全以确保与外部各方的安全连接。</span><span class="sxs-lookup"><span data-stu-id="19757-110">They use ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web security to ensure a secure connection with external parties.</span></span> <span data-ttu-id="19757-111">它们提供了可以在其中实现容错、 可伸缩性和高可用性的服务层。</span><span class="sxs-lookup"><span data-stu-id="19757-111">They provide a layer in which you can implement fault tolerance, scalability, and highly available services.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="19757-112">安装程序将安装一个 RNIFSend.aspx 页和一个 RNIFReceive.aspx 页上的每个部署[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="19757-112">setup installs an RNIFSend.aspx page and an RNIFReceive.aspx page on each deployment of [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="19757-113">当发起方或响应程序与其交换消息的贸易合作伙伴[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]使用 ASPX 页将消息发送到，或从伙伴 URL 接收消息。</span><span class="sxs-lookup"><span data-stu-id="19757-113">When the initiator or responder exchanges messages with the trading partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] uses the ASPX pages to send messages to, or receive messages from, the partner URL.</span></span> <span data-ttu-id="19757-114">如果发起方和响应方使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，发起方上的两个 ASPX 页交换消息的响应方上的两个 ASPX 页。</span><span class="sxs-lookup"><span data-stu-id="19757-114">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the two ASPX pages on the initiator exchange messages with the two ASPX pages on the responder.</span></span> <span data-ttu-id="19757-115">有关详细信息，请参阅"发起方和响应方 ASPX 页的交互方式"下面的子节。</span><span class="sxs-lookup"><span data-stu-id="19757-115">For more information, see the "How Initiator and Responder ASPX Pages Interact" subsection below.</span></span>  
  
## <a name="send-aspx-page"></a><span data-ttu-id="19757-116">发送 ASPX 页</span><span class="sxs-lookup"><span data-stu-id="19757-116">Send ASPX Page</span></span>  
 <span data-ttu-id="19757-117">RNIFSend.aspx 页从 BizTalk HTTP 适配器接收消息。</span><span class="sxs-lookup"><span data-stu-id="19757-117">The RNIFSend.aspx page receives a message from the BizTalk HTTP adapter.</span></span> <span data-ttu-id="19757-118">它创建和将 RNIF 头添加到消息，然后通过 Internet 向合作伙伴发送消息。</span><span class="sxs-lookup"><span data-stu-id="19757-118">It creates and adds RNIF headers to the message, and then sends the message to the partner over the Internet.</span></span> <span data-ttu-id="19757-119">HTTP 适配器使用以下命令调用 RNIFSend.aspx:</span><span class="sxs-lookup"><span data-stu-id="19757-119">The HTTP adapter calls RNIFSend.aspx with the following command:</span></span>  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 <span data-ttu-id="19757-120">查询字符串包括发送页需要将消息发送到合作伙伴，以下数据和必须为合作伙伴来处理该消息的数据：</span><span class="sxs-lookup"><span data-stu-id="19757-120">The query string includes the following data that the send page needs to send the message to the partner, and the data that the partner must have to process the message:</span></span>  
  
- <span data-ttu-id="19757-121">贸易合作伙伴 URL: http://www.\<*地址*\>.com/RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="19757-121">The trading-partner URL: http://www.\<*address*\>.com/RNIFReceive.aspx</span></span>  
  
- <span data-ttu-id="19757-122">响应类型： sync 或 async</span><span class="sxs-lookup"><span data-stu-id="19757-122">The response type: sync or async</span></span>  
  
- <span data-ttu-id="19757-123">RNIF 版本：1.1 或 2.0。</span><span class="sxs-lookup"><span data-stu-id="19757-123">The RNIF version: 1.1 or 2.0.</span></span>  
  
  <span data-ttu-id="19757-124">BizTalk HTTP 适配器发送生成的 MIME 消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]发起方的 RNIFSend.aspx 页的发送管道。</span><span class="sxs-lookup"><span data-stu-id="19757-124">The BizTalk HTTP adapter sends a MIME message produced by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline to the initiator RNIFSend.aspx page.</span></span> <span data-ttu-id="19757-125">RNIFSend.aspx 处理该消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="19757-125">RNIFSend.aspx processes the message as follows:</span></span>  
  
1.  <span data-ttu-id="19757-126">发送页对消息执行验证。</span><span class="sxs-lookup"><span data-stu-id="19757-126">The send page performs validation on the message.</span></span>  
  
2.  <span data-ttu-id="19757-127">发送页创建基于内容类型、 长度、 ID 和 MIME 版本的多用途 Internet 邮件扩展 (MIME) 标头。</span><span class="sxs-lookup"><span data-stu-id="19757-127">The send page creates a Multipurpose Internet Mail Extensions (MIME) header based upon the content type, the length, the ID, and the MIME version.</span></span> <span data-ttu-id="19757-128">它将 MIME 头和上限和下限 MIME 边界添加到消息中。</span><span class="sxs-lookup"><span data-stu-id="19757-128">It adds the MIME header, and upper and lower MIME boundaries, to the message.</span></span>  
  
3.  <span data-ttu-id="19757-129">对于 RNIF 2.01，发送页，如下所示设置 HTTP 标头的属性：</span><span class="sxs-lookup"><span data-stu-id="19757-129">For RNIF 2.01, the send page sets properties of the HTTP header as follows:</span></span>  
  
    1.  <span data-ttu-id="19757-130">它将 X RN 版本属性设置为流程配置设置的版本属性中输入的版本。</span><span class="sxs-lookup"><span data-stu-id="19757-130">It sets the X-RN-Version property to the version entered in the Version property of the process configuration settings.</span></span>  
  
    2.  <span data-ttu-id="19757-131">它将 X RN ResponseType 属性设置为 sync 或 async，取决于在流程配置设置中 IsSynchronous 属性的设置。</span><span class="sxs-lookup"><span data-stu-id="19757-131">It sets the X-RN-ResponseType property to either sync or async, depending upon the setting of the IsSynchronous property in the process configuration settings.</span></span>  
  
    3.  <span data-ttu-id="19757-132">它将 Content-length 属性设置为完整消息的大小。</span><span class="sxs-lookup"><span data-stu-id="19757-132">It sets the Content-Length property to the size of the full message.</span></span>  
  
4.  <span data-ttu-id="19757-133">使用 HTTP Post，发送页作为发送消息到合作伙伴的目标 URL 中的贸易合作伙伴协议中的操作 URL 或信号 URL 设置。</span><span class="sxs-lookup"><span data-stu-id="19757-133">Using an HTTP Post, the send page sends the message to the partner's destination URL, as set in the Action URL or Signal URL settings in the trading partner agreement.</span></span>  
  
5.  <span data-ttu-id="19757-134">发送页等待 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="19757-134">The send page waits for the HTTP response.</span></span> <span data-ttu-id="19757-135">当它收到响应时，它将其路由到 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="19757-135">When it receives the response, it routes it to the HTTP adapter.</span></span>  
  
6.  <span data-ttu-id="19757-136">如果连接是异步的发送页将关闭连接，并处理过程完成。</span><span class="sxs-lookup"><span data-stu-id="19757-136">If the connection is asynchronous, the send page closes the connection, and its processing is complete.</span></span>  
  
7.  <span data-ttu-id="19757-137">如果连接是同步的则发送页将保持打开返回的消息进行连接。</span><span class="sxs-lookup"><span data-stu-id="19757-137">If the connection is synchronous, the send page keeps the connection open for a returned message.</span></span> <span data-ttu-id="19757-138">收到消息后，它会执行相同的处理 RNIFReceive.aspx 页收到的消息执行、 将接收到的消息发送到 HTTP 适配器，然后关闭连接。</span><span class="sxs-lookup"><span data-stu-id="19757-138">After it receives the message, it performs the same processing that an RNIFReceive.aspx page performs on a received message, sends the received message to the HTTP adapter, and then closes the connection.</span></span>  
  
## <a name="receive-aspx-page"></a><span data-ttu-id="19757-139">接收 ASPX 页</span><span class="sxs-lookup"><span data-stu-id="19757-139">Receive ASPX Page</span></span>  
 <span data-ttu-id="19757-140">RNIFReceive.aspx 页通过 Internet 从合作伙伴接收 HTTP 消息。</span><span class="sxs-lookup"><span data-stu-id="19757-140">The RNIFReceive.aspx page receives an HTTP message from the partner over the Internet.</span></span> <span data-ttu-id="19757-141">它处理、 验证，然后删除 RNIF 头，并将消息提交到 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="19757-141">It processes, validates, and then removes the RNIF headers, and submits the message to the HTTP adapter.</span></span> <span data-ttu-id="19757-142">接收页收到的消息必须与 RNIF HTTP 传输兼容。</span><span class="sxs-lookup"><span data-stu-id="19757-142">The message received by the receive page must be RNIF HTTP transport-compliant.</span></span> <span data-ttu-id="19757-143">接收页处理消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="19757-143">The receive page processes messages as follows:</span></span>  
  
1.  <span data-ttu-id="19757-144">响应方 RNIFReceive.aspx 页接收的消息从发起方。</span><span class="sxs-lookup"><span data-stu-id="19757-144">The responder RNIFReceive.aspx page receives the message from the initiator.</span></span> <span data-ttu-id="19757-145">该消息包含 MIME 头和上下边界。</span><span class="sxs-lookup"><span data-stu-id="19757-145">The message contains the MIME header and upper and lower boundaries.</span></span>  
  
2.  <span data-ttu-id="19757-146">接收页验证 MIME 标头。</span><span class="sxs-lookup"><span data-stu-id="19757-146">The receive page validates the MIME header.</span></span>  
  
3.  <span data-ttu-id="19757-147">接收页从消息中删除 MIME 头和边界。</span><span class="sxs-lookup"><span data-stu-id="19757-147">The receive page removes the MIME header and boundaries from the message.</span></span>  
  
4.  <span data-ttu-id="19757-148">接收页将消息发布到 HTTP 适配器使用 HTTP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="19757-148">The receive page posts the message to the HTTP adapter using the HTTP receive location.</span></span> <span data-ttu-id="19757-149">接收页收到 HTTP 响应，并返回到发起方发送页的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="19757-149">The receive page receives an HTTP response, and returns the HTTP response to the send page of the initiator.</span></span>  
  
5.  <span data-ttu-id="19757-150">如果连接是异步的接收页将关闭连接。</span><span class="sxs-lookup"><span data-stu-id="19757-150">If the connection is asynchronous, the receive page closes the connection.</span></span>  
  
6.  <span data-ttu-id="19757-151">如果连接是同步的则接收页将保持打开状态，等待返回的消息连接。</span><span class="sxs-lookup"><span data-stu-id="19757-151">If the connection is synchronous, the receive page keeps the connection open, waiting for a returned message.</span></span>  
  
7.  <span data-ttu-id="19757-152">它从 HTTP 适配器接收返回的消息后，接收页执行相同的处理 RNIFSend.aspx 页，并将返回的消息发送到发起方发送页。</span><span class="sxs-lookup"><span data-stu-id="19757-152">After it receives the returned message from the HTTP adapter, the receive page performs the same processing that an RNIFSend.aspx page does, and sends the returned message to the initiator send page.</span></span> <span data-ttu-id="19757-153">它收到 HTTP 响应后，它将关闭连接。</span><span class="sxs-lookup"><span data-stu-id="19757-153">After it receives the HTTP response, it closes the connection.</span></span>  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a><span data-ttu-id="19757-154">发起方和响应方 ASPX 页交互的方式</span><span class="sxs-lookup"><span data-stu-id="19757-154">How Initiator and Responder ASPX Pages Interact</span></span>  
 <span data-ttu-id="19757-155">如果发起方和响应方使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，发起方和响应方上的四个 ASPX 页交互以不同的方式具体取决于连接是同步还是异步、 和的消息是否是单操作还是双操作.</span><span class="sxs-lookup"><span data-stu-id="19757-155">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the four ASPX pages on the initiator and responder interact differently depending on whether the connections are asynchronous or synchronous, and whether the messages are single-action or double-action.</span></span> <span data-ttu-id="19757-156">以下小节介绍了一整套的交互。</span><span class="sxs-lookup"><span data-stu-id="19757-156">The following subsections describe the complete set of interactions.</span></span>  
  
 <span data-ttu-id="19757-157">**双操作异步**</span><span class="sxs-lookup"><span data-stu-id="19757-157">**Double-Action Asynchronous**</span></span>  
  
 <span data-ttu-id="19757-158">此方案涉及四个独立的 HTTP 连接，另一个用于每个步骤：</span><span class="sxs-lookup"><span data-stu-id="19757-158">This scenario involves four separate HTTP connections, one for each step:</span></span>  
  
1. <span data-ttu-id="19757-159">发起方发送页操作请求将消息的发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="19757-159">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="19757-160">步骤 2 和 3 下可能发生相反的顺序，根据系统负载。</span><span class="sxs-lookup"><span data-stu-id="19757-160">Steps 2 and 3 below may occur in the reverse order, depending upon system load.</span></span>  
  
2. <span data-ttu-id="19757-161">响应方发送页请求信号将消息的发送到发起方接收页。</span><span class="sxs-lookup"><span data-stu-id="19757-161">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
3. <span data-ttu-id="19757-162">响应方发送页操作响应将消息的发送到发起方接收页。</span><span class="sxs-lookup"><span data-stu-id="19757-162">The responder send page sends an action response message to the initiator receive page.</span></span>  
  
4. <span data-ttu-id="19757-163">发起方发送页响应信号将消息的发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="19757-163">The initiator send page sends a response signal message to the responder receive page.</span></span>  
  
   <span data-ttu-id="19757-164">**单操作异步**</span><span class="sxs-lookup"><span data-stu-id="19757-164">**Single-Action Asynchronous**</span></span>  
  
   <span data-ttu-id="19757-165">此方案涉及到两个独立的 HTTP 连接，另一个用于每个步骤。</span><span class="sxs-lookup"><span data-stu-id="19757-165">This scenario involves two separate HTTP connections, one for each step.</span></span> <span data-ttu-id="19757-166">请注意此方案包含的步骤 1 和 2 双操作异步方案。</span><span class="sxs-lookup"><span data-stu-id="19757-166">Note that this scenario consists of step 1 and 2 of the double-action asynchronous scenario.</span></span>  
  
5. <span data-ttu-id="19757-167">发起方发送页操作请求将消息的发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="19757-167">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
6. <span data-ttu-id="19757-168">响应方发送页请求信号将消息的发送到发起方接收页。</span><span class="sxs-lookup"><span data-stu-id="19757-168">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
   <span data-ttu-id="19757-169">**双操作同步**</span><span class="sxs-lookup"><span data-stu-id="19757-169">**Double-Action Synchronous**</span></span>  
  
   <span data-ttu-id="19757-170">此方案涉及一个 HTTP 连接：</span><span class="sxs-lookup"><span data-stu-id="19757-170">This scenario involves one HTTP connection:</span></span>  
  
7. <span data-ttu-id="19757-171">发起方发送页操作请求将消息的发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="19757-171">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
8. <span data-ttu-id="19757-172">响应方接收页将操作响应消息 （或异常，如果问题） 在步骤 1 中使用的相同连接的发起方发送页。</span><span class="sxs-lookup"><span data-stu-id="19757-172">The responder receive page sends an action response message (or an exception, if there is a problem) to the initiator send page on the same connection used in step 1.</span></span>  
  
   <span data-ttu-id="19757-173">**单操作同步**</span><span class="sxs-lookup"><span data-stu-id="19757-173">**Single-Action Synchronous**</span></span>  
  
   <span data-ttu-id="19757-174">此方案涉及一个 HTTP 连接：</span><span class="sxs-lookup"><span data-stu-id="19757-174">This scenario involves one HTTP connection:</span></span>  
  
9. <span data-ttu-id="19757-175">发起方发送页操作请求将消息的发送到响应方接收页。</span><span class="sxs-lookup"><span data-stu-id="19757-175">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
10. <span data-ttu-id="19757-176">响应方接收页将请求信号消息 （或异常，如果问题） 相同的连接的发起方发送页。</span><span class="sxs-lookup"><span data-stu-id="19757-176">The responder receive page sends a request signal message (or an exception, if there is a problem) to the initiator send page on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19757-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="19757-177">See Also</span></span>  
 <span data-ttu-id="19757-178">[BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="19757-178">[Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span></span>  
 <span data-ttu-id="19757-179">[BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="19757-179">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="19757-180">BTARN 发送管道</span><span class="sxs-lookup"><span data-stu-id="19757-180">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)