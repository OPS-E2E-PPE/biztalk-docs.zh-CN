---
title: "什么是 FileAct 适配器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62b83fc723bbebce857eb442384b14179c1072ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-fileact-adapter"></a><span data-ttu-id="0799d-103">什么是 FileAct 适配器？</span><span class="sxs-lookup"><span data-stu-id="0799d-103">What Is the FileAct Adapter?</span></span>
<span data-ttu-id="0799d-104">SWIFTNet FileAct 适配器提供 BizTalk Server 和互联网协会之间的连接的全球 Interbank 财务电信 (SWIFT) 保护 IP 网络 (SIPN) 传输的文件。</span><span class="sxs-lookup"><span data-stu-id="0799d-104">The FileAct adapter for SWIFTNet provides connectivity between BizTalk Server and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) Secure IP Network (SIPN) for the transfer of files.</span></span> <span data-ttu-id="0799d-105">SIPN 连接金融机构、 金融业基础结构和客户的安全专用网络上传输消息和文件。</span><span class="sxs-lookup"><span data-stu-id="0799d-105">The SIPN transfers messages and files over a secure private network which connects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="0799d-106">FileAct 适配器使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) s 要连接到 SIPN。</span><span class="sxs-lookup"><span data-stu-id="0799d-106">The FileAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="0799d-107">FileAct 适配器 SWIFT 参加安全地提供一种机制，并可靠地交换文件和与这些文件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="0799d-107">The FileAct adapter provides a mechanism for SWIFT participants to securely and reliably exchange files and information pertaining to those files.</span></span> <span data-ttu-id="0799d-108">它支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="0799d-108">It supports the following functionality:</span></span>  
  
-   <span data-ttu-id="0799d-109">将文件发送到 SWIFTNet 用户</span><span class="sxs-lookup"><span data-stu-id="0799d-109">Sending files to a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="0799d-110">从 SWIFTNet 用户检索文件</span><span class="sxs-lookup"><span data-stu-id="0799d-110">Retrieving files from a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="0799d-111">确认接收方接收的文件传递通知</span><span class="sxs-lookup"><span data-stu-id="0799d-111">Delivery notification confirming file receipt by a receiver</span></span>  
  
-   <span data-ttu-id="0799d-112">中止的正在进行的传输</span><span class="sxs-lookup"><span data-stu-id="0799d-112">Abort of transfers in progress</span></span>  
  
-   <span data-ttu-id="0799d-113">文件传输状态监视</span><span class="sxs-lookup"><span data-stu-id="0799d-113">File transfer state monitoring</span></span>  
  
-   <span data-ttu-id="0799d-114">并发文件传输</span><span class="sxs-lookup"><span data-stu-id="0799d-114">Concurrent file transfers</span></span>  
  
-   <span data-ttu-id="0799d-115">数据的真实性和完整性保证</span><span class="sxs-lookup"><span data-stu-id="0799d-115">Assurance of data authenticity and integrity</span></span>  
  
-   <span data-ttu-id="0799d-116">在传输过程中的文件数据保密性</span><span class="sxs-lookup"><span data-stu-id="0799d-116">Confidentiality of file data in transit</span></span>  
  
-   <span data-ttu-id="0799d-117">不可否认性的文件传输</span><span class="sxs-lookup"><span data-stu-id="0799d-117">Non-repudiation of file transfers</span></span>  
  
-   <span data-ttu-id="0799d-118">时间戳</span><span class="sxs-lookup"><span data-stu-id="0799d-118">Time-stamping</span></span>  
  
## <a name="the-fileact-service"></a><span data-ttu-id="0799d-119">FileAct 服务</span><span class="sxs-lookup"><span data-stu-id="0799d-119">The FileAct Service</span></span>  
 <span data-ttu-id="0799d-120">SWIFTNet FileAct 适配器提供安全且可靠传输文件，如批次的结构化的财务消息或大型报表。</span><span class="sxs-lookup"><span data-stu-id="0799d-120">The FileAct adapter for SWIFTNet provides secure and reliable transfer of files, such as batches of structured financial messages or large reports.</span></span> <span data-ttu-id="0799d-121">典型的应用程序包括如退休金或设置薪金支付、 有价证券增值信息和报告和监管报告的重复的信用额度传输。</span><span class="sxs-lookup"><span data-stu-id="0799d-121">Typical applications include repetitive credit transfers such as pension or salary payments, securities value-added information and reporting, and regulatory reporting.</span></span> <span data-ttu-id="0799d-122">SWIFTNet FileAct 提供各种消息传递模式：</span><span class="sxs-lookup"><span data-stu-id="0799d-122">SWIFTNet FileAct offers a variety of messaging modes:</span></span>  
  
