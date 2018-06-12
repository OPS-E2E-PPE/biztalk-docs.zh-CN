---
title: RNIF 消息处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RosettaNet Implementation Framework (RNIF)
- RosettaNet, about RosettaNet
- RNIF
- RNIF, non-repudiation
- RNIF, BizTalk Accelerator for RosettaNet
- non-repudiation
- RNIF, about RNIF
- BizTalk Accelerator for RosettaNet, RNIF
- RosettaNet
ms.assetid: 994f15bc-765c-4220-8ab1-176919e9e821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810f673b9ae2cf9c6e1b64ccab6a6a541118cbca
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855520"
---
# <a name="rnif-message-processing"></a><span data-ttu-id="1a498-102">RNIF 消息处理</span><span class="sxs-lookup"><span data-stu-id="1a498-102">RNIF Message Processing</span></span>
<span data-ttu-id="1a498-103">RosettaNet 组织依据 RosettaNet 实现框架 (RNIF) 的规范定义消息交换。</span><span class="sxs-lookup"><span data-stu-id="1a498-103">The RosettaNet organization defines message exchange in the RosettaNet Implementation Framework (RNIF) specifications.</span></span> <span data-ttu-id="1a498-104">RNIF 定义如何集成系统将传输消息。</span><span class="sxs-lookup"><span data-stu-id="1a498-104">RNIF defines how integration systems will transport messages.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1a498-105"> 完全实现 RNIF 规范，将该功能添加到什么[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]本机提供的框。</span><span class="sxs-lookup"><span data-stu-id="1a498-105"> fully implements the RNIF specifications, adding that functionality to what [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] natively provides out-of-the-box.</span></span>  
  
<span data-ttu-id="1a498-106">RNIF 通信非常复杂。</span><span class="sxs-lookup"><span data-stu-id="1a498-106">RNIF communications are complex.</span></span> <span data-ttu-id="1a498-107">执行 RNIF 处理这些公共进程包括各种验证检查和复杂工作流逻辑。</span><span class="sxs-lookup"><span data-stu-id="1a498-107">The public processes that perform RNIF processing include a variety of validation checks and complex workflow logic.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1a498-108"> 本机提供此功能。</span><span class="sxs-lookup"><span data-stu-id="1a498-108"> provides this functionality natively.</span></span> <span data-ttu-id="1a498-109">这样，您便可使用 RosettaNet 兼容系统，而无需重新开发或维护 RNIF 逻辑。</span><span class="sxs-lookup"><span data-stu-id="1a498-109">This lets you use a RosettaNet-compliant system without developing or maintaining RNIF logic from scratch.</span></span>  
  
## <a name="btarn-support-for-rnif"></a><span data-ttu-id="1a498-110">BTARN 对 RNIF 的支持</span><span class="sxs-lookup"><span data-stu-id="1a498-110">BTARN Support for RNIF</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1a498-111"> 支持这两个版本的 RNIF: RNIF 1.1 和 RNIF 2.0 (V02.00.01)。</span><span class="sxs-lookup"><span data-stu-id="1a498-111"> supports both versions of RNIF: RNIF 1.1 and RNIF 2.0 (V02.00.01).</span></span> <span data-ttu-id="1a498-112">RNIF 2.0 增加了 RNIF 1.1 所不能支持的重要功能，包括加密、附件和同步事务。</span><span class="sxs-lookup"><span data-stu-id="1a498-112">RNIF 2.0 added significant functionality beyond that supported by RNIF 1.1, including encryption, attachments, and synchronous transactions.</span></span> <span data-ttu-id="1a498-113">RNIF 2.0 并不向后兼容 RNIF 1.1。</span><span class="sxs-lookup"><span data-stu-id="1a498-113">RNIF 2.0 is not backward compatible with RNIF 1.1.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1a498-114"> 可与 RosettaNet Ready RNIF 2.0 兼容。</span><span class="sxs-lookup"><span data-stu-id="1a498-114"> is RosettaNet Ready RNIF 2.0 compliant.</span></span>  
  
<span data-ttu-id="1a498-115">两个版本对 RosettaNet 消息的定义有所不同。</span><span class="sxs-lookup"><span data-stu-id="1a498-115">The two versions define the RosettaNet message differently.</span></span> <span data-ttu-id="1a498-116">有关不同的消息容器的详细信息，请参阅[RNIF 标准](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="1a498-116">For more information about the different message containers, see [RNIF Standard](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md).</span></span>  
  
<span data-ttu-id="1a498-117">集成系统执行 RNIF 传输 HTTP/HTTPS 和 SMTP;但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]实现仅 HTTP/HTTPS。</span><span class="sxs-lookup"><span data-stu-id="1a498-117">Integration systems perform RNIF transfer over HTTP/HTTPS and SMTP; however, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implements only HTTP/HTTPS.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1a498-118"> 不支持附件和同步事务中 RNIF 1.1。</span><span class="sxs-lookup"><span data-stu-id="1a498-118"> does not support attachments and synchronous transactions in RNIF 1.1.</span></span>  
  
