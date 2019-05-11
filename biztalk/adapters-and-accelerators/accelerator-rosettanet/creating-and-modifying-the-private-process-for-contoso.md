---
title: 创建和修改 Contoso 专用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, creating
- configuring, private processes
- private processes, configuring
- private process tutorial, creating private processes
- creating, private processes
- private process tutorial, configuring private processes
ms.assetid: 0690aaef-cd9e-46aa-8bd5-22744d5aec4c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f89a9c51d99ba257acbda7c1b417e46b2ad48a03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284518"
---
# <a name="creating-and-modifying-the-private-process-for-contoso"></a><span data-ttu-id="3766c-102">创建和修改 Contoso 专用流程</span><span class="sxs-lookup"><span data-stu-id="3766c-102">Creating and Modifying the Private Process for Contoso</span></span>
<span data-ttu-id="3766c-103">通过自定义专用流程中 Microsoft® 实现解决方案时，你可以执行与基于 RosettaNet 的消息的其他任务[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3766c-103">You can perform additional tasks with RosettaNet-based messages when implementing your solution by customizing the private process within Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="3766c-104">本部分演示如何通过使用业务规则引擎 (BRE) 策略和自定义专用业务流程的 BizTalk 编辑器创建自定义专用流程。</span><span class="sxs-lookup"><span data-stu-id="3766c-104">This section demonstrates how to customize the private process by using the Business Rule Engine (BRE) to create policies and BizTalk Editor to customize the private process orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3766c-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="3766c-105">In This Section</span></span>  
  
-   [<span data-ttu-id="3766c-106">步骤 1：向现有 Contoso 解决方案添加现有 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="3766c-106">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution.md)  
  
-   [<span data-ttu-id="3766c-107">步骤 2：定义和发布 Contoso 的词汇</span><span class="sxs-lookup"><span data-stu-id="3766c-107">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)  
  
-   [<span data-ttu-id="3766c-108">步骤 3：定义、发布和部署 Contoso 的业务策略</span><span class="sxs-lookup"><span data-stu-id="3766c-108">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)  
  
-   [<span data-ttu-id="3766c-109">步骤 4：创建 HeaderHelper 项目</span><span class="sxs-lookup"><span data-stu-id="3766c-109">Step 4: Creating the HeaderHelper Project</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)  
  
-   [<span data-ttu-id="3766c-110">步骤 5：修改 Contoso 专用业务流程</span><span class="sxs-lookup"><span data-stu-id="3766c-110">Step 5: Modifying the Contoso Private Process Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)  
  
-   [<span data-ttu-id="3766c-111">步骤 6：配置业务流程形状 (Contoso)</span><span class="sxs-lookup"><span data-stu-id="3766c-111">Step 6: Configuring Orchestration Shapes (Contoso)</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)  
  
-   [<span data-ttu-id="3766c-112">步骤 7：创建和配置端口</span><span class="sxs-lookup"><span data-stu-id="3766c-112">Step 7: Creating and Configuring Ports</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)  
  
-   [<span data-ttu-id="3766c-113">步骤 8：生成和部署 Contoso 业务流程</span><span class="sxs-lookup"><span data-stu-id="3766c-113">Step 8: Building and Deploying the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)  
  
-   [<span data-ttu-id="3766c-114">步骤 9：启动 Contoso 业务流程</span><span class="sxs-lookup"><span data-stu-id="3766c-114">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)