-   <span data-ttu-id="0799d-123">**存储转发文件传输。**</span><span class="sxs-lookup"><span data-stu-id="0799d-123">**Store-and-forward file transfer.**</span></span> <span data-ttu-id="0799d-124">SWIFTNet FileAct 存储转发功能中删除的不确定性和不便担心你的通讯对象都处于联机状态时传输该文件。</span><span class="sxs-lookup"><span data-stu-id="0799d-124">SWIFTNet FileAct’s store-and-forward capability removes the uncertainty and inconvenience of worrying about whether or not your correspondents are online at the time you transmit the file.</span></span> <span data-ttu-id="0799d-125">一旦接收方准备好接收它，则传递该文件。</span><span class="sxs-lookup"><span data-stu-id="0799d-125">The file is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="0799d-126">因此，它提供将文件发送到大量通讯对象，其中一些可能在不同时区的理想途径。</span><span class="sxs-lookup"><span data-stu-id="0799d-126">As a result, it provides an ideal way to send files to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
-   <span data-ttu-id="0799d-127">**实时文件传输。**</span><span class="sxs-lookup"><span data-stu-id="0799d-127">**Real-time file transfer.**</span></span> <span data-ttu-id="0799d-128">实时消息传递提供的成本较低的替代方法存储和转发的以在传输时处于联机状态的通讯对象为目标的文件。</span><span class="sxs-lookup"><span data-stu-id="0799d-128">Real-time messaging offers a lower-cost alternative to store and forward for files that are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="0799d-129">因此它非常适合用于将文件发送到几大通讯对象或市场基础结构。</span><span class="sxs-lookup"><span data-stu-id="0799d-129">As a result it is ideal for sending files to a few large correspondents or market infrastructures.</span></span>  
  
-   <span data-ttu-id="0799d-130">**实时文件检索。**</span><span class="sxs-lookup"><span data-stu-id="0799d-130">**Real-time file retrieval.**</span></span> <span data-ttu-id="0799d-131">这是通常用于检索基于工作站的系统上下文中并通常与 SWIFTNet 浏览结合使用的文件交互服务。</span><span class="sxs-lookup"><span data-stu-id="0799d-131">This is an interactive service typically used to retrieve files in the context of workstation-based systems and often in conjunction with SWIFTNet Browse.</span></span> <span data-ttu-id="0799d-132">我们将支持此模式。</span><span class="sxs-lookup"><span data-stu-id="0799d-132">We will support this mode.</span></span>  
  
 <span data-ttu-id="0799d-133">（基于文件的文件发生） 的可选 SWIFTNet FileAct 功能包括：</span><span class="sxs-lookup"><span data-stu-id="0799d-133">The optional SWIFTNet FileAct features (on a file by file basis) include:</span></span>  
  
-   <span data-ttu-id="0799d-134">**消息优先级。**</span><span class="sxs-lookup"><span data-stu-id="0799d-134">**Message priority.**</span></span> <span data-ttu-id="0799d-135">在消息中，以允许适当处理你的通讯对象，可以将文件传输标记为"紧急"。</span><span class="sxs-lookup"><span data-stu-id="0799d-135">File transfers can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
-   <span data-ttu-id="0799d-136">**传递通知 （实时和存储转发模式）。**</span><span class="sxs-lookup"><span data-stu-id="0799d-136">**Delivery notification (real-time and store-and-forward modes).**</span></span> <span data-ttu-id="0799d-137">提供你通信者收到你的文件的确认消息。</span><span class="sxs-lookup"><span data-stu-id="0799d-137">Provides confirmation that your correspondent received your file.</span></span>  
  
-   <span data-ttu-id="0799d-138">**不可否认性发出和接收。**</span><span class="sxs-lookup"><span data-stu-id="0799d-138">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="0799d-139">发生争议，允许 SWIFT 以确认所声称的那个，传输未成功进行。</span><span class="sxs-lookup"><span data-stu-id="0799d-139">In case of dispute, allows SWIFT to confirm that the file transfer did take place as claimed.</span></span>  
  
 <span data-ttu-id="0799d-140">标准 SWIFTNet FileAct 功能包括 SWIFTNet PKI 安全性**。**</span><span class="sxs-lookup"><span data-stu-id="0799d-140">The standard SWIFTNet FileAct features include SWIFTNet PKI security**.**</span></span> <span data-ttu-id="0799d-141">SWIFTNet FileAct 使用 SWIFTNet PKI 进行了保护，并提供消息身份验证和完整性控件。</span><span class="sxs-lookup"><span data-stu-id="0799d-141">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
 <span data-ttu-id="0799d-142">所有消息和交换 SWIFTNet 上的文件都对一组通用的检查，以确保安全、 验证和平台的路由规则没有用户可以绕过。</span><span class="sxs-lookup"><span data-stu-id="0799d-142">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="0799d-143">SWIFTAlliance 网关 （压降） 应用程序执行这些检查。</span><span class="sxs-lookup"><span data-stu-id="0799d-143">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0799d-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0799d-144">See Also</span></span>  
 <span data-ttu-id="0799d-145">[Getting Started with FileAct 和交互适配器](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="0799d-145">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="0799d-146">[什么是 SWIFTNet？](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="0799d-146">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="0799d-147">什么是交互适配器？</span><span class="sxs-lookup"><span data-stu-id="0799d-147">What Is the InterAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)