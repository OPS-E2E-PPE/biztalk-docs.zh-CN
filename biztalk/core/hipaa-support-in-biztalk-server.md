---
title: BizTalk Server 中的 HIPAA 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ad8c64-6375-4364-80ce-440db943c222
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06d59b485553f2a994dc3dcc47ce14f58a469735
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344359"
---
# <a name="hipaa-support-in-biztalk-server"></a><span data-ttu-id="3825c-102">BizTalk Server 中的 HIPAA 支持</span><span class="sxs-lookup"><span data-stu-id="3825c-102">HIPAA Support in BizTalk Server</span></span>
<span data-ttu-id="3825c-103">本主题提供了 HIPAA 的简要概述以及如何[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]支持 HIPAA。</span><span class="sxs-lookup"><span data-stu-id="3825c-103">This topic provides a brief overview of HIPAA and how [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] supports HIPAA.</span></span>  
  
## <a name="introduction-to-hipaa"></a><span data-ttu-id="3825c-104">HIPAA 简介</span><span class="sxs-lookup"><span data-stu-id="3825c-104">Introduction to HIPAA</span></span>  
 <span data-ttu-id="3825c-105">健康保险流通与责任法案 (HIPAA) 1996年要求涵盖的实体时它们以电子方式执行事务如声明、 汇款、 资格、 声明状态请求和响应，使用强制的标准和其他人。</span><span class="sxs-lookup"><span data-stu-id="3825c-105">The Health Insurance Portability and Accountability Act of 1996 (HIPAA) requires covered entities to use mandated standards when they electronically conduct transactions such as claims, remittance, eligibility, claims status requests and responses, and others.</span></span> <span data-ttu-id="3825c-106">Hipaa 涵盖的实体是运行状况计划、 交换所和大多数医疗保健提供商。</span><span class="sxs-lookup"><span data-stu-id="3825c-106">Covered entities under HIPAA are health plans, clearing houses, and most health care providers.</span></span>  
  
## <a name="hipaa-support-in-biztalk-server"></a><span data-ttu-id="3825c-107">BizTalk Server 中的 HIPAA 支持</span><span class="sxs-lookup"><span data-stu-id="3825c-107">HIPAA support in BizTalk Server</span></span>  
 <span data-ttu-id="3825c-108">Microsoft 还致力于帮助医疗保健和联盟的组织改进医疗保健及进行融资的方法。</span><span class="sxs-lookup"><span data-stu-id="3825c-108">Microsoft is committed to helping health care and allied organizations improve the way health care is delivered and financed.</span></span> <span data-ttu-id="3825c-109">Microsoft 致力于减少的时间和金钱，组织必须花费符合 HIPAA 法规。</span><span class="sxs-lookup"><span data-stu-id="3825c-109">Microsoft intends to reduce the amount of time and money that organizations must spend complying with HIPAA regulations.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3825c-110">可帮助组织解决的挑战创建自动化的业务流程的连接，并在不同的医疗保健系统之间进行互操作。</span><span class="sxs-lookup"><span data-stu-id="3825c-110">helps organizations meet the challenges of creating automated business processes that connect and interoperate across diverse healthcare systems.</span></span> <span data-ttu-id="3825c-111">受 HIPAA 影响的组织可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的功能，可帮助在开发、 实现和集成符合事务的解决方案同时也符合联邦法律。</span><span class="sxs-lookup"><span data-stu-id="3825c-111">Organizations affected by HIPAA can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]’s capabilities to help in developing, implementing, and integrating transaction-compliant solutions which also comply with federal law.</span></span>  
  
