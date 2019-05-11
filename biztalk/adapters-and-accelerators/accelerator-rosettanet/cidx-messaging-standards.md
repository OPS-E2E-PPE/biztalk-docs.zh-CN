---
title: CIDX 消息传送标准 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, RosettaNet
- RosettaNet, CIDX
ms.assetid: 6f70fa56-1fc3-4016-ac9e-6af18026292a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a39b76ef67374796d9ba569a50e7d5357dac819d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284858"
---
# <a name="cidx-messaging-standards"></a><span data-ttu-id="3f0f1-102">CIDX 消息传送标准</span><span class="sxs-lookup"><span data-stu-id="3f0f1-102">CIDX Messaging Standards</span></span>
<span data-ttu-id="3f0f1-103">CIDX （化工行业数据交换） 表示，它支持和维护的标准化的消息交换 Chem eStandards 的标准组织。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-103">CIDX (Chemical Industry Data Exchange) operates as a standards organization that supports and maintains the Chem eStandards for standardized message exchange.</span></span> <span data-ttu-id="3f0f1-104">化工行业中的公司对其特定于行业的消息传送需求都使用这些标准。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-104">Companies in the chemical industry use these standards for their industry-specific messaging needs.</span></span>  
  
 <span data-ttu-id="3f0f1-105">CIDX 已采用 RosettaNet 实现框架 (RNIF) 消息传递层来实现 XML 文档的交换。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-105">CIDX has adopted the RosettaNet Implementation Framework (RNIF) at the messaging layer to enable the exchange of XML documents.</span></span> <span data-ttu-id="3f0f1-106">CIDX 不已采用的 RNIF 标准的公用流程层。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-106">CIDX has not adopted the public-process layer of the RNIF standards.</span></span>  
  
 <span data-ttu-id="3f0f1-107">Chem eStandards 定义描述系统交换的消息的服务内容的 XML 文档类型定义 (Dtd)。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-107">Chem eStandards define XML document type definitions (DTDs) that describe the service content of a message that systems exchange.</span></span> <span data-ttu-id="3f0f1-108">该消息是在结构中，具有服务内容和一些标头值之间的差异的 RNIF 1.1 RosettaNet 对象相同。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-108">The message is the same as an RNIF 1.1 RosettaNet object in structure, with differences in the service content and some header values.</span></span> <span data-ttu-id="3f0f1-109">当有标准 CIDX 与 RosettaNet 消息相匹配时，CIDX 标准采用 RosettaNet 元素名称和数据结构。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-109">When there is a match between CIDX standards and RosettaNet messages, the CIDX standard adopts RosettaNet element names and data structures.</span></span>  
  
 <span data-ttu-id="3f0f1-110">CIDX 具有传统上用于电子文档交换 (EDI) 消息交换，但具有格式正确的一组新的基于 XML 技术的文档。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-110">CIDX has traditionally used electronic document interchange (EDI) for message exchange, but has formed a new set of documents based on XML technologies.</span></span> <span data-ttu-id="3f0f1-111">Chem eStandards 提供 EDI 消息的 XML 的副本。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-111">Chem eStandards provide XML replicas of EDI messages.</span></span>  
  
 <span data-ttu-id="3f0f1-112">Chem eStandards 创建各个消息的每个业务事务。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-112">Chem eStandards create individual messages for every business transaction.</span></span> <span data-ttu-id="3f0f1-113">Chem eStandards 使用两种类型的消息响应： 技术响应以及事务响应。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-113">Chem eStandards use two types of message responses: technical responses and transaction responses.</span></span> <span data-ttu-id="3f0f1-114">对于安全和可靠消息传送，Chem eStandards 仅使用 RNIF 1.1 的通知类型处理。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-114">For secure and reliable messaging, Chem eStandards only use Notification type processes of RNIF 1.1.</span></span> <span data-ttu-id="3f0f1-115">Chem eStandards 不要使用合作伙伴接口流程 (PIP) 0A1。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-115">Chem eStandards do not use Partner Interface Process (PIP) 0A1.</span></span>  
  
