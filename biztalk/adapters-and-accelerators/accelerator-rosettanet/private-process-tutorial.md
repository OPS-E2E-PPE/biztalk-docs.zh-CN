---
title: "私有过程教程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, tutorial
- private process tutorial
- tutorials, private process tutorial
ms.assetid: 58affc48-af73-406e-895f-696bc284d945
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c017d8b9b52c1f477aba62308ca2e65a1550564
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="private-process-tutorial"></a><span data-ttu-id="17a8c-102">私有过程教程</span><span class="sxs-lookup"><span data-stu-id="17a8c-102">Private Process Tutorial</span></span>
<span data-ttu-id="17a8c-103">本教程包含使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 的完整端对端解决方案。</span><span class="sxs-lookup"><span data-stu-id="17a8c-103">This tutorial contains a complete end-to-end solution using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="17a8c-104">本教程详述了通过在两个虚构的公司：Contoso（供应商组织）和 Fabrikam（买方组织）之间创建贸易方案来实现 RosettaNet 兼容解决方案时，应该遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="17a8c-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="17a8c-105">本教程实施的方案使用 3A2-价格与可用性合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="17a8c-105">The scenario this tutorial implements uses the 3A2-Price and Availability Partner Interface Process (PIP).</span></span> <span data-ttu-id="17a8c-106">买方 Fabrikam 在购买前会向供应商 Contoso 发送 3A2-价格与可用性请求。</span><span class="sxs-lookup"><span data-stu-id="17a8c-106">Before a purchase, the buyer, Fabrikam, sends a 3A2-Price and Availability Request to the supplier, Contoso.</span></span> <span data-ttu-id="17a8c-107">此 PIP 可使 Fabrikam 获取特定产品的相关信息，然后可以通过业务规则对这些信息进行处理，从而确定是否要购买该产品。</span><span class="sxs-lookup"><span data-stu-id="17a8c-107">This PIP enables Fabrikam to obtain information about a certain product that they can then process through business rules to make a determination about whether to purchase the product.</span></span> <span data-ttu-id="17a8c-108">下图显示了 3A2 PIP 交换过程中发起方组织和响应方组织之间的通信模式。</span><span class="sxs-lookup"><span data-stu-id="17a8c-108">The following figure shows the communication pattern between the initiator and responder organizations during a 3A2 PIP exchange.</span></span>  
  
 <span data-ttu-id="17a8c-109">![&#60;无更改 &#62;] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span><span class="sxs-lookup"><span data-stu-id="17a8c-109">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span></span>  
  
 <span data-ttu-id="17a8c-110">本教程的重点在于 Contoso 解决方案。</span><span class="sxs-lookup"><span data-stu-id="17a8c-110">The focus of this tutorial is on the Contoso solution.</span></span> <span data-ttu-id="17a8c-111">本教程探讨了创建基于 RosettaNet 的解决方案的各个方面，包括 ERP 集成、业务策略的实施、专用流程的自定义以及改进安全通信。</span><span class="sxs-lookup"><span data-stu-id="17a8c-111">It outlines various aspects of creating a RosettaNet-based solution, including ERP integration, business policy enforcement, private process customization, and promoting secure communication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17a8c-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="17a8c-112">In This Section</span></span>  
  
-   [<span data-ttu-id="17a8c-113">准备私有过程教程</span><span class="sxs-lookup"><span data-stu-id="17a8c-113">Preparing for the Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-private-process-tutorial.md)  
  
-   [<span data-ttu-id="17a8c-114">创建 Contoso 解决方案</span><span class="sxs-lookup"><span data-stu-id="17a8c-114">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)  
  
-   [<span data-ttu-id="17a8c-115">创建 Fabrikam 解决方案</span><span class="sxs-lookup"><span data-stu-id="17a8c-115">Creating the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="17a8c-116">测试解决方案</span><span class="sxs-lookup"><span data-stu-id="17a8c-116">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)