[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3825c-112">包括提供对 HIPAA 的支持的固有功能。</span><span class="sxs-lookup"><span data-stu-id="3825c-112">includes native functionality providing support for HIPAA.</span></span> <span data-ttu-id="3825c-113">它不是外接程序对产品，例如适配器或加速器。</span><span class="sxs-lookup"><span data-stu-id="3825c-113">It is not an add-in to the product, such as an adapter or an accelerator.</span></span> <span data-ttu-id="3825c-114">它是内置于产品。</span><span class="sxs-lookup"><span data-stu-id="3825c-114">It is built into the product.</span></span> [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3825c-115">包括 EDI 组件和功能所需同时遵守 HIPAA 要求，并需要将 hipaa 作为管理良好且经过测定的业务流程。</span><span class="sxs-lookup"><span data-stu-id="3825c-115">includes the EDI components and capabilities that are required to both comply with the HIPAA mandates and to also embrace HIPAA as a well-managed and measured business process.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3825c-116">支持 HIPAA 5010 和 4010 版本。</span><span class="sxs-lookup"><span data-stu-id="3825c-116">supports HIPAA version 5010 and 4010.</span></span>  
  
## <a name="hipaa-documentation-in-biztalk-server"></a><span data-ttu-id="3825c-117">BizTalk Server 中的 HIPAA 文档</span><span class="sxs-lookup"><span data-stu-id="3825c-117">HIPAA documentation in BizTalk Server</span></span>  
 <span data-ttu-id="3825c-118">主要的 EDI 标准包括 X12 （由 ANSI 进行标准化，主要在北美地区） 和 EDIFACT （由联合国进行标准化，主要在美国以外）。</span><span class="sxs-lookup"><span data-stu-id="3825c-118">The primary EDI standards are X12 (standardized by ANSI and primarily used in North America) and EDIFACT (standardized by the United Nations and primarily used outside the U.S.).</span></span> <span data-ttu-id="3825c-119">HIPAA 是从 X12 派生的标准。</span><span class="sxs-lookup"><span data-stu-id="3825c-119">HIPAA is a standard derived from X12.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3825c-120">作为本地 X12 的一部分提供的 HIPAA 支持 EDI 功能。</span><span class="sxs-lookup"><span data-stu-id="3825c-120">provides HIPAA support as part of the native X12 EDI functionality.</span></span> <span data-ttu-id="3825c-121">因此，将出现在支持对 X12 引用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档，这一支持也适用于 HIPAA 处理，除非明确声明。</span><span class="sxs-lookup"><span data-stu-id="3825c-121">Therefore, where you see references to X12 support in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation, this support also applies to HIPAA processing, unless explicitly stated otherwise.</span></span>  
  
 <span data-ttu-id="3825c-122">中的以下节[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有关于 HIPAA 的特定信息。</span><span class="sxs-lookup"><span data-stu-id="3825c-122">The following sections in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] have specific information about HIPAA.</span></span>  
  
 <span data-ttu-id="3825c-123">**入门**</span><span class="sxs-lookup"><span data-stu-id="3825c-123">**Getting Started**</span></span>  
  
- [<span data-ttu-id="3825c-124">HIPAA 事务集</span><span class="sxs-lookup"><span data-stu-id="3825c-124">HIPAA Transaction Sets</span></span>](../core/hipaa-transaction-sets.md)  
  
  <span data-ttu-id="3825c-125">**规划和体系结构**</span><span class="sxs-lookup"><span data-stu-id="3825c-125">**Planning and Architecture**</span></span>  
  
- [<span data-ttu-id="3825c-126">HIPAA 文档架构版本 5010</span><span class="sxs-lookup"><span data-stu-id="3825c-126">HIPAA Document Schema Version 5010</span></span>](../core/hipaa-document-schema-version-5010.md)  
  
- [<span data-ttu-id="3825c-127">HIPAA 架构触发器字段批注</span><span class="sxs-lookup"><span data-stu-id="3825c-127">HIPAA Schema Trigger Field Annotations</span></span>](../core/hipaa-schema-trigger-field-annotations.md)  
  
- [<span data-ttu-id="3825c-128">拆分 HIPAA 子文档</span><span class="sxs-lookup"><span data-stu-id="3825c-128">Splitting HIPAA Subdocuments</span></span>](../core/splitting-hipaa-subdocuments.md)  
  
  <span data-ttu-id="3825c-129">**开发**</span><span class="sxs-lookup"><span data-stu-id="3825c-129">**Development**</span></span>  
  
- [<span data-ttu-id="3825c-130">修改 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="3825c-130">Modifying EDI Schemas</span></span>](../core/modifying-edi-schemas.md) 

- [<span data-ttu-id="3825c-131">在信封架构中自定义枚举</span><span class="sxs-lookup"><span data-stu-id="3825c-131">Customizing Enumerations in the Envelope Schema</span></span>](../core/customizing-enumerations-in-the-envelope-schema.md)

- [<span data-ttu-id="3825c-132">配置跨字段验证</span><span class="sxs-lookup"><span data-stu-id="3825c-132">Configuring Cross-Field Validation</span></span>](../core/configuring-cross-field-validation.md)

  
 <span data-ttu-id="3825c-133">**故障排除**</span><span class="sxs-lookup"><span data-stu-id="3825c-133">**Troubleshooting**</span></span>  
  
-   [<span data-ttu-id="3825c-134">EDI 接收处理的已知问题</span><span class="sxs-lookup"><span data-stu-id="3825c-134">Known Issues with EDI Receive Processing</span></span>](../core/known-issues-with-edi-receive-processing.md)  
  
-   [<span data-ttu-id="3825c-135">XML 工具与 EDI 解决方案一起使用时的已知问题</span><span class="sxs-lookup"><span data-stu-id="3825c-135">Known Issues with XML Tools Used with EDI Solutions</span></span>](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)  
  
## <a name="more-information-about-hipaa"></a><span data-ttu-id="3825c-136">有关 HIPAA 的详细信息</span><span class="sxs-lookup"><span data-stu-id="3825c-136">More information about HIPAA</span></span>  
  
-   <span data-ttu-id="3825c-137">有关美国国家标准协会，转到的电子数据交换的公认标准委员会[ASC X12 主页](http://www.x12.org/)。</span><span class="sxs-lookup"><span data-stu-id="3825c-137">For information about the American National Standards Institute, Accredited Standards Committee for Electronic Data Interchange, go to [ASC X12 home](http://www.x12.org/).</span></span>  
  
-   <span data-ttu-id="3825c-138">有关 HIPAA 采用的指南有关 X12 的保险小组委员会和其实现的信息，请转到[华盛顿发布公司的 HIPAA EDI 指导](http://www.wpc-edi.com/)。</span><span class="sxs-lookup"><span data-stu-id="3825c-138">For information about X12's Insurance Subcommittee and their implementation guides adopted under HIPAA, go to [Washington Publishing Company's HIPAA EDI guides](http://www.wpc-edi.com/).</span></span>
  
-   <span data-ttu-id="3825c-139">有关电子数据交换工作组的信息，请转到[电子数据交换主页上的工作组](http://www.wedi.org/)。</span><span class="sxs-lookup"><span data-stu-id="3825c-139">For information about the Workgroup for Electronic Data Interchange, go to [Workgroup for Electronic Data Interchange home page](http://www.wedi.org/).</span></span>