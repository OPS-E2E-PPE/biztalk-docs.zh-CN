---
title: 第 1 课：定义架构和映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, creating solutions
ms.assetid: 4fe7720d-722e-4fa0-a556-477fc66ffa12
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02069f45a537a645dc0c3948e13d1f9208a8e5b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380772"
---
# <a name="lesson-1-define-schemas-and-a-map"></a><span data-ttu-id="ed13f-102">第 1 课：定义架构和映射</span><span class="sxs-lookup"><span data-stu-id="ed13f-102">Lesson 1: Define Schemas and a Map</span></span>
<span data-ttu-id="ed13f-103">在本课程中，将创建和构建企业应用程序集成 (EAI) 解决方案中的第一个项目。</span><span class="sxs-lookup"><span data-stu-id="ed13f-103">In this lesson, you create and build the first project in the enterprise application integration (EAI) solution.</span></span> <span data-ttu-id="ed13f-104">该项目包含两个消息架构和映射。</span><span class="sxs-lookup"><span data-stu-id="ed13f-104">The project contains two message schemas, and a map.</span></span>  
  
 <span data-ttu-id="ed13f-105">在 EAI 解决方案中，仓库系统将发送到库存补货请求消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行处理。</span><span class="sxs-lookup"><span data-stu-id="ed13f-105">In the EAI solution, a warehouse system sends a request message for inventory replenishment to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> <span data-ttu-id="ed13f-106">在本课中，您将创建以下各项：</span><span class="sxs-lookup"><span data-stu-id="ed13f-106">In this lesson, you create the following items:</span></span>  
  
- <span data-ttu-id="ed13f-107">EAI 解决方案中，若要保存项目。</span><span class="sxs-lookup"><span data-stu-id="ed13f-107">The EAI solution, to hold the project.</span></span>  
  
- <span data-ttu-id="ed13f-108">项目，用来容纳架构和映射。</span><span class="sxs-lookup"><span data-stu-id="ed13f-108">The project, to hold the schemas and the map.</span></span>  
  
- <span data-ttu-id="ed13f-109">由仓库发送给消息的架构，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到库存补货请求。</span><span class="sxs-lookup"><span data-stu-id="ed13f-109">The schema, for the message the warehouse sends to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to request inventory replenishment.</span></span>  
  
- <span data-ttu-id="ed13f-110">在请求遭到拒绝时仓库接收的消息架构。</span><span class="sxs-lookup"><span data-stu-id="ed13f-110">The schema, for the message that the warehouse is expecting when a request is rejected.</span></span>  
  
- <span data-ttu-id="ed13f-111">映射，用来重新格式化请求消息创建请求拒绝消息。</span><span class="sxs-lookup"><span data-stu-id="ed13f-111">A map, for reformatting a request message to create a request decline message.</span></span>  
  
  <span data-ttu-id="ed13f-112">在开始之前生成项目的最后[第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)。</span><span class="sxs-lookup"><span data-stu-id="ed13f-112">Finally you build the project before starting [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span> <span data-ttu-id="ed13f-113">第 2 课中创建路由消息并根据批准条件的库存补货请求消息的内容的计算结果的业务流程。</span><span class="sxs-lookup"><span data-stu-id="ed13f-113">In Lesson 2, you create the business process that routes the messages and evaluates the contents of the inventory replenishment request message against approval criteria.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed13f-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="ed13f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="ed13f-115">步骤 1：创建 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="ed13f-115">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
-   [<span data-ttu-id="ed13f-116">步骤 2：创建库存请求架构</span><span class="sxs-lookup"><span data-stu-id="ed13f-116">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [<span data-ttu-id="ed13f-117">步骤 3：创建请求拒绝架构</span><span class="sxs-lookup"><span data-stu-id="ed13f-117">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
-   [<span data-ttu-id="ed13f-118">步骤 4：创建映射</span><span class="sxs-lookup"><span data-stu-id="ed13f-118">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
-   [<span data-ttu-id="ed13f-119">步骤 5：生成 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="ed13f-119">Step 5: Build the EAISchemas Project</span></span>](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed13f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed13f-120">See Also</span></span>  
 <span data-ttu-id="ed13f-121">[开始本教程之前](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ed13f-121">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="ed13f-122">[第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="ed13f-122">[Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="ed13f-123">第 3 课：部署解决方案</span><span class="sxs-lookup"><span data-stu-id="ed13f-123">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)