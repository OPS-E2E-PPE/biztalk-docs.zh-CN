---
title: FIN 响应类型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, response types
- deploying, schemas
- FIN Response Reconciliation, message types
- FRR, deploying schemas
- schemas, deploying
- FIN Response Reconciliation, response types
- messages, message types
- response types [FIN Response Reconciliation]
ms.assetid: a6ef2f20-08ab-40d3-a0a5-cc4048ce0987
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54c890a5e0f51207cce1897b10095a87ae438793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208061"
---
# <a name="fin-response-types"></a><span data-ttu-id="bdba5-102">FIN 响应类型</span><span class="sxs-lookup"><span data-stu-id="bdba5-102">FIN Response Types</span></span>
<span data-ttu-id="bdba5-103">FIN 响应对帐 (FRR) 来协调对任何类别 0 到 9 SWIFT FIN 消息的响应。</span><span class="sxs-lookup"><span data-stu-id="bdba5-103">FIN Response Reconciliation (FRR) reconciles responses to any Category 0 to 9 SWIFT FIN message.</span></span> <span data-ttu-id="bdba5-104">SWIFT FIN 应用程序始终将至少一个，并且可能不只一个，确认 (ACK) 发送响应这些 FIN 消息之一，或否定确认 （否认）。</span><span class="sxs-lookup"><span data-stu-id="bdba5-104">In response to one of these FIN messages, the SWIFT FIN application always sends at least one, and possibly more than one, acknowledgment (ACK) or negative acknowledgment (NAK).</span></span> <span data-ttu-id="bdba5-105">下表显示的消息类型的出站和入站 （响应） FRR 所处理的消息。</span><span class="sxs-lookup"><span data-stu-id="bdba5-105">The following table shows the message types of the outbound and inbound (response) messages processed by FRR.</span></span>  
  
