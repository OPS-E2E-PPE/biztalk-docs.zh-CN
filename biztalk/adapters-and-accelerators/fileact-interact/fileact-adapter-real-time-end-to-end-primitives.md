---
title: FileAct 适配器实时端到端基元 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8591120-7259-49cb-90ac-954d8be226ed
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0532c0240be0032a46100e46d9cd58d4ff4820e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367179"
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a><span data-ttu-id="498d9-102">FileAct 适配器实时端到端基元</span><span class="sxs-lookup"><span data-stu-id="498d9-102">FileAct Adapter Real-Time End-to-End Primitives</span></span>
<span data-ttu-id="498d9-103">SWIFTNet 基元是两个应用程序和 SWIFTNet 链接 (SNL) 之间交换 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="498d9-103">SWIFTNet primitives are a pair of XML documents exchanged between the application and SWIFTNet Link (SNL).</span></span> <span data-ttu-id="498d9-104">以每个端到端基元，存在两个版本的基元-一个在客户端 （或发送） 位置，在服务器上的一个 （或接收） 端。</span><span class="sxs-lookup"><span data-stu-id="498d9-104">For each end-to-end primitive, there are two versions of the primitive – one at the client (or send) side and one at the server (or receive) side.</span></span> <span data-ttu-id="498d9-105">这包括共四个消息：将为每个文件基元、 文件获取基元和发送送达通知。</span><span class="sxs-lookup"><span data-stu-id="498d9-105">This comprises a total of four messages: Put File primitive, Get File primitive, and a Send Delivery Notification for each.</span></span>  
  
 <span data-ttu-id="498d9-106">下图显示了 FileAct 端到端基元。</span><span class="sxs-lookup"><span data-stu-id="498d9-106">The following figure shows the FileAct end-to-end primitives.</span></span>  
  
 <span data-ttu-id="498d9-107">![FileAct 端&#45;到&#45;结束基元](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")</span><span class="sxs-lookup"><span data-stu-id="498d9-107">![FileAct end&#45;to&#45;end primitives](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")</span></span>  
  
## <a name="put-file"></a><span data-ttu-id="498d9-108">将文件放入</span><span class="sxs-lookup"><span data-stu-id="498d9-108">Put File</span></span>  
 <span data-ttu-id="498d9-109">应用程序发起的 Put 文件基元将文件发送到另一个 SWIFTNet 用户的文件系统。</span><span class="sxs-lookup"><span data-stu-id="498d9-109">An application initiates the Put File primitive to send a file to the file system of another SWIFTNet user.</span></span> <span data-ttu-id="498d9-110">作为应用的端到端函数，是客户端和服务器端将文件基元。</span><span class="sxs-lookup"><span data-stu-id="498d9-110">As an end-to-end function, there are both client-side and server side Put File primitives.</span></span> <span data-ttu-id="498d9-111">这些共同协作以成功完成文件传输。</span><span class="sxs-lookup"><span data-stu-id="498d9-111">These collaborate together to successfully complete a file transfer.</span></span>  
  
 <span data-ttu-id="498d9-112">每个这种协作将发送单个文件。</span><span class="sxs-lookup"><span data-stu-id="498d9-112">Each such collaboration sends a single file.</span></span> <span data-ttu-id="498d9-113">可能会并行执行多个放置文件基元。</span><span class="sxs-lookup"><span data-stu-id="498d9-113">Multiple Put File primitives may be exercised in parallel.</span></span>  
  
## <a name="get-file"></a><span data-ttu-id="498d9-114">获取文件</span><span class="sxs-lookup"><span data-stu-id="498d9-114">Get File</span></span>  
 <span data-ttu-id="498d9-115">应用程序启动的文件系统的另一个 SWIFTNet 用户从文件中检索的文件获取基元。</span><span class="sxs-lookup"><span data-stu-id="498d9-115">An application initiates the Get File primitive to retrieve a file from the file system of another SWIFTNet user.</span></span> <span data-ttu-id="498d9-116">作为应用的端到端函数，是客户端和服务器端文件获取基元。</span><span class="sxs-lookup"><span data-stu-id="498d9-116">As an end-to-end function, there are both client-side and server-side Get File primitives.</span></span> <span data-ttu-id="498d9-117">这些共同协作以成功完成文件传输。</span><span class="sxs-lookup"><span data-stu-id="498d9-117">These collaborate together to successfully complete a file transfer.</span></span>  
  
 <span data-ttu-id="498d9-118">每个此类协作检索单个文件。</span><span class="sxs-lookup"><span data-stu-id="498d9-118">Each such collaboration retrieves a single file.</span></span> <span data-ttu-id="498d9-119">可能会并行执行多个文件获取基元。</span><span class="sxs-lookup"><span data-stu-id="498d9-119">Multiple Get File primitives may be exercised in parallel.</span></span>  
  
## <a name="send-delivery-notification"></a><span data-ttu-id="498d9-120">送达通知</span><span class="sxs-lookup"><span data-stu-id="498d9-120">Send Delivery Notification</span></span>  
 <span data-ttu-id="498d9-121">每个放置文件和每个文件获取基元已拥有的文件请求的接收方返回送达通知以便与相关的文件传输的发送端的选项。</span><span class="sxs-lookup"><span data-stu-id="498d9-121">Every Put File and every Get File primitive has the option of having the sending side of the file request that the receiving side return a delivery notification related to the file transfer.</span></span> <span data-ttu-id="498d9-122">对于 Put 文件基元，请求消息包含送达通知的请求。</span><span class="sxs-lookup"><span data-stu-id="498d9-122">For a Put File primitive, the request message contains the request for a delivery notification.</span></span>  
  
 <span data-ttu-id="498d9-123">如果是获取文件基元，响应消息包含送达通知的请求。</span><span class="sxs-lookup"><span data-stu-id="498d9-123">In the case of a Get File primitive, the response message contains the request for a delivery notification.</span></span>  
  
 <span data-ttu-id="498d9-124">在任一情况下，验证该文件已接收到全部 （通过执行其中一个状态基元来检查在传输达到已完成的状态） 和该文件已被充分安全存储 （例如，在后端办公系统上） 后,接收应用程序单独执行送达通知基元来返回传递到发件人肯定确认。</span><span class="sxs-lookup"><span data-stu-id="498d9-124">In either case, after verifying that the file was received in its entirety (by exercising one of the status primitives to check that the transfer reaches the state Completed) and that the file has been adequately safe stored (for example, on a back-office system), the receiving application separately exercises the Delivery Notification primitive to return a positive confirmation of delivery to the sender.</span></span> <span data-ttu-id="498d9-125">作为应用的端到端函数，是客户端和服务器端送达通知基元。</span><span class="sxs-lookup"><span data-stu-id="498d9-125">As an end-to-end function, there are both client-side and server-side Delivery Notification primitives.</span></span> <span data-ttu-id="498d9-126">这些共同协作以成功完成文件送达通知。</span><span class="sxs-lookup"><span data-stu-id="498d9-126">These collaborate together to successfully complete a file delivery notification.</span></span>  
  
 <span data-ttu-id="498d9-127">送达通知需要服务设计器来建立并强制执行发送方和接收方的文件之间的协议。</span><span class="sxs-lookup"><span data-stu-id="498d9-127">Delivery notification requires the service designer to establish and enforce a protocol between the senders and receivers of files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="498d9-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="498d9-128">See Also</span></span>  
 <span data-ttu-id="498d9-129">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="498d9-129">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="498d9-130">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="498d9-130">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="498d9-131">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="498d9-131">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="498d9-132">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="498d9-132">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="498d9-133">[FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="498d9-133">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="498d9-134">[FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="498d9-134">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="498d9-135">[FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="498d9-135">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="498d9-136">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="498d9-136">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)