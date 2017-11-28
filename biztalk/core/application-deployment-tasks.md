---
title: "应用程序部署任务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, deploying
- applications, tasks
- deploying [applications], tasks
ms.assetid: 8cb29292-9868-41fa-9f2c-d1c20dfdddbb
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed5dd5b2a15bd8408ee11934d7dd6274e81651b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="application-deployment-tasks"></a><span data-ttu-id="73f9d-102">应用程序部署任务</span><span class="sxs-lookup"><span data-stu-id="73f9d-102">Application Deployment Tasks</span></span>
<span data-ttu-id="73f9d-103">本部分中的主题提供有关 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的应用程序部署过程中各个阶段所涉及的以下任务的详细信息：</span><span class="sxs-lookup"><span data-stu-id="73f9d-103">The topics in this section provide details about the following tasks involved in each phase of the application deployment process for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="73f9d-104">**开发。**</span><span class="sxs-lookup"><span data-stu-id="73f9d-104">**Development.**</span></span> <span data-ttu-id="73f9d-105">开发人员部署包括在从 BizTalk 应用程序的 BizTalk 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在开发计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="73f9d-105">The developer deploys the BizTalk assemblies that are to be included in the BizTalk application from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on the development computer.</span></span> <span data-ttu-id="73f9d-106">这会自动创建应用程序并使用包含在程序集中的项目填充该应用程序。</span><span class="sxs-lookup"><span data-stu-id="73f9d-106">This automatically creates the application and populates it with the artifacts contained in the assemblies.</span></span> <span data-ttu-id="73f9d-107">项目是组成 BizTalk 业务解决方案的所有内容，包括 BizTalk 程序集、.NET 程序集、架构、映射、绑定和证书等。</span><span class="sxs-lookup"><span data-stu-id="73f9d-107">Artifacts are all of the items that comprise a BizTalk business solution, including BizTalk assemblies, .NET assemblies, schemas, maps, bindings, certificates, and so forth.</span></span> <span data-ttu-id="73f9d-108">开发人员通过向应用程序添加任何附加项目或执行其他配置来完成应用程序。</span><span class="sxs-lookup"><span data-stu-id="73f9d-108">The developer completes the application by adding any additional artifacts to it or performing additional configuration.</span></span> <span data-ttu-id="73f9d-109">然后，开发人员从 .msi 文件安装该应用程序，进行测试以验证其功能，修复所有问题，再将该应用程序从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出到 .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="73f9d-109">The developer then installs the application from the .msi file, tests it to verify functionality, fixes any issues, and then exports the application from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as an .msi file.</span></span>  
  
2.  <span data-ttu-id="73f9d-110">**测试。**</span><span class="sxs-lookup"><span data-stu-id="73f9d-110">**Testing.**</span></span> <span data-ttu-id="73f9d-111">测试人员导入到的.msi 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]测试计算机，这将创建中的应用程序上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="73f9d-111">The tester imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on a test computer, which creates the application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="73f9d-112">测试人员还从 .msi 文件将该应用程序安装到主机计算机上。</span><span class="sxs-lookup"><span data-stu-id="73f9d-112">The tester also installs the application on the host computers from the .msi file.</span></span> <span data-ttu-id="73f9d-113">完成测试和错误修复后，测试人员将该应用程序从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出到 .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="73f9d-113">After testing and bug-fixing is complete, the tester exports the application from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as an .msi file.</span></span>  
  
3.  <span data-ttu-id="73f9d-114">**过渡。**</span><span class="sxs-lookup"><span data-stu-id="73f9d-114">**Staging.**</span></span> <span data-ttu-id="73f9d-115">IT 管理员导入到的.msi 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]暂存服务器上运行将其配置为生产环境、 在主机计算机上安装它，验证功能，然后将完成的应用程序导出为.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="73f9d-115">The IT administrator imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on a staging server, configures it for the production environment, installs it on host computers, verifies the functionality, and then exports the finished application as an .msi file.</span></span>  
  
4.  <span data-ttu-id="73f9d-116">**生产。**</span><span class="sxs-lookup"><span data-stu-id="73f9d-116">**Production.**</span></span> <span data-ttu-id="73f9d-117">IT 管理员导入到的.msi 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行在生产环境中，在主计算机上安装应用程序，然后启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="73f9d-117">The IT administrator imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running in a production environment, installs the application on the host computers, and then starts the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73f9d-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="73f9d-118">In This Section</span></span>  
  
-   [<span data-ttu-id="73f9d-119">BizTalk 应用程序部署的开发任务</span><span class="sxs-lookup"><span data-stu-id="73f9d-119">Development Tasks for BizTalk Application Deployment</span></span>](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="73f9d-120">BizTalk 应用程序部署为测试任务，</span><span class="sxs-lookup"><span data-stu-id="73f9d-120">Testing Tasks for BizTalk Application Deployment</span></span>](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="73f9d-121">BizTalk 应用程序部署的暂存任务</span><span class="sxs-lookup"><span data-stu-id="73f9d-121">Staging Tasks for BizTalk Application Deployment</span></span>](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="73f9d-122">BizTalk 应用程序部署的生产任务</span><span class="sxs-lookup"><span data-stu-id="73f9d-122">Production Tasks for BizTalk Application Deployment</span></span>](../core/production-tasks-for-biztalk-application-deployment.md)