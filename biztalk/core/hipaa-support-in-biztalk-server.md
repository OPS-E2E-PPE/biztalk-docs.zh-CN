---
title: "BizTalk Server 中的 HIPAA 支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1ad8c64-6375-4364-80ce-440db943c222
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34dd17ed875c5927b7a10d8238ec7828ab96c79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="hipaa-support-in-biztalk-server"></a><span data-ttu-id="326c5-102">BizTalk Server 中的 HIPAA 支持</span><span class="sxs-lookup"><span data-stu-id="326c5-102">HIPAA Support in BizTalk Server</span></span>
<span data-ttu-id="326c5-103">本主题提供了 HIPAA 和 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 如何支持 HIPAA 的简要概述。</span><span class="sxs-lookup"><span data-stu-id="326c5-103">This topic provides a brief overview of HIPAA and how [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] supports HIPAA.</span></span>  
  
## <a name="introduction-to-hipaa"></a><span data-ttu-id="326c5-104">HIPAA 简介</span><span class="sxs-lookup"><span data-stu-id="326c5-104">Introduction to HIPAA</span></span>  
 <span data-ttu-id="326c5-105">1996 年通过的健康保险流通与责任法案 (HIPAA) 要求，受保护的实体在以电子方式执行交易（如声明、汇款、资格证明、声明状态请求和响应，以及其他活动）时，使用强制标准。</span><span class="sxs-lookup"><span data-stu-id="326c5-105">The Health Insurance Portability and Accountability Act of 1996 (HIPAA) requires covered entities to use mandated standards when they electronically conduct transactions such as claims, remittance, eligibility, claims status requests and responses, and others.</span></span> <span data-ttu-id="326c5-106">下 HIPAA 涵盖的实体是运行状况计划、 交换所和大多数卫生保健的提供程序。</span><span class="sxs-lookup"><span data-stu-id="326c5-106">Covered entities under HIPAA are health plans, clearing houses, and most health care providers.</span></span>  
  
## <a name="hipaa-support-in-biztalk-server"></a><span data-ttu-id="326c5-107">BizTalk Server 中的 HIPAA 支持</span><span class="sxs-lookup"><span data-stu-id="326c5-107">HIPAA support in BizTalk Server</span></span>  
 <span data-ttu-id="326c5-108">Microsoft 承诺帮助医疗保健和联盟组织改进提供医疗保健及进行融资的方法。</span><span class="sxs-lookup"><span data-stu-id="326c5-108">Microsoft is committed to helping health care and allied organizations improve the way health care is delivered and financed.</span></span> <span data-ttu-id="326c5-109">Microsoft 将尝试减少组织为遵循 HIPAA 规章必须花费的时间和金钱。</span><span class="sxs-lookup"><span data-stu-id="326c5-109">Microsoft intends to reduce the amount of time and money that organizations must spend complying with HIPAA regulations.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="326c5-110"> 可帮助组织解决以下难题：创建自动化的业务流程，以连接不同的健康保健系统并在这些系统之间进行互操作。</span><span class="sxs-lookup"><span data-stu-id="326c5-110"> helps organizations meet the challenges of creating automated business processes that connect and interoperate across diverse healthcare systems.</span></span> <span data-ttu-id="326c5-111">受 HIPAA 影响的组织可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的功能，来帮助开发、实现和集成符合事务，同时也符合联邦法的解决方案。</span><span class="sxs-lookup"><span data-stu-id="326c5-111">Organizations affected by HIPAA can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]’s capabilities to help in developing, implementing, and integrating transaction-compliant solutions which also comply with federal law.</span></span>  
  
