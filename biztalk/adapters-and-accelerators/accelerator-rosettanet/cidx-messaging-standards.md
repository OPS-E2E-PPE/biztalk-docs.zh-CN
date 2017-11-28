---
title: "消息传送标准 CIDX |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CIDX, RosettaNet
- RosettaNet, CIDX
ms.assetid: 6f70fa56-1fc3-4016-ac9e-6af18026292a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d37cd02f92a8a13857071d0b3d84ab40c480787
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="cidx-messaging-standards"></a><span data-ttu-id="5ac70-102">CIDX 消息传送标准</span><span class="sxs-lookup"><span data-stu-id="5ac70-102">CIDX Messaging Standards</span></span>
<span data-ttu-id="5ac70-103">作为标准组织支持和维护的标准化的消息交换 Chem eStandards 操作 CIDX （筛选行业数据交换）。</span><span class="sxs-lookup"><span data-stu-id="5ac70-103">CIDX (Chemical Industry Data Exchange) operates as a standards organization that supports and maintains the Chem eStandards for standardized message exchange.</span></span> <span data-ttu-id="5ac70-104">筛选行业中的公司为其特定于行业的消息传递需求使用这些标准。</span><span class="sxs-lookup"><span data-stu-id="5ac70-104">Companies in the chemical industry use these standards for their industry-specific messaging needs.</span></span>  
  
 <span data-ttu-id="5ac70-105">CIDX 已采用 RosettaNet 实现框架 (RNIF) 在消息传递层实现 XML 文档的交换。</span><span class="sxs-lookup"><span data-stu-id="5ac70-105">CIDX has adopted the RosettaNet Implementation Framework (RNIF) at the messaging layer to enable the exchange of XML documents.</span></span> <span data-ttu-id="5ac70-106">CIDX 未采用 RNIF 标准公共进程层。</span><span class="sxs-lookup"><span data-stu-id="5ac70-106">CIDX has not adopted the public-process layer of the RNIF standards.</span></span>  
  
 <span data-ttu-id="5ac70-107">Chem eStandards 定义描述系统交换的消息的服务内容的 XML 文档类型定义 (Dtd)。</span><span class="sxs-lookup"><span data-stu-id="5ac70-107">Chem eStandards define XML document type definitions (DTDs) that describe the service content of a message that systems exchange.</span></span> <span data-ttu-id="5ac70-108">消息已在结构中，具有服务内容和某些标头值之间的差异的 RNIF 1.1 RosettaNet 对象相同。</span><span class="sxs-lookup"><span data-stu-id="5ac70-108">The message is the same as an RNIF 1.1 RosettaNet object in structure, with differences in the service content and some header values.</span></span> <span data-ttu-id="5ac70-109">如果没有 CIDX 标准和 RosettaNet 消息之间匹配，CIDX 标准采用 RosettaNet 元素名称和数据结构。</span><span class="sxs-lookup"><span data-stu-id="5ac70-109">When there is a match between CIDX standards and RosettaNet messages, the CIDX standard adopts RosettaNet element names and data structures.</span></span>  
  
 <span data-ttu-id="5ac70-110">CIDX 具有传统上用于电子文档交换 (EDI) 消息交换，但建立了一组新的基于 XML 技术的文档。</span><span class="sxs-lookup"><span data-stu-id="5ac70-110">CIDX has traditionally used electronic document interchange (EDI) for message exchange, but has formed a new set of documents based on XML technologies.</span></span> <span data-ttu-id="5ac70-111">Chem eStandards 提供 XML 的 EDI 消息的副本。</span><span class="sxs-lookup"><span data-stu-id="5ac70-111">Chem eStandards provide XML replicas of EDI messages.</span></span>  
  
 <span data-ttu-id="5ac70-112">Chem eStandards 创建每个业务事务的单个的消息。</span><span class="sxs-lookup"><span data-stu-id="5ac70-112">Chem eStandards create individual messages for every business transaction.</span></span> <span data-ttu-id="5ac70-113">Chem eStandards 使用两种类型的消息响应： 技术响应和事务响应。</span><span class="sxs-lookup"><span data-stu-id="5ac70-113">Chem eStandards use two types of message responses: technical responses and transaction responses.</span></span> <span data-ttu-id="5ac70-114">对于安全、 可靠消息传递，Chem eStandards 只能使用 RNIF 1.1 的通知类型进程。</span><span class="sxs-lookup"><span data-stu-id="5ac70-114">For secure and reliable messaging, Chem eStandards only use Notification type processes of RNIF 1.1.</span></span> <span data-ttu-id="5ac70-115">Chem eStandards 不使用合作伙伴接口过程 (PIP) 0A1。</span><span class="sxs-lookup"><span data-stu-id="5ac70-115">Chem eStandards do not use Partner Interface Process (PIP) 0A1.</span></span>  
  
