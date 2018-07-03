---
title: FileAct 适配器是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc6fe9b28e4ea2b5eee087b61866827a766c3e3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971486"
---
# <a name="what-is-the-fileact-adapter"></a><span data-ttu-id="df594-103">FileAct 适配器是什么？</span><span class="sxs-lookup"><span data-stu-id="df594-103">What Is the FileAct Adapter?</span></span>
<span data-ttu-id="df594-104">SWIFTNet FileAct 适配器之间提供连接 BizTalk Server 和在全球范围内 Interbank 金融电信 (SWIFT) Secure IP Network (SIPN) 为传输的文件。</span><span class="sxs-lookup"><span data-stu-id="df594-104">The FileAct adapter for SWIFTNet provides connectivity between BizTalk Server and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) Secure IP Network (SIPN) for the transfer of files.</span></span> <span data-ttu-id="df594-105">SIPN 连接金融机构、 金融业基础结构和客户的安全专用网络上传输消息和文件。</span><span class="sxs-lookup"><span data-stu-id="df594-105">The SIPN transfers messages and files over a secure private network which connects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="df594-106">FileAct 适配器使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) s 要连接到 SIPN。</span><span class="sxs-lookup"><span data-stu-id="df594-106">The FileAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="df594-107">FileAct 适配器安全地向 SWIFT 参与者提供一种机制，并可靠地交换文件和与这些文件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="df594-107">The FileAct adapter provides a mechanism for SWIFT participants to securely and reliably exchange files and information pertaining to those files.</span></span> <span data-ttu-id="df594-108">它支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="df594-108">It supports the following functionality:</span></span>  
  
-   <span data-ttu-id="df594-109">将文件发送给 SWIFTNet 用户</span><span class="sxs-lookup"><span data-stu-id="df594-109">Sending files to a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="df594-110">从 SWIFTNet 用户检索文件</span><span class="sxs-lookup"><span data-stu-id="df594-110">Retrieving files from a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="df594-111">送达通知确认由接收方接收的文件</span><span class="sxs-lookup"><span data-stu-id="df594-111">Delivery notification confirming file receipt by a receiver</span></span>  
  
-   <span data-ttu-id="df594-112">中止正在进行中传输的</span><span class="sxs-lookup"><span data-stu-id="df594-112">Abort of transfers in progress</span></span>  
  
-   <span data-ttu-id="df594-113">文件传输状态监视</span><span class="sxs-lookup"><span data-stu-id="df594-113">File transfer state monitoring</span></span>  
  
-   <span data-ttu-id="df594-114">并发文件传输</span><span class="sxs-lookup"><span data-stu-id="df594-114">Concurrent file transfers</span></span>  
  
-   <span data-ttu-id="df594-115">确保数据的真实性和完整性的情况</span><span class="sxs-lookup"><span data-stu-id="df594-115">Assurance of data authenticity and integrity</span></span>  
  
-   <span data-ttu-id="df594-116">在传输过程中的文件数据的机密性</span><span class="sxs-lookup"><span data-stu-id="df594-116">Confidentiality of file data in transit</span></span>  
  
-   <span data-ttu-id="df594-117">文件传输的不可否认性</span><span class="sxs-lookup"><span data-stu-id="df594-117">Non-repudiation of file transfers</span></span>  
  
-   <span data-ttu-id="df594-118">时间戳</span><span class="sxs-lookup"><span data-stu-id="df594-118">Time-stamping</span></span>  
  
## <a name="the-fileact-service"></a><span data-ttu-id="df594-119">FileAct 服务</span><span class="sxs-lookup"><span data-stu-id="df594-119">The FileAct Service</span></span>  
 <span data-ttu-id="df594-120">SWIFTNet FileAct 适配器提供文件，如批次的结构化的财务消息或大型报表的安全且可靠的传输。</span><span class="sxs-lookup"><span data-stu-id="df594-120">The FileAct adapter for SWIFTNet provides secure and reliable transfer of files, such as batches of structured financial messages or large reports.</span></span> <span data-ttu-id="df594-121">典型的应用程序包括重复的信用额度传输如养老金或薪金付款、 证券增值信息报告和法规报告。</span><span class="sxs-lookup"><span data-stu-id="df594-121">Typical applications include repetitive credit transfers such as pension or salary payments, securities value-added information and reporting, and regulatory reporting.</span></span> <span data-ttu-id="df594-122">SWIFTNet FileAct 提供各种消息传送模式：</span><span class="sxs-lookup"><span data-stu-id="df594-122">SWIFTNet FileAct offers a variety of messaging modes:</span></span>  
  
