---
title: PIP 实现 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8105cabdb5019cc706abfd8624de6cef76f9179
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282948"
---
# <a name="pip-implementation"></a><span data-ttu-id="c30b3-102">PIP 实现</span><span class="sxs-lookup"><span data-stu-id="c30b3-102">PIP Implementation</span></span>
<span data-ttu-id="c30b3-103">RosettaNet 合作伙伴接口流程 (Pip) 定义在供应链中的贸易合作伙伴之间的业务流程。</span><span class="sxs-lookup"><span data-stu-id="c30b3-103">RosettaNet Partner Interface Processes (PIPs) define business processes between trading partners in a supply chain.</span></span> <span data-ttu-id="c30b3-104">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供了一组 Pip 的开箱，你可以创建其他 Pip。</span><span class="sxs-lookup"><span data-stu-id="c30b3-104">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides a set of PIPs out-of-the-box and you can create additional PIPs.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="c30b3-105">支持 RosettaNet 组织定义的所有 Pip。</span><span class="sxs-lookup"><span data-stu-id="c30b3-105">supports all PIPs defined by the RosettaNet organization.</span></span>  
  
 <span data-ttu-id="c30b3-106">有关详细信息，请参阅[RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)。</span><span class="sxs-lookup"><span data-stu-id="c30b3-106">For more information, see [RosettaNet PIPs](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md).</span></span>  
  