|<span data-ttu-id="bdba5-106">出站 /</span><span class="sxs-lookup"><span data-stu-id="bdba5-106">Outbound/</span></span><br /><br /> <span data-ttu-id="bdba5-107">入站</span><span class="sxs-lookup"><span data-stu-id="bdba5-107">inbound</span></span>|<span data-ttu-id="bdba5-108">消息类型</span><span class="sxs-lookup"><span data-stu-id="bdba5-108">Message type</span></span>|<span data-ttu-id="bdba5-109">消息状态</span><span class="sxs-lookup"><span data-stu-id="bdba5-109">Message status</span></span>|  
|----------------------------|------------------|--------------------|  
|<span data-ttu-id="bdba5-110">出站</span><span class="sxs-lookup"><span data-stu-id="bdba5-110">Outbound</span></span>|<span data-ttu-id="bdba5-111">所有类别 0 到 9 SWIFT FIN 消息类型</span><span class="sxs-lookup"><span data-stu-id="bdba5-111">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="bdba5-112">N/A</span><span class="sxs-lookup"><span data-stu-id="bdba5-112">N/A</span></span>|  
|<span data-ttu-id="bdba5-113">入站</span><span class="sxs-lookup"><span data-stu-id="bdba5-113">Inbound</span></span>|<span data-ttu-id="bdba5-114">MQ 系列平移/NAN （MQ 系列传输级 ACK/否认）</span><span class="sxs-lookup"><span data-stu-id="bdba5-114">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="bdba5-115">MQSeries 传输确认</span><span class="sxs-lookup"><span data-stu-id="bdba5-115">MQSeries transport acknowledgment</span></span>|  
||<span data-ttu-id="bdba5-116">MT010 （未送达警告）</span><span class="sxs-lookup"><span data-stu-id="bdba5-116">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="bdba5-117">SWIFT 成功发送原始消息到合作伙伴，但不合作伙伴接收消息会指示。</span><span class="sxs-lookup"><span data-stu-id="bdba5-117">SWIFT successfully sent the original message to the partner, but has no indication that the partner received the message.</span></span> <span data-ttu-id="bdba5-118">如果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收多个未送达警告 (NDW) 消息，它循环并等待下一步的预期消息。</span><span class="sxs-lookup"><span data-stu-id="bdba5-118">If [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives multiple Non-Delivery Warning (NDW) messages, it loops and waits for the next expected message.</span></span>|  
||<span data-ttu-id="bdba5-119">MT011 （传递通知）</span><span class="sxs-lookup"><span data-stu-id="bdba5-119">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="bdba5-120">已成功发送原始 SWIFT 向合作伙伴，发送消息，以及接收合作伙伴接收消息的指示。</span><span class="sxs-lookup"><span data-stu-id="bdba5-120">SWIFT successfully sent the original message to the partner, and received an indication that the partner received the message.</span></span>|  
||<span data-ttu-id="bdba5-121">MT012 （发件人通知）</span><span class="sxs-lookup"><span data-stu-id="bdba5-121">MT012 (Sender Notification)</span></span>|<span data-ttu-id="bdba5-122">SWIFT 成功接收来自的原始消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bdba5-122">SWIFT successfully received the original message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>|  
||<span data-ttu-id="bdba5-123">MT015 （DNK 或延迟的否认）</span><span class="sxs-lookup"><span data-stu-id="bdba5-123">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="bdba5-124">SWIFT 尚未成功发送原始消息到合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="bdba5-124">SWIFT has not successfully sent the original message to the partner.</span></span>|  
||<span data-ttu-id="bdba5-125">MT019 （中止通知）</span><span class="sxs-lookup"><span data-stu-id="bdba5-125">MT019 (Abort Notification)</span></span>|<span data-ttu-id="bdba5-126">在 SWIFT 中止消息传输。</span><span class="sxs-lookup"><span data-stu-id="bdba5-126">Message transmission aborted at SWIFT.</span></span>|  
||<span data-ttu-id="bdba5-127">MTS21_FIN_ACKNAK （确认消息或否定确认 （ACK/否认） LT 发送的 FIN 消息的）</span><span class="sxs-lookup"><span data-stu-id="bdba5-127">MTS21_FIN_ACKNAK (Acknowledgment or negative acknowledgment of a FIN message sent by an LT (ACK/NAK))</span></span>|<span data-ttu-id="bdba5-128">SWIFT 成功或失败收到来自的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bdba5-128">SWIFT successfully or unsuccessfully received the message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="bdba5-129">此消息介绍这两种情况。</span><span class="sxs-lookup"><span data-stu-id="bdba5-129">This message covers both of these cases.</span></span> <span data-ttu-id="bdba5-130">它是一个 ACK 还是否认已确定消息 ("0"ACK) 和"1"的否认 451 字段中的值。</span><span class="sxs-lookup"><span data-stu-id="bdba5-130">Whether it is an ACK or a NAK is determined by the value in the 451 field of the message ("0" for ACK and "1" for NAK).</span></span> <span data-ttu-id="bdba5-131">这将是第一个响应发送回[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bdba5-131">This will be the first response delivered back to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>|  
  
## <a name="deployment-of-schemas-for-frr"></a><span data-ttu-id="bdba5-132">FRR 架构的部署</span><span class="sxs-lookup"><span data-stu-id="bdba5-132">Deployment of Schemas for FRR</span></span>  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="bdba5-133">安装程序将部署 FrrSchemas.dll 中的所有系统级消息的架构 （如上面的表中所示）。</span><span class="sxs-lookup"><span data-stu-id="bdba5-133"> setup deploys schemas in FrrSchemas.dll for all system-level messages (as shown in the table above).</span></span> <span data-ttu-id="bdba5-134">FRR 业务流程要求要部署这些架构。</span><span class="sxs-lookup"><span data-stu-id="bdba5-134">The FRR orchestration requires these schemas to be deployed.</span></span> <span data-ttu-id="bdba5-135">因为[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将部署中 FrrSchemas.dll 这些架构，你不是必需的并且不是，必须部署在其他项目中的这些架构。</span><span class="sxs-lookup"><span data-stu-id="bdba5-135">Because [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup deploys these schemas in FrrSchemas.dll, you do not have to, and must not, deploy these schemas in another project.</span></span> <span data-ttu-id="bdba5-136">执行此操作将生成错误。</span><span class="sxs-lookup"><span data-stu-id="bdba5-136">Doing so will generate an error.</span></span>  
  
 <span data-ttu-id="bdba5-137">FRRSchemas.dll 包括以下架构：</span><span class="sxs-lookup"><span data-stu-id="bdba5-137">FRRSchemas.dll includes the following schemas:</span></span>  
  
-   <span data-ttu-id="bdba5-138">TransportAck</span><span class="sxs-lookup"><span data-stu-id="bdba5-138">TransportAck</span></span>  
  
-   <span data-ttu-id="bdba5-139">MT010</span><span class="sxs-lookup"><span data-stu-id="bdba5-139">MT010</span></span>  
  
-   <span data-ttu-id="bdba5-140">MT011</span><span class="sxs-lookup"><span data-stu-id="bdba5-140">MT011</span></span>  
  
-   <span data-ttu-id="bdba5-141">MT012</span><span class="sxs-lookup"><span data-stu-id="bdba5-141">MT012</span></span>  
  
-   <span data-ttu-id="bdba5-142">MT015</span><span class="sxs-lookup"><span data-stu-id="bdba5-142">MT015</span></span>  
  
-   <span data-ttu-id="bdba5-143">MT019</span><span class="sxs-lookup"><span data-stu-id="bdba5-143">MT019</span></span>  
  
-   <span data-ttu-id="bdba5-144">MTS21_FIN_ACKNAK</span><span class="sxs-lookup"><span data-stu-id="bdba5-144">MTS21_FIN_ACKNAK</span></span>