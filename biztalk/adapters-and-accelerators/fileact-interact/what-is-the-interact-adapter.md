---
title: "什么是交互适配器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a09063df-c6c4-41b9-96a1-e5059777fa72
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25877b95a440faef802d3d2ba7861687d7e4b108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-interact-adapter"></a><span data-ttu-id="e1bcd-103">什么是交互适配器？</span><span class="sxs-lookup"><span data-stu-id="e1bcd-103">What Is the InterAct Adapter?</span></span>
<span data-ttu-id="e1bcd-104">SWIFTNet 交互适配器传输的消息提供 BizTalk Server 和 SWIFT 保护 IP 网络 (SIPN) 之间的连接。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-104">The InterAct Adapter for SWIFTNet provides connectivity between BizTalk Server and the SWIFT Secure IP Network (SIPN) for the transfer of messages.</span></span> <span data-ttu-id="e1bcd-105">SIPN 互连金融机构、 金融业基础结构和客户的安全专用网络上传输消息和文件。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-105">The SIPN transfers messages and files over a secure private network which interconnects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="e1bcd-106">交互适配器使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) s 要连接到 SIPN。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-106">The InterAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="e1bcd-107">SWIFTNet 交互提供安全、 可靠单个结构化的财务消息交换。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-107">SWIFTNet InterAct provides secure and reliable exchange of individual structured financial messages.</span></span> <span data-ttu-id="e1bcd-108">客户客户，但还从消息到消息，SWIFT 客户的消息传送要求各不相同。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-108">SWIFT customers’ messaging requirements vary from customer to customer but also from message to message.</span></span>  
  
 <span data-ttu-id="e1bcd-109">它支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="e1bcd-109">It supports the following functionality:</span></span>  
  
-   <span data-ttu-id="e1bcd-110">PKI 安全性</span><span class="sxs-lookup"><span data-stu-id="e1bcd-110">PKI security</span></span>  
  
-   <span data-ttu-id="e1bcd-111">消息验证</span><span class="sxs-lookup"><span data-stu-id="e1bcd-111">Message validation</span></span>  
  
-   <span data-ttu-id="e1bcd-112">可配置的中央路由</span><span class="sxs-lookup"><span data-stu-id="e1bcd-112">Configurable central routing</span></span>  
  
-   <span data-ttu-id="e1bcd-113">消息优先级</span><span class="sxs-lookup"><span data-stu-id="e1bcd-113">Message priority</span></span>  
  
-   <span data-ttu-id="e1bcd-114">应用商店应用和转发的消息传递通知</span><span class="sxs-lookup"><span data-stu-id="e1bcd-114">Delivery notification for store and forward messages</span></span>  
  
-   <span data-ttu-id="e1bcd-115">不可否认性发出和接收。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-115">Non-repudiation of emission and receipt.</span></span>  
  
 <span data-ttu-id="e1bcd-116">使用交互适配器 SWIFTNet 与外部提供的应用程序以利用交互的功能。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-116">You use the InterAct Adapter for SWIFTNet with externally supplied applications to utilize the features of InterAct.</span></span> <span data-ttu-id="e1bcd-117">此适配器程序不知道要传输，并将审核或未验证的消息，但 exchange 基元除外的内容的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-117">This adapter has no knowledge of the contents of the messages to be transferred, and will not audit nor validate the contents of the messages, except for the exchange primitives.</span></span>  
  
## <a name="interact-message-exchange"></a><span data-ttu-id="e1bcd-118">交互消息交换</span><span class="sxs-lookup"><span data-stu-id="e1bcd-118">InterAct Message Exchange</span></span>  
 <span data-ttu-id="e1bcd-119">SWIFTNet 交互提供安全、 可靠单个结构化的财务消息交换。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-119">SWIFTNet InterAct provides secure and reliable exchange of individual structured financial messages.</span></span> <span data-ttu-id="e1bcd-120">客户客户，但还从消息到消息，SWIFT 客户的消息传送要求各不相同。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-120">SWIFT customers’ messaging requirements vary from customer to customer but also from message to message.</span></span> <span data-ttu-id="e1bcd-121">SWIFTNet 交互提供广泛的电信模式：</span><span class="sxs-lookup"><span data-stu-id="e1bcd-121">SWIFTNet InterAct offers you a broad range of telecommunication modes:</span></span>  
  