## <a name="cidx-and-rosettanet-differences"></a><span data-ttu-id="5ac70-116">CIDX 和 RosettaNet 差异</span><span class="sxs-lookup"><span data-stu-id="5ac70-116">CIDX and RosettaNet Differences</span></span>  
 <span data-ttu-id="5ac70-117">下表显示了一些 RosettaNet 和 CIDX 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="5ac70-117">The following table shows some of the differences between RosettaNet and CIDX.</span></span>  
  
|<span data-ttu-id="5ac70-118">RosettaNet 实现</span><span class="sxs-lookup"><span data-stu-id="5ac70-118">RosettaNet implementation</span></span>|<span data-ttu-id="5ac70-119">CIDX 实现</span><span class="sxs-lookup"><span data-stu-id="5ac70-119">CIDX implementation</span></span>|  
|-------------------------------|-------------------------|  
|<span data-ttu-id="5ac70-120">RosettaNet 使用“Application/x-RosettaNet”作为多用途 Internet 邮件扩展 (MIME) 类型。</span><span class="sxs-lookup"><span data-stu-id="5ac70-120">RosettaNet uses the "Application/x-RosettaNet" as the Multipurpose Internet Mail Extensions (MIME) type.</span></span>|<span data-ttu-id="5ac70-121">CIDX 使用“Application/x-ChemXML”作为 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="5ac70-121">CIDX uses "Application/x-ChemXML" as the MIME type.</span></span>|  
|<span data-ttu-id="5ac70-122">有关 RosettaNet 标头，RosettaNet 使用 GlobalAdministeringAuthorityCode = RosettaNet</span><span class="sxs-lookup"><span data-stu-id="5ac70-122">For RosettaNet headers, RosettaNet uses GlobalAdministeringAuthorityCode = RosettaNet</span></span>|<span data-ttu-id="5ac70-123">CIDX 使用 GlobalAdministeringAuthorityCode = CIDX</span><span class="sxs-lookup"><span data-stu-id="5ac70-123">CIDX uses GlobalAdministeringAuthorityCode = CIDX</span></span>|  
|<span data-ttu-id="5ac70-124">RosettaNet 支持单操作和双操作的消息。</span><span class="sxs-lookup"><span data-stu-id="5ac70-124">RosettaNet supports single-action and double-action messages.</span></span>|<span data-ttu-id="5ac70-125">CIDX 支持仅单操作的消息。</span><span class="sxs-lookup"><span data-stu-id="5ac70-125">CIDX supports only single-action messages.</span></span>|  
|<span data-ttu-id="5ac70-126">RosettaNet 支持 PIP 0A1 （故障通知）。</span><span class="sxs-lookup"><span data-stu-id="5ac70-126">RosettaNet supports PIP 0A1 (Notification of Failure).</span></span>|<span data-ttu-id="5ac70-127">CIDX 不支持 PIP 0A1。</span><span class="sxs-lookup"><span data-stu-id="5ac70-127">CIDX does not support PIP 0A1.</span></span>|  
|<span data-ttu-id="5ac70-128">RosettaNet 消息可以为事务或通知类型。</span><span class="sxs-lookup"><span data-stu-id="5ac70-128">RosettaNet messages can be of Transaction or Notification type.</span></span>|<span data-ttu-id="5ac70-129">所有 CIDX 消息都都的通知类型。</span><span class="sxs-lookup"><span data-stu-id="5ac70-129">All CIDX messages are of the Notification type.</span></span>|  
|<span data-ttu-id="5ac70-130">在 RosettaNet，必须从 PIP 规范派生 PIP 配置设置。</span><span class="sxs-lookup"><span data-stu-id="5ac70-130">In RosettaNet, you must derive PIP Configuration Settings from the PIP specifications.</span></span>|<span data-ttu-id="5ac70-131">在 CIDX，必须从 CIDX Chem eStandards 规范派生 PIP 配置设置。</span><span class="sxs-lookup"><span data-stu-id="5ac70-131">In CIDX, you must derive PIP Configuration Settings from the CIDX Chem eStandards specifications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ac70-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ac70-132">See Also</span></span>  
 <span data-ttu-id="5ac70-133">[RosettaNet 和 CIDX 标准消息传送](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="5ac70-133">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 <span data-ttu-id="5ac70-134">[RNIF 标准](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md) </span><span class="sxs-lookup"><span data-stu-id="5ac70-134">[RNIF Standard](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md) </span></span>  
 <span data-ttu-id="5ac70-135">[RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md) </span><span class="sxs-lookup"><span data-stu-id="5ac70-135">[RosettaNet PIPs](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md) </span></span>  
 [<span data-ttu-id="5ac70-136">CIDX 支持</span><span class="sxs-lookup"><span data-stu-id="5ac70-136">CIDX Support</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)