---
title: "PIP 实现 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs
- PIPs, element-level constraints
- Document Type Definitions (DTDs)
- PIPs, schemas
- examples, schemas
- schemas, examples
- PIPs, about PIPs
- element-level constraints
- PIPs, DTDs
- schemas, PIPs
- XML Schema Definition files (XSDs)
- Partner Interface Processes (PIPs)
- DTDs, XSDs
- schemas, XSDs
ms.assetid: 0d964223-e0b6-4377-b26a-5fdc89ec81f4
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9eeadda11d70998eff676c38a1d21e618acd2762
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="pip-implementation"></a><span data-ttu-id="40ebf-102">PIP 实现</span><span class="sxs-lookup"><span data-stu-id="40ebf-102">PIP Implementation</span></span>
<span data-ttu-id="40ebf-103">RosettaNet 合作伙伴接口进程 (Pip) 定义供应链中的贸易合作伙伴之间的业务流程。</span><span class="sxs-lookup"><span data-stu-id="40ebf-103">RosettaNet Partner Interface Processes (PIPs) define business processes between trading partners in a supply chain.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="40ebf-104">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供了一组的 Pip 现成可用，你可以创建其他 Pip。</span><span class="sxs-lookup"><span data-stu-id="40ebf-104">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides a set of PIPs out-of-the-box and you can create additional PIPs.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40ebf-105">支持所有 Pip RosettaNet 组织定义的。</span><span class="sxs-lookup"><span data-stu-id="40ebf-105"> supports all PIPs defined by the RosettaNet organization.</span></span>  
  
 <span data-ttu-id="40ebf-106">有关详细信息，请参阅[RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)。</span><span class="sxs-lookup"><span data-stu-id="40ebf-106">For more information, see [RosettaNet PIPs](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md).</span></span>  
  
## <a name="schemas-in-btarn"></a><span data-ttu-id="40ebf-107">BTARN 中的架构</span><span class="sxs-lookup"><span data-stu-id="40ebf-107">Schemas in BTARN</span></span>  
 <span data-ttu-id="40ebf-108">RosettaNet 将所有 PIP 消息架构都指定为文档类型定义 (DTD) 形式。</span><span class="sxs-lookup"><span data-stu-id="40ebf-108">RosettaNet specifies all PIP message schemas in the form of Document Type Definitions (DTDs).</span></span> <span data-ttu-id="40ebf-109">参与业务文档交换的贸易伙伴必须遵守这些 DTD。</span><span class="sxs-lookup"><span data-stu-id="40ebf-109">Trading partners who participate in the business-document exchange must comply with these DTDs.</span></span> <span data-ttu-id="40ebf-110">但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]作为 XML 架构定义文件 (Xsd)，实现这些 Dtd，因为 Microsoft BizTalk Server 表示通过使用不 Dtd 的 Xsd 文档。</span><span class="sxs-lookup"><span data-stu-id="40ebf-110">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implements these DTDs as XML Schema Definition files (XSDs), because Microsoft  BizTalk Server represents documents by using XSDs, not DTDs.</span></span> <span data-ttu-id="40ebf-111">XSD 在功能方面可以取代 DTD，并可以表示本地消息指南中提供的大多数信息。</span><span class="sxs-lookup"><span data-stu-id="40ebf-111">XSDs supersede DTDs in terms of functionality, and can represent most of the information provided in the message guidelines natively.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40ebf-112"> 还支持 RosettaNet 组织最新发布的、使用 XSD 规范的下一代 PIP。</span><span class="sxs-lookup"><span data-stu-id="40ebf-112"> also supports next-generation PIPs, recently published by the RosettaNet organization, that use XSD specifications.</span></span>  
  
 <span data-ttu-id="40ebf-113">要实施新的 PIP，必须将 PIP 的 DTD 形式转换为 XSD。</span><span class="sxs-lookup"><span data-stu-id="40ebf-113">To implement a new PIP, you must convert the PIP's DTD into an XSD.</span></span> <span data-ttu-id="40ebf-114">下载与从位于的 RosettaNet 网站 PIP 关联的 DTD [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)。</span><span class="sxs-lookup"><span data-stu-id="40ebf-114">You download the DTD associated with the PIP from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span> <span data-ttu-id="40ebf-115">然后你可以基于 PIP 创建 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 流程配置的配置文件。</span><span class="sxs-lookup"><span data-stu-id="40ebf-115">You then create a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] process configuration profile based on the PIP.</span></span> <span data-ttu-id="40ebf-116">有关详细信息，请参阅[合并新的合作伙伴接口进程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)。</span><span class="sxs-lookup"><span data-stu-id="40ebf-116">For more information, see [Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span></span>  
  
 <span data-ttu-id="40ebf-117">可以基于现有的配置文件新建一个流程配置的配置文件。</span><span class="sxs-lookup"><span data-stu-id="40ebf-117">You can create a new process configuration profile based on an existing profile.</span></span> <span data-ttu-id="40ebf-118">有关详细信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="40ebf-118">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span> <span data-ttu-id="40ebf-119">可以基于相同合作伙伴之间的同一个流程配置的配置文件创建多个协议。</span><span class="sxs-lookup"><span data-stu-id="40ebf-119">You can create multiple agreements based on the same process configuration profile between the same partners.</span></span> <span data-ttu-id="40ebf-120">但是，一次只能激活一个协议。</span><span class="sxs-lookup"><span data-stu-id="40ebf-120">However, you can only activate one of them at a time.</span></span> <span data-ttu-id="40ebf-121">若要创建并激活协议，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="40ebf-121">To create and activate an agreement, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40ebf-122"> 利用对以下 RosettaNet 头的 RosettaNet 消息指南约束来实施 XSD：</span><span class="sxs-lookup"><span data-stu-id="40ebf-122"> implements XSDs with the RosettaNet message-guideline constraints for the following RosettaNet headers:</span></span>  
  
