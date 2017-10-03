---
title: "步骤 5： 生成 EAISchemas 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: "41"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394d9df78f7064df8501ed43149bd26793533c47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-build-the-eaischemas-project"></a><span data-ttu-id="24380-102">步骤 5：生成 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="24380-102">Step 5: Build the EAISchemas Project</span></span>
<span data-ttu-id="24380-103">![步骤 5 5](../core/media/step-5of5.gif "Step_5of5")</span><span class="sxs-lookup"><span data-stu-id="24380-103">![Step 5 of 5](../core/media/step-5of5.gif "Step_5of5")</span></span>  
  
 <span data-ttu-id="24380-104">**完成时间：** 6 だ 牧</span><span class="sxs-lookup"><span data-stu-id="24380-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="24380-105">**目标：**在此步骤中，您将编译 EAISchemas 项目。</span><span class="sxs-lookup"><span data-stu-id="24380-105">**Objective:** In this step, you compile the EAISchemas project.</span></span>  
  
 <span data-ttu-id="24380-106">**用途：** Microsoft BizTalk Server 和.NET Framework 的最重要方面是，所有的 BizTalk Server 项目; 地图、 架构、 业务流程和管道，可以编译成.NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="24380-106">**Purpose:** The most important aspect of Microsoft BizTalk Server and the .NET Framework is that all BizTalk Server artifacts; maps, schemas, orchestrations, and pipelines, get compiled into .NET assemblies.</span></span> <span data-ttu-id="24380-107">此设计的两个最重要含义是：这些程序集必须具有强名称，为此它们还需遵守 .NET 版本控制规则。</span><span class="sxs-lookup"><span data-stu-id="24380-107">The two most important implications of this design are that these assemblies must have strong names, and because of that, they also follow .NET versioning rules.</span></span> <span data-ttu-id="24380-108">其主要含义是：根据特定版本的其他 .NET 项目或程序集（包括 BizTalk 项目）生成 BizTalk 项目后，该 BizTalk 项目将继续使用该版本，直到根据更高的版本重新生成该 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="24380-108">The main implication of this is that a BizTalk project, once built against a particular version of another .NET project or assembly (including BizTalk projects), continues to use that version until it has been rebuilt against a newer version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="24380-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="24380-109">Prerequisites</span></span>  
 <span data-ttu-id="24380-110">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="24380-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="24380-111">在开始此步骤之前，必须完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="24380-111">Before you begin this step you must complete the following steps:</span></span>  
  
    -   [<span data-ttu-id="24380-112">步骤 1： 创建 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="24380-112">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
    -   [<span data-ttu-id="24380-113">步骤 2： 创建清单请求架构</span><span class="sxs-lookup"><span data-stu-id="24380-113">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [<span data-ttu-id="24380-114">步骤 3： 创建请求拒绝架构</span><span class="sxs-lookup"><span data-stu-id="24380-114">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [<span data-ttu-id="24380-115">步骤 4： 创建代码图</span><span class="sxs-lookup"><span data-stu-id="24380-115">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a><span data-ttu-id="24380-116">过程</span><span class="sxs-lookup"><span data-stu-id="24380-116">Procedures</span></span>  
  
#### <a name="to-build-the-eaischemas-project"></a><span data-ttu-id="24380-117">若要生成 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="24380-117">To build the EAISchemas project</span></span>  
  
1.  <span data-ttu-id="24380-118">在解决方案资源管理器，右键单击**EAISchemas**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="24380-118">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
     <span data-ttu-id="24380-119">屏幕底部应显示：</span><span class="sxs-lookup"><span data-stu-id="24380-119">The bottom of the screen should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="24380-120">内容回顾</span><span class="sxs-lookup"><span data-stu-id="24380-120">What did I just do?</span></span>  
 <span data-ttu-id="24380-121">在此步骤中，为生成程序集文件 (DLL)，您需要构建 EAISchemas 项目。</span><span class="sxs-lookup"><span data-stu-id="24380-121">In this step, you built the EAISchemas project to generate an assembly file (DLL).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="24380-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="24380-122">Next Steps</span></span>  
 <span data-ttu-id="24380-123">创建针对中批准条件库存补货请求消息的内容的计算结果的业务流程[第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)。</span><span class="sxs-lookup"><span data-stu-id="24380-123">You create the business process that evaluates the contents of the inventory replenishment request message against approval criteria in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24380-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24380-124">See Also</span></span>  
 <span data-ttu-id="24380-125">[步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="24380-125">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="24380-126">[步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="24380-126">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="24380-127">[步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="24380-127">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 [<span data-ttu-id="24380-128">步骤 4： 创建代码图</span><span class="sxs-lookup"><span data-stu-id="24380-128">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)