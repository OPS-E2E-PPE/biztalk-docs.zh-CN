---
title: 开始使用 BizTalk Accelerator for RosettaNet |Microsoft Docs
description: 请参阅可用的教程，以帮助了解和开始使用 BizTalk Server 中的 RosettaNet 加速器 (BTARN)
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btarn.configuration.introduction
ms.assetid: 28a8942c-b461-4b2f-bc1f-1fc22cd08882
ms.author: mandia
ms.openlocfilehash: 6b4a732943e5d6cc1ada8bab55be8f595dac9d9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283706"
---
# <a name="get-started-with-biztalk-accelerator-for-rosettanet"></a><span data-ttu-id="b3f66-103">开始使用 BizTalk Accelerator for RosettaNet</span><span class="sxs-lookup"><span data-stu-id="b3f66-103">Get started with BizTalk Accelerator for RosettaNet</span></span>
<span data-ttu-id="b3f66-104">Microsoft BizTalk Accelerator for RosettaNet (BTARN) 简化了开发和部署的 RosettaNet 基于标准的集成解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3f66-104">The Microsoft BizTalk Accelerator for RosettaNet (BTARN) streamlines the development and deployment of RosettaNet standards-based integration solutions.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="b3f66-105">支持 RosettaNet 实现框架 (RNIF) 版本 1.1 和 2.0.01。</span><span class="sxs-lookup"><span data-stu-id="b3f66-105">supports the RosettaNet Implementation Framework (RNIF) versions 1.1 and 2.0.01.</span></span> <span data-ttu-id="b3f66-106">RNIF 是一种开放式网络应用程序框架，使业务合作伙伴能够协同运行 RosettaNet 合作伙伴接口流程 (Pip)。</span><span class="sxs-lookup"><span data-stu-id="b3f66-106">RNIF is an open network application framework that enables business partners to collaboratively run RosettaNet Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="b3f66-107">请参阅[GS1 美国](http://go.microsoft.com/fwlink/?LinkID=33859)有关 RosettaNet 标准的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3f66-107">See [GS1 US](http://go.microsoft.com/fwlink/?LinkID=33859) for more information about RosettaNet standard.</span></span>
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="b3f66-108">此外支持化工数据交换 (CIDX) Chem eStandards 的交换。</span><span class="sxs-lookup"><span data-stu-id="b3f66-108">also supports the exchange of Chemical Data Exchange (CIDX) Chem eStandards.</span></span>  
  
<span data-ttu-id="b3f66-109">本部分提供有关如何使用 BizTalk Server 与 RosettaNet 加速器在公司中的企业应用程序集成 (EAI) 和业务合作伙伴之间自动执行企业到企业采购特定于角色的信息解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3f66-109">This section provides role-specific information about how you can use BizTalk Server and the RosettaNet accelerator in your company for enterprise application integration (EAI), and among business partners to automate business-to-business procurement solutions.</span></span>  

## <a name="loopback-tutorial"></a><span data-ttu-id="b3f66-110">Loopback 教程</span><span class="sxs-lookup"><span data-stu-id="b3f66-110">Loopback tutorial</span></span>

<span data-ttu-id="b3f66-111">包含介绍如何使用 RosettaNet 加速器模拟一台计算机上的家庭和合作伙伴组织之间的流程实施的详细的步骤。</span><span class="sxs-lookup"><span data-stu-id="b3f66-111">Includes detailed steps that describe how to use the RosettaNet accelerator to simulate a process implementation between the home and partner organization on a single computer.</span></span>

<span data-ttu-id="b3f66-112">在本教程中，您将创建本组织、 合作伙伴组织和贸易协议、 使用 Loopback 实用工具创建镜像协议，，然后运行示例流程来验证环回方案。</span><span class="sxs-lookup"><span data-stu-id="b3f66-112">In this tutorial, you create a home organization, a partner organization, a trade agreement, use the Loopback utility to create a mirror agreement, and then run a sample process to verify the loop-back scenario.</span></span>

<span data-ttu-id="b3f66-113">转到[Loopback 教程](loopback-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="b3f66-113">Go to [Loopback tutorial](loopback-tutorial.md).</span></span> 

## <a name="double-action-tutorial"></a><span data-ttu-id="b3f66-114">双操作教程</span><span class="sxs-lookup"><span data-stu-id="b3f66-114">Double action tutorial</span></span>

<span data-ttu-id="b3f66-115">使用 RosettaNet 加速器的端到端解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3f66-115">An end-to-end solution using the RosettaNet accelerator.</span></span> <span data-ttu-id="b3f66-116">本教程详述了通过创建两个虚构的公司之间的贸易合作伙伴方案来实现 RosettaNet 兼容解决方案的步骤：Contoso (供应商组织） 和 Fabrikam，买方组织。</span><span class="sxs-lookup"><span data-stu-id="b3f66-116">The tutorial details the steps to implement a RosettaNet-compliant solution by creating a trading partner scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>

<span data-ttu-id="b3f66-117">它包括使用 BTARN 管理控制台、 创建业务线 (LOB) 应用程序，以及创建自定义业务流程。</span><span class="sxs-lookup"><span data-stu-id="b3f66-117">It includes working with the BTARN Management Console, creating line-of-business (LOB) applications, and creating custom orchestrations.</span></span>

<span data-ttu-id="b3f66-118">转到[双操作教程](double-action-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="b3f66-118">Go to [Double action tutorial](double-action-tutorial.md).</span></span> 


## <a name="private-process-tutorial"></a><span data-ttu-id="b3f66-119">专用流程教程</span><span class="sxs-lookup"><span data-stu-id="b3f66-119">Private process tutorial</span></span>
<span data-ttu-id="b3f66-120">使用 RosettaNet 加速器的端到端解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3f66-120">An end-to-end solution using the RosettaNet accelerator.</span></span> <span data-ttu-id="b3f66-121">本教程详述了通过创建两个虚构的公司之间的贸易方案来实现 RosettaNet 兼容解决方案的步骤：Contoso (供应商组织） 和 Fabrikam，买方组织。</span><span class="sxs-lookup"><span data-stu-id="b3f66-121">The tutorial details the steps to implement a RosettaNet-compliant solution by creating a trading scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>

<span data-ttu-id="b3f66-122">它概述了创建基于 RosettaNet 的解决方案，包括 ERP 集成、 业务策略的实施、 专用流程的自定义和改进安全通信的各个方面。</span><span class="sxs-lookup"><span data-stu-id="b3f66-122">It outlines various aspects of creating a RosettaNet-based solution, including ERP integration, business policy enforcement, private process customization, and promoting secure communication.</span></span>

<span data-ttu-id="b3f66-123">转到[专用流程教程](private-process-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="b3f66-123">Go to [Private process tutorial](private-process-tutorial.md)</span></span>


## <a name="tutorial-links"></a><span data-ttu-id="b3f66-124">教程的链接</span><span class="sxs-lookup"><span data-stu-id="b3f66-124">Tutorial Links</span></span>
[<span data-ttu-id="b3f66-125">Loopback 教程</span><span class="sxs-lookup"><span data-stu-id="b3f66-125">Loopback tutorial</span></span>](loopback-tutorial.md)  
[<span data-ttu-id="b3f66-126">双操作教程</span><span class="sxs-lookup"><span data-stu-id="b3f66-126">Double action tutorial</span></span>](double-action-tutorial.md)  
[<span data-ttu-id="b3f66-127">专用流程教程</span><span class="sxs-lookup"><span data-stu-id="b3f66-127">Private process tutorial</span></span>](private-process-tutorial.md)

## <a name="see-also"></a><span data-ttu-id="b3f66-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3f66-128">See also</span></span>
[<span data-ttu-id="b3f66-129">为残障人士提供的辅助功能</span><span class="sxs-lookup"><span data-stu-id="b3f66-129">Accessibility for People with Disabilities</span></span>](accessibility-for-people-with-disabilities3.md)