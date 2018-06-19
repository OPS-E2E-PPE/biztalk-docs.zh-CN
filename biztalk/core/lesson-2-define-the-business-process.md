---
title: 第 2 课： 定义的业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, defining business processes
ms.assetid: 644aa049-4dd7-4392-b97f-31b1f29e12bd
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a2a9512fe847fdf50957456ec3d3eeff087c33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262045"
---
# <a name="lesson-2-define-the-business-process"></a><span data-ttu-id="ec345-102">第 2 课：定义业务流程</span><span class="sxs-lookup"><span data-stu-id="ec345-102">Lesson 2: Define the Business Process</span></span>
<span data-ttu-id="ec345-103">在本课程中，你可以创建企业应用程序 Integration(EAI) 解决方案中的第二个项目。</span><span class="sxs-lookup"><span data-stu-id="ec345-103">In this lesson, you create the second project in the Enterprise Application Integration(EAI) solution.</span></span> <span data-ttu-id="ec345-104">此项目包含一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="ec345-104">This project contains an orchestration.</span></span>  
  
 <span data-ttu-id="ec345-105">在 EAI 方案中，仓库应用程序发送到库存补货消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行处理。</span><span class="sxs-lookup"><span data-stu-id="ec345-105">In the EAI scenario, the warehouse application sends an inventory replenishment message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ec345-106">使用业务流程创建自动执行业务流程。</span><span class="sxs-lookup"><span data-stu-id="ec345-106"> uses the orchestration you create to automate the business process.</span></span> <span data-ttu-id="ec345-107">业务流程将提供工作流、操作和表达式，以使消息通过系统并对其内容进行处理。</span><span class="sxs-lookup"><span data-stu-id="ec345-107">The orchestration provides the workflow, actions, and expressions to move messages through the system and process their contents.</span></span>  
  
 <span data-ttu-id="ec345-108">在开始前生成项目的最后[第 3 课： 部署解决方案](../core/lesson-3-deploy-the-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="ec345-108">Finally you build the project before starting [Lesson 3: Deploy the Solution](../core/lesson-3-deploy-the-solution.md).</span></span>  
  
 <span data-ttu-id="ec345-109">有关详细信息，请参阅[创建业务流程使用 Orchestration 设计器](../core/creating-orchestrations-using-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="ec345-109">For more information, see [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec345-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="ec345-110">In This Section</span></span>  
  
-   [<span data-ttu-id="ec345-111">步骤 1： 向解决方案添加 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="ec345-111">Step 1: Add EAIOrchestration Project to the Solution</span></span>](../core/step-1-add-eaiorchestration-project-to-the-solution.md)  
  
-   [<span data-ttu-id="ec345-112">步骤 2： 定义的业务流程</span><span class="sxs-lookup"><span data-stu-id="ec345-112">Step 2: Define the Business Process</span></span>](../core/step-2-define-the-business-process.md)  
  
-   [<span data-ttu-id="ec345-113">步骤 3： 将端口添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="ec345-113">Step 3: Add Ports to the Orchestration</span></span>](../core/step-3-add-ports-to-the-orchestration.md)  
  
-   [<span data-ttu-id="ec345-114">步骤 4： 生成 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="ec345-114">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec345-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec345-115">See Also</span></span>  
 <span data-ttu-id="ec345-116">[在开始本教程之前](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ec345-116">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="ec345-117">[第 1 课： 定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="ec345-117">[Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md) </span></span>  
 [<span data-ttu-id="ec345-118">第 3 课： 部署解决方案</span><span class="sxs-lookup"><span data-stu-id="ec345-118">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)