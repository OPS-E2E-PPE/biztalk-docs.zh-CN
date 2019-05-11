---
title: 部署 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.deployment.application
helpviewer_keywords:
- deploying [applications]
- managing [applications], deploying
- applications, deploying
ms.assetid: eef12d8a-6f5c-4eb2-b85b-df9281c0b88e
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c41b3d0a964dc4f8cd922db324367efa2ffde15
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352113"
---
# <a name="deploying-biztalk-applications"></a><span data-ttu-id="00bf8-102">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="00bf8-102">Deploying BizTalk Applications</span></span>
<span data-ttu-id="00bf8-103">本部分提供有关部署 BizTalk 应用程序的以下信息：</span><span class="sxs-lookup"><span data-stu-id="00bf8-103">This section provides the following information about deploying BizTalk applications:</span></span>  
  
- <span data-ttu-id="00bf8-104">将应用程序及其项目导出到 Windows Installer (.msi) 文件</span><span class="sxs-lookup"><span data-stu-id="00bf8-104">Exporting an application and its artifacts to a Windows Installer (.msi) file</span></span>  
  
- <span data-ttu-id="00bf8-105">.Msi 文件导入到其他 BizTalk 组，以便在新组中创建应用程序及其项目</span><span class="sxs-lookup"><span data-stu-id="00bf8-105">Importing the .msi file into another BizTalk group to create the application and its artifacts in the new group</span></span>  
  
- <span data-ttu-id="00bf8-106">将运行它的计算机上安装应用程序</span><span class="sxs-lookup"><span data-stu-id="00bf8-106">Installing the application on the computers that will run it</span></span>  
  
- <span data-ttu-id="00bf8-107">BizTalk 程序集安装到全局程序集缓存 (GAC)</span><span class="sxs-lookup"><span data-stu-id="00bf8-107">Installing BizTalk assemblies to the global assembly cache (GAC)</span></span>  
  
- <span data-ttu-id="00bf8-108">监视部署进度和测试应用程序</span><span class="sxs-lookup"><span data-stu-id="00bf8-108">Monitoring the progress of the deployment and testing the application</span></span>  
  
- <span data-ttu-id="00bf8-109">应用程序部署到的业务合作伙伴</span><span class="sxs-lookup"><span data-stu-id="00bf8-109">Deploying an application to a business partner</span></span>  
  
- <span data-ttu-id="00bf8-110">编辑绑定文件以自定义不同的部署环境的绑定</span><span class="sxs-lookup"><span data-stu-id="00bf8-110">Editing a binding file to customize the bindings for different deployment environments</span></span>  
  
  <span data-ttu-id="00bf8-111">有关需要在不同的应用程序部署方案中执行的任务的清单，请参阅[BizTalk 应用程序部署和管理清单](../core/biztalk-application-deployment-and-management-checklists.md)。</span><span class="sxs-lookup"><span data-stu-id="00bf8-111">For checklists of tasks that you need to perform in different application deployment scenarios, see [BizTalk Application Deployment and Management Checklists](../core/biztalk-application-deployment-and-management-checklists.md).</span></span> <span data-ttu-id="00bf8-112">BizTalk 应用程序和其部署的背景信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。</span><span class="sxs-lookup"><span data-stu-id="00bf8-112">For background information on BizTalk applications and their deployment, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="00bf8-113">有关创建应用程序和修改通过添加或删除项目或添加另一个应用程序的引用信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="00bf8-113">For information about creating an application and modifying it by adding or removing artifacts or adding a reference to another application, see [Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md).</span></span> <span data-ttu-id="00bf8-114">有关部署 BizTalk 程序集的信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="00bf8-114">For information about deploying BizTalk assemblies, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00bf8-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="00bf8-115">In This Section</span></span>  
  
-   [<span data-ttu-id="00bf8-116">导出 BizTalk 应用程序、绑定和策略</span><span class="sxs-lookup"><span data-stu-id="00bf8-116">Exporting BizTalk Applications, Bindings, and Policies</span></span>](../core/exporting-biztalk-applications-bindings-and-policies.md)  
  
-   [<span data-ttu-id="00bf8-117">导入 BizTalk 应用程序、绑定和策略</span><span class="sxs-lookup"><span data-stu-id="00bf8-117">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)  
  
-   [<span data-ttu-id="00bf8-118">如何安装 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="00bf8-118">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)  
  
-   [<span data-ttu-id="00bf8-119">监视 BizTalk 应用程序部署的进度</span><span class="sxs-lookup"><span data-stu-id="00bf8-119">Monitoring the Progress of Your BizTalk Application Deployment</span></span>](../core/monitoring-the-progress-of-your-biztalk-application-deployment.md)