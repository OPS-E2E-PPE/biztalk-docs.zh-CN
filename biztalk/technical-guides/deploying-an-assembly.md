---
title: 部署程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65f8ee21-0e52-4a74-b114-864a3069659c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4cbffe6b060e856288606aa89d8a00f08fd8a21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305819"
---
# <a name="deploying-an-assembly"></a><span data-ttu-id="d4463-102">部署程序集</span><span class="sxs-lookup"><span data-stu-id="d4463-102">Deploying an Assembly</span></span>
<span data-ttu-id="d4463-103">部署程序集生成的程序集，并将其，以及业务流程、 管道、 架构和映射 （项目），它包含到本地 BizTalk 管理数据库导入。</span><span class="sxs-lookup"><span data-stu-id="d4463-103">Deploying an assembly builds the assembly and imports it, along with the orchestrations, pipelines, schemas, and maps (artifacts) that it contains into the local BizTalk Management database.</span></span> <span data-ttu-id="d4463-104">最初，这是在开发环境。</span><span class="sxs-lookup"><span data-stu-id="d4463-104">Initially, this is done in the development environment.</span></span>  
  
 <span data-ttu-id="d4463-105">部署还将程序集与您在 Visual Studio 中的项目属性中指定的 BizTalk 应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="d4463-105">Deployment also associates the assembly with the BizTalk application that you have specified in project properties within Visual Studio.</span></span> <span data-ttu-id="d4463-106">部署解决方案后，可以查看和管理已部署的程序集和从其项目在 BizTalk Server 管理控制台内或通过使用 BTSTask 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="d4463-106">After you deploy a solution, you can view and manage the deployed assemblies and their artifacts from within the BizTalk Server Administration console or by using the BTSTask command-line tool.</span></span> <span data-ttu-id="d4463-107">可以管理的项目可以单独或组合在应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d4463-107">You can manage the artifacts either individually or grouped within the application.</span></span>  
  
## <a name="deploying-an-assembly"></a><span data-ttu-id="d4463-108">部署程序集</span><span class="sxs-lookup"><span data-stu-id="d4463-108">Deploying an Assembly</span></span>  
 <span data-ttu-id="d4463-109">按以下方式，可以将程序集添加到应用程序：</span><span class="sxs-lookup"><span data-stu-id="d4463-109">You can add assemblies to applications in the following ways:</span></span>  
  
- <span data-ttu-id="d4463-110">从 Visual Studio 环境内的应用程序部署的程序集</span><span class="sxs-lookup"><span data-stu-id="d4463-110">Deploy an assembly to an application from within the Visual Studio environment</span></span>  
  
- <span data-ttu-id="d4463-111">手动将 BizTalk Server 程序集添加到 BizTalk Server 管理控制台中从应用程序</span><span class="sxs-lookup"><span data-stu-id="d4463-111">Manually add BizTalk Server assemblies to the application from within the BizTalk Server Administration console</span></span>  
  
- <span data-ttu-id="d4463-112">使用脚本从命令行向应用程序添加 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="d4463-112">Add a BizTalk assembly to an application by using script from the command line</span></span>  
  
- <span data-ttu-id="d4463-113">从 BizTalk Server 管理控制台从其他应用程序移动 BizTalk Server 程序集</span><span class="sxs-lookup"><span data-stu-id="d4463-113">Move BizTalk Server assemblies from other applications from within the BizTalk Server Administration console</span></span>  
  
  <span data-ttu-id="d4463-114">有关将程序集添加到应用程序的详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。</span><span class="sxs-lookup"><span data-stu-id="d4463-114">For more information about adding assemblies to applications, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span></span>  
  
## <a name="redeploying-assemblies"></a><span data-ttu-id="d4463-115">重新部署程序集</span><span class="sxs-lookup"><span data-stu-id="d4463-115">Redeploying Assemblies</span></span>  
 <span data-ttu-id="d4463-116">在过程中开发和调试您的 BizTalk 程序集，可能需要多次重新部署它们。</span><span class="sxs-lookup"><span data-stu-id="d4463-116">In the process of developing and debugging your BizTalk assemblies, you may need to redeploy them multiple times.</span></span> <span data-ttu-id="d4463-117">BizTalk Server 提供用于重新部署一个简单的机制。</span><span class="sxs-lookup"><span data-stu-id="d4463-117">BizTalk Server provides a simple mechanism for redeployment.</span></span> <span data-ttu-id="d4463-118">如果不更改版本号的情况下，要重新部署程序集，可以使用重新部署属性。</span><span class="sxs-lookup"><span data-stu-id="d4463-118">If you are redeploying an assembly without changing the version number, you can use the Redeploy property.</span></span> <span data-ttu-id="d4463-119">BizTalk Server 将自动执行所有步骤才能重新部署您的程序集。</span><span class="sxs-lookup"><span data-stu-id="d4463-119">BizTalk Server will automatically perform all of the steps to redeploy the assembly for you.</span></span>  
  
 <span data-ttu-id="d4463-120">重新部署程序集的详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720)。</span><span class="sxs-lookup"><span data-stu-id="d4463-120">For more information about redeploying assemblies, see [How to Redeploy a BizTalk Assembly from Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720).</span></span>  
  