-   <span data-ttu-id="40ebf-123">RNIF 1.1 和 RNIF 2.01 的前导头</span><span class="sxs-lookup"><span data-stu-id="40ebf-123">Preamble for RNIF 1.1 and RNIF 2.01</span></span>  
  
-   <span data-ttu-id="40ebf-124">RNIF 1.1 和 RNIF 2.0 的服务头</span><span class="sxs-lookup"><span data-stu-id="40ebf-124">Service header for RNIF 1.1 and RNIF 2.0</span></span>  
  
-   <span data-ttu-id="40ebf-125">RNIF 2.0 的传递头</span><span class="sxs-lookup"><span data-stu-id="40ebf-125">Delivery header for RNIF 2.0</span></span>  
  
-   <span data-ttu-id="40ebf-126">RNIF 1.1 和 RNIF 2.01 的所有信号消息的服务内容。</span><span class="sxs-lookup"><span data-stu-id="40ebf-126">Service content for all signal messages of RNIF 1.1 and RNIF 2.01.</span></span>  
  
## <a name="sample-schemas"></a><span data-ttu-id="40ebf-127">示例架构</span><span class="sxs-lookup"><span data-stu-id="40ebf-127">Sample Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="40ebf-128">安装程序将安装 Pip 在一组\<*驱动器*\>: files\microsoft BizTalk\<版本\>RosettaNet\SDK\Schemas 快捷键。</span><span class="sxs-lookup"><span data-stu-id="40ebf-128"> setup installs a set of PIPs in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas.</span></span> <span data-ttu-id="40ebf-129">这些 PIP 仅用作示例。</span><span class="sxs-lookup"><span data-stu-id="40ebf-129">These are for sample purposes only.</span></span> <span data-ttu-id="40ebf-130">强烈建议你在将其用于生产过程之前，将这些架构与最新发布的 RosettaNet PIP 规范和消息指南进行比较。</span><span class="sxs-lookup"><span data-stu-id="40ebf-130">Before using them in production, it is highly recommended that you compare these schemas against the latest published RosettaNet PIP specifications and message guidelines.</span></span> <span data-ttu-id="40ebf-131">BTARN 支持所有 RosettaNet PIP 的实施。</span><span class="sxs-lookup"><span data-stu-id="40ebf-131">BTARN supports implementation of all RosettaNet PIPs.</span></span>  
  
## <a name="element-level-constraints-in-btarn"></a><span data-ttu-id="40ebf-132">BTARN 中的元素级约束</span><span class="sxs-lookup"><span data-stu-id="40ebf-132">Element-Level Constraints in BTARN</span></span>  
 <span data-ttu-id="40ebf-133">在 BTARN 中，将 PIP 消息指南文档中指定的元素级约束作为流程配置设置来实施。</span><span class="sxs-lookup"><span data-stu-id="40ebf-133">In BTARN, you implement the element-level constraints specified in the PIP message-guideline documents as process configuration settings.</span></span> <span data-ttu-id="40ebf-134">运行时组件使用流程配置来确定处理特定 PIP 的方式。</span><span class="sxs-lookup"><span data-stu-id="40ebf-134">Runtime components use the process configuration to determine how to process a specific PIP.</span></span>  
  
 <span data-ttu-id="40ebf-135">要实施新的 PIP，必须通过新建流程配置的配置文件来应用对 PIP 的消息指南约束。</span><span class="sxs-lookup"><span data-stu-id="40ebf-135">To implement a new PIP, you must apply the message guideline constraints for the PIP by creating a new process configuration profile.</span></span> <span data-ttu-id="40ebf-136">这一操作在 BTARN 管理控制台中实现。</span><span class="sxs-lookup"><span data-stu-id="40ebf-136">You do this in the BTARN Management Console.</span></span> <span data-ttu-id="40ebf-137">有关详细信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="40ebf-137">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="40ebf-138">过程配置的配置文件映射到 RosettaNet PIP 规范中所示[使用 PIP 规范创建过程配置](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="40ebf-138">The process configuration profile maps to the RosettaNet PIP specification as shown in [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ebf-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40ebf-139">See Also</span></span>  
 <span data-ttu-id="40ebf-140">[BizTalk Accelerator for RosettaNet 将添加到 BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="40ebf-140">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 <span data-ttu-id="40ebf-141">[贸易合作伙伴协议](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md) </span><span class="sxs-lookup"><span data-stu-id="40ebf-141">[Trading Partner Agreements](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md) </span></span>  
 [<span data-ttu-id="40ebf-142">RosettaNet PIP</span><span class="sxs-lookup"><span data-stu-id="40ebf-142">RosettaNet PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)