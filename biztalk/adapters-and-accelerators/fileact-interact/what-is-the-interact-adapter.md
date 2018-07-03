---
title: 什么是 InterAct 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a09063df-c6c4-41b9-96a1-e5059777fa72
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc2f29f08edda2fb8d2b0cf05f3ba5b2b786e8f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967078"
---
# <a name="what-is-the-interact-adapter"></a><span data-ttu-id="64581-103">什么是 InterAct 适配器？</span><span class="sxs-lookup"><span data-stu-id="64581-103">What Is the InterAct Adapter?</span></span>
<span data-ttu-id="64581-104">SWIFTNet 交互适配器传输的消息提供 BizTalk Server 和 SWIFT Secure IP Network (SIPN) 之间的连接。</span><span class="sxs-lookup"><span data-stu-id="64581-104">The InterAct Adapter for SWIFTNet provides connectivity between BizTalk Server and the SWIFT Secure IP Network (SIPN) for the transfer of messages.</span></span> <span data-ttu-id="64581-105">SIPN 互联金融机构、 金融业基础结构和客户的安全专用网络上传输消息和文件。</span><span class="sxs-lookup"><span data-stu-id="64581-105">The SIPN transfers messages and files over a secure private network which interconnects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="64581-106">InterAct 适配器使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) s 要连接到 SIPN。</span><span class="sxs-lookup"><span data-stu-id="64581-106">The InterAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="64581-107">SWIFTNet 交互提供了安全且可靠的单个结构化的财务消息的交换。</span><span class="sxs-lookup"><span data-stu-id="64581-107">SWIFTNet InterAct provides secure and reliable exchange of individual structured financial messages.</span></span> <span data-ttu-id="64581-108">在客户之间，但还从消息到消息，SWIFT 客户的消息传送要求各不相同。</span><span class="sxs-lookup"><span data-stu-id="64581-108">SWIFT customers’ messaging requirements vary from customer to customer but also from message to message.</span></span>  
  
 <span data-ttu-id="64581-109">它支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="64581-109">It supports the following functionality:</span></span>  
  
- <span data-ttu-id="64581-110">PKI 安全性</span><span class="sxs-lookup"><span data-stu-id="64581-110">PKI security</span></span>  
  
- <span data-ttu-id="64581-111">消息验证</span><span class="sxs-lookup"><span data-stu-id="64581-111">Message validation</span></span>  
  
- <span data-ttu-id="64581-112">可配置的中央路由</span><span class="sxs-lookup"><span data-stu-id="64581-112">Configurable central routing</span></span>  
  
- <span data-ttu-id="64581-113">消息优先级</span><span class="sxs-lookup"><span data-stu-id="64581-113">Message priority</span></span>  
  
- <span data-ttu-id="64581-114">为存储和转发消息的送达通知</span><span class="sxs-lookup"><span data-stu-id="64581-114">Delivery notification for store and forward messages</span></span>  
  
- <span data-ttu-id="64581-115">不可否认性的回执和句子。</span><span class="sxs-lookup"><span data-stu-id="64581-115">Non-repudiation of emission and receipt.</span></span>  
  
  <span data-ttu-id="64581-116">使用交互适配器为 SWIFTNet 与外部提供的应用程序使用的交互功能。</span><span class="sxs-lookup"><span data-stu-id="64581-116">You use the InterAct Adapter for SWIFTNet with externally supplied applications to utilize the features of InterAct.</span></span> <span data-ttu-id="64581-117">此适配器并不知道要传输，并将不审核也不会验证消息，除了 exchange 基元的内容的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="64581-117">This adapter has no knowledge of the contents of the messages to be transferred, and will not audit nor validate the contents of the messages, except for the exchange primitives.</span></span>  
  
## <a name="interact-message-exchange"></a><span data-ttu-id="64581-118">InterAct 消息交换</span><span class="sxs-lookup"><span data-stu-id="64581-118">InterAct Message Exchange</span></span>  
 <span data-ttu-id="64581-119">SWIFTNet 交互提供了安全且可靠的单个结构化的财务消息的交换。</span><span class="sxs-lookup"><span data-stu-id="64581-119">SWIFTNet InterAct provides secure and reliable exchange of individual structured financial messages.</span></span> <span data-ttu-id="64581-120">在客户之间，但还从消息到消息，SWIFT 客户的消息传送要求各不相同。</span><span class="sxs-lookup"><span data-stu-id="64581-120">SWIFT customers’ messaging requirements vary from customer to customer but also from message to message.</span></span> <span data-ttu-id="64581-121">SWIFTNet 交互提供了广泛的电信模式：</span><span class="sxs-lookup"><span data-stu-id="64581-121">SWIFTNet InterAct offers you a broad range of telecommunication modes:</span></span>  
  
