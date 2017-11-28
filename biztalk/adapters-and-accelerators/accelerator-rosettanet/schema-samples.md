---
title: "架构示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SDK samples, schemas
- examples, schemas
- schemas, examples
ms.assetid: 7d7e696d-935f-4582-b873-c5637673b651
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f346d2e7258c14e09dbcdc5f29ff0f7690cb4a4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-samples"></a><span data-ttu-id="461f5-102">架构示例</span><span class="sxs-lookup"><span data-stu-id="461f5-102">Schema Samples</span></span>
<span data-ttu-id="461f5-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 包含一系列的 RNIF 和合作伙伴接口过程 (PIP) 处理的 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="461f5-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK includes a series of XSD schemas for RNIF and Partner Interface Process (PIP) processing.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="461f5-104">使用这些架构来处理消息。</span><span class="sxs-lookup"><span data-stu-id="461f5-104"> uses these schemas to process messages.</span></span> <span data-ttu-id="461f5-105">你可以根据需要修改这些架构，或使用这些架构来排除故障。</span><span class="sxs-lookup"><span data-stu-id="461f5-105">You can modify these schemas for your own purposes, or use these to troubleshoot failures.</span></span>  
  
 <span data-ttu-id="461f5-106">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 提供三组架构。</span><span class="sxs-lookup"><span data-stu-id="461f5-106">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK provides three sets of schemas.</span></span> <span data-ttu-id="461f5-107">它们是与 RosettaNet PIP 相关联的 XSD 架构、RosettaNet 下一代架构和 RNIF 架构。</span><span class="sxs-lookup"><span data-stu-id="461f5-107">These schemas are XSD schemas associated with RosettaNet PIPs, RosettaNet next-generation schemas, and RNIF schemas.</span></span>  
  
## <a name="xsd-schemas-associated-with-rosettanet-pips"></a><span data-ttu-id="461f5-108">与 RosettaNet PIP 关联的 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="461f5-108">XSD Schemas associated with RosettaNet PIPs</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="461f5-109"> 使用这些架构来验证消息实例的服务内容。</span><span class="sxs-lookup"><span data-stu-id="461f5-109"> uses these schemas to validate the service content of message instances.</span></span> <span data-ttu-id="461f5-110">你可以修改这些架构来改变消息处理的流程。</span><span class="sxs-lookup"><span data-stu-id="461f5-110">You can modify these schemas to change message processing.</span></span> <span data-ttu-id="461f5-111">在排除服务内容处理过程中的错误时，可以使用这些架构来验证消息实例。</span><span class="sxs-lookup"><span data-stu-id="461f5-111">You can also use the schemas to validate message instances when troubleshooting errors in processing service content.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="461f5-112"> 已将这些架构编译到 RNPIP 程序集中。</span><span class="sxs-lookup"><span data-stu-id="461f5-112"> has compiled these schemas into the RNPIPs assembly.</span></span> <span data-ttu-id="461f5-113">通过取消部署 RNPIP 程序集，更改架构，然后重新部署 RNPIP，可以修改这些架构中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="461f5-113">You can modify any one of these schemas by undeploying the RNPIPs assembly, changing the schema, and then redeploying RNPIPs.</span></span> <span data-ttu-id="461f5-114">但你必须小心谨慎，确保不要对架构进行大幅度更改。</span><span class="sxs-lookup"><span data-stu-id="461f5-114">You must be careful that you do not change the schema.</span></span> <span data-ttu-id="461f5-115">如果你大幅度更改架构，你所做的更改可能会与相应的 RosettaNet PIP 不符。</span><span class="sxs-lookup"><span data-stu-id="461f5-115">If you change the schema, your changes may not comply with the corresponding RosettaNet PIP.</span></span> <span data-ttu-id="461f5-116">你还可以向 RNPIP 中添加架构。</span><span class="sxs-lookup"><span data-stu-id="461f5-116">You can also add a schema to RNPIPs.</span></span> <span data-ttu-id="461f5-117">有关详细信息，请参阅[修改现有 PIP 在 RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。</span><span class="sxs-lookup"><span data-stu-id="461f5-117">For more information, see [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  
  
 <span data-ttu-id="461f5-118">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装在这些架构\<*驱动器*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > RosettaNet\SDK\Schemas 快捷键。</span><span class="sxs-lookup"><span data-stu-id="461f5-118">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\Schemas.</span></span>  
  
## <a name="rnif-schemas"></a><span data-ttu-id="461f5-119">RNIF 架构</span><span class="sxs-lookup"><span data-stu-id="461f5-119">RNIF Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="461f5-120"> 使用这些架构来验证 RNIF 消息的各部分，如前导头、服务头和传递头。</span><span class="sxs-lookup"><span data-stu-id="461f5-120"> uses these schemas to validate RNIF message parts, such as the preamble, service header, and delivery header.</span></span> <span data-ttu-id="461f5-121">这些架构还包括适用于确认和异常的架构。</span><span class="sxs-lookup"><span data-stu-id="461f5-121">These also include schemas for acknowledgments and exceptions.</span></span>  
  
 <span data-ttu-id="461f5-122">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装在这些架构\<*驱动器*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > RosettaNet\SDK\RNIFSchemas 快捷键。</span><span class="sxs-lookup"><span data-stu-id="461f5-122">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\RNIFSchemas.</span></span>  
  
## <a name="rosettanet-next-generation-schemas"></a><span data-ttu-id="461f5-123">RosettaNet 下一代架构</span><span class="sxs-lookup"><span data-stu-id="461f5-123">RosettaNet Next-Generation Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="461f5-124"> 使用这些架构来验证消息是否符合 RosettaNet 的下一代架构要求。</span><span class="sxs-lookup"><span data-stu-id="461f5-124"> uses these schemas to validate messages conforming to next-generation schemas for RosettaNet.</span></span> <span data-ttu-id="461f5-125">这些架构是为支持 XSD（而非 DTD）而设计的。</span><span class="sxs-lookup"><span data-stu-id="461f5-125">These schemas support XSD natively, instead of DTDs.</span></span> <span data-ttu-id="461f5-126">若要使用这些架构，将它们添加到 RNPIPs 程序集中所述[修改现有 PIP 在 RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。</span><span class="sxs-lookup"><span data-stu-id="461f5-126">To use these schemas, add them to the RNPIPs assembly as described in [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  
  
 <span data-ttu-id="461f5-127">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装在这些架构\<*驱动器*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > RosettaNet\SDK\Schemas\ 快捷键域、 \Interchange 和 \Universal 文件夹。</span><span class="sxs-lookup"><span data-stu-id="461f5-127">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in the \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\Schemas\Domain, \Interchange, and \Universal folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="461f5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="461f5-128">See Also</span></span>  
 <span data-ttu-id="461f5-129">[PIP 实现](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="461f5-129">[PIP Implementation](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md) </span></span>  
 <span data-ttu-id="461f5-130">[使用 Pip](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span><span class="sxs-lookup"><span data-stu-id="461f5-130">[Working with PIPs](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span></span>  
 [<span data-ttu-id="461f5-131">示例</span><span class="sxs-lookup"><span data-stu-id="461f5-131">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)