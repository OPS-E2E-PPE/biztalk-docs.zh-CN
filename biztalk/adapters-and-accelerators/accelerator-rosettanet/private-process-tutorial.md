---
title: 专用流程教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, tutorial
- private process tutorial
- tutorials, private process tutorial
ms.assetid: 58affc48-af73-406e-895f-696bc284d945
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adb94c1f7897ecd848d63f9141d2c244fccd0a07
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282582"
---
# <a name="private-process-tutorial"></a><span data-ttu-id="94ec6-102">专用流程教程</span><span class="sxs-lookup"><span data-stu-id="94ec6-102">Private Process Tutorial</span></span>
<span data-ttu-id="94ec6-103">本教程中包含的完整端到端解决方案中使用 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="94ec6-103">This tutorial contains a complete end-to-end solution using Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="94ec6-104">本教程详细介绍了必须为通过创建两个虚构的公司之间的贸易方案来实现 RosettaNet 兼容解决方案要遵循的步骤：Contoso (供应商组织） 和 Fabrikam，买方组织。</span><span class="sxs-lookup"><span data-stu-id="94ec6-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="94ec6-105">本教程中实现的方案使用 3A2-价格与可用性合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="94ec6-105">The scenario this tutorial implements uses the 3A2-Price and Availability Partner Interface Process (PIP).</span></span> <span data-ttu-id="94ec6-106">购买前买方 Fabrikam 向供应商 Contoso 发送 3A2-价格与可用性请求。</span><span class="sxs-lookup"><span data-stu-id="94ec6-106">Before a purchase, the buyer, Fabrikam, sends a 3A2-Price and Availability Request to the supplier, Contoso.</span></span> <span data-ttu-id="94ec6-107">此 PIP 可使 Fabrikam 获取特定产品，它们就可以处理通过业务规则来确定要购买产品有关的信息。</span><span class="sxs-lookup"><span data-stu-id="94ec6-107">This PIP enables Fabrikam to obtain information about a certain product that they can then process through business rules to make a determination about whether to purchase the product.</span></span> <span data-ttu-id="94ec6-108">下图显示了 3A2 PIP 交换过程在发起方和响应方组织之间的通信模式。</span><span class="sxs-lookup"><span data-stu-id="94ec6-108">The following figure shows the communication pattern between the initiator and responder organizations during a 3A2 PIP exchange.</span></span>  
  
 <span data-ttu-id="94ec6-109">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span><span class="sxs-lookup"><span data-stu-id="94ec6-109">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span></span>  
  
 <span data-ttu-id="94ec6-110">本教程的重点是 Contoso 解决方案。</span><span class="sxs-lookup"><span data-stu-id="94ec6-110">The focus of this tutorial is on the Contoso solution.</span></span> <span data-ttu-id="94ec6-111">它概述了创建基于 RosettaNet 的解决方案，包括 ERP 集成、 业务策略的实施、 专用流程的自定义和改进安全通信的各个方面。</span><span class="sxs-lookup"><span data-stu-id="94ec6-111">It outlines various aspects of creating a RosettaNet-based solution, including ERP integration, business policy enforcement, private process customization, and promoting secure communication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94ec6-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="94ec6-112">In This Section</span></span>  
  
-   [<span data-ttu-id="94ec6-113">准备私有流程教程</span><span class="sxs-lookup"><span data-stu-id="94ec6-113">Preparing for the Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-private-process-tutorial.md)  
  
-   [<span data-ttu-id="94ec6-114">创建 Contoso 解决方案</span><span class="sxs-lookup"><span data-stu-id="94ec6-114">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)  
  
-   [<span data-ttu-id="94ec6-115">创建 Fabrikam 解决方案</span><span class="sxs-lookup"><span data-stu-id="94ec6-115">Creating the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="94ec6-116">测试解决方案</span><span class="sxs-lookup"><span data-stu-id="94ec6-116">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)