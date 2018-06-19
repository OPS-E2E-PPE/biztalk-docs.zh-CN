---
title: 配置通过 AS2 消息接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01d4d897-d12b-4de4-a86b-e6d2718470c2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 324d8a7faf3ce21630502f219d033fb797aa3fc6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968987"
---
# <a name="configuring-a-receive-port-for-messages-over-as2"></a><span data-ttu-id="08bb1-102">配置 AS2 消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="08bb1-102">Configuring a Receive Port for Messages over AS2</span></span>
<span data-ttu-id="08bb1-103">若要接收带有 EDI 或非 EDI 负载的 AS2 消息，请创建一个 HTTP 接收端口以接收消息并向参与方返回响应。</span><span class="sxs-lookup"><span data-stu-id="08bb1-103">To receive an AS2 message with an EDI or non-EDI payload, create an HTTP receive port to receive the message and return a response back to the party.</span></span>  
  
 <span data-ttu-id="08bb1-104">如果将同步返回 MDN，接收端口必须是双向请求-响应接收端口。</span><span class="sxs-lookup"><span data-stu-id="08bb1-104">If the MDN will be returned synchronously, the receive port must be a two-way request-response receive port.</span></span> <span data-ttu-id="08bb1-105">接收端口中的接收位置将接收该 AS2 消息，而与双向接收端口相关联的发送端口将发送同步 MDN。</span><span class="sxs-lookup"><span data-stu-id="08bb1-105">A receive location in the receive port will receive the AS2 message, while the send port associated with the two-way receive port will send the synschronous MDN.</span></span>  
  
 <span data-ttu-id="08bb1-106">如果将异步返回 MDN，接收端口可以是单向的，因为 MDN 必须通过单独的动态发送端口返回。</span><span class="sxs-lookup"><span data-stu-id="08bb1-106">If the MDN will be returned asynchronously, the receive port can be a one-way receive port, because the MDN must be returned over a separate dynamic send port.</span></span> <span data-ttu-id="08bb1-107">无论接收端口是单向还是双向端口，都将返回一个 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="08bb1-107">An HTTP response will be returned by the receive port, whether it is a one-way or two-way port.</span></span> <span data-ttu-id="08bb1-108">如果设置一个双向接收端口来接收 AS2 消息，则在返回异步 MDN 时，将通过双向接收位置的发送端口返回 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="08bb1-108">If you set up a two-way receive port to receive an AS2 message, while returning an asynchronoius MDN, the HTTP response will be returned over the send port of the two-way receive location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08bb1-109">用于接收 AS2 消息的双向接收端口不得用于接收 MDN 消息，</span><span class="sxs-lookup"><span data-stu-id="08bb1-109">The two-way receive port used to receive AS2 messages should not be used to receive MDN messages.</span></span> <span data-ttu-id="08bb1-110">而应使用静态单向接收端口来接收 MDN 消息。</span><span class="sxs-lookup"><span data-stu-id="08bb1-110">MDN messages should be received on a static one-way receive port.</span></span> <span data-ttu-id="08bb1-111">对 MDN 使用请求/响应接收端口将会阻止返回 200OK 消息来响应传入 MDN，从而导致不必要地重试 MDN 传输。</span><span class="sxs-lookup"><span data-stu-id="08bb1-111">Using a request/response receive port for an MDN would prevent a 200OK message from being returned in response to the incoming MDN, thereby causing unnecessary retries of the MDN transmission.</span></span>  
  
 <span data-ttu-id="08bb1-112">使用下列配置创建接收端口：</span><span class="sxs-lookup"><span data-stu-id="08bb1-112">Create the receive port with the following configuration:</span></span>  
  
