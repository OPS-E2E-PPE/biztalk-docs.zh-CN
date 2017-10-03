---
title: "部署程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65f8ee21-0e52-4a74-b114-864a3069659c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73112fd9efb536452b8641faa976f42bb892b67c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-an-assembly"></a><span data-ttu-id="e264c-102">部署程序集</span><span class="sxs-lookup"><span data-stu-id="e264c-102">Deploying an Assembly</span></span>
<span data-ttu-id="e264c-103">部署程序集生成程序集，并将其，以及业务流程、 管道、 架构和映射 （项目），它将包含的本地 BizTalk 管理数据库导入。</span><span class="sxs-lookup"><span data-stu-id="e264c-103">Deploying an assembly builds the assembly and imports it, along with the orchestrations, pipelines, schemas, and maps (artifacts) that it contains into the local BizTalk Management database.</span></span> <span data-ttu-id="e264c-104">最初，这可在开发环境中。</span><span class="sxs-lookup"><span data-stu-id="e264c-104">Initially, this is done in the development environment.</span></span>  
  
 <span data-ttu-id="e264c-105">部署还将与 BizTalk 应用程序已在 Visual Studio 中的项目属性中指定关联程序集。</span><span class="sxs-lookup"><span data-stu-id="e264c-105">Deployment also associates the assembly with the BizTalk application that you have specified in project properties within Visual Studio.</span></span> <span data-ttu-id="e264c-106">在您部署某一解决方案后，可以从 BizTalk Server 管理控制台内或通过使用 BTSTask 命令行工具查看和管理已部署的程序集及其项目。</span><span class="sxs-lookup"><span data-stu-id="e264c-106">After you deploy a solution, you can view and manage the deployed assemblies and their artifacts from within the BizTalk Server Administration console or by using the BTSTask command-line tool.</span></span> <span data-ttu-id="e264c-107">你可以管理这些项目可以单独或应用程序中已分组。</span><span class="sxs-lookup"><span data-stu-id="e264c-107">You can manage the artifacts either individually or grouped within the application.</span></span>  
  
## <a name="deploying-an-assembly"></a><span data-ttu-id="e264c-108">部署程序集</span><span class="sxs-lookup"><span data-stu-id="e264c-108">Deploying an Assembly</span></span>  
 <span data-ttu-id="e264c-109">通过以下方式，可以将程序集添加到应用程序：</span><span class="sxs-lookup"><span data-stu-id="e264c-109">You can add assemblies to applications in the following ways:</span></span>  
  
-   <span data-ttu-id="e264c-110">将程序集部署到从 Visual Studio 环境中的应用程序</span><span class="sxs-lookup"><span data-stu-id="e264c-110">Deploy an assembly to an application from within the Visual Studio environment</span></span>  
  
-   <span data-ttu-id="e264c-111">手动将 BizTalk Server 程序集添加到从 BizTalk Server 管理控制台中的应用程序</span><span class="sxs-lookup"><span data-stu-id="e264c-111">Manually add BizTalk Server assemblies to the application from within the BizTalk Server Administration console</span></span>  
  
-   <span data-ttu-id="e264c-112">通过从命令行的脚本将 BizTalk 程序集添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="e264c-112">Add a BizTalk assembly to an application by using script from the command line</span></span>  
  
-   <span data-ttu-id="e264c-113">将 BizTalk Server 程序集移从 BizTalk Server 管理控制台中其他应用程序</span><span class="sxs-lookup"><span data-stu-id="e264c-113">Move BizTalk Server assemblies from other applications from within the BizTalk Server Administration console</span></span>  
  
 <span data-ttu-id="e264c-114">有关将程序集添加到应用程序的详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719)。</span><span class="sxs-lookup"><span data-stu-id="e264c-114">For more information about adding assemblies to applications, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span></span>  
  