### <a name="best-practices-for-redeploying-an-assembly"></a><span data-ttu-id="d4463-121">重新部署程序集的最佳实践</span><span class="sxs-lookup"><span data-stu-id="d4463-121">Best Practices for Redeploying an Assembly</span></span>  
 <span data-ttu-id="d4463-122">**必须在 GAC 中安装新程序集**</span><span class="sxs-lookup"><span data-stu-id="d4463-122">**You must install the new assembly in the GAC**</span></span>  
  
- <span data-ttu-id="d4463-123">时重新部署程序集时，始终必须安装在全局程序集缓存 (GAC) 中的程序集的新版本。</span><span class="sxs-lookup"><span data-stu-id="d4463-123">When you redeploy an assembly, you must always install the new version of the assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="d4463-124">重新部署它后，你可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d4463-124">You can do this after you redeploy it.</span></span> <span data-ttu-id="d4463-125">有关详细信息，请参阅[如何将程序集安装到 GAC 中](http://go.microsoft.com/fwlink/?LinkID=154828)(http://go.microsoft.com/fwlink/?LinkID=154828)。</span><span class="sxs-lookup"><span data-stu-id="d4463-125">For more information, see [How to Install an Assembly in the GAC](http://go.microsoft.com/fwlink/?LinkID=154828) (http://go.microsoft.com/fwlink/?LinkID=154828).</span></span>  
  
  <span data-ttu-id="d4463-126">**您应始终重新部署解决方案级别的依赖项时**</span><span class="sxs-lookup"><span data-stu-id="d4463-126">**You should always redeploy at the solution level when there are dependencies**</span></span>  
  
- <span data-ttu-id="d4463-127">如果在解决方案中，有多个程序集并在解决方案中的一个或多个程序集具有你想要重新部署的程序集的依赖项，则应重新部署您在解决方案级别的程序集。</span><span class="sxs-lookup"><span data-stu-id="d4463-127">If you have multiple assemblies in a solution, and one or more assemblies in the solution has a dependency on the assembly that you want to redeploy, you should redeploy your assemblies at the solution level.</span></span> <span data-ttu-id="d4463-128">这是因为 BizTalk Server 时重新部署项目级别的程序集，将停止、 取消登记、 取消绑定，并删除中的所有程序集是取决于此程序集或此程序集所依赖的项目。</span><span class="sxs-lookup"><span data-stu-id="d4463-128">This is because when you redeploy an assembly at the project level, BizTalk Server will stop, unenlist, unbind, and remove the artifacts in all assemblies that either depend on this assembly or on upon which this assembly depends.</span></span> <span data-ttu-id="d4463-129">BizTalk Server 不会执行附加步骤以部署、 绑定、 登记和启动这些项目。</span><span class="sxs-lookup"><span data-stu-id="d4463-129">BizTalk Server will not take the additional steps to deploy, bind, enlist, and start the artifacts.</span></span> <span data-ttu-id="d4463-130">当您重新部署整个解决方案时，但是，BizTalk Server 会自动编制取消部署和重新部署所有基于及其依赖项的解决方案中的项目所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="d4463-130">When you redeploy the entire solution, however, BizTalk Server automatically takes the steps required to undeploy and redeploy all of the artifacts in the solution based on their dependencies.</span></span>  
  
  <span data-ttu-id="d4463-131">**可能需要手动重新部署依存程序集**</span><span class="sxs-lookup"><span data-stu-id="d4463-131">**You may need to manually redeploy dependent assemblies**</span></span>  
  