|<span data-ttu-id="08bb1-113">位置</span><span class="sxs-lookup"><span data-stu-id="08bb1-113">Location</span></span>|<span data-ttu-id="08bb1-114">属性</span><span class="sxs-lookup"><span data-stu-id="08bb1-114">Property</span></span>|<span data-ttu-id="08bb1-115">设置</span><span class="sxs-lookup"><span data-stu-id="08bb1-115">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="08bb1-116">**接收端口属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="08bb1-116">**Receive Port Properties: General**</span></span>|<span data-ttu-id="08bb1-117">端口类型</span><span class="sxs-lookup"><span data-stu-id="08bb1-117">Port type</span></span>|<span data-ttu-id="08bb1-118">请求-响应</span><span class="sxs-lookup"><span data-stu-id="08bb1-118">Request-Response</span></span>|  
|<span data-ttu-id="08bb1-119">**接收位置属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="08bb1-119">**Receive Location Properties: General**</span></span>|<span data-ttu-id="08bb1-120">传输类型</span><span class="sxs-lookup"><span data-stu-id="08bb1-120">Transport Type</span></span>|<span data-ttu-id="08bb1-121">HTTP**注意：** 仅 HTTP 适配器可以用于编码 EDIINT/AS2 消息传输。</span><span class="sxs-lookup"><span data-stu-id="08bb1-121">HTTP **Note:**  Only the HTTP adapter can be used for transporting EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="08bb1-122">此传输不能用于除 HTTP 适配器之外的其他适配器。</span><span class="sxs-lookup"><span data-stu-id="08bb1-122">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="08bb1-123">**接收位置属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="08bb1-123">**Receive Location Properties: General**</span></span>|<span data-ttu-id="08bb1-124">接收处理程序</span><span class="sxs-lookup"><span data-stu-id="08bb1-124">Receive handler</span></span>|<span data-ttu-id="08bb1-125">BizTalkServerIsolatedHost</span><span class="sxs-lookup"><span data-stu-id="08bb1-125">BizTalkServerIsolatedHost</span></span>|  
|<span data-ttu-id="08bb1-126">**接收位置属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="08bb1-126">**Receive Location Properties: General**</span></span>|<span data-ttu-id="08bb1-127">接收管道</span><span class="sxs-lookup"><span data-stu-id="08bb1-127">Receive pipeline</span></span>|<span data-ttu-id="08bb1-128">-AS2EdiReceive (如果负载是 EDI 编码)</span><span class="sxs-lookup"><span data-stu-id="08bb1-128">-   AS2EdiReceive (if the payload is EDI-encoded)</span></span><br /><span data-ttu-id="08bb1-129">-AS2Receive （如果负载不是 EDI 编码）**注意：** 使用 AS2EdiReceive 管道时，你必须添加到 BizTalk 应用程序用户组运行 BizTalk 隔离主机实例进程的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="08bb1-129">-   AS2Receive (if the payload is not EDI-encoded) **Note:**  When using the AS2EdiReceive pipeline, you must add the user account that the BizTalk Isolated Host Instance process is running under to the BizTalk Application Users group.</span></span> <span data-ttu-id="08bb1-130">AS2EdiReceive 管道在 BizTalk 独立主机实例进程中执行。</span><span class="sxs-lookup"><span data-stu-id="08bb1-130">The AS2EdiReceive pipeline executes in the BizTalk Isolated Host Instance process.</span></span> <span data-ttu-id="08bb1-131">AS2EdiReceive 管道会访问 SSO 存储区，这要求用户属于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Users 组。</span><span class="sxs-lookup"><span data-stu-id="08bb1-131">The AS2EdiReceive pipeline accesses the SSO store, which requires that the user is in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Users group.</span></span>|  
|<span data-ttu-id="08bb1-132">**接收位置属性： 常规**</span><span class="sxs-lookup"><span data-stu-id="08bb1-132">**Receive Location Properties: General**</span></span>|<span data-ttu-id="08bb1-133">发送管道</span><span class="sxs-lookup"><span data-stu-id="08bb1-133">Send pipeline</span></span>|<span data-ttu-id="08bb1-134">AS2Send</span><span class="sxs-lookup"><span data-stu-id="08bb1-134">AS2Send</span></span>|  
|<span data-ttu-id="08bb1-135">**HTTP 传输属性**</span><span class="sxs-lookup"><span data-stu-id="08bb1-135">**HTTP Transport Properties**</span></span>|<span data-ttu-id="08bb1-136">虚拟目录和 ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="08bb1-136">Virtual directory plus ISAPI extension</span></span>|<span data-ttu-id="08bb1-137">/\<虚拟目录名称\>/BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="08bb1-137">/\<name of virtual directory\>/BTSHTTPReceive.dll</span></span>|  
|<span data-ttu-id="08bb1-138">**HTTP 传输属性**</span><span class="sxs-lookup"><span data-stu-id="08bb1-138">**HTTP Transport Properties**</span></span>|<span data-ttu-id="08bb1-139">请求-响应返回内容类型</span><span class="sxs-lookup"><span data-stu-id="08bb1-139">Request-Response Return content type</span></span>|<span data-ttu-id="08bb1-140">text/xml</span><span class="sxs-lookup"><span data-stu-id="08bb1-140">text/xml</span></span>|  
  
