---
title: 部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: accef4b8-acdf-4043-8fd7-2db9ea752074
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c80c4be7e6b647ab7f62d025f867b2e1a808ab2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389587"
---
# <a name="deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application"></a><span data-ttu-id="838ea-102">部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="838ea-102">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>
<span data-ttu-id="838ea-103">部署和重新部署 BizTalk 程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="838ea-103">Deploy and redeploy BizTalk assemblies from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into a BizTalk application.</span></span> <span data-ttu-id="838ea-104">您可能想要执行此操作以测试的程序集，您已开发并将其打包以便提交功能。</span><span class="sxs-lookup"><span data-stu-id="838ea-104">You may want to do this to test the functionality of the assemblies that you have been developing and package them for handoff.</span></span>  

## <a name="overview"></a><span data-ttu-id="838ea-105">概述</span><span class="sxs-lookup"><span data-stu-id="838ea-105">Overview</span></span>  
 <span data-ttu-id="838ea-106">BizTalk 应用程序提供一种查看和管理的项，称为"项目"构成 BizTalk 业务解决方案的方法。</span><span class="sxs-lookup"><span data-stu-id="838ea-106">BizTalk applications provide a way to view and manage the items, called "artifacts," that comprise a BizTalk business solution.</span></span> <span data-ttu-id="838ea-107">项目包含 BizTalk 程序集 （包含业务流程、 架构、 映射和管道），您可以部署到这些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="838ea-107">Artifacts include BizTalk assemblies (containing orchestrations, schemas, maps, and pipelines), which you can deploy into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="838ea-108">项目还包括诸如.NET 程序集、 证书、 脚本、 自述文件和策略，您将添加到 BizTalk 应用程序使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 BTSTask 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="838ea-108">Artifacts also include items such as .NET assemblies, certificates, scripts, Readme files, and policies, which you add to your BizTalk application by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or the BTSTask command-line tool.</span></span> <span data-ttu-id="838ea-109">解决方案开发人员或 IT 管理员可以然后查看、 打包、 部署和管理应用程序及其项目作为单个实体。</span><span class="sxs-lookup"><span data-stu-id="838ea-109">The solution developer or IT administrator can then view, package, deploy, and manage the application and its artifacts as a single entity.</span></span> <span data-ttu-id="838ea-110">有关创建，部署和管理 BizTalk 应用程序，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="838ea-110">For more information about creating, deploying, and managing BizTalk applications, see [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="838ea-111">生成并部署 BizTalk 程序集之前，必须创建的项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，并创建或添加你想要包含在程序集中的项。</span><span class="sxs-lookup"><span data-stu-id="838ea-111">Before you can build and deploy a BizTalk assembly, you must create a project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and either create or add the items that you want to include in the assembly.</span></span> <span data-ttu-id="838ea-112">可以创建一个解决方案中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以包含多个项目，然后生成并部署及其整批发送到同一个应用程序或不同的应用程序的程序集。</span><span class="sxs-lookup"><span data-stu-id="838ea-112">You can create a solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to contain multiple projects and then build and deploy their assemblies all at once into the same application or different applications.</span></span> <span data-ttu-id="838ea-113">有关执行这些任务的说明，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="838ea-113">For instructions on performing these tasks, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span>  
  
 <span data-ttu-id="838ea-114">这些任务后，可以生成、 部署和通过执行以下步骤，取消部署 BizTalk 程序集，在本部分中的主题中所述：</span><span class="sxs-lookup"><span data-stu-id="838ea-114">After completing these tasks, you can build, deploy, and undeploy the BizTalk assemblies by taking the following steps, as described in the topics in this section:</span></span>  
  
- <span data-ttu-id="838ea-115">每个配置强名称程序集密钥文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="838ea-115">Configure a strong name assembly key file for each [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project.</span></span>  
  
- <span data-ttu-id="838ea-116">设置项目，包括配置重新部署即可轻松地重新部署程序集的部署属性。</span><span class="sxs-lookup"><span data-stu-id="838ea-116">Set deployment properties for the project, including configuring the Redeploy option to easily redeploy the assembly.</span></span>  
  
- <span data-ttu-id="838ea-117">使用中的部署命令[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]生成 BizTalk 程序集包含在解决方案中并将其部署到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="838ea-117">Use the Deploy command in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build the BizTalk assemblies contained in a solution and deploy them into a BizTalk application.</span></span> <span data-ttu-id="838ea-118">或者，您可以使用部署命令生成和部署程序集在单个项目中，尽管我们不建议执行此操作。</span><span class="sxs-lookup"><span data-stu-id="838ea-118">Alternatively, you can use the Deploy command to build and deploy an assembly in a single project, although we do not recommend doing this.</span></span>  
  
- <span data-ttu-id="838ea-119">测试应用程序并进行必要的更改之后, 使用在部署命令[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以重新生成并重新部署程序集。</span><span class="sxs-lookup"><span data-stu-id="838ea-119">After testing the application and making necessary changes, use the Deploy command in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to rebuild and redeploy the assembly.</span></span>  
  
- <span data-ttu-id="838ea-120">如有必要，将程序集安装在全局程序集缓存 (GAC) 中或从 GAC 中删除该程序集。</span><span class="sxs-lookup"><span data-stu-id="838ea-120">Install the assembly in the global assembly cache (GAC), if necessary, or remove the assembly from the GAC.</span></span>  
  
- <span data-ttu-id="838ea-121">取消部署程序集。</span><span class="sxs-lookup"><span data-stu-id="838ea-121">Undeploy the assembly.</span></span>  
  
  <span data-ttu-id="838ea-122">部署到 BizTalk 应用程序的一个或多个程序集之后, 可以完成的应用程序的配置，并将其部署到测试和生产环境。</span><span class="sxs-lookup"><span data-stu-id="838ea-122">After deploying one or more assemblies into a BizTalk application, you can complete the configuration of the application and deploy it into a test and then production environment.</span></span> <span data-ttu-id="838ea-123">有关详细信息，请参阅[BizTalk 应用程序部署的开发任务](../core/development-tasks-for-biztalk-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="838ea-123">For more information, see [Development Tasks for BizTalk Application Deployment](../core/development-tasks-for-biztalk-application-deployment.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="838ea-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="838ea-124">In This Section</span></span>  
  
-   [<span data-ttu-id="838ea-125">从 Visual Studio 部署程序集时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="838ea-125">What Happens When You Deploy an Assembly from Visual Studio</span></span>](../core/what-happens-when-you-deploy-an-assembly-from-visual-studio.md)  
  
-   [<span data-ttu-id="838ea-126">GAC 中的程序集安装</span><span class="sxs-lookup"><span data-stu-id="838ea-126">Assembly Installation in the GAC</span></span>](../core/assembly-installation-in-the-gac.md)  
  
-   [<span data-ttu-id="838ea-127">如何配置强名称程序集密钥文件</span><span class="sxs-lookup"><span data-stu-id="838ea-127">How to Configure a Strong Name Assembly Key File</span></span>](../core/how-to-configure-a-strong-name-assembly-key-file.md)  
  
-   [<span data-ttu-id="838ea-128">如何在 Visual Studio 中设置部署属性</span><span class="sxs-lookup"><span data-stu-id="838ea-128">How to Set Deployment Properties in Visual Studio</span></span>](../core/how-to-set-deployment-properties-in-visual-studio.md)  
  
-   [<span data-ttu-id="838ea-129">如何部署 BizTalk 程序集从 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="838ea-129">How to Deploy a BizTalk Assembly from Visual Studio</span></span>](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [<span data-ttu-id="838ea-130">如何重新部署 BizTalk 程序集从 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="838ea-130">How to Redeploy a BizTalk Assembly from Visual Studio</span></span>](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [<span data-ttu-id="838ea-131">如何安装或卸载程序集位于 GAC 中</span><span class="sxs-lookup"><span data-stu-id="838ea-131">How to Install or uninstall an Assembly in the GAC</span></span>](../core/how-to-install-an-assembly-in-the-gac.md)  