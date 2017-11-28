---
title: "BizTalk 应用程序是什么？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk.System application, about BizTalk.System application
- applications, default
- BizTalk.System application
- artifacts, about artifacts
- applications
- applications, about applications
- applications, warnings
- applications, BizTalk.System
- what's new, applications
- BizTalk.System application, warnings
ms.assetid: 68b5527c-d5e1-453b-a51b-3fc1a1d5dce2
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9ff0e2be82d528c7070955c1ce79b1f5e37cc6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-a-biztalk-application"></a><span data-ttu-id="f372b-103">BizTalk 应用程序是什么？</span><span class="sxs-lookup"><span data-stu-id="f372b-103">What Is a BizTalk Application?</span></span>
<span data-ttu-id="f372b-104">BizTalk 应用程序是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一个功能，可使您更快、更轻松地对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务解决方案进行部署、管理和故障排除。</span><span class="sxs-lookup"><span data-stu-id="f372b-104">The BizTalk application is a feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that makes it quicker and easier to deploy, manage, and troubleshoot [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solutions.</span></span> <span data-ttu-id="f372b-105">BizTalk 应用程序是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务解决方案中使用的项（称为“项目”）的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="f372b-105">A BizTalk application is a logical grouping of the items, called "artifacts," used in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solution.</span></span> <span data-ttu-id="f372b-106">本主题后面的部分对项目进行了详细介绍。</span><span class="sxs-lookup"><span data-stu-id="f372b-106">Artifacts are described in more detail later in this topic.</span></span>  
  
 <span data-ttu-id="f372b-107">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的新设计的管理和监视工具利用了这一新概念，因此您可以在应用程序级别而不仅仅是在各项目级别来管理和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="f372b-107">The newly designed administration and monitoring tools of [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] take advantage of this new concept, so that you can manage and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solutions at the application level, and not just at the individual artifact level.</span></span> <span data-ttu-id="f372b-108">通过创建应用程序并向其添加项目，您可以将解决方案中的一组项目作为单个实体进行查看、打包、部署和管理。</span><span class="sxs-lookup"><span data-stu-id="f372b-108">By creating an application and adding artifacts to it, you can view, package, deploy, and manage a group of artifacts in a solution as a single entity.</span></span> <span data-ttu-id="f372b-109">因此，随着复杂应用程序的数量在增加，您仍然可以用简单而直观的方式分别管理它们。</span><span class="sxs-lookup"><span data-stu-id="f372b-109">Therefore, as the number of complex applications increases you can still manage them individually in a simple and intuitive manner.</span></span>  
  
 <span data-ttu-id="f372b-110">有几种工具可用于创建和管理应用程序中, 所述[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f372b-110">There are several tools you can use to create and manage applications, which are described in [Application Deployment and Management Tools](../core/application-deployment-and-management-tools.md).</span></span>  
  
 <span data-ttu-id="f372b-111">下图描述了两个 BizTalk 应用程序及其包含的项目。</span><span class="sxs-lookup"><span data-stu-id="f372b-111">The following diagram depicts two BizTalk applications and the artifacts that they contain.</span></span>  
  
 <span data-ttu-id="f372b-112">![BizTalk 应用程序和项目](../core/media/biztalkapplication.gif "BizTalkApplication")</span><span class="sxs-lookup"><span data-stu-id="f372b-112">![BizTalk applications and artifacts](../core/media/biztalkapplication.gif "BizTalkApplication")</span></span>  
  
## <a name="artifacts"></a><span data-ttu-id="f372b-113">项目</span><span class="sxs-lookup"><span data-stu-id="f372b-113">Artifacts</span></span>  
 <span data-ttu-id="f372b-114">项目包括以下组成部分：</span><span class="sxs-lookup"><span data-stu-id="f372b-114">Artifacts include the following:</span></span>  
  
-   <span data-ttu-id="f372b-115">BizTalk 程序集及其包含的特定于 BizTalk 的资源：业务流程、管道、架构和映射</span><span class="sxs-lookup"><span data-stu-id="f372b-115">BizTalk assemblies and the BizTalk-specific resources that they contain – orchestrations, pipelines, schemas, and maps</span></span>  
  
-   <span data-ttu-id="f372b-116">不包括特定于 BizTalk 的资源的 .NET 程序集</span><span class="sxs-lookup"><span data-stu-id="f372b-116">.NET assemblies that do not contain BizTalk-specific resources</span></span>  
  
-   <span data-ttu-id="f372b-117">策略</span><span class="sxs-lookup"><span data-stu-id="f372b-117">Policies</span></span>  
  
-   <span data-ttu-id="f372b-118">发送端口、发送端口组、接收位置和接收端口</span><span class="sxs-lookup"><span data-stu-id="f372b-118">Send ports, send port groups, receive locations, and receive ports</span></span>  
  
-   <span data-ttu-id="f372b-119">解决方案使用的其他项，如证书、COM 组件和脚本</span><span class="sxs-lookup"><span data-stu-id="f372b-119">Other items that are used by the solution, such as certificates, COM components, and scripts</span></span>  
  
 <span data-ttu-id="f372b-120">有关每种类型的项目的背景信息，请参阅[运行时体系结构](../core/runtime-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="f372b-120">For background information about each type of artifact, see [Runtime Architecture](../core/runtime-architecture.md).</span></span> <span data-ttu-id="f372b-121">有关添加的详细信息，删除和配置项目，请参阅[管理项目](../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="f372b-121">For more information about adding, removing, and configuring artifacts, see [Managing Artifacts](../core/managing-artifacts.md).</span></span>  
  
 <span data-ttu-id="f372b-122">应用程序可包含一个业务解决方案中使用的所有项目，也可以只包含其中的一部分。</span><span class="sxs-lookup"><span data-stu-id="f372b-122">An application can contain all of the artifacts used in a business solution or only some of them.</span></span> <span data-ttu-id="f372b-123">根据您希望部署项目的方式，您可能需要将它们放在单个应用程序中，或放在两个或更多应用程序中。</span><span class="sxs-lookup"><span data-stu-id="f372b-123">Depending on how you want to deploy the artifacts, you may want to place them into a single application or into two or more applications.</span></span> <span data-ttu-id="f372b-124">有关确定组项目的详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f372b-124">For more information about deciding how to group artifacts, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span>  
  
## <a name="the-default-application"></a><span data-ttu-id="f372b-125">默认应用程序</span><span class="sxs-lookup"><span data-stu-id="f372b-125">The default application</span></span>  
 <span data-ttu-id="f372b-126">当[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装完成后，自动创建命名的 BizTalk 应用程序 1 的默认应用程序配置。</span><span class="sxs-lookup"><span data-stu-id="f372b-126">When [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] is configured following installation, a default application named BizTalk Application 1 is automatically created.</span></span> <span data-ttu-id="f372b-127">有关最佳实践分组项目到不同的应用程序的信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f372b-127">For information about best practices for grouping artifacts into different applications, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span> <span data-ttu-id="f372b-128">您还可以更改默认应用程序或重命名默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="f372b-128">You can also change the default application or rename the default application.</span></span>  
  
 <span data-ttu-id="f372b-129">在以下情况下，项目自动添加到默认应用程序：</span><span class="sxs-lookup"><span data-stu-id="f372b-129">In the following scenarios, artifacts are automatically added to the default application:</span></span>  
  
-   <span data-ttu-id="f372b-130">将程序集从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时未指定应用程序名。</span><span class="sxs-lookup"><span data-stu-id="f372b-130">When you deploy an assembly from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] without specifying an application name.</span></span> <span data-ttu-id="f372b-131">有关详细信息，请参阅[如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="f372b-131">For more information, see [How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).</span></span>  
  
-   <span data-ttu-id="f372b-132">使用 BTSTask 将项目添加到应用程序时不指定应用程序名。</span><span class="sxs-lookup"><span data-stu-id="f372b-132">When you use BTSTask to add an artifact to an application without specifying an application name.</span></span> <span data-ttu-id="f372b-133">有关详细信息，请参阅[AddResource 命令](../core/addresource-command.md)。</span><span class="sxs-lookup"><span data-stu-id="f372b-133">For more information, see [AddResource Command](../core/addresource-command.md).</span></span>  
  
-   <span data-ttu-id="f372b-134">使用 BTSTask 导入应用程序 .msi 文件时不指定应用程序名。</span><span class="sxs-lookup"><span data-stu-id="f372b-134">When you use BTSTask to import an application .msi file without specifying an application name.</span></span> <span data-ttu-id="f372b-135">有关详细信息，请参阅[ImportApp 命令](../core/importapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="f372b-135">For more information, see [ImportApp Command](../core/importapp-command.md).</span></span>  
  
## <a name="the-biztalksystem-application"></a><span data-ttu-id="f372b-136">BizTalk.System 应用程序</span><span class="sxs-lookup"><span data-stu-id="f372b-136">The BizTalk.System application</span></span>  
 <span data-ttu-id="f372b-137">当[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装完成后，应用程序命名的 BizTalk.System 上自动创建并填充所有 BizTalk 应用程序，例如默认架构和管道都使用的常见项目配置。</span><span class="sxs-lookup"><span data-stu-id="f372b-137">When [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] is configured following installation, an application named BizTalk.System is automatically created and populated with common artifacts that are used by all BizTalk applications, such as the default schemas and pipelines.</span></span> <span data-ttu-id="f372b-138">BizTalk.System 及其项目是只读的。</span><span class="sxs-lookup"><span data-stu-id="f372b-138">BizTalk.System and its artifacts are read-only.</span></span> <span data-ttu-id="f372b-139">您不能删除或重命名 BizTalk.System，也不能删除、重命名或移动它包含的任何项目。</span><span class="sxs-lookup"><span data-stu-id="f372b-139">You cannot delete or rename BizTalk.System, nor can you delete, rename, or move any of the artifacts that it contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f372b-140">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的每个应用程序都自动包含对 BizTalk.System 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="f372b-140">Every application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically contains a reference to the BizTalk.System application.</span></span> <span data-ttu-id="f372b-141">这是因为 BizTalk.System 中的项目会被每一个 BizTalk 应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="f372b-141">This is because the artifacts in BizTalk.System are used by every BizTalk application.</span></span> <span data-ttu-id="f372b-142">绝不能删除对 BizTalk.System 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="f372b-142">You should never remove a reference to the BizTalk.System application.</span></span> <span data-ttu-id="f372b-143">如果删除了，则应用程序无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="f372b-143">If you do, your application may not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f372b-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f372b-144">See Also</span></span>  
 [<span data-ttu-id="f372b-145">了解 BizTalk 应用程序部署和管理</span><span class="sxs-lookup"><span data-stu-id="f372b-145">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)