### <a name="non-repudiation"></a><span data-ttu-id="1a498-119">不可否认性</span><span class="sxs-lookup"><span data-stu-id="1a498-119">Non-Repudiation</span></span>  
<span data-ttu-id="1a498-120">RNIF 标准包括对不可否认性的要求。</span><span class="sxs-lookup"><span data-stu-id="1a498-120">The RNIF standard includes a requirement for non-repudiation.</span></span> <span data-ttu-id="1a498-121">这涉及到将 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 接收或发送的所有消息的线路格式存储在不可否认性数据库中，这样，便可以合法地证明您已收到或发送了消息。</span><span class="sxs-lookup"><span data-stu-id="1a498-121">This involves storing the wire format of any message received or sent by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] in a non-repudiation database, so that you can prove legally that you have received or sent it.</span></span> <span data-ttu-id="1a498-122">为此，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]使用中的 MessageStorageIn 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]存档数据库对于传入消息和传出消息的同一数据库中的 MessageStorageOut 表。</span><span class="sxs-lookup"><span data-stu-id="1a498-122">For this purpose, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] uses the MessageStorageIn table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive database for incoming messages and the MessageStorageOut table in the same database for outgoing messages.</span></span>  
  
<span data-ttu-id="1a498-123">您可以在流程配置的配置文件中分别设置服务内容和消息确认的不可否认性要求。</span><span class="sxs-lookup"><span data-stu-id="1a498-123">You set non-repudiation requirements for service content and for acknowledgements separately in the process configuration profile.</span></span> <span data-ttu-id="1a498-124">如果你设置一个或两个**的起点和内容的不可否认性**和**不可否认性所需**选项到`True`，然后[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将存储以下数据：</span><span class="sxs-lookup"><span data-stu-id="1a498-124">If you set one or both of the **Non-Repudiation of Origin and Content** and **Non-Repudiation Required** options to `True`, then [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will store the following data:</span></span>  
  
|<span data-ttu-id="1a498-125">data</span><span class="sxs-lookup"><span data-stu-id="1a498-125">Data</span></span>|<span data-ttu-id="1a498-126">目录</span><span class="sxs-lookup"><span data-stu-id="1a498-126">Contents</span></span>|  
|----------|--------------|  
|<span data-ttu-id="1a498-127">RecordID</span><span class="sxs-lookup"><span data-stu-id="1a498-127">RecordID</span></span>|<span data-ttu-id="1a498-128">存储消息的唯一专用 ID</span><span class="sxs-lookup"><span data-stu-id="1a498-128">Proprietary unique ID of the stored message</span></span>|  
|<span data-ttu-id="1a498-129">MessageCategory</span><span class="sxs-lookup"><span data-stu-id="1a498-129">MessageCategory</span></span>|<span data-ttu-id="1a498-130">请求 (0)、响应 (1) 或信号 (2)</span><span class="sxs-lookup"><span data-stu-id="1a498-130">Request (0), Response (1), or Signal (2)</span></span>|  
|<span data-ttu-id="1a498-131">DestinationParty</span><span class="sxs-lookup"><span data-stu-id="1a498-131">DestinationParty</span></span>|<span data-ttu-id="1a498-132">目标参与方名称</span><span class="sxs-lookup"><span data-stu-id="1a498-132">Name of the destination party</span></span>|  
|<span data-ttu-id="1a498-133">SourceParty</span><span class="sxs-lookup"><span data-stu-id="1a498-133">SourceParty</span></span>|<span data-ttu-id="1a498-134">源参与方名称</span><span class="sxs-lookup"><span data-stu-id="1a498-134">Name of the source party</span></span>|  
|<span data-ttu-id="1a498-135">PIPCode</span><span class="sxs-lookup"><span data-stu-id="1a498-135">PIPCode</span></span>|<span data-ttu-id="1a498-136">例如，PIP3A4</span><span class="sxs-lookup"><span data-stu-id="1a498-136">For example, PIP3A4</span></span>|  
|<span data-ttu-id="1a498-137">PIPVersion</span><span class="sxs-lookup"><span data-stu-id="1a498-137">PIPVersion</span></span>|<span data-ttu-id="1a498-138">例如，V02.00</span><span class="sxs-lookup"><span data-stu-id="1a498-138">For example, V02.00</span></span>|  
|<span data-ttu-id="1a498-139">MessageContent</span><span class="sxs-lookup"><span data-stu-id="1a498-139">MessageContent</span></span>|<span data-ttu-id="1a498-140">二进制格式的消息</span><span class="sxs-lookup"><span data-stu-id="1a498-140">Message in binary format</span></span>|  
|<span data-ttu-id="1a498-141">MessageTrackingID</span><span class="sxs-lookup"><span data-stu-id="1a498-141">MessageTrackingID</span></span>|<span data-ttu-id="1a498-142">消息的消息跟踪 ID</span><span class="sxs-lookup"><span data-stu-id="1a498-142">Message tracking ID of the message</span></span>|  
|<span data-ttu-id="1a498-143">PIPInstanceID</span><span class="sxs-lookup"><span data-stu-id="1a498-143">PIPInstanceID</span></span>|<span data-ttu-id="1a498-144">流程的 PIP 实例 ID</span><span class="sxs-lookup"><span data-stu-id="1a498-144">PIP instance ID of the process</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a498-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a498-145">See Also</span></span>  
 <span data-ttu-id="1a498-146">[BizTalk Accelerator for RosettaNet 将添加到 BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="1a498-146">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="1a498-147">PIP 实现</span><span class="sxs-lookup"><span data-stu-id="1a498-147">PIP Implementation</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)
