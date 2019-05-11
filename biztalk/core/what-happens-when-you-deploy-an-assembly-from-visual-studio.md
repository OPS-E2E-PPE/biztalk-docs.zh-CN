---
title: 在部署 Visual Studio 中的程序集时，会发生什么情况 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 421df529-1ddb-4f49-a40a-c06f2a434ffc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1721f519313eb9d2d6aaeba8e1d03e3f7b85d0cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394807"
---
# <a name="what-happens-when-you-deploy-an-assembly-from-visual-studio"></a><span data-ttu-id="bc017-102">在部署 Visual Studio 中的程序集时，会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="bc017-102">What Happens When You Deploy an Assembly from Visual Studio</span></span>
<span data-ttu-id="bc017-103">本主题介绍在部署中的程序集时，会发生什么情况[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上的 BizTalk 应用程序到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bc017-103">This topic describes what happens when you deploy assemblies from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into a BizTalk application on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bc017-104">可以单独部署项目或解决方案中项目的所有部署在同一时间。</span><span class="sxs-lookup"><span data-stu-id="bc017-104">You can deploy a project individually, or you can deploy all of the projects in a solution at the same time.</span></span> <span data-ttu-id="bc017-105">部署一个项目之前, 单独或作为解决方案的一部分指定要将在项目属性中，其程序集部署到其中的应用程序中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="bc017-105">Before deploying a project, either separately or as part of a solution, you specify the application into which to deploy its assembly in project properties, as described in [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span> <span data-ttu-id="bc017-106">部署项目或解决方案时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，程序集是自动生成并部署到指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc017-106">When you deploy a project or solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the assemblies are automatically built and deployed into the specified application.</span></span> <span data-ttu-id="bc017-107">如果本地 BizTalk 组中的现有应用程序具有与项目属性中指定的应用程序相同的名称，该程序集部署到现有应用程序;否则为创建具有指定的名称的新应用程序和程序集部署到其中。</span><span class="sxs-lookup"><span data-stu-id="bc017-107">If an existing application in the local BizTalk group has the same name as the application specified in project properties, the assembly is deployed into the existing application; otherwise, a new application having the specified name is created and assembly is deployed into it.</span></span> <span data-ttu-id="bc017-108">作为此过程的一部分，以及业务流程、 管道、 架构和映射，它包含 （称为"项目"） 的程序集是导入本地 BizTalk 管理数据库，数据库中与指定的应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="bc017-108">As part of this process, the assembly along with the orchestrations, pipelines, schemas, and maps that it contains (called "artifacts") are imported into the local BizTalk Management database and associated in the database with the specified application.</span></span>  
  
 <span data-ttu-id="bc017-109">即使在同一时间部署解决方案中的项目，你可以部署到同一个 BizTalk 应用程序或不同的 BizTalk 应用程序，在解决方案中的项目。</span><span class="sxs-lookup"><span data-stu-id="bc017-109">You can deploy the projects in a solution into the same BizTalk application or different BizTalk applications, even when you deploy the projects in a solution at the same time.</span></span> <span data-ttu-id="bc017-110">下图说明了部署中的 BizTalk 解决方案中包含的三个程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到两个不同的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc017-110">The following diagram illustrates deploying three assemblies contained in a BizTalk solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into two different BizTalk applications.</span></span>  
  
 <span data-ttu-id="bc017-111">![部署 BizTalk 程序集](../core/media/visualstudiodeploy.gif "VisualStudioDeploy")</span><span class="sxs-lookup"><span data-stu-id="bc017-111">![Deploy BizTalk assemblies](../core/media/visualstudiodeploy.gif "VisualStudioDeploy")</span></span>  
  
 <span data-ttu-id="bc017-112">在部署项目或解决方案后，可以查看和管理中的程序集及其项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或通过使用 BTSTask 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="bc017-112">After you deploy a project or solution, you can view and manage the assemblies and their artifacts from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or by using the BTSTask command-line tool.</span></span>  
  
## <a name="destination-locations"></a><span data-ttu-id="bc017-113">目标位置</span><span class="sxs-lookup"><span data-stu-id="bc017-113">Destination Locations</span></span>  
 <span data-ttu-id="bc017-114">部署中的程序集时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，程序集的目标位置默认为程序集的源位置。</span><span class="sxs-lookup"><span data-stu-id="bc017-114">When deploying assemblies from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the destination location of an assembly defaults to the source location of the assembly.</span></span> <span data-ttu-id="bc017-115">安装或导出中的程序集时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如果"from"和"目标"环境是不相同，则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="bc017-115">When installing or exporting an assembly from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], if the "from" and "to" environment is not the same, the installation will fail.</span></span> <span data-ttu-id="bc017-116">例如，如果源位置为 d: [路径] / [文件名] 和目标安装计算机不具有"D"驱动器，则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="bc017-116">For example, if the source location is D:[path]/[filename] and the target machine installation machine does not have a "D" drive, the installation will fail.</span></span>  
  
 <span data-ttu-id="bc017-117">添加使用 BizTalk 管理器资源与此行为在这种情况下，默认目标位置为 %btad_installdir%。</span><span class="sxs-lookup"><span data-stu-id="bc017-117">This behavior is in contrast to adding a resource using BizTalk Administrator, in which case, the default destination location is %BTAD_InstallDir%.</span></span> <span data-ttu-id="bc017-118">此环境变量将扩展安装期间指定的安装目录。</span><span class="sxs-lookup"><span data-stu-id="bc017-118">This environment variable expands to the install directory specified during installation.</span></span>  
  
 <span data-ttu-id="bc017-119">若要解决此问题，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="bc017-119">To work around this issue, use the following procedure:</span></span>  
  
1. <span data-ttu-id="bc017-120">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，部署程序集。</span><span class="sxs-lookup"><span data-stu-id="bc017-120">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], deploy the assembly.</span></span>  
  
