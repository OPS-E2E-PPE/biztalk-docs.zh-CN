---
title: 步骤 5：生成 EAISchemas 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b82d7b4d322464cb873e47e0e15e57c6f68f51d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244303"
---
# <a name="step-5-build-the-eaischemas-project"></a><span data-ttu-id="15157-102">步骤 5：生成 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="15157-102">Step 5: Build the EAISchemas Project</span></span>
<span data-ttu-id="15157-103">![步骤 5，共 5](../core/media/step-5of5.gif "Step_5of5")</span><span class="sxs-lookup"><span data-stu-id="15157-103">![Step 5 of 5](../core/media/step-5of5.gif "Step_5of5")</span></span>  
  
 <span data-ttu-id="15157-104">**若要完成的时间：** 6 分钟</span><span class="sxs-lookup"><span data-stu-id="15157-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="15157-105">**目标：** 在此步骤中，您将编译 EAISchemas 项目。</span><span class="sxs-lookup"><span data-stu-id="15157-105">**Objective:** In this step, you compile the EAISchemas project.</span></span>  
  
 <span data-ttu-id="15157-106">**目的：** Microsoft BizTalk Server 和.NET Framework 的最重要方面是，所有 BizTalk Server 项目;映射、 架构、 业务流程和管道，获取编译到.NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="15157-106">**Purpose:** The most important aspect of Microsoft BizTalk Server and the .NET Framework is that all BizTalk Server artifacts; maps, schemas, orchestrations, and pipelines, get compiled into .NET assemblies.</span></span> <span data-ttu-id="15157-107">这种设计的两个最重要的意义是，这些程序集必须具有强名称，并且正因为如此，它们还需遵守.NET 版本控制规则。</span><span class="sxs-lookup"><span data-stu-id="15157-107">The two most important implications of this design are that these assemblies must have strong names, and because of that, they also follow .NET versioning rules.</span></span> <span data-ttu-id="15157-108">其主要含义是，一次生成的其他.NET 项目或程序集 （包括 BizTalk 项目） 的特定版本的 BizTalk 项目，将继续使用该版本，直到它已针对较新版本重新生成。</span><span class="sxs-lookup"><span data-stu-id="15157-108">The main implication of this is that a BizTalk project, once built against a particular version of another .NET project or assembly (including BizTalk projects), continues to use that version until it has been rebuilt against a newer version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15157-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="15157-109">Prerequisites</span></span>  
 <span data-ttu-id="15157-110">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="15157-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="15157-111">开始此步骤之前，必须完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="15157-111">Before you begin this step you must complete the following steps:</span></span>  
  
    -   [<span data-ttu-id="15157-112">步骤 1：创建 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="15157-112">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
    -   [<span data-ttu-id="15157-113">步骤 2：创建库存请求架构</span><span class="sxs-lookup"><span data-stu-id="15157-113">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [<span data-ttu-id="15157-114">步骤 3：创建请求拒绝架构</span><span class="sxs-lookup"><span data-stu-id="15157-114">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [<span data-ttu-id="15157-115">步骤 4：创建映射</span><span class="sxs-lookup"><span data-stu-id="15157-115">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a><span data-ttu-id="15157-116">过程</span><span class="sxs-lookup"><span data-stu-id="15157-116">Procedures</span></span>  
  
#### <a name="to-build-the-eaischemas-project"></a><span data-ttu-id="15157-117">若要生成 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="15157-117">To build the EAISchemas project</span></span>  
  
1.  <span data-ttu-id="15157-118">在解决方案资源管理器中右键单击**EAISchemas**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="15157-118">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
     <span data-ttu-id="15157-119">在屏幕底部应显示：</span><span class="sxs-lookup"><span data-stu-id="15157-119">The bottom of the screen should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="15157-120">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="15157-120">What did I just do?</span></span>  
 <span data-ttu-id="15157-121">在此步骤中，您需要构建 EAISchemas 项目以生成程序集文件 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="15157-121">In this step, you built the EAISchemas project to generate an assembly file (DLL).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="15157-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="15157-122">Next Steps</span></span>  
 <span data-ttu-id="15157-123">创建计算结果根据批准条件中的库存补货请求消息的内容的业务流程[第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)。</span><span class="sxs-lookup"><span data-stu-id="15157-123">You create the business process that evaluates the contents of the inventory replenishment request message against approval criteria in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15157-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="15157-124">See Also</span></span>  
 <span data-ttu-id="15157-125">[步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="15157-125">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="15157-126">[步骤 2：创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="15157-126">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="15157-127">[步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="15157-127">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 [<span data-ttu-id="15157-128">步骤 4：创建映射</span><span class="sxs-lookup"><span data-stu-id="15157-128">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)