## <a name="functionality-of-the-receive-location-in-synchronous-and-asynchronous-modes"></a><span data-ttu-id="08bb1-141">同步和异步模式中的接收位置的功能</span><span class="sxs-lookup"><span data-stu-id="08bb1-141">Functionality of the Receive Location in Synchronous and Asynchronous Modes</span></span>  
 <span data-ttu-id="08bb1-142">双向接收端口执行以下操作来接收和处理 EDI/AS2 消息并返回一个响应：</span><span class="sxs-lookup"><span data-stu-id="08bb1-142">The two-way receive port does the following to receive and process an EDI/AS2 message and return a response:</span></span>  
  
-   <span data-ttu-id="08bb1-143">通过 HTTP 接收 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="08bb1-143">Receive the AS2 message over HTTP.</span></span>  
  
-   <span data-ttu-id="08bb1-144">使用 AS2EDIReceive 接收管道（对于 EDI 编码的消息）或 AS2Receive 接收管道（对于非 EDI 编码的消息）处理 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="08bb1-144">Process the AS2 message using the AS2EDIReceive receive pipeline (for EDI-encoded messages) or the AS2Receive receive pipeline (for messages that are not encoded in EDI).</span></span> <span data-ttu-id="08bb1-145">此过程的详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="08bb1-145">For more information on this process, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
-   <span data-ttu-id="08bb1-146">在接收的消息上设置下列上下文属性：</span><span class="sxs-lookup"><span data-stu-id="08bb1-146">Set the following context properties on the received message:</span></span>  
  
    -   <span data-ttu-id="08bb1-147">`IsAS2PayloadMessage == True`（因为它是负载消息）</span><span class="sxs-lookup"><span data-stu-id="08bb1-147">`IsAS2PayloadMessage == True` (because it is a payload message)</span></span>  
  
    -   <span data-ttu-id="08bb1-148">`IsEmptyMDNResponse == False`（因为它不是空 MDN）</span><span class="sxs-lookup"><span data-stu-id="08bb1-148">`IsEmptyMDNResponse == False` (because it is not an empty MDN)</span></span>  
  
-   <span data-ttu-id="08bb1-149">如果是 EDI 编码的消息，则拆装 EDI 文件、生成 XML 文件并将它们放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="08bb1-149">If the message is EDI-encoded, disassemble the EDI file, generate XML files, and drop them into the MessageBox.</span></span> <span data-ttu-id="08bb1-150">为每个 XML 文件将 `BTS.MessageType` 的上下文属性设置为带有命名空间的架构名称。</span><span class="sxs-lookup"><span data-stu-id="08bb1-150">Set the context property of `BTS.MessageType` for each XML file to the schema name with namespace.</span></span>  
  
-   <span data-ttu-id="08bb1-151">如果不是 EDI 编码的消息，则将消息以其本机格式放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="08bb1-151">If the message is not EDI-encoded, drop the message in its native format into the MessageBox.</span></span>  
  
-   <span data-ttu-id="08bb1-152">使用 AS2EdiReceive 接收管道生成 MDN 文件（如果启用）。</span><span class="sxs-lookup"><span data-stu-id="08bb1-152">Generate the MDN file, if enabled, using the AS2EdiReceive receive pipeline.</span></span> <span data-ttu-id="08bb1-153">此过程的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="08bb1-153">For more information on this process, see [Generating an Outgoing MDN](../core/generating-an-outgoing-mdn.md).</span></span> <span data-ttu-id="08bb1-154">在消息上设置下列上下文属性：</span><span class="sxs-lookup"><span data-stu-id="08bb1-154">Set the following context properties on the message:</span></span>  
  
    -   <span data-ttu-id="08bb1-155">`EdiIntAS.IsAS2AsynchronousMdn == False`（如果处于同步模式）</span><span class="sxs-lookup"><span data-stu-id="08bb1-155">`EdiIntAS.IsAS2AsynchronousMdn == False` (if in synchronous mode)</span></span>  
  
    -   <span data-ttu-id="08bb1-156">`EdiIntAS.IsAS2AsynchronousMdn== True`（如果处于异步模式）</span><span class="sxs-lookup"><span data-stu-id="08bb1-156">`EdiIntAS.IsAS2AsynchronousMdn== True` (if in asynchronous mode)</span></span>  
  