- <span data-ttu-id="d4463-132">BizTalk Server 通常取消部署依存程序集时取消部署程序集，但在以下情况下，您必须执行附加步骤以部署、 绑定和登记中每个依赖程序集后重新部署的程序集的项目程序集取决于：</span><span class="sxs-lookup"><span data-stu-id="d4463-132">BizTalk Server always undeploys dependent assemblies when it undeploys an assembly, but in the following cases, you must take the additional steps to deploy, bind, and enlist the artifacts in each dependent assembly after redeploying the assembly on which the assembly depends:</span></span>  
  
   <span data-ttu-id="d4463-133">如果重新部署项目级别的程序集，并且在同一解决方案中的另一个程序集依赖于它。</span><span class="sxs-lookup"><span data-stu-id="d4463-133">If you redeploy an assembly at the project level and another assembly in the same solution depends on it.</span></span>  
  
   <span data-ttu-id="d4463-134">如果重新部署程序集级别的解决方案，但依赖程序集存在于另一种解决方案。</span><span class="sxs-lookup"><span data-stu-id="d4463-134">If you redeploy an assembly at the solution level, but a dependent assembly exists in a different solution.</span></span>  
  
  <span data-ttu-id="d4463-135">**必须重新启动主机实例**</span><span class="sxs-lookup"><span data-stu-id="d4463-135">**You must restart host instances**</span></span>  
  
- <span data-ttu-id="d4463-136">重新部署包含业务流程，而无需更改程序集版本号的程序集时，现有程序集将在 BizTalk 管理数据库中被覆盖。</span><span class="sxs-lookup"><span data-stu-id="d4463-136">When you redeploy an assembly that contains an orchestration without changing the assembly version number, the existing assembly is overwritten in the BizTalk Management database.</span></span> <span data-ttu-id="d4463-137">此更改将生效之前，但是，必须重新启动该业务流程绑定到主机的每个主机实例。</span><span class="sxs-lookup"><span data-stu-id="d4463-137">Before the change will take effect, however, you must restart each host instance of the host to which the orchestration is bound.</span></span> <span data-ttu-id="d4463-138">可以指定本地计算机上的所有主机实例时自动重新都启动重新部署程序集的选项。</span><span class="sxs-lookup"><span data-stu-id="d4463-138">You can specify the option that all host instances on the local computer restart automatically when you redeploy an assembly.</span></span>  
  
   <span data-ttu-id="d4463-139">重新部署包含业务流程，而无需更改程序集版本号的程序集时，现有程序集将在 BizTalk 管理数据库中被覆盖。</span><span class="sxs-lookup"><span data-stu-id="d4463-139">When you redeploy an assembly that contains an orchestration without changing the assembly version number, the existing assembly is overwritten in the BizTalk Management database.</span></span> <span data-ttu-id="d4463-140">此更改将生效之前，但是，必须重新启动该业务流程绑定到主机的每个主机实例。</span><span class="sxs-lookup"><span data-stu-id="d4463-140">Before the change will take effect, however, you must restart each host instance of the host to which the orchestration is bound.</span></span> <span data-ttu-id="d4463-141">可以指定本地计算机上的所有主机实例时自动重新都启动重新部署程序集的选项。</span><span class="sxs-lookup"><span data-stu-id="d4463-141">You can specify the option that all host instances on the local computer restart automatically when you redeploy an assembly.</span></span> <span data-ttu-id="d4463-142">有关部署属性的详细信息，请参阅[如何在 Visual Studio 中设置部署属性](http://go.microsoft.com/fwlink/?LinkID=154718)(http://go.microsoft.com/fwlink/?LinkID=154718)。</span><span class="sxs-lookup"><span data-stu-id="d4463-142">For more information about deployment properties, see [How to Set Deployment Properties in Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154718) (http://go.microsoft.com/fwlink/?LinkID=154718).</span></span>  
  
   <span data-ttu-id="d4463-143">您可以手动停止和启动每个主机实例。</span><span class="sxs-lookup"><span data-stu-id="d4463-143">You can also manually stop and start each host instance.</span></span> <span data-ttu-id="d4463-144">有关停止和启动主机实例的详细信息，请参阅[如何停止主机实例](http://go.microsoft.com/fwlink/?LinkID=154829)(http://go.microsoft.com/fwlink/?LinkID=154829)并[如何启动主机实例](http://go.microsoft.com/fwlink/?LinkID=154830)(http://go.microsoft.com/fwlink/?LinkID=154830)。</span><span class="sxs-lookup"><span data-stu-id="d4463-144">For more information about stopping and starting a host instance, see [How to Stop a Host Instance](http://go.microsoft.com/fwlink/?LinkID=154829) (http://go.microsoft.com/fwlink/?LinkID=154829) and [How to Start a Host Instance](http://go.microsoft.com/fwlink/?LinkID=154830) (http://go.microsoft.com/fwlink/?LinkID=154830).</span></span>