-   <span data-ttu-id="e1bcd-122">**存储转发消息传送。**</span><span class="sxs-lookup"><span data-stu-id="e1bcd-122">**Store-and-forward messaging.**</span></span> <span data-ttu-id="e1bcd-123">SWIFTNet 交互的存储和转发功能旨在用于消息发送到大量的通讯对象，其中许多员工可能不处于联机状态的传输时间。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-123">SWIFTNet InterAct’s store-and-forward capability is designed for messages destined for a large number of correspondents, many of whom may not be online at the time of transmission.</span></span> <span data-ttu-id="e1bcd-124">它会删除的不确定性和不便担心你的通讯对象处于联机状态时发送消息。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-124">It removes the uncertainty and inconvenience of worrying about whether or not your correspondents are on-line at the time you send the message.</span></span> <span data-ttu-id="e1bcd-125">一旦接收方准备好接收它，邮件将被传递。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-125">The message is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="e1bcd-126">因此，它提供了将单个说明、 确认和报表发送到大量通讯对象，其中一些可能在不同时区的理想途径。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-126">As a result, it provides an ideal way to send individual instructions, confirmations and reports to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
-   <span data-ttu-id="e1bcd-127">**实时消息传递。**</span><span class="sxs-lookup"><span data-stu-id="e1bcd-127">**Real-time messaging.**</span></span> <span data-ttu-id="e1bcd-128">实时消息传递提供低成本替代对其进行存储和转发的消息都以在传输时处于联机状态的通讯对象为目标。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-128">Real-time messaging offers a low-cost alternative to store and forward for messages which are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="e1bcd-129">因此，它非常适合于发送单个说明、 确认和报表，为几大通讯对象或消息推向市场基础结构。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-129">As a result, it is ideal for sending individual instructions, confirmations and reports, to a few large correspondents or for messages to market infrastructures.</span></span>  
  
 <span data-ttu-id="e1bcd-130">（在消息的消息的基础） 的可选 SWIFTNet 交互功能包括：</span><span class="sxs-lookup"><span data-stu-id="e1bcd-130">The optional SWIFTNet InterAct features (on a message by message basis) include:</span></span>  
  
-   <span data-ttu-id="e1bcd-131">**消息优先级。**</span><span class="sxs-lookup"><span data-stu-id="e1bcd-131">**Message priority.**</span></span> <span data-ttu-id="e1bcd-132">在消息中，以允许适当处理你的通讯对象，可以将消息标记为"紧急"。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-132">Messages can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
-   <span data-ttu-id="e1bcd-133">**传递通知 （存储转发模式）。**</span><span class="sxs-lookup"><span data-stu-id="e1bcd-133">**Delivery notification (store-and-forward mode).**</span></span> <span data-ttu-id="e1bcd-134">提供你通信者接收消息的确认</span><span class="sxs-lookup"><span data-stu-id="e1bcd-134">Provides confirmation that your correspondent received your message</span></span>  
  
-   <span data-ttu-id="e1bcd-135">**不可否认性发出和接收。**</span><span class="sxs-lookup"><span data-stu-id="e1bcd-135">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="e1bcd-136">发生争议，允许 SWIFT 以确认的消息交换未进行，所声称的那个。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-136">In case of dispute, allows SWIFT to confirm that the message exchange did take place as claimed.</span></span>  
  
 <span data-ttu-id="e1bcd-137">标准 SWIFTNet 交互功能包括 SWIFTNet PKI 安全性。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-137">The standard SWIFTNet InterAct features include SWIFTNet PKI security.</span></span> <span data-ttu-id="e1bcd-138">SWIFTNet FileAct 使用 SWIFTNet PKI 进行了保护，并提供消息身份验证和完整性控件。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-138">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
 <span data-ttu-id="e1bcd-139">所有消息和交换 SWIFTNet 上的文件都对一组通用的检查，以确保安全、 验证和平台的路由规则没有用户可以绕过。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-139">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="e1bcd-140">SWIFTAlliance 网关 （压降） 应用程序执行这些检查。</span><span class="sxs-lookup"><span data-stu-id="e1bcd-140">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bcd-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1bcd-141">See Also</span></span>  
 <span data-ttu-id="e1bcd-142">[Getting Started with FileAct 和交互适配器](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="e1bcd-142">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="e1bcd-143">[什么是 SWIFTNet？](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="e1bcd-143">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="e1bcd-144">什么是 FileAct 适配器？</span><span class="sxs-lookup"><span data-stu-id="e1bcd-144">What Is the FileAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)