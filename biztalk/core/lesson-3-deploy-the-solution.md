---
title: 第 3 课： 部署解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, deploying solutions
ms.assetid: b2f50fe7-7636-45bf-a09b-776065dd8a33
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1f8c565a55bf59c49ccda9f1c521ebadc60aac5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-3-deploy-the-solution"></a><span data-ttu-id="3b3af-102">第 3 课：部署解决方案</span><span class="sxs-lookup"><span data-stu-id="3b3af-102">Lesson 3: Deploy the Solution</span></span>
<span data-ttu-id="3b3af-103">部署 EAISolution 的第一步是将程序集添加到 BizTalk 管理数据库和全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="3b3af-103">The first step in deploying EAISolution is to add assemblies to the BizTalk Management database and the global assembly cache.</span></span>  
  
 <span data-ttu-id="3b3af-104">第二步是配置并启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b3af-104">The second step is to configure and start the application.</span></span>  
  
 <span data-ttu-id="3b3af-105">在[第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)，你添加到 eai 进程业务流程的逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="3b3af-105">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), you added logical ports to the EAIProcess orchestration.</span></span> <span data-ttu-id="3b3af-106">在本课中，您将定义物理端口并将物理端口绑定到逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="3b3af-106">In this lesson, you define the physical ports, and bind the physical ports to the logical ports.</span></span> <span data-ttu-id="3b3af-107">您还必须将业务流程、接收端口和发送端口分配给主机。</span><span class="sxs-lookup"><span data-stu-id="3b3af-107">You must also assign orchestration, receive port and send ports to hosts.</span></span>  <span data-ttu-id="3b3af-108">主机是 BizTalk 项目的虚拟容器。</span><span class="sxs-lookup"><span data-stu-id="3b3af-108">A host is a virtual container for BizTalk artifacts.</span></span>  <span data-ttu-id="3b3af-109">每个主机都已指定主机实例来处理项目。</span><span class="sxs-lookup"><span data-stu-id="3b3af-109">Each host has designated host instances to process the artifacts.</span></span>  
  
 <span data-ttu-id="3b3af-110">在本课中，您将了解到如何通过使用 BizTalk Server 管理控制台管理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="3b3af-110">In this lesson, you learn about administering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts by using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="3b3af-111">有关使用 BizTalk Server 管理控制台的信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="3b3af-111">For information about using the BizTalk Server Administration Console, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b3af-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="3b3af-112">In This Section</span></span>  
  
-   [<span data-ttu-id="3b3af-113">步骤 1： 部署项目</span><span class="sxs-lookup"><span data-stu-id="3b3af-113">Step 1: Deploy the Projects</span></span>](../core/step-1-deploy-the-projects.md)  
  
-   [<span data-ttu-id="3b3af-114">步骤 2： 配置并启动应用程序</span><span class="sxs-lookup"><span data-stu-id="3b3af-114">Step 2: Configure and Start the Application</span></span>](../core/step-2-configure-and-start-the-application1.md)  
  
-   [<span data-ttu-id="3b3af-115">步骤 3： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="3b3af-115">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)  
  
## <a name="see-also"></a><span data-ttu-id="3b3af-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b3af-116">See Also</span></span>  
 <span data-ttu-id="3b3af-117">[在开始本教程之前](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="3b3af-117">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="3b3af-118">[第 1 课： 定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="3b3af-118">[Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md) </span></span>  
 [<span data-ttu-id="3b3af-119">第 2 课： 定义的业务流程</span><span class="sxs-lookup"><span data-stu-id="3b3af-119">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)