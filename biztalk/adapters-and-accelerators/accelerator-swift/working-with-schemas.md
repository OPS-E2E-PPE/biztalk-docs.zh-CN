---
title: "使用架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, schemas
- schemas, developing
ms.assetid: 123c4b43-34e4-41c7-980d-5d518b1479c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 404beaeb617f7a6c0c5e3fc4ddc40126e6b97990
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="working-with-schemas"></a><span data-ttu-id="ec18b-102">使用架构</span><span class="sxs-lookup"><span data-stu-id="ec18b-102">Working with Schemas</span></span>
<span data-ttu-id="ec18b-103">中提供的架构[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]是[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]XSD 表示形式的全球 Interbank 财务电信 (SWIFT) FIN 消息互联网协会。</span><span class="sxs-lookup"><span data-stu-id="ec18b-103">The schemas provided in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] XSD representation of the Society for Worldwide Interbank Financial Telecommunication (SWIFT) FIN messages.</span></span> <span data-ttu-id="ec18b-104">每个消息类型都有其自己的架构，包括 SWIFT 标头和 SWIFT 预告片 （交换格式）。</span><span class="sxs-lookup"><span data-stu-id="ec18b-104">Each message type has its own schema, including the SWIFT header and SWIFT trailer (interchange format).</span></span> <span data-ttu-id="ec18b-105">此架构并有效地发送或接收 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="ec18b-105">This schema is sufficient to send or receive a SWIFT message.</span></span> <span data-ttu-id="ec18b-106">这些架构是分隔和位置的记录，提供详细的 XML 表示形式的平面文件 FIN 结构的唯一组合。</span><span class="sxs-lookup"><span data-stu-id="ec18b-106">These schemas are a unique mixture of delimited and positional records, providing a detailed XML representation of the flat-file FIN structures.</span></span>  
  
 <span data-ttu-id="ec18b-107">大多数 SWIFT 客户使用 SWIFT FIN 消息的一个相对较小子集。</span><span class="sxs-lookup"><span data-stu-id="ec18b-107">Most SWIFT customers use a relatively small subset of the SWIFT FIN messages.</span></span> <span data-ttu-id="ec18b-108">若要为这些客户实现解决方案，你可以创建 BizTalk 架构项目 (如所示[模块 2： 添加新的架构项目](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)的 A4SWIFT 教程)。</span><span class="sxs-lookup"><span data-stu-id="ec18b-108">To implement a solution for these customers, you can create a BizTalk schema project (as demonstrated in [Module 2: Adding a New Schemas Project](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md) of the A4SWIFT tutorial).</span></span> <span data-ttu-id="ec18b-109">将相关消息架构添加 (MT*xxx*.xsd) 从\\\ 程序 Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>MessagePack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category x\MT xyy 目录，其中 x 是 FIN 消息类型的第一个数字，xyy 是消息的三个数字消息类型。</span><span class="sxs-lookup"><span data-stu-id="ec18b-109">Add the relevant message schemas (MT*xxx*.xsd) from \\\ Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category x\MT xyy directory, where x is the first digit of the FIN message type and xyy is the three-digit message type for the message.</span></span>  
  
 <span data-ttu-id="ec18b-110">你可以将多个架构添加到同一个项目。</span><span class="sxs-lookup"><span data-stu-id="ec18b-110">You can add several schemas to the same project.</span></span> <span data-ttu-id="ec18b-111">若要维护可管理性，则不应添加 20 个以上的消息架构，每个项目。</span><span class="sxs-lookup"><span data-stu-id="ec18b-111">To maintain manageability, you should not add more than 20 message schemas per project.</span></span> <span data-ttu-id="ec18b-112">你还需要将这些基类和常见架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="ec18b-112">You also need to add the base and common schemas to the project.</span></span> <span data-ttu-id="ec18b-113">如果你已部署的基类和常用的架构，你需要使其程序集的引用，而不是将它们部署。</span><span class="sxs-lookup"><span data-stu-id="ec18b-113">If you have already deployed the base and common schemas, you need to make a reference to their assembly, rather than deploy them.</span></span> <span data-ttu-id="ec18b-114">本部分介绍这些架构。</span><span class="sxs-lookup"><span data-stu-id="ec18b-114">This section describes these schemas.</span></span> <span data-ttu-id="ec18b-115">消息架构已准备好使用，因为是到 SWIFT 网络发送的消息和从 SWIFT 接收的消息。</span><span class="sxs-lookup"><span data-stu-id="ec18b-115">The message schemas are ready to use as is for both messages sent to the SWIFT network and messages received from SWIFT.</span></span>  
  
 <span data-ttu-id="ec18b-116">你可以检查每个 SWIFT 架构中的内容[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]使用架构编辑器。</span><span class="sxs-lookup"><span data-stu-id="ec18b-116">You can examine the contents of each SWIFT schema in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] using the Schema Editor.</span></span> <span data-ttu-id="ec18b-117">所有消息交换架构具有以下常见结构：</span><span class="sxs-lookup"><span data-stu-id="ec18b-117">All of the message interchange schemas have the following common structure:</span></span>  
  
-   <span data-ttu-id="ec18b-118">标头</span><span class="sxs-lookup"><span data-stu-id="ec18b-118">Headers</span></span>  
  
-   <span data-ttu-id="ec18b-119">消息正文</span><span class="sxs-lookup"><span data-stu-id="ec18b-119">Message text</span></span>  
  
