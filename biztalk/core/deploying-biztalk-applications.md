---
title: 部署 BizTalk 应用程序 |Microsoft 文档
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
ms.openlocfilehash: 56417fa7e9c4aef40a6c76144a8e2d9e5bae548f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239069"
---
# <a name="deploying-biztalk-applications"></a><span data-ttu-id="c0134-102">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="c0134-102">Deploying BizTalk Applications</span></span>
<span data-ttu-id="c0134-103">本部分提供有关部署 BizTalk 应用程序的下列信息：</span><span class="sxs-lookup"><span data-stu-id="c0134-103">This section provides the following information about deploying BizTalk applications:</span></span>  
  
-   <span data-ttu-id="c0134-104">将应用程序及其项目导出到 Windows Installer (.msi) 文件中</span><span class="sxs-lookup"><span data-stu-id="c0134-104">Exporting an application and its artifacts to a Windows Installer (.msi) file</span></span>  
  
-   <span data-ttu-id="c0134-105">将此 .msi 文件导入到其他 BizTalk 组中，以在新组中创建该应用程序及其项目</span><span class="sxs-lookup"><span data-stu-id="c0134-105">Importing the .msi file into another BizTalk group to create the application and its artifacts in the new group</span></span>  
  
-   <span data-ttu-id="c0134-106">将应用程序安装在要运行该应用程序的计算机上</span><span class="sxs-lookup"><span data-stu-id="c0134-106">Installing the application on the computers that will run it</span></span>  
  
-   <span data-ttu-id="c0134-107">将 BizTalk 程序集安装到全局程序集缓存 (GAC) 中</span><span class="sxs-lookup"><span data-stu-id="c0134-107">Installing BizTalk assemblies to the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="c0134-108">监视部署的进度并测试应用程序</span><span class="sxs-lookup"><span data-stu-id="c0134-108">Monitoring the progress of the deployment and testing the application</span></span>  
  
-   <span data-ttu-id="c0134-109">将应用程序部署到业务合作伙伴</span><span class="sxs-lookup"><span data-stu-id="c0134-109">Deploying an application to a business partner</span></span>  
  
-   <span data-ttu-id="c0134-110">编辑绑定文件以为不同的部署环境自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c0134-110">Editing a binding file to customize the bindings for different deployment environments</span></span>  
  
 <span data-ttu-id="c0134-111">你需要在不同的应用程序部署方案中执行的任务的清单，请参阅[BizTalk 应用程序部署和管理清单](../core/biztalk-application-deployment-and-management-checklists.md)。</span><span class="sxs-lookup"><span data-stu-id="c0134-111">For checklists of tasks that you need to perform in different application deployment scenarios, see [BizTalk Application Deployment and Management Checklists](../core/biztalk-application-deployment-and-management-checklists.md).</span></span> <span data-ttu-id="c0134-112">在 BizTalk 应用程序和其部署的背景信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。</span><span class="sxs-lookup"><span data-stu-id="c0134-112">For background information on BizTalk applications and their deployment, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="c0134-113">有关创建应用程序和对其进行修改通过添加或删除项目或添加对另一个应用程序的引用的信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="c0134-113">For information about creating an application and modifying it by adding or removing artifacts or adding a reference to another application, see [Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md).</span></span> <span data-ttu-id="c0134-114">有关部署 BizTalk 程序集的信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c0134-114">For information about deploying BizTalk assemblies, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0134-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="c0134-115">In This Section</span></span>  
  
-   [<span data-ttu-id="c0134-116">导出 BizTalk 应用程序、 绑定和策略</span><span class="sxs-lookup"><span data-stu-id="c0134-116">Exporting BizTalk Applications, Bindings, and Policies</span></span>](../core/exporting-biztalk-applications-bindings-and-policies.md)  
  
-   [<span data-ttu-id="c0134-117">导入 BizTalk 应用程序、 绑定和策略</span><span class="sxs-lookup"><span data-stu-id="c0134-117">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)  
  
-   [<span data-ttu-id="c0134-118">如何安装 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="c0134-118">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)  
  
-   [<span data-ttu-id="c0134-119">监视你的 BizTalk 应用程序部署的进度</span><span class="sxs-lookup"><span data-stu-id="c0134-119">Monitoring the Progress of Your BizTalk Application Deployment</span></span>](../core/monitoring-the-progress-of-your-biztalk-application-deployment.md)