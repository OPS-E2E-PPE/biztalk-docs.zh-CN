---
title: 双操作教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, PIPs
- double action tutorial, about the tutorial
- trading partners, tutorials
- double action tutorial
- tutorials, trading partners
- PIPs, tutorials
- tutorials, double action tutorial
ms.assetid: b692c043-82ef-46f4-8683-7ae1fd6e4421
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 220f853788462d3c9b53b8fb043c65ac54872fd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973974"
---
# <a name="double-action-tutorial"></a><span data-ttu-id="8f00b-102">双操作教程</span><span class="sxs-lookup"><span data-stu-id="8f00b-102">Double Action Tutorial</span></span>
<span data-ttu-id="8f00b-103">本教程介绍如何使用 Microsoft® 的端到端解决方案[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8f00b-103">This tutorial covers an end-to-end solution using Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="8f00b-104">本教程详述了通过在两个虚构的公司：Contoso（供应商组织）和 Fabrikam（买方组织）之间创建贸易合作伙伴方案来实现 RosettaNet 兼容解决方案时，应该遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="8f00b-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading partner scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="8f00b-105">本教程使用四种不同的合作伙伴接口流程 (PIP)：</span><span class="sxs-lookup"><span data-stu-id="8f00b-105">This tutorial uses four different Partner Interface Processes (PIPs):</span></span>  
  
- <span data-ttu-id="8f00b-106">0C2 - 异步测试请求</span><span class="sxs-lookup"><span data-stu-id="8f00b-106">0C2 - Asynchronous Test Request</span></span>  
  
- <span data-ttu-id="8f00b-107">0C4 - 同步测试查询</span><span class="sxs-lookup"><span data-stu-id="8f00b-107">0C4 - Synchronous Test Query</span></span>  
  
- <span data-ttu-id="8f00b-108">3A2 - 请求价格与可用性</span><span class="sxs-lookup"><span data-stu-id="8f00b-108">3A2 - Request Price and Availability</span></span>  
  
- <span data-ttu-id="8f00b-109">3A4 - 请求采购订单</span><span class="sxs-lookup"><span data-stu-id="8f00b-109">3A4 - Request Purchase Order</span></span>  
  
  <span data-ttu-id="8f00b-110">本教程探讨 RosettaNet 解决方案的几个不同方面，包括使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台、创建业务线 (LOB) 应用程序，以及创建可用于与企业资源计划 (ERP) 系统集成的自定义业务流程。</span><span class="sxs-lookup"><span data-stu-id="8f00b-110">This tutorial addresses several distinct areas of a RosettaNet-based solution, including working with the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, creating line-of-business (LOB) applications, and creating custom orchestrations that you can use to integrate Enterprise Resource Planning (ERP) systems.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f00b-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f00b-111">In This Section</span></span>  
  
-   [<span data-ttu-id="8f00b-112">准备双操作教程</span><span class="sxs-lookup"><span data-stu-id="8f00b-112">Preparing for the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-double-action-tutorial.md)  
  
-   [<span data-ttu-id="8f00b-113">创建和配置 Contoso 解决方案</span><span class="sxs-lookup"><span data-stu-id="8f00b-113">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)  
  
-   [<span data-ttu-id="8f00b-114">创建和配置 Fabrikam 解决方案</span><span class="sxs-lookup"><span data-stu-id="8f00b-114">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="8f00b-115">测试双操作教程</span><span class="sxs-lookup"><span data-stu-id="8f00b-115">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)