## <a name="cidx-and-rosettanet-differences"></a><span data-ttu-id="3f0f1-116">CIDX 与 RosettaNet 差异</span><span class="sxs-lookup"><span data-stu-id="3f0f1-116">CIDX and RosettaNet Differences</span></span>  
 <span data-ttu-id="3f0f1-117">下表显示了一些 RosettaNet 和 CIDX 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-117">The following table shows some of the differences between RosettaNet and CIDX.</span></span>  
  
|<span data-ttu-id="3f0f1-118">RosettaNet 实现</span><span class="sxs-lookup"><span data-stu-id="3f0f1-118">RosettaNet implementation</span></span>|<span data-ttu-id="3f0f1-119">CIDX 实现</span><span class="sxs-lookup"><span data-stu-id="3f0f1-119">CIDX implementation</span></span>|  
|-------------------------------|-------------------------|  
|<span data-ttu-id="3f0f1-120">RosettaNet 使用"应用程序/X-rosettanet"作为多用途 Internet 邮件扩展 (MIME) 类型。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-120">RosettaNet uses the "Application/x-RosettaNet" as the Multipurpose Internet Mail Extensions (MIME) type.</span></span>|<span data-ttu-id="3f0f1-121">CIDX 使用"应用程序/X-chemxml"作为 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-121">CIDX uses "Application/x-ChemXML" as the MIME type.</span></span>|  
|<span data-ttu-id="3f0f1-122">RosettaNet 标头的 RosettaNet 使用 GlobalAdministeringAuthorityCode = RosettaNet</span><span class="sxs-lookup"><span data-stu-id="3f0f1-122">For RosettaNet headers, RosettaNet uses GlobalAdministeringAuthorityCode = RosettaNet</span></span>|<span data-ttu-id="3f0f1-123">CIDX 使用 GlobalAdministeringAuthorityCode = CIDX</span><span class="sxs-lookup"><span data-stu-id="3f0f1-123">CIDX uses GlobalAdministeringAuthorityCode = CIDX</span></span>|  
|<span data-ttu-id="3f0f1-124">RosettaNet 支持单操作和双操作消息。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-124">RosettaNet supports single-action and double-action messages.</span></span>|<span data-ttu-id="3f0f1-125">CIDX 支持仅单操作消息。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-125">CIDX supports only single-action messages.</span></span>|  
|<span data-ttu-id="3f0f1-126">RosettaNet 支持的 PIP 0A1 （失败通知）。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-126">RosettaNet supports PIP 0A1 (Notification of Failure).</span></span>|<span data-ttu-id="3f0f1-127">CIDX 不支持的 PIP 0A1。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-127">CIDX does not support PIP 0A1.</span></span>|  
|<span data-ttu-id="3f0f1-128">RosettaNet 消息可以是事务或通知的类型。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-128">RosettaNet messages can be of Transaction or Notification type.</span></span>|<span data-ttu-id="3f0f1-129">所有 CIDX 消息都都会的通知类型。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-129">All CIDX messages are of the Notification type.</span></span>|  
|<span data-ttu-id="3f0f1-130">在 RosettaNet，必须从 PIP 规范派生 PIP 配置设置。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-130">In RosettaNet, you must derive PIP Configuration Settings from the PIP specifications.</span></span>|<span data-ttu-id="3f0f1-131">在 CIDX，必须从 CIDX Chem eStandards 规范派生 PIP 配置设置。</span><span class="sxs-lookup"><span data-stu-id="3f0f1-131">In CIDX, you must derive PIP Configuration Settings from the CIDX Chem eStandards specifications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f0f1-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0f1-132">See Also</span></span>  
 <span data-ttu-id="3f0f1-133">[RosettaNet 和 CIDX 标准消息传送](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="3f0f1-133">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 <span data-ttu-id="3f0f1-134">[RNIF 标准](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md) </span><span class="sxs-lookup"><span data-stu-id="3f0f1-134">[RNIF Standard](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md) </span></span>  
 <span data-ttu-id="3f0f1-135">[RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md) </span><span class="sxs-lookup"><span data-stu-id="3f0f1-135">[RosettaNet PIPs](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md) </span></span>  
 [<span data-ttu-id="3f0f1-136">CIDX 支持</span><span class="sxs-lookup"><span data-stu-id="3f0f1-136">CIDX Support</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)