- <span data-ttu-id="64581-122">**存储和转发消息传递。**</span><span class="sxs-lookup"><span data-stu-id="64581-122">**Store-and-forward messaging.**</span></span> <span data-ttu-id="64581-123">SWIFTNet 交互的存储和转发功能专为发送到大量的帖者，许多用户可能不处于联机状态时的传输的消息。</span><span class="sxs-lookup"><span data-stu-id="64581-123">SWIFTNet InterAct’s store-and-forward capability is designed for messages destined for a large number of correspondents, many of whom may not be online at the time of transmission.</span></span> <span data-ttu-id="64581-124">它删除的不确定性和的担心在帖者处于联机状态时将消息发送给您带来不便。</span><span class="sxs-lookup"><span data-stu-id="64581-124">It removes the uncertainty and inconvenience of worrying about whether or not your correspondents are on-line at the time you send the message.</span></span> <span data-ttu-id="64581-125">一旦接收方已准备好接收其传递消息。</span><span class="sxs-lookup"><span data-stu-id="64581-125">The message is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="64581-126">因此，它提供了将单个指令、 确认和报告发送到大量的帖者，其中一些可能在不同时区的理想方法。</span><span class="sxs-lookup"><span data-stu-id="64581-126">As a result, it provides an ideal way to send individual instructions, confirmations and reports to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
- <span data-ttu-id="64581-127">**实时消息传送。**</span><span class="sxs-lookup"><span data-stu-id="64581-127">**Real-time messaging.**</span></span> <span data-ttu-id="64581-128">实时消息传送提供了低成本替代方法来存储和转发的消息的目标为帖者，在传输时处于联机状态。</span><span class="sxs-lookup"><span data-stu-id="64581-128">Real-time messaging offers a low-cost alternative to store and forward for messages which are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="64581-129">因此，它非常适合于几个大型帖者或市场的基础结构将消息发送单个指令、 确认和报告、。</span><span class="sxs-lookup"><span data-stu-id="64581-129">As a result, it is ideal for sending individual instructions, confirmations and reports, to a few large correspondents or for messages to market infrastructures.</span></span>  
  
  <span data-ttu-id="64581-130">可选的 SWIFTNet 交互功能 （在消息由消息的基础） 包括：</span><span class="sxs-lookup"><span data-stu-id="64581-130">The optional SWIFTNet InterAct features (on a message by message basis) include:</span></span>  
  
- <span data-ttu-id="64581-131">**消息优先级。**</span><span class="sxs-lookup"><span data-stu-id="64581-131">**Message priority.**</span></span> <span data-ttu-id="64581-132">这些消息可以在消息中，以允许适当处理你的通讯对象标记为"紧急"。</span><span class="sxs-lookup"><span data-stu-id="64581-132">Messages can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
- <span data-ttu-id="64581-133">**送达通知 （存储和转发模式）。**</span><span class="sxs-lookup"><span data-stu-id="64581-133">**Delivery notification (store-and-forward mode).**</span></span> <span data-ttu-id="64581-134">提供对响应方返回收到您的消息的确认消息</span><span class="sxs-lookup"><span data-stu-id="64581-134">Provides confirmation that your correspondent received your message</span></span>  
  
- <span data-ttu-id="64581-135">**发出和接收的不可否认。**</span><span class="sxs-lookup"><span data-stu-id="64581-135">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="64581-136">争议，如果允许 SWIFT 确认的消息交换未进行，所声称的那个。</span><span class="sxs-lookup"><span data-stu-id="64581-136">In case of dispute, allows SWIFT to confirm that the message exchange did take place as claimed.</span></span>  
  
  <span data-ttu-id="64581-137">SWIFTNet 进行交互的标准功能包括 SWIFTNet PKI 安全性。</span><span class="sxs-lookup"><span data-stu-id="64581-137">The standard SWIFTNet InterAct features include SWIFTNet PKI security.</span></span> <span data-ttu-id="64581-138">SWIFTNet FileAct SWIFTNet pki 保护，并提供消息身份验证和完整性控制。</span><span class="sxs-lookup"><span data-stu-id="64581-138">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
  <span data-ttu-id="64581-139">所有消息以及交换 SWIFTNet 上的文件会都进行一组通用的检查，以确保安全、 验证和平台的路由规则没有用户可以绕过。</span><span class="sxs-lookup"><span data-stu-id="64581-139">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="64581-140">SWIFTAlliance 网关 （压降） 应用程序执行这些检查。</span><span class="sxs-lookup"><span data-stu-id="64581-140">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64581-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="64581-141">See Also</span></span>  
 <span data-ttu-id="64581-142">[开始使用 FileAct 和 InterAct 适配器](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="64581-142">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="64581-143">[SWIFTNet 是什么？](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="64581-143">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="64581-144">FileAct 适配器概述</span><span class="sxs-lookup"><span data-stu-id="64581-144">What Is the FileAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)