- <span data-ttu-id="df594-123">**存储和转发文件传输。**</span><span class="sxs-lookup"><span data-stu-id="df594-123">**Store-and-forward file transfer.**</span></span> <span data-ttu-id="df594-124">SWIFTNet FileAct 存储和转发功能删除的不确定性和不便的担心在帖者都处于联机状态时传输文件。</span><span class="sxs-lookup"><span data-stu-id="df594-124">SWIFTNet FileAct’s store-and-forward capability removes the uncertainty and inconvenience of worrying about whether or not your correspondents are online at the time you transmit the file.</span></span> <span data-ttu-id="df594-125">接收方已准备好接收它，该文件是立即传递。</span><span class="sxs-lookup"><span data-stu-id="df594-125">The file is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="df594-126">因此，它提供将文件发送到大量的帖者，其中一些可能在不同时区的理想方式。</span><span class="sxs-lookup"><span data-stu-id="df594-126">As a result, it provides an ideal way to send files to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
- <span data-ttu-id="df594-127">**实时文件传输。**</span><span class="sxs-lookup"><span data-stu-id="df594-127">**Real-time file transfer.**</span></span> <span data-ttu-id="df594-128">实时消息传送提供成本较低的替代方法来存储和转发目标为帖者，在传输时处于联机状态的文件。</span><span class="sxs-lookup"><span data-stu-id="df594-128">Real-time messaging offers a lower-cost alternative to store and forward for files that are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="df594-129">因此它非常适合用于将文件发送到几个大型帖者或市场的基础结构。</span><span class="sxs-lookup"><span data-stu-id="df594-129">As a result it is ideal for sending files to a few large correspondents or market infrastructures.</span></span>  
  
- <span data-ttu-id="df594-130">**实时文件检索。**</span><span class="sxs-lookup"><span data-stu-id="df594-130">**Real-time file retrieval.**</span></span> <span data-ttu-id="df594-131">这是通常用于检索文件的基于工作站的系统上下文中，通常是在与 SWIFTNet 浏览一起交互服务。</span><span class="sxs-lookup"><span data-stu-id="df594-131">This is an interactive service typically used to retrieve files in the context of workstation-based systems and often in conjunction with SWIFTNet Browse.</span></span> <span data-ttu-id="df594-132">我们将支持此模式。</span><span class="sxs-lookup"><span data-stu-id="df594-132">We will support this mode.</span></span>  
  
  <span data-ttu-id="df594-133">（以文件的文件为单位） 的可选 SWIFTNet FileAct 功能包括：</span><span class="sxs-lookup"><span data-stu-id="df594-133">The optional SWIFTNet FileAct features (on a file by file basis) include:</span></span>  
  
- <span data-ttu-id="df594-134">**消息优先级。**</span><span class="sxs-lookup"><span data-stu-id="df594-134">**Message priority.**</span></span> <span data-ttu-id="df594-135">文件传输可以在消息中，以允许适当处理你的通讯对象标记为"紧急"。</span><span class="sxs-lookup"><span data-stu-id="df594-135">File transfers can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
- <span data-ttu-id="df594-136">**送达通知 （实时和存储转发模式）。**</span><span class="sxs-lookup"><span data-stu-id="df594-136">**Delivery notification (real-time and store-and-forward modes).**</span></span> <span data-ttu-id="df594-137">提供对响应方返回收到你的文件的确认消息。</span><span class="sxs-lookup"><span data-stu-id="df594-137">Provides confirmation that your correspondent received your file.</span></span>  
  
- <span data-ttu-id="df594-138">**发出和接收的不可否认。**</span><span class="sxs-lookup"><span data-stu-id="df594-138">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="df594-139">争议，如果允许 SWIFT 以确认所声称的那个，传输未成功进行。</span><span class="sxs-lookup"><span data-stu-id="df594-139">In case of dispute, allows SWIFT to confirm that the file transfer did take place as claimed.</span></span>  
  
  <span data-ttu-id="df594-140">标准 SWIFTNet FileAct 功能包括 SWIFTNet PKI 安全性<strong>。</strong></span><span class="sxs-lookup"><span data-stu-id="df594-140">The standard SWIFTNet FileAct features include SWIFTNet PKI security<strong>.</strong></span></span> <span data-ttu-id="df594-141">SWIFTNet FileAct SWIFTNet pki 保护，并提供消息身份验证和完整性控制。</span><span class="sxs-lookup"><span data-stu-id="df594-141">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
  <span data-ttu-id="df594-142">所有消息以及交换 SWIFTNet 上的文件会都进行一组通用的检查，以确保安全、 验证和平台的路由规则没有用户可以绕过。</span><span class="sxs-lookup"><span data-stu-id="df594-142">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="df594-143">SWIFTAlliance 网关 （压降） 应用程序执行这些检查。</span><span class="sxs-lookup"><span data-stu-id="df594-143">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df594-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="df594-144">See Also</span></span>  
 <span data-ttu-id="df594-145">[开始使用 FileAct 和 InterAct 适配器](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="df594-145">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="df594-146">[SWIFTNet 是什么？](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="df594-146">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="df594-147">InterAct 适配器概述</span><span class="sxs-lookup"><span data-stu-id="df594-147">What Is the InterAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)