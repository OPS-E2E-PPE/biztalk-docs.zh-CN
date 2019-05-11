---
title: 架构示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SDK samples, schemas
- examples, schemas
- schemas, examples
ms.assetid: 7d7e696d-935f-4582-b873-c5637673b651
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 344780047c9072dab00bb4b04ffe33f783e4d9fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281930"
---
# <a name="schema-samples"></a><span data-ttu-id="665d9-102">架构示例</span><span class="sxs-lookup"><span data-stu-id="665d9-102">Schema Samples</span></span>
<span data-ttu-id="665d9-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 包括一系列用于 RNIF 和合作伙伴接口流程 (PIP) 处理的 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="665d9-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK includes a series of XSD schemas for RNIF and Partner Interface Process (PIP) processing.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="665d9-104">使用这些架构来处理消息。</span><span class="sxs-lookup"><span data-stu-id="665d9-104">uses these schemas to process messages.</span></span> <span data-ttu-id="665d9-105">可以修改这些架构以根据自己的目的，或使用这些来排除故障。</span><span class="sxs-lookup"><span data-stu-id="665d9-105">You can modify these schemas for your own purposes, or use these to troubleshoot failures.</span></span>  
  
 <span data-ttu-id="665d9-106">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 提供三组架构。</span><span class="sxs-lookup"><span data-stu-id="665d9-106">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK provides three sets of schemas.</span></span> <span data-ttu-id="665d9-107">这些架构包括与 RosettaNet Pip 相关联的 XSD 架构、 RosettaNet 下一代架构和 RNIF 架构。</span><span class="sxs-lookup"><span data-stu-id="665d9-107">These schemas are XSD schemas associated with RosettaNet PIPs, RosettaNet next-generation schemas, and RNIF schemas.</span></span>  
  
## <a name="xsd-schemas-associated-with-rosettanet-pips"></a><span data-ttu-id="665d9-108">与 RosettaNet Pip 相关联的 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="665d9-108">XSD Schemas associated with RosettaNet PIPs</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="665d9-109">使用这些架构来验证消息实例的服务内容。</span><span class="sxs-lookup"><span data-stu-id="665d9-109">uses these schemas to validate the service content of message instances.</span></span> <span data-ttu-id="665d9-110">您可以修改这些架构来改变消息处理。</span><span class="sxs-lookup"><span data-stu-id="665d9-110">You can modify these schemas to change message processing.</span></span> <span data-ttu-id="665d9-111">此外可以使用架构来验证消息实例中处理服务内容的错误进行故障排除时。</span><span class="sxs-lookup"><span data-stu-id="665d9-111">You can also use the schemas to validate message instances when troubleshooting errors in processing service content.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="665d9-112">已编译到 Rnpip 程序集的两个架构。</span><span class="sxs-lookup"><span data-stu-id="665d9-112">has compiled these schemas into the RNPIPs assembly.</span></span> <span data-ttu-id="665d9-113">通过取消部署 Rnpip 程序集、 更改架构，以及然后重新部署 Rnpip，可以修改这些架构中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="665d9-113">You can modify any one of these schemas by undeploying the RNPIPs assembly, changing the schema, and then redeploying RNPIPs.</span></span> <span data-ttu-id="665d9-114">您必须小心不要更改架构。</span><span class="sxs-lookup"><span data-stu-id="665d9-114">You must be careful that you do not change the schema.</span></span> <span data-ttu-id="665d9-115">如果您更改架构，所做的更改可能不符合相应的 RosettaNet PIP。</span><span class="sxs-lookup"><span data-stu-id="665d9-115">If you change the schema, your changes may not comply with the corresponding RosettaNet PIP.</span></span> <span data-ttu-id="665d9-116">您还可以向 Rnpip 中添加架构。</span><span class="sxs-lookup"><span data-stu-id="665d9-116">You can also add a schema to RNPIPs.</span></span> <span data-ttu-id="665d9-117">有关详细信息，请参阅[修改 Rnpip 中的现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。</span><span class="sxs-lookup"><span data-stu-id="665d9-117">For more information, see [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  
  
 <span data-ttu-id="665d9-118">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将这些架构安装\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Schemas。</span><span class="sxs-lookup"><span data-stu-id="665d9-118">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas.</span></span>  
  
## <a name="rnif-schemas"></a><span data-ttu-id="665d9-119">RNIF 架构</span><span class="sxs-lookup"><span data-stu-id="665d9-119">RNIF Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="665d9-120">使用这些架构来验证 RNIF 消息部分，如前导头、 服务头和传递头。</span><span class="sxs-lookup"><span data-stu-id="665d9-120">uses these schemas to validate RNIF message parts, such as the preamble, service header, and delivery header.</span></span> <span data-ttu-id="665d9-121">这些内容还包括适用于确认和异常的架构。</span><span class="sxs-lookup"><span data-stu-id="665d9-121">These also include schemas for acknowledgments and exceptions.</span></span>  
  
 <span data-ttu-id="665d9-122">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将这些架构安装\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNIFSchemas。</span><span class="sxs-lookup"><span data-stu-id="665d9-122">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\RNIFSchemas.</span></span>  
  
## <a name="rosettanet-next-generation-schemas"></a><span data-ttu-id="665d9-123">RosettaNet 下一代架构</span><span class="sxs-lookup"><span data-stu-id="665d9-123">RosettaNet Next-Generation Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="665d9-124">使用这些架构来验证符合 RosettaNet 的下一代架构的消息。</span><span class="sxs-lookup"><span data-stu-id="665d9-124">uses these schemas to validate messages conforming to next-generation schemas for RosettaNet.</span></span> <span data-ttu-id="665d9-125">这些架构本身，而不是 Dtd 支持 XSD。</span><span class="sxs-lookup"><span data-stu-id="665d9-125">These schemas support XSD natively, instead of DTDs.</span></span> <span data-ttu-id="665d9-126">若要使用这些架构，将其添加到 Rnpip 程序集中所述[修改 Rnpip 中的现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。</span><span class="sxs-lookup"><span data-stu-id="665d9-126">To use these schemas, add them to the RNPIPs assembly as described in [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  
  
 <span data-ttu-id="665d9-127">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将这些架构安装\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK\Schemas\Domain、 \Interchange 和 \Universal 文件夹。</span><span class="sxs-lookup"><span data-stu-id="665d9-127">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in the \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas\Domain, \Interchange, and \Universal folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665d9-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="665d9-128">See Also</span></span>  
 <span data-ttu-id="665d9-129">[PIP 实现](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="665d9-129">[PIP Implementation](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md) </span></span>  
 <span data-ttu-id="665d9-130">[使用 Pip](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span><span class="sxs-lookup"><span data-stu-id="665d9-130">[Working with PIPs](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span></span>  
 [<span data-ttu-id="665d9-131">示例</span><span class="sxs-lookup"><span data-stu-id="665d9-131">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)