## <a name="schemas-in-btarn"></a><span data-ttu-id="c30b3-107">BTARN 中的架构</span><span class="sxs-lookup"><span data-stu-id="c30b3-107">Schemas in BTARN</span></span>  
 <span data-ttu-id="c30b3-108">RosettaNet 文档类型定义 (Dtd) 的形式指定所有 PIP 消息架构。</span><span class="sxs-lookup"><span data-stu-id="c30b3-108">RosettaNet specifies all PIP message schemas in the form of Document Type Definitions (DTDs).</span></span> <span data-ttu-id="c30b3-109">贸易合作伙伴参与业务文档交换必须遵守这些 Dtd。</span><span class="sxs-lookup"><span data-stu-id="c30b3-109">Trading partners who participate in the business-document exchange must comply with these DTDs.</span></span> <span data-ttu-id="c30b3-110">但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]实施这些 Dtd 作为 XML 架构定义文件 (Xsd)，因为 Microsoft BizTalk Server 使用 xsd 而不是 Dtd 来表示文档。</span><span class="sxs-lookup"><span data-stu-id="c30b3-110">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implements these DTDs as XML Schema Definition files (XSDs), because Microsoft  BizTalk Server represents documents by using XSDs, not DTDs.</span></span> <span data-ttu-id="c30b3-111">Xsd 在功能，方面取代 Dtd，并可以代表着大部分的本机消息指南中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="c30b3-111">XSDs supersede DTDs in terms of functionality, and can represent most of the information provided in the message guidelines natively.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="c30b3-112">此外支持下一代 Pip，最新发布的 RosettaNet 组织使用 XSD 规范。</span><span class="sxs-lookup"><span data-stu-id="c30b3-112">also supports next-generation PIPs, recently published by the RosettaNet organization, that use XSD specifications.</span></span>  
  
 <span data-ttu-id="c30b3-113">若要实现新的 PIP，必须将 PIP 的 DTD 转换为 XSD 中。</span><span class="sxs-lookup"><span data-stu-id="c30b3-113">To implement a new PIP, you must convert the PIP's DTD into an XSD.</span></span> <span data-ttu-id="c30b3-114">下载与从 RosettaNet 网站下载，网址 PIP 相关联的 DTD [ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859)。</span><span class="sxs-lookup"><span data-stu-id="c30b3-114">You download the DTD associated with the PIP from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span> <span data-ttu-id="c30b3-115">然后，创建[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]处理基于 PIP 配置配置文件。</span><span class="sxs-lookup"><span data-stu-id="c30b3-115">You then create a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] process configuration profile based on the PIP.</span></span> <span data-ttu-id="c30b3-116">有关详细信息，请参阅[并入新的合作伙伴接口流程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)。</span><span class="sxs-lookup"><span data-stu-id="c30b3-116">For more information, see [Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span></span>  
  
 <span data-ttu-id="c30b3-117">可以创建基于现有的配置文件的新流程配置配置文件。</span><span class="sxs-lookup"><span data-stu-id="c30b3-117">You can create a new process configuration profile based on an existing profile.</span></span> <span data-ttu-id="c30b3-118">有关详细信息，请参阅[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="c30b3-118">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span> <span data-ttu-id="c30b3-119">您可以创建基于相同合作伙伴之间的相同过程配置配置文件的多个协议。</span><span class="sxs-lookup"><span data-stu-id="c30b3-119">You can create multiple agreements based on the same process configuration profile between the same partners.</span></span> <span data-ttu-id="c30b3-120">但是，你只能激活其中一个一次。</span><span class="sxs-lookup"><span data-stu-id="c30b3-120">However, you can only activate one of them at a time.</span></span> <span data-ttu-id="c30b3-121">若要创建并激活协议，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="c30b3-121">To create and activate an agreement, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="c30b3-122">对以下 RosettaNet 头的 RosettaNet 消息指南约束来实施 Xsd:</span><span class="sxs-lookup"><span data-stu-id="c30b3-122">implements XSDs with the RosettaNet message-guideline constraints for the following RosettaNet headers:</span></span>  
  
-   <span data-ttu-id="c30b3-123">RNIF 1.1 和 RNIF 2.01 的前导头</span><span class="sxs-lookup"><span data-stu-id="c30b3-123">Preamble for RNIF 1.1 and RNIF 2.01</span></span>  
  
-   <span data-ttu-id="c30b3-124">RNIF 1.1 和 RNIF 2.0 的服务头</span><span class="sxs-lookup"><span data-stu-id="c30b3-124">Service header for RNIF 1.1 and RNIF 2.0</span></span>  
  
-   <span data-ttu-id="c30b3-125">对于 RNIF 2.0 的传递头</span><span class="sxs-lookup"><span data-stu-id="c30b3-125">Delivery header for RNIF 2.0</span></span>  
  
-   <span data-ttu-id="c30b3-126">所有信号消息的 RNIF 1.1 和 RNIF 2.01 的服务内容。</span><span class="sxs-lookup"><span data-stu-id="c30b3-126">Service content for all signal messages of RNIF 1.1 and RNIF 2.01.</span></span>  
  
## <a name="sample-schemas"></a><span data-ttu-id="c30b3-127">示例架构</span><span class="sxs-lookup"><span data-stu-id="c30b3-127">Sample Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="c30b3-128">安装程序将安装 Pip 中一组\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for rosettanet\sdk\schemas 中找到。</span><span class="sxs-lookup"><span data-stu-id="c30b3-128">setup installs a set of PIPs in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas.</span></span> <span data-ttu-id="c30b3-129">这些是仅用于示例。</span><span class="sxs-lookup"><span data-stu-id="c30b3-129">These are for sample purposes only.</span></span> <span data-ttu-id="c30b3-130">然后才在生产环境中使用它们，强烈建议您将这些架构与最新已发布的 RosettaNet PIP 规范和消息指南进行比较。</span><span class="sxs-lookup"><span data-stu-id="c30b3-130">Before using them in production, it is highly recommended that you compare these schemas against the latest published RosettaNet PIP specifications and message guidelines.</span></span> <span data-ttu-id="c30b3-131">BTARN 支持所有 RosettaNet Pip 的实现。</span><span class="sxs-lookup"><span data-stu-id="c30b3-131">BTARN supports implementation of all RosettaNet PIPs.</span></span>  
  
## <a name="element-level-constraints-in-btarn"></a><span data-ttu-id="c30b3-132">BTARN 中的元素级约束</span><span class="sxs-lookup"><span data-stu-id="c30b3-132">Element-Level Constraints in BTARN</span></span>  
 <span data-ttu-id="c30b3-133">在 BTARN 中，您将实现 PIP 消息指南文档作为流程配置设置中指定的元素级约束。</span><span class="sxs-lookup"><span data-stu-id="c30b3-133">In BTARN, you implement the element-level constraints specified in the PIP message-guideline documents as process configuration settings.</span></span> <span data-ttu-id="c30b3-134">运行时组件使用流程配置来确定如何处理特定 PIP。</span><span class="sxs-lookup"><span data-stu-id="c30b3-134">Runtime components use the process configuration to determine how to process a specific PIP.</span></span>  
  
 <span data-ttu-id="c30b3-135">若要实施新的 PIP，你必须应用消息指南约束对 pip 通过创建新的流程配置配置文件。</span><span class="sxs-lookup"><span data-stu-id="c30b3-135">To implement a new PIP, you must apply the message guideline constraints for the PIP by creating a new process configuration profile.</span></span> <span data-ttu-id="c30b3-136">在 BTARN 管理控制台中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c30b3-136">You do this in the BTARN Management Console.</span></span> <span data-ttu-id="c30b3-137">有关详细信息，请参阅[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="c30b3-137">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="c30b3-138">流程配置配置文件映射到 RosettaNet PIP 规范中所示[使用 PIP 规范创建流程配置](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="c30b3-138">The process configuration profile maps to the RosettaNet PIP specification as shown in [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30b3-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="c30b3-139">See Also</span></span>  
 <span data-ttu-id="c30b3-140">[BizTalk Accelerator for RosettaNet 向 BizTalk Server 的添加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="c30b3-140">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 <span data-ttu-id="c30b3-141">[贸易合作伙伴协议](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md) </span><span class="sxs-lookup"><span data-stu-id="c30b3-141">[Trading Partner Agreements](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md) </span></span>  
 [<span data-ttu-id="c30b3-142">RosettaNet Pip</span><span class="sxs-lookup"><span data-stu-id="c30b3-142">RosettaNet PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)