## <a name="redeploying-assemblies"></a><span data-ttu-id="e264c-115">重新部署程序集</span><span class="sxs-lookup"><span data-stu-id="e264c-115">Redeploying Assemblies</span></span>  
 <span data-ttu-id="e264c-116">在过程中开发和调试你的 BizTalk 程序集，你可能需要将其重新部署多次。</span><span class="sxs-lookup"><span data-stu-id="e264c-116">In the process of developing and debugging your BizTalk assemblies, you may need to redeploy them multiple times.</span></span> <span data-ttu-id="e264c-117">BizTalk Server 提供简单的机制，用于重新部署。</span><span class="sxs-lookup"><span data-stu-id="e264c-117">BizTalk Server provides a simple mechanism for redeployment.</span></span> <span data-ttu-id="e264c-118">如果要重新程序集部署而无需更改的版本号，你可以使用重新部署属性。</span><span class="sxs-lookup"><span data-stu-id="e264c-118">If you are redeploying an assembly without changing the version number, you can use the Redeploy property.</span></span> <span data-ttu-id="e264c-119">BizTalk Server 将自动执行的所有步骤后，重新部署你的程序集。</span><span class="sxs-lookup"><span data-stu-id="e264c-119">BizTalk Server will automatically perform all of the steps to redeploy the assembly for you.</span></span>  
  
 <span data-ttu-id="e264c-120">有关重新部署程序集的详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720)。</span><span class="sxs-lookup"><span data-stu-id="e264c-120">For more information about redeploying assemblies, see [How to Redeploy a BizTalk Assembly from Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720).</span></span>  
  
### <a name="best-practices-for-redeploying-an-assembly"></a><span data-ttu-id="e264c-121">重新部署程序集的最佳做法</span><span class="sxs-lookup"><span data-stu-id="e264c-121">Best Practices for Redeploying an Assembly</span></span>  
 <span data-ttu-id="e264c-122">**你必须在 gac 中安装新的程序集**</span><span class="sxs-lookup"><span data-stu-id="e264c-122">**You must install the new assembly in the GAC**</span></span>  
  
