---
title: 用于接收 Idoc 消息上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, message context properties for receiving
ms.assetid: fadb2284-2f55-49c2-bae9-95325f1be539
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5468a1944ecfb4e2ae3da2ded5d941d19ac37712
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373262"
---
# <a name="message-context-properties-for-receiving-idocs"></a><span data-ttu-id="5d6af-102">用于接收 Idoc 的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="5d6af-102">Message Context Properties for Receiving IDOCs</span></span>
<span data-ttu-id="5d6af-103">用于接收 IDOC 使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持以下消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="5d6af-103">For receiving an IDOC using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following message context properties.</span></span>  
  
 <span data-ttu-id="5d6af-104">**IDOC 控制记录的属性。**</span><span class="sxs-lookup"><span data-stu-id="5d6af-104">**IDOC Control Record properties.**</span></span>  
  
- <span data-ttu-id="5d6af-105">**TABNAM** -表结构的名称</span><span class="sxs-lookup"><span data-stu-id="5d6af-105">**TABNAM** - Name of table structure</span></span>  
  
- <span data-ttu-id="5d6af-106">**MANDT** -客户端</span><span class="sxs-lookup"><span data-stu-id="5d6af-106">**MANDT** - Client</span></span>  
  
- <span data-ttu-id="5d6af-107">**DOCNUM** -IDOC 号码</span><span class="sxs-lookup"><span data-stu-id="5d6af-107">**DOCNUM** - IDOC number</span></span>  
  
- <span data-ttu-id="5d6af-108">**DOCREL** -SAP 的 IDOC 版本</span><span class="sxs-lookup"><span data-stu-id="5d6af-108">**DOCREL** - SAP Release for IDOC</span></span>  
  
- <span data-ttu-id="5d6af-109">**状态**-IDOC 的状态</span><span class="sxs-lookup"><span data-stu-id="5d6af-109">**STATUS** - Status of IDOC</span></span>  
  
- <span data-ttu-id="5d6af-110">**直接**-方向</span><span class="sxs-lookup"><span data-stu-id="5d6af-110">**DIRECT** - Direction</span></span>  
  
- <span data-ttu-id="5d6af-111">**OUTMOD** -输出模式</span><span class="sxs-lookup"><span data-stu-id="5d6af-111">**OUTMOD** - Output mode</span></span>  
  
- <span data-ttu-id="5d6af-112">**表达**-入站处理中重写</span><span class="sxs-lookup"><span data-stu-id="5d6af-112">**EXPRSS** - Overriding in inbound processing</span></span>  
  
- <span data-ttu-id="5d6af-113">**测试**-测试标志</span><span class="sxs-lookup"><span data-stu-id="5d6af-113">**TEST** - Test flag</span></span>  
  
- <span data-ttu-id="5d6af-114">**IDOCTYP** -基本类型的名称</span><span class="sxs-lookup"><span data-stu-id="5d6af-114">**IDOCTYP** - Name of basic type</span></span>  
  
- <span data-ttu-id="5d6af-115">**CIMTYP** -扩展 （由客户定义）</span><span class="sxs-lookup"><span data-stu-id="5d6af-115">**CIMTYP** - Extension (defined by customer)</span></span>  
  
- <span data-ttu-id="5d6af-116">**MESTYP** -消息类型</span><span class="sxs-lookup"><span data-stu-id="5d6af-116">**MESTYP** - Message type</span></span>  
  
- <span data-ttu-id="5d6af-117">**MESCOD** -消息代码</span><span class="sxs-lookup"><span data-stu-id="5d6af-117">**MESCOD** - Message code</span></span>  
  
- <span data-ttu-id="5d6af-118">**MESFCT** -消息函数</span><span class="sxs-lookup"><span data-stu-id="5d6af-118">**MESFCT** - Message function</span></span>  
  
- <span data-ttu-id="5d6af-119">**标准**-EDI 标准，标志</span><span class="sxs-lookup"><span data-stu-id="5d6af-119">**STD** - EDI standard, flag</span></span>  
  
- <span data-ttu-id="5d6af-120">**STDVRS** -EDI 标准、 版本和发行版本</span><span class="sxs-lookup"><span data-stu-id="5d6af-120">**STDVRS** - EDI standard, version and release</span></span>  
  
- <span data-ttu-id="5d6af-121">**STDMES**的 EDI 消息类型</span><span class="sxs-lookup"><span data-stu-id="5d6af-121">**STDMES** - EDI message type</span></span>  
  
- <span data-ttu-id="5d6af-122">**SNDPOR** -发件人端口 （SAP 系统，外部子系统）</span><span class="sxs-lookup"><span data-stu-id="5d6af-122">**SNDPOR** - Sender port (SAP System, external subsystem)</span></span>  
  
- <span data-ttu-id="5d6af-123">**SNDPRT** -合作伙伴的发送程序类型</span><span class="sxs-lookup"><span data-stu-id="5d6af-123">**SNDPRT** - Partner type of sender</span></span>  
  
- <span data-ttu-id="5d6af-124">**SNDPFC** -合作伙伴的发件人的函数</span><span class="sxs-lookup"><span data-stu-id="5d6af-124">**SNDPFC** - Partner Function of Sender</span></span>  
  