[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="326c5-112"> 包括提供对 HIPAA 的支持的本机功能。</span><span class="sxs-lookup"><span data-stu-id="326c5-112"> includes native functionality providing support for HIPAA.</span></span> <span data-ttu-id="326c5-113">它不是产品的外接程序，例如适配器或加速器。</span><span class="sxs-lookup"><span data-stu-id="326c5-113">It is not an add-in to the product, such as an adapter or an accelerator.</span></span> <span data-ttu-id="326c5-114">而是内置于产品之中。</span><span class="sxs-lookup"><span data-stu-id="326c5-114">It is built into the product.</span></span> [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="326c5-115">包括 EDI 组件和功能所需两者都遵守 HIPAA 要求，并还实现为管理完善且经过测定业务流程的 HIPAA。</span><span class="sxs-lookup"><span data-stu-id="326c5-115"> includes the EDI components and capabilities that are required to both comply with the HIPAA mandates and to also embrace HIPAA as a well-managed and measured business process.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="326c5-116"> 支持 HIPAA 5010 和 4010 版本。</span><span class="sxs-lookup"><span data-stu-id="326c5-116"> supports HIPAA version 5010 and 4010.</span></span>  
  
## <a name="hipaa-documentation-in-biztalk-server"></a><span data-ttu-id="326c5-117">BizTalk Server 中的 HIPAA 文档</span><span class="sxs-lookup"><span data-stu-id="326c5-117">HIPAA documentation in BizTalk Server</span></span>  
 <span data-ttu-id="326c5-118">主要的 EDI 标准包括 X12（由 ANSI 进行标准化，主要在北美地区使用）和 EDIFACT（由联合国进行标准化，主要在美国以外的国家/地区使用）。</span><span class="sxs-lookup"><span data-stu-id="326c5-118">The primary EDI standards are X12 (standardized by ANSI and primarily used in North America) and EDIFACT (standardized by the United Nations and primarily used outside the U.S.).</span></span> <span data-ttu-id="326c5-119">HIPAA 是派生自 X12 标准。</span><span class="sxs-lookup"><span data-stu-id="326c5-119">HIPAA is a standard derived from X12.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="326c5-120">提供 HIPAA 支持作为一部分本机 X12 EDI 功能。</span><span class="sxs-lookup"><span data-stu-id="326c5-120"> provides HIPAA support as part of the native X12 EDI functionality.</span></span> <span data-ttu-id="326c5-121">因此，你在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中看到的对 X12 引用的支持也适用于 HIPAA 处理，除非你明确声明。</span><span class="sxs-lookup"><span data-stu-id="326c5-121">Therefore, where you see references to X12 support in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation, this support also applies to HIPAA processing, unless explicitly stated otherwise.</span></span>  
  
 <span data-ttu-id="326c5-122">以下各节中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有 HIPAA 的特定信息。</span><span class="sxs-lookup"><span data-stu-id="326c5-122">The following sections in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] have specific information about HIPAA.</span></span>  
  
 <span data-ttu-id="326c5-123">**入门**</span><span class="sxs-lookup"><span data-stu-id="326c5-123">**Getting Started**</span></span>  
  
-   [<span data-ttu-id="326c5-124">HIPAA 事务集</span><span class="sxs-lookup"><span data-stu-id="326c5-124">HIPAA Transaction Sets</span></span>](../core/hipaa-transaction-sets.md)  
  
 <span data-ttu-id="326c5-125">**规划和体系结构**</span><span class="sxs-lookup"><span data-stu-id="326c5-125">**Planning and Architecture**</span></span>  
  
-   [<span data-ttu-id="326c5-126">HIPAA 文档架构版本 5010</span><span class="sxs-lookup"><span data-stu-id="326c5-126">HIPAA Document Schema Version 5010</span></span>](../core/hipaa-document-schema-version-5010.md)  
  
-   [<span data-ttu-id="326c5-127">HIPAA 架构触发器字段批注</span><span class="sxs-lookup"><span data-stu-id="326c5-127">HIPAA Schema Trigger Field Annotations</span></span>](../core/hipaa-schema-trigger-field-annotations.md)  
  
-   [<span data-ttu-id="326c5-128">拆分 HIPAA 子文档</span><span class="sxs-lookup"><span data-stu-id="326c5-128">Splitting HIPAA Subdocuments</span></span>](../core/splitting-hipaa-subdocuments.md)  
  
 <span data-ttu-id="326c5-129">**开发**</span><span class="sxs-lookup"><span data-stu-id="326c5-129">**Development**</span></span>  
  
-   [<span data-ttu-id="326c5-130">修改 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="326c5-130">Modifying EDI Schemas</span></span>](../core/modifying-edi-schemas.md) 

- [<span data-ttu-id="326c5-131">信封架构中的自定义枚举</span><span class="sxs-lookup"><span data-stu-id="326c5-131">Customizing Enumerations in the Envelope Schema</span></span>](../core/customizing-enumerations-in-the-envelope-schema.md)

- [<span data-ttu-id="326c5-132">配置跨字段验证</span><span class="sxs-lookup"><span data-stu-id="326c5-132">Configuring Cross-Field Validation</span></span>](../core/configuring-cross-field-validation.md)

  
 <span data-ttu-id="326c5-133">**故障排除**</span><span class="sxs-lookup"><span data-stu-id="326c5-133">**Troubleshooting**</span></span>  
  
-   [<span data-ttu-id="326c5-134">已知的问题的 EDI 接收处理</span><span class="sxs-lookup"><span data-stu-id="326c5-134">Known Issues with EDI Receive Processing</span></span>](../core/known-issues-with-edi-receive-processing.md)  
  
-   [<span data-ttu-id="326c5-135">使用与 EDI 解决方案一起使用的 XML 工具的已知的问题</span><span class="sxs-lookup"><span data-stu-id="326c5-135">Known Issues with XML Tools Used with EDI Solutions</span></span>](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)  
  
## <a name="more-information-about-hipaa"></a><span data-ttu-id="326c5-136">有关 HIPAA 的详细信息</span><span class="sxs-lookup"><span data-stu-id="326c5-136">More information about HIPAA</span></span>  
  
-   <span data-ttu-id="326c5-137">有关美国国家标准局，经认证的委员会的电子数据交换，请转到[ASC X12 主](http://www.x12.org/)。</span><span class="sxs-lookup"><span data-stu-id="326c5-137">For information about the American National Standards Institute, Accredited Standards Committee for Electronic Data Interchange, go to [ASC X12 home](http://www.x12.org/).</span></span>  
  
-   <span data-ttu-id="326c5-138">对于 X12 的保险技术委员会及方法的实现有关的信息将指导下采用的 HIPAA，请转到[华盛顿发布公司 HIPAA EDI 指导](http://www.wpc-edi.com/)。</span><span class="sxs-lookup"><span data-stu-id="326c5-138">For information about X12's Insurance Subcommittee and their implementation guides adopted under HIPAA, go to [Washington Publishing Company's HIPAA EDI guides](http://www.wpc-edi.com/).</span></span>
  
-   <span data-ttu-id="326c5-139">有关工作组的电子数据交换的信息，请转到[电子数据交换主页上的工作组](http://www.wedi.org/)。</span><span class="sxs-lookup"><span data-stu-id="326c5-139">For information about the Workgroup for Electronic Data Interchange, go to [Workgroup for Electronic Data Interchange home page](http://www.wedi.org/).</span></span>