-   <span data-ttu-id="e264c-123">当你重新部署程序集时，始终必须安装在全局程序集缓存 (GAC) 中的程序集的新版本。</span><span class="sxs-lookup"><span data-stu-id="e264c-123">When you redeploy an assembly, you must always install the new version of the assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="e264c-124">重新部署程序集后可实现此目的。</span><span class="sxs-lookup"><span data-stu-id="e264c-124">You can do this after you redeploy it.</span></span> <span data-ttu-id="e264c-125">有关详细信息，请参阅[如何将程序集安装在 GAC 中](http://go.microsoft.com/fwlink/?LinkID=154828)(http://go.microsoft.com/fwlink/?LinkID=154828)。</span><span class="sxs-lookup"><span data-stu-id="e264c-125">For more information, see [How to Install an Assembly in the GAC](http://go.microsoft.com/fwlink/?LinkID=154828) (http://go.microsoft.com/fwlink/?LinkID=154828).</span></span>  
  
 <span data-ttu-id="e264c-126">**你应始终重新部署解决方案级别时不存在依赖关系**</span><span class="sxs-lookup"><span data-stu-id="e264c-126">**You should always redeploy at the solution level when there are dependencies**</span></span>  
  
-   <span data-ttu-id="e264c-127">如果解决方案中有多个程序集，并且解决方案中的一个或多个程序集对要重新部署的程序集具有依存关系，则应在解决方案级重新部署程序集。</span><span class="sxs-lookup"><span data-stu-id="e264c-127">If you have multiple assemblies in a solution, and one or more assemblies in the solution has a dependency on the assembly that you want to redeploy, you should redeploy your assemblies at the solution level.</span></span> <span data-ttu-id="e264c-128">这是因为 BizTalk Server 时重新部署项目级别的程序集，将停止，取消登记，解除绑定，并删除中的所有程序集依赖于此程序集或在此程序集所依赖的项。</span><span class="sxs-lookup"><span data-stu-id="e264c-128">This is because when you redeploy an assembly at the project level, BizTalk Server will stop, unenlist, unbind, and remove the artifacts in all assemblies that either depend on this assembly or on upon which this assembly depends.</span></span> <span data-ttu-id="e264c-129">BizTalk Server 不会执行额外的步骤来部署、绑定、登记以及启动这些项目。</span><span class="sxs-lookup"><span data-stu-id="e264c-129">BizTalk Server will not take the additional steps to deploy, bind, enlist, and start the artifacts.</span></span> <span data-ttu-id="e264c-130">但是，在重新部署整个解决方案时，BizTalk Server 将根据解决方案中所有项目的依存关系，自动执行所需步骤来取消部署和重新部署这些项目。</span><span class="sxs-lookup"><span data-stu-id="e264c-130">When you redeploy the entire solution, however, BizTalk Server automatically takes the steps required to undeploy and redeploy all of the artifacts in the solution based on their dependencies.</span></span>  
  
 <span data-ttu-id="e264c-131">**你可能需要手动重新部署依赖程序集**</span><span class="sxs-lookup"><span data-stu-id="e264c-131">**You may need to manually redeploy dependent assemblies**</span></span>  
  
-   <span data-ttu-id="e264c-132">BizTalk Server 始终取消部署依赖程序集时它取消部署程序集，但是在以下情况下，您必须采取附加步骤以部署，将绑定，并登记中每个依赖程序集后重新部署在其上的程序集的项目依赖程序集：</span><span class="sxs-lookup"><span data-stu-id="e264c-132">BizTalk Server always undeploys dependent assemblies when it undeploys an assembly, but in the following cases, you must take the additional steps to deploy, bind, and enlist the artifacts in each dependent assembly after redeploying the assembly on which the assembly depends:</span></span>  
  
     <span data-ttu-id="e264c-133">在项目级重新部署了某个程序集，同一解决方案中的另一个程序集依赖于此程序集。</span><span class="sxs-lookup"><span data-stu-id="e264c-133">If you redeploy an assembly at the project level and another assembly in the same solution depends on it.</span></span>  
  
     <span data-ttu-id="e264c-134">在解决方案级重新部署了某个程序集，但依存程序集存在于其他解决方案中。</span><span class="sxs-lookup"><span data-stu-id="e264c-134">If you redeploy an assembly at the solution level, but a dependent assembly exists in a different solution.</span></span>  
  
 <span data-ttu-id="e264c-135">**必须重启主机实例**</span><span class="sxs-lookup"><span data-stu-id="e264c-135">**You must restart host instances**</span></span>  
  
-   <span data-ttu-id="e264c-136">在不更改程序集版本号的情况下重新部署包含业务流程的程序集时，BizTalk 管理数据库中的现有程序集将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="e264c-136">When you redeploy an assembly that contains an orchestration without changing the assembly version number, the existing assembly is overwritten in the BizTalk Management database.</span></span> <span data-ttu-id="e264c-137">不过，在更改生效之前，必须重新启动该业务流程绑定到的主机的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="e264c-137">Before the change will take effect, however, you must restart each host instance of the host to which the orchestration is bound.</span></span> <span data-ttu-id="e264c-138">你可以指定在重新部署程序集时自动重新启动本地计算机上的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="e264c-138">You can specify the option that all host instances on the local computer restart automatically when you redeploy an assembly.</span></span>  
  
     <span data-ttu-id="e264c-139">在不更改程序集版本号的情况下重新部署包含业务流程的程序集时，BizTalk 管理数据库中的现有程序集将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="e264c-139">When you redeploy an assembly that contains an orchestration without changing the assembly version number, the existing assembly is overwritten in the BizTalk Management database.</span></span> <span data-ttu-id="e264c-140">不过，在更改生效之前，必须重新启动该业务流程绑定到的主机的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="e264c-140">Before the change will take effect, however, you must restart each host instance of the host to which the orchestration is bound.</span></span> <span data-ttu-id="e264c-141">你可以指定在重新部署程序集时自动重新启动本地计算机上的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="e264c-141">You can specify the option that all host instances on the local computer restart automatically when you redeploy an assembly.</span></span> <span data-ttu-id="e264c-142">有关部署属性的详细信息，请参阅[如何在 Visual Studio 中设置部署属性](http://go.microsoft.com/fwlink/?LinkID=154718)(http://go.microsoft.com/fwlink/?LinkID=154718)。</span><span class="sxs-lookup"><span data-stu-id="e264c-142">For more information about deployment properties, see [How to Set Deployment Properties in Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154718) (http://go.microsoft.com/fwlink/?LinkID=154718).</span></span>  
  
     <span data-ttu-id="e264c-143">你可以手动停止和启动每个主机实例。</span><span class="sxs-lookup"><span data-stu-id="e264c-143">You can also manually stop and start each host instance.</span></span> <span data-ttu-id="e264c-144">有关停止和启动主机实例的详细信息，请参阅[如何停止主机实例](http://go.microsoft.com/fwlink/?LinkID=154829)(http://go.microsoft.com/fwlink/?LinkID = 154829) 和[如何启动的主机实例](http://go.microsoft.com/fwlink/?LinkID=154830)(http://go.microsoft.com/fwlink/?LinkID = 154830)。</span><span class="sxs-lookup"><span data-stu-id="e264c-144">For more information about stopping and starting a host instance, see [How to Stop a Host Instance](http://go.microsoft.com/fwlink/?LinkID=154829) (http://go.microsoft.com/fwlink/?LinkID=154829) and [How to Start a Host Instance](http://go.microsoft.com/fwlink/?LinkID=154830) (http://go.microsoft.com/fwlink/?LinkID=154830).</span></span>