-   <span data-ttu-id="ec18b-120">拖车安排</span><span class="sxs-lookup"><span data-stu-id="ec18b-120">Trailers</span></span>  
  
 <span data-ttu-id="ec18b-121">本部分介绍的标头和尾的架构。</span><span class="sxs-lookup"><span data-stu-id="ec18b-121">This section describes the header and trailer schemas.</span></span> <span data-ttu-id="ec18b-122">消息文本包括 FIN 消息中的负载和包含的所有数据字段包含消息类型，发送方和接收方，字段除外。</span><span class="sxs-lookup"><span data-stu-id="ec18b-122">The message text comprises the payload of the FIN message, and contains all of the data fields except the fields containing the sender, receiver, and message type.</span></span> <span data-ttu-id="ec18b-123">这三个字段都包含在标头部分。</span><span class="sxs-lookup"><span data-stu-id="ec18b-123">These three fields are contained in the header portion.</span></span> <span data-ttu-id="ec18b-124">有些消息还包含一个可选的用户标头，也可提供处理信息。</span><span class="sxs-lookup"><span data-stu-id="ec18b-124">Some messages also contain an optional user header, which may also provide processing information.</span></span>  
  
 <span data-ttu-id="ec18b-125">每个 FIN 消息负载包含的一系列定义的序列中的字段。</span><span class="sxs-lookup"><span data-stu-id="ec18b-125">Each FIN message payload consists of a series of fields in a defined sequence.</span></span> <span data-ttu-id="ec18b-126">这些字段符合以下规则：</span><span class="sxs-lookup"><span data-stu-id="ec18b-126">These fields conform to the following rules:</span></span>  
  
-   <span data-ttu-id="ec18b-127">字段可能必需或可选在序列中。</span><span class="sxs-lookup"><span data-stu-id="ec18b-127">The fields may be required or optional within the sequence.</span></span>  
  
-   <span data-ttu-id="ec18b-128">序列可能包含子序列，并且子序列可以重复序列内。</span><span class="sxs-lookup"><span data-stu-id="ec18b-128">A sequence may contain sub-sequences, and a sub-sequence may repeat within a sequence.</span></span>  
  
-   <span data-ttu-id="ec18b-129">你可以使用几种消息类型中的字段。</span><span class="sxs-lookup"><span data-stu-id="ec18b-129">You can use a field in several message types.</span></span>  
  
-   <span data-ttu-id="ec18b-130">在字段中，可能有元素或子字段。</span><span class="sxs-lookup"><span data-stu-id="ec18b-130">Within a field, there may be elements or subfields.</span></span> <span data-ttu-id="ec18b-131">元素或子字段可能是普遍适用于多个字段。</span><span class="sxs-lookup"><span data-stu-id="ec18b-131">An element or subfield may be common to several fields.</span></span>  
  
-   <span data-ttu-id="ec18b-132">组节点表示每个重复的序列。</span><span class="sxs-lookup"><span data-stu-id="ec18b-132">A group node represents each repeating sequence.</span></span>  
  
-   <span data-ttu-id="ec18b-133">每个字段可能本身具有多个 nodal 级别，每个作为记录所述。</span><span class="sxs-lookup"><span data-stu-id="ec18b-133">Each field may itself have multiple nodal levels, each described as a record.</span></span>  
  
-   <span data-ttu-id="ec18b-134">架构元素表示仅最低的级别个子字段。</span><span class="sxs-lookup"><span data-stu-id="ec18b-134">Schema elements represent only the lowest level subfields.</span></span>  
  
-   <span data-ttu-id="ec18b-135">常见和基架构定义通用记录和元素。</span><span class="sxs-lookup"><span data-stu-id="ec18b-135">The common and base schemas define common records and elements.</span></span>  
  
-   <span data-ttu-id="ec18b-136">架构表示几种格式 （如方字段） 中的某些字段。</span><span class="sxs-lookup"><span data-stu-id="ec18b-136">Schemas represent some fields in several formats (such as party fields).</span></span> <span data-ttu-id="ec18b-137">架构定义选择字段为此类字段。</span><span class="sxs-lookup"><span data-stu-id="ec18b-137">Schemas define such fields as choice fields.</span></span>  
  
-   <span data-ttu-id="ec18b-138">某些字段具有有限组值。</span><span class="sxs-lookup"><span data-stu-id="ec18b-138">Some fields have limited sets of values.</span></span> <span data-ttu-id="ec18b-139">大多数情况下，架构列出了这些值。</span><span class="sxs-lookup"><span data-stu-id="ec18b-139">For the most part, the schema lists these values.</span></span> <span data-ttu-id="ec18b-140">架构定义还包括字符集验证。</span><span class="sxs-lookup"><span data-stu-id="ec18b-140">Schema definitions also include character set validation.</span></span>  
  
 <span data-ttu-id="ec18b-141">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="ec18b-141">This section contains:</span></span>  
  
-   [<span data-ttu-id="ec18b-142">基础架构和通用架构</span><span class="sxs-lookup"><span data-stu-id="ec18b-142">Base and Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/base-and-common-schemas.md)  
  
-   [<span data-ttu-id="ec18b-143">SWIFT 标头和尾部架构</span><span class="sxs-lookup"><span data-stu-id="ec18b-143">SWIFT Header and Trailer Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
-   [<span data-ttu-id="ec18b-144">SWIFT 架构命名约定</span><span class="sxs-lookup"><span data-stu-id="ec18b-144">SWIFT Schema Naming Conventions</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-schema-naming-conventions.md)