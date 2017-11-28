---
title: "FileAct 适配器实时端到端基元 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8591120-7259-49cb-90ac-954d8be226ed
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95e52d4fbd5ec0df8ee580583f429ffe9e0f08d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a><span data-ttu-id="e8700-102">FileAct 适配器实时端到端基元</span><span class="sxs-lookup"><span data-stu-id="e8700-102">FileAct Adapter Real-Time End-to-End Primitives</span></span>
<span data-ttu-id="e8700-103">SWIFTNet 基元是两个应用程序和 SWIFTNet 链接 (SNL) 之间交换的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="e8700-103">SWIFTNet primitives are a pair of XML documents exchanged between the application and SWIFTNet Link (SNL).</span></span> <span data-ttu-id="e8700-104">为每个端到端基元，这里是两个版本的基元 – 一个在客户端 （或发送） 一侧，在服务器上的另一个 （或接收） 端。</span><span class="sxs-lookup"><span data-stu-id="e8700-104">For each end-to-end primitive, there are two versions of the primitive – one at the client (or send) side and one at the server (or receive) side.</span></span> <span data-ttu-id="e8700-105">这包含四个消息总数： 将文件基元、 获取文件基元和每个发送传递通知。</span><span class="sxs-lookup"><span data-stu-id="e8700-105">This comprises a total of four messages: Put File primitive, Get File primitive, and a Send Delivery Notification for each.</span></span>  
  
 <span data-ttu-id="e8700-106">下图显示 FileAct 端到端基元。</span><span class="sxs-lookup"><span data-stu-id="e8700-106">The following figure shows the FileAct end-to-end primitives.</span></span>  
  
 <span data-ttu-id="e8700-107">![FileAct 结束 &#45; 到 &#45; 结束基元](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")</span><span class="sxs-lookup"><span data-stu-id="e8700-107">![FileAct end&#45;to&#45;end primitives](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")</span></span>  
  
## <a name="put-file"></a><span data-ttu-id="e8700-108">将文件放</span><span class="sxs-lookup"><span data-stu-id="e8700-108">Put File</span></span>  
 <span data-ttu-id="e8700-109">应用程序启动放置文件的基元，以便将文件发送到文件系统中的另一个 SWIFTNet 用户。</span><span class="sxs-lookup"><span data-stu-id="e8700-109">An application initiates the Put File primitive to send a file to the file system of another SWIFTNet user.</span></span> <span data-ttu-id="e8700-110">作为一个端到端的函数，没有客户端和服务器端放文件基元。</span><span class="sxs-lookup"><span data-stu-id="e8700-110">As an end-to-end function, there are both client-side and server side Put File primitives.</span></span> <span data-ttu-id="e8700-111">这些共同协作以成功完成的文件传输。</span><span class="sxs-lookup"><span data-stu-id="e8700-111">These collaborate together to successfully complete a file transfer.</span></span>  
  
 <span data-ttu-id="e8700-112">每个此类协作发送单个文件。</span><span class="sxs-lookup"><span data-stu-id="e8700-112">Each such collaboration sends a single file.</span></span> <span data-ttu-id="e8700-113">可能中并行执行多个放置文件基元。</span><span class="sxs-lookup"><span data-stu-id="e8700-113">Multiple Put File primitives may be exercised in parallel.</span></span>  
  
## <a name="get-file"></a><span data-ttu-id="e8700-114">获取文件</span><span class="sxs-lookup"><span data-stu-id="e8700-114">Get File</span></span>  
 <span data-ttu-id="e8700-115">应用程序启动获取文件的基元，以便从另一个 SWIFTNet 用户的文件系统中检索文件。</span><span class="sxs-lookup"><span data-stu-id="e8700-115">An application initiates the Get File primitive to retrieve a file from the file system of another SWIFTNet user.</span></span> <span data-ttu-id="e8700-116">作为一个端到端的函数，没有客户端和服务器端获取文件基元。</span><span class="sxs-lookup"><span data-stu-id="e8700-116">As an end-to-end function, there are both client-side and server-side Get File primitives.</span></span> <span data-ttu-id="e8700-117">这些共同协作以成功完成的文件传输。</span><span class="sxs-lookup"><span data-stu-id="e8700-117">These collaborate together to successfully complete a file transfer.</span></span>  
  
 <span data-ttu-id="e8700-118">每个此类协作检索单个文件。</span><span class="sxs-lookup"><span data-stu-id="e8700-118">Each such collaboration retrieves a single file.</span></span> <span data-ttu-id="e8700-119">可能中并行执行多个获取文件基元。</span><span class="sxs-lookup"><span data-stu-id="e8700-119">Multiple Get File primitives may be exercised in parallel.</span></span>  
  
## <a name="send-delivery-notification"></a><span data-ttu-id="e8700-120">发送传递通知</span><span class="sxs-lookup"><span data-stu-id="e8700-120">Send Delivery Notification</span></span>  
 <span data-ttu-id="e8700-121">每个放置文件和基元每个获取文件已拥有的文件请求的接收端返回相关的文件传输传递通知的发送端的选项。</span><span class="sxs-lookup"><span data-stu-id="e8700-121">Every Put File and every Get File primitive has the option of having the sending side of the file request that the receiving side return a delivery notification related to the file transfer.</span></span> <span data-ttu-id="e8700-122">对于 Put 文件基元，该请求消息包含传递通知的请求。</span><span class="sxs-lookup"><span data-stu-id="e8700-122">For a Put File primitive, the request message contains the request for a delivery notification.</span></span>  
  
 <span data-ttu-id="e8700-123">如果是获取文件基元，响应消息包含传递通知的请求。</span><span class="sxs-lookup"><span data-stu-id="e8700-123">In the case of a Get File primitive, the response message contains the request for a delivery notification.</span></span>  
  
 <span data-ttu-id="e8700-124">在任一情况下，验证该文件，已接收到整个 （通过执行以检查传输达到已完成的状态的状态基元之一），该文件已被充分安全存储 （例如，在后端系统中） 后,接收应用程序单独执行传递通知的基元，以便返回传递到发件人的肯定确认。</span><span class="sxs-lookup"><span data-stu-id="e8700-124">In either case, after verifying that the file was received in its entirety (by exercising one of the status primitives to check that the transfer reaches the state Completed) and that the file has been adequately safe stored (for example, on a back-office system), the receiving application separately exercises the Delivery Notification primitive to return a positive confirmation of delivery to the sender.</span></span> <span data-ttu-id="e8700-125">作为一个端到端的函数，没有客户端和服务器端传递通知基元。</span><span class="sxs-lookup"><span data-stu-id="e8700-125">As an end-to-end function, there are both client-side and server-side Delivery Notification primitives.</span></span> <span data-ttu-id="e8700-126">这些共同协作以成功完成文件传递通知。</span><span class="sxs-lookup"><span data-stu-id="e8700-126">These collaborate together to successfully complete a file delivery notification.</span></span>  
  
 <span data-ttu-id="e8700-127">传递通知需要服务设计器建立并强制使用发送方和接收方的文件之间的协议。</span><span class="sxs-lookup"><span data-stu-id="e8700-127">Delivery notification requires the service designer to establish and enforce a protocol between the senders and receivers of files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8700-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8700-128">See Also</span></span>  
 <span data-ttu-id="e8700-129">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="e8700-129">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="e8700-130">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="e8700-130">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="e8700-131">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="e8700-131">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="e8700-132">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="e8700-132">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="e8700-133">[FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="e8700-133">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="e8700-134">[FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="e8700-134">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="e8700-135">[FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="e8700-135">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="e8700-136">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="e8700-136">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)