2. <span data-ttu-id="bc017-121">部署程序集后，打开 BizTalk Administrator 组。</span><span class="sxs-lookup"><span data-stu-id="bc017-121">After the assembly is deployed, open BizTalk Administrator.</span></span>  
  
3. <span data-ttu-id="bc017-122">修改相应的目标位置。</span><span class="sxs-lookup"><span data-stu-id="bc017-122">Modify the destination location as appropriate.</span></span> <span data-ttu-id="bc017-123">例如，更改目标位置为 %btad_installdir%。</span><span class="sxs-lookup"><span data-stu-id="bc017-123">For example, change the destination location to %BTAD_InstallDir%.</span></span>  
  
   <span data-ttu-id="bc017-124">后修改目标位置，将同一程序集的后续重新部署作为默认使用此新位置。</span><span class="sxs-lookup"><span data-stu-id="bc017-124">Once you modify the destination location, this new location will be used as default for subsequent redeploys of the same assembly.</span></span>  
  
   <span data-ttu-id="bc017-125">有关详细信息，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="bc017-125">For more information, see [How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).</span></span>  
  
## <a name="deploying-solutions-vs-projects"></a><span data-ttu-id="bc017-126">部署解决方案 vs。项目</span><span class="sxs-lookup"><span data-stu-id="bc017-126">Deploying Solutions vs. Projects</span></span>  
 <span data-ttu-id="bc017-127">我们强烈建议您始终部署解决方案而不是单个项目。</span><span class="sxs-lookup"><span data-stu-id="bc017-127">We strongly recommend that you always deploy a solution rather than an individual project.</span></span> <span data-ttu-id="bc017-128">如果有要部署的程序集与另一个程序集之间的依赖项部署单个项目，必须执行一系列手动步骤来完成部署。</span><span class="sxs-lookup"><span data-stu-id="bc017-128">When you deploy an individual project and there are dependencies between an assembly you are deploying and another assembly, you must take a number of manual steps to complete the deployment.</span></span> <span data-ttu-id="bc017-129">但是，部署解决方案时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动采取所有步骤才能管理程序集之间的依赖项。</span><span class="sxs-lookup"><span data-stu-id="bc017-129">When you deploy a solution, however, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically take all of the steps to manage dependencies between assemblies.</span></span> <span data-ttu-id="bc017-130">有关详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="bc017-130">For more information, see [How to Redeploy a BizTalk Assembly from Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md).</span></span>  
  
 <span data-ttu-id="bc017-131">下图说明的步骤，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所需重新部署时部署解决方案有依赖关系的程序集。</span><span class="sxs-lookup"><span data-stu-id="bc017-131">The following diagram illustrates the steps that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] takes to redeploy assemblies that have dependencies when you deploy a solution.</span></span>  
  
 <span data-ttu-id="bc017-132">![部署解决方案中的程序集](../core/media/deployassemblies.gif "DeployAssemblies")</span><span class="sxs-lookup"><span data-stu-id="bc017-132">![Deploying assemblies in a solution](../core/media/deployassemblies.gif "DeployAssemblies")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc017-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc017-133">See Also</span></span>  
 [<span data-ttu-id="bc017-134">将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="bc017-134">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)