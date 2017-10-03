---
title: "步骤 3： 测试 Solution2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30dbc7c9-3c5f-4953-b26f-5c41141c22ad
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0e484a9f6af788775ec4ae7309965327378267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-solution"></a><span data-ttu-id="85838-102">步骤 3： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="85838-102">Step 3: Test the Solution</span></span>
<span data-ttu-id="85838-103">![步骤 3 / 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="85838-103">![Step 3 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="85838-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="85838-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="85838-105">**目标：**在此步骤中，你测试 EAI 解决方案如何处理消息。</span><span class="sxs-lookup"><span data-stu-id="85838-105">**Objective:** In this step, you test how the EAI solution processes messages.</span></span>  
  
 <span data-ttu-id="85838-106">**用途：**在此步骤中，检查 eai 进程业务流程正确处理消息。</span><span class="sxs-lookup"><span data-stu-id="85838-106">**Purpose:** In this step, you check that the EAIProcess orchestration processes messages correctly.</span></span> <span data-ttu-id="85838-107">检查方法是将示例消息放入为 EAI 应用程序指定的接收位置。</span><span class="sxs-lookup"><span data-stu-id="85838-107">You do this by dropping sample messages into the receive location specified for the EAI application.</span></span> <span data-ttu-id="85838-108">如果 EAI 解决方案工作正常，则当 EAIProcess 业务流程从仓库接收到请求多于 500 个货品的消息时，该业务流程将生成拒绝请求消息。</span><span class="sxs-lookup"><span data-stu-id="85838-108">If the EAI solution is working properly, if the EAIProcess orchestration receives a message from the warehouse requesting more than 500 items, the orchestration generates a decline request message.</span></span> <span data-ttu-id="85838-109">如果 EAIProcess 业务流程从仓库接收到请求少于 500 个货品的消息，则该业务流程会将消息传递到 ERP 系统。</span><span class="sxs-lookup"><span data-stu-id="85838-109">If the EAIProcess orchestration receives a message from the warehouse requesting fewer than 500 items, the orchestration passes the message on to the ERP system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="85838-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="85838-110">Prerequisites</span></span>  
 <span data-ttu-id="85838-111">在开始此步骤之前必须完成[步骤 2： 配置并启动应用程序](../core/step-2-configure-and-start-the-application1.md)。</span><span class="sxs-lookup"><span data-stu-id="85838-111">Before you begin this step you must complete [Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="85838-112">过程</span><span class="sxs-lookup"><span data-stu-id="85838-112">Procedures</span></span>  
  
#### <a name="to-test-the-eai-solution"></a><span data-ttu-id="85838-113">测试 EAI 解决方案</span><span class="sxs-lookup"><span data-stu-id="85838-113">To test the EAI solution</span></span>  
  
1.  <span data-ttu-id="85838-114">打开 Windows 资源管理器，并导航到**C:\BTSTutorials\WareHouse**。</span><span class="sxs-lookup"><span data-stu-id="85838-114">Open Windows Explorer, and navigate to **C:\BTSTutorials\WareHouse**.</span></span>  <span data-ttu-id="85838-115">此文件夹是通过安装教程文件创建的。</span><span class="sxs-lookup"><span data-stu-id="85838-115">This folder is created by installing the tutorial files.</span></span>  
  
2.  <span data-ttu-id="85838-116">复制**RequestInstance.XML**将其粘贴到**C:\BTSTutorials\WareHouse\Request**。</span><span class="sxs-lookup"><span data-stu-id="85838-116">Copy **RequestInstance.XML** and paste it into **C:\BTSTutorials\WareHouse\Request**.</span></span>  
  
3.  <span data-ttu-id="85838-117">当该文件将消失时，检查**C:\BTSTutorials\ERP\Request**。</span><span class="sxs-lookup"><span data-stu-id="85838-117">When the file disappears, check **C:\BTSTutorials\ERP\Request**.</span></span>  
  
4.  <span data-ttu-id="85838-118">在 Windows 资源管理器，导航到**C:\BTSTutorials\WareHouse**。</span><span class="sxs-lookup"><span data-stu-id="85838-118">In Windows Explorer, navigate to **C:\BTSTutorials\WareHouse**.</span></span>  
  
5.  <span data-ttu-id="85838-119">复制**请求实例 （通过限制）。XML**将其粘贴到**C:\BTSTutorials\WareHouse\Request**。</span><span class="sxs-lookup"><span data-stu-id="85838-119">Copy **RequestInstance(Over Limit).XML** and paste it into **C:\BTSTutorials\WareHouse\Request**.</span></span>  
  
6.  <span data-ttu-id="85838-120">当该文件将消失时，检查**C:\BTSTutorials\WareHouse\RequestDecline**。</span><span class="sxs-lookup"><span data-stu-id="85838-120">When the file disappears, check **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="85838-121">内容回顾</span><span class="sxs-lookup"><span data-stu-id="85838-121">What did I just do?</span></span>  
 <span data-ttu-id="85838-122">通过将示例消息放在 EAI 应用程序的接收位置中，您测试了 EAI 解决方案。</span><span class="sxs-lookup"><span data-stu-id="85838-122">You tested the EAI solution by placing sample messages in the receive location for the EAI application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85838-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85838-123">See Also</span></span>  
 <span data-ttu-id="85838-124">[步骤 1： 部署项目](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="85838-124">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="85838-125">步骤 2： 配置并启动应用程序</span><span class="sxs-lookup"><span data-stu-id="85838-125">Step 2: Configure and Start the Application</span></span>](../core/step-2-configure-and-start-the-application1.md)