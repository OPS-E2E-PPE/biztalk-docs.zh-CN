---
title: 第 4 课： 构建和部署程序集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 58397c35-6048-4ac9-a8b8-a528dd1cb82a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca5a539fdaea9026a7c18cae6f076e72df9efe2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961923"
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a><span data-ttu-id="836fa-102">第 4 课： 构建和部署程序集</span><span class="sxs-lookup"><span data-stu-id="836fa-102">Lesson 4: Building and Deploying the Assembly</span></span>
<span data-ttu-id="836fa-103">在本课程中，你可以生成和部署此项目以生成该程序集包含你在前面的课程中创建的架构。</span><span class="sxs-lookup"><span data-stu-id="836fa-103">In this lesson, you build and deploy the project to generate an assembly that contains the schemas you created in the previous lessons.</span></span> <span data-ttu-id="836fa-104">此任务可确保到目前为止创建的工作中没有任何编译错误。</span><span class="sxs-lookup"><span data-stu-id="836fa-104">This task ensures there are no compilation errors in the work you created so far.</span></span>  
  
 <span data-ttu-id="836fa-105">部署程序集将程序集的副本放在配置数据库，而将其安装在全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="836fa-105">Deploying an assembly places a copy of the assembly in the Configuration database and installs it in the global assembly cache (GAC).</span></span> <span data-ttu-id="836fa-106">在下面的过程中，你部署直接从解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="836fa-106">In the following procedure, you deploy directly from Solution Explorer.</span></span>  
  
 <span data-ttu-id="836fa-107">当项目编译为程序集 （DLL 文件）、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]将保存在 DLL \<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for在项目文件夹内的 SWIFT\bin\Development 文件夹。</span><span class="sxs-lookup"><span data-stu-id="836fa-107">When the project compiles into an assembly (DLL file), [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] saves the DLL in the \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for SWIFT\bin\Development folder within the project folder.</span></span>  
  
### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="836fa-108">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="836fa-108">To build and deploy the project</span></span>  
  
1.  <span data-ttu-id="836fa-109">在解决方案资源管理器，右键单击**SWIFTSchemas**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="836fa-109">In Solution Explorer, right-click **SWIFTSchemas**, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="836fa-110">验证**生成成功**将显示在屏幕左下角。</span><span class="sxs-lookup"><span data-stu-id="836fa-110">Verify that **Build Succeeded** appears in the lower left-hand corner of the screen.</span></span> <span data-ttu-id="836fa-111">在编译过程中，你可能会看到某些状态消息。</span><span class="sxs-lookup"><span data-stu-id="836fa-111">During the compilation process, you may see some status messages.</span></span> <span data-ttu-id="836fa-112">当处理 SWIFT 架构时，这些消息是正常的。</span><span class="sxs-lookup"><span data-stu-id="836fa-112">These messages are normal when dealing with the SWIFT schemas.</span></span> <span data-ttu-id="836fa-113">如果出现任何错误，请单击工具，然后单击 BizTalk Server 管理来打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="836fa-113">If any errors appear, click Tools, and then click BizTalk Server Administration to open the BizTalk Server Administration Console.</span></span> <span data-ttu-id="836fa-114">使用 BizTalk 管理控制台中事件查看器的运行状况和活动跟踪 (HAT) 功能，若要更正你的错误并重新生成。</span><span class="sxs-lookup"><span data-stu-id="836fa-114">Use the Event Viewer and the Health and Activity Tracking (HAT) feature in the BizTalk Administration Console to correct your errors and rebuild.</span></span>  
  
2.  <span data-ttu-id="836fa-115">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \labs\SWIFTProject\SWIFTSchemas\bin\Development**文件夹，并确认**SWIFTSchemas.dll**文件是否存在于此文件夹。</span><span class="sxs-lookup"><span data-stu-id="836fa-115">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\labs\SWIFTProject\SWIFTSchemas\bin\Development** folder, and verify that the **SWIFTSchemas.dll** file exists in this folder.</span></span>  
  
3.  <span data-ttu-id="836fa-116">在解决方案资源管理器，右键单击**SWIFTSchemas**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="836fa-116">In Solution Explorer, right-click **SWIFTSchemas**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="836fa-117">验证**部署已成功**将显示在屏幕左下角。</span><span class="sxs-lookup"><span data-stu-id="836fa-117">Verify that **Deploy Succeeded** appears in the lower left corner of the screen.</span></span>  
  
### <a name="to-confirm-deployment-success"></a><span data-ttu-id="836fa-118">若要确认部署成功</span><span class="sxs-lookup"><span data-stu-id="836fa-118">To confirm deployment success</span></span>  
  
1.  <span data-ttu-id="836fa-119">单击**视图**，然后单击**BizTalk 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="836fa-119">Click **View** and then click **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="836fa-120">展开**程序集**节点，并确认**SWIFTSchemas (1.0.0.0)** 出现在列表中。</span><span class="sxs-lookup"><span data-stu-id="836fa-120">Expand the **Assemblies** node and confirm that **SWIFTSchemas (1.0.0.0)** appears in the list.</span></span>  
  
     <span data-ttu-id="836fa-121">如果 SWIFTSchemas 出现在列表中，程序集成功部署并可以引用和使用从其他[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="836fa-121">If SWIFTSchemas appears in the list, the assembly deployed successfully and can be referenced and used from other [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] projects.</span></span>  
  
 <span data-ttu-id="836fa-122">继续执行[模块 3： 添加的管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)。</span><span class="sxs-lookup"><span data-stu-id="836fa-122">Proceed to [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md).</span></span>