-   <span data-ttu-id="08bb1-157">如果在同步模式下，则使用 AS2Send 发送管道发送 MDN 文件（如果启用）。</span><span class="sxs-lookup"><span data-stu-id="08bb1-157">If in synchronous mode, send the MDN file, if enabled, using the AS2Send send pipeline.</span></span> <span data-ttu-id="08bb1-158">此过程的详细信息，请参阅[发送传出 MDN](../core/sending-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="08bb1-158">For more information on this process, see [Sending an Outgoing MDN](../core/sending-an-outgoing-mdn.md).</span></span>  
  
-   <span data-ttu-id="08bb1-159">如果在异步模式下，则将 MDN 文件（如果启用）路由到 MessageBox（以便独立的动态发送端口提取并发送它）。</span><span class="sxs-lookup"><span data-stu-id="08bb1-159">If in asynchronous mode, route the MDN file, if enabled, to the MessageBox (for a separate dynamic send port to pick it up and send it).</span></span>  
  
-   <span data-ttu-id="08bb1-160">如果在异步模式下，则除生成异步返回的完整 MDN 之外还生成空的 MDN。</span><span class="sxs-lookup"><span data-stu-id="08bb1-160">If in asynchronous mode, generate an empty MDN in addition to the complete MDN that it returns asynchronously.</span></span> <span data-ttu-id="08bb1-161">在消息上设置下列上下文属性：</span><span class="sxs-lookup"><span data-stu-id="08bb1-161">Set the following context properties on the message:</span></span>  
  
    -   `IsAS2PayloadMessage == False`  
  
    -   `IsEmptyMDNResponse == True`  
  
-   <span data-ttu-id="08bb1-162">如果在异步模式下，则通过接收端口和发送方之间的 HTTP 连接对原始发送方返回 HTTP 响应，此响应将关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="08bb1-162">If in asynchronous mode, return the HTTP response to the original sender over the HTTP connection between the receive port and the sending party, which closes that connection.</span></span> <span data-ttu-id="08bb1-163">这是必要的，因为完整 MDN 不会关闭同步连接。</span><span class="sxs-lookup"><span data-stu-id="08bb1-163">This is necessary because the synchronous connection is not closed by the complete MDN.</span></span>  
  
-   <span data-ttu-id="08bb1-164">生成确认消息（如果启用）并将其放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="08bb1-164">Generate an acknowledgment message, if enabled, and drop it into the MessageBox.</span></span> <span data-ttu-id="08bb1-165">将 `BTS.MessageType` 的上下文属性设置为确认控制架构。</span><span class="sxs-lookup"><span data-stu-id="08bb1-165">Set the context property of `BTS.MessageType` to the acknowledgment control schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08bb1-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08bb1-166">See Also</span></span>  
 <span data-ttu-id="08bb1-167">[为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md) </span><span class="sxs-lookup"><span data-stu-id="08bb1-167">[Configuring Ports for an AS2 Solution](../core/configuring-ports-for-an-as2-solution.md) </span></span>  
 <span data-ttu-id="08bb1-168">[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md) </span><span class="sxs-lookup"><span data-stu-id="08bb1-168">[Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md) </span></span>  
 <span data-ttu-id="08bb1-169">[生成传出 MDN](../core/generating-an-outgoing-mdn.md) </span><span class="sxs-lookup"><span data-stu-id="08bb1-169">[Generating an Outgoing MDN](../core/generating-an-outgoing-mdn.md) </span></span>  
 [<span data-ttu-id="08bb1-170">发送传出 MDN</span><span class="sxs-lookup"><span data-stu-id="08bb1-170">Sending an Outgoing MDN</span></span>](../core/sending-an-outgoing-mdn.md)