- <span data-ttu-id="5d6af-125">**SNDPRN** -合作伙伴的发送方数</span><span class="sxs-lookup"><span data-stu-id="5d6af-125">**SNDPRN** - Partner Number of Sender</span></span>  
  
- <span data-ttu-id="5d6af-126">**SNDSAD** -发件人地址 (SADR)</span><span class="sxs-lookup"><span data-stu-id="5d6af-126">**SNDSAD** - Sender address (SADR)</span></span>  
  
- <span data-ttu-id="5d6af-127">**SNDLAD** -逻辑发件人地址</span><span class="sxs-lookup"><span data-stu-id="5d6af-127">**SNDLAD** - Logical address of sender</span></span>  
  
- <span data-ttu-id="5d6af-128">**RCVPOR** -接收端口</span><span class="sxs-lookup"><span data-stu-id="5d6af-128">**RCVPOR** - Receiver port</span></span>  
  
- <span data-ttu-id="5d6af-129">**RCVPRT** -接收方的合作伙伴类型</span><span class="sxs-lookup"><span data-stu-id="5d6af-129">**RCVPRT** - Partner Type of receiver</span></span>  
  
- <span data-ttu-id="5d6af-130">**RCVPFC** -合作伙伴的接收方的函数</span><span class="sxs-lookup"><span data-stu-id="5d6af-130">**RCVPFC** - Partner function of recipient</span></span>  
  
- <span data-ttu-id="5d6af-131">**RCVPRN** -合作伙伴的接收方数</span><span class="sxs-lookup"><span data-stu-id="5d6af-131">**RCVPRN** - Partner number of recipient</span></span>  
  
- <span data-ttu-id="5d6af-132">**RCVSAD** -收件人地址 (SADR)</span><span class="sxs-lookup"><span data-stu-id="5d6af-132">**RCVSAD** - Recipient address (SADR)</span></span>  
  
- <span data-ttu-id="5d6af-133">**RCVLAD** -收件人的逻辑地址</span><span class="sxs-lookup"><span data-stu-id="5d6af-133">**RCVLAD** - Logical address of recipient</span></span>  
  
- <span data-ttu-id="5d6af-134">**CREDAT** -在上创建的</span><span class="sxs-lookup"><span data-stu-id="5d6af-134">**CREDAT** - Created on</span></span>  
  
- <span data-ttu-id="5d6af-135">**CRETIM**的创建时间</span><span class="sxs-lookup"><span data-stu-id="5d6af-135">**CRETIM** - Time Created</span></span>  
  
- <span data-ttu-id="5d6af-136">**REFINT** -传输文件 （EDI 交换）</span><span class="sxs-lookup"><span data-stu-id="5d6af-136">**REFINT** - Transmission file (EDI Interchange)</span></span>  
  
- <span data-ttu-id="5d6af-137">**REFGRP** -消息组 （EDI 消息组）</span><span class="sxs-lookup"><span data-stu-id="5d6af-137">**REFGRP** - Message group (EDI Message Group)</span></span>  
  
- <span data-ttu-id="5d6af-138">**REFMES** -消息 （EDI 消息）</span><span class="sxs-lookup"><span data-stu-id="5d6af-138">**REFMES** - Message (EDI Message)</span></span>  
  
- <span data-ttu-id="5d6af-139">**ARCKEY** -密钥对外部消息存档</span><span class="sxs-lookup"><span data-stu-id="5d6af-139">**ARCKEY** - Key for external message archive</span></span>  
  
- <span data-ttu-id="5d6af-140">**串行**-序列化</span><span class="sxs-lookup"><span data-stu-id="5d6af-140">**SERIAL** - Serialization</span></span>  
  
- <span data-ttu-id="5d6af-141">**DOCTYP** -IDOC 类型 （这仅提供 EDI_DC。</span><span class="sxs-lookup"><span data-stu-id="5d6af-141">**DOCTYP** - IDOC type (This is available in EDI_DC only.</span></span> <span data-ttu-id="5d6af-142">应为上下文属性中存在，但应仅升级为版本 2 Idoc）</span><span class="sxs-lookup"><span data-stu-id="5d6af-142">Should be present in the context property but should be promoted for Version 2 IDOCs only)</span></span>  
  
  <span data-ttu-id="5d6af-143">**TID** – 表示 SAP 系统发送传入 TRFC 调用 TID。</span><span class="sxs-lookup"><span data-stu-id="5d6af-143">**TID** – Represents the TID sent by the SAP system for the incoming TRFC call.</span></span>  
  
  <span data-ttu-id="5d6af-144">**GUID** – 表示 GUID 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在内部使用。</span><span class="sxs-lookup"><span data-stu-id="5d6af-144">**GUID** – Represents the GUID which the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses internally.</span></span> <span data-ttu-id="5d6af-145">这具有 TID 这来自 SAP 系统具有一对一的映射。</span><span class="sxs-lookup"><span data-stu-id="5d6af-145">This has a one-to-one mapping with the TID which was received from the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6af-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d6af-146">See Also</span></span>  
 [<span data-ttu-id="5d6af-147">消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="5d6af-147">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)