---
title: 什么是 BizTalk 应用程序？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf72f7508444e456d938c4157e25cc9869e93e36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395187"
---
# <a name="what-is-a-biztalk-application"></a><span data-ttu-id="3080d-103">什么是 BizTalk 应用程序？</span><span class="sxs-lookup"><span data-stu-id="3080d-103">What Is a BizTalk Application?</span></span>
<span data-ttu-id="3080d-104">BizTalk 应用程序是一项功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]更快、 更轻松地部署、 管理和故障排除变得[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="3080d-104">The BizTalk application is a feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that makes it quicker and easier to deploy, manage, and troubleshoot [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solutions.</span></span> <span data-ttu-id="3080d-105">BizTalk 应用程序是项，称为"项目"中使用的逻辑分组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="3080d-105">A BizTalk application is a logical grouping of the items, called "artifacts," used in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solution.</span></span> <span data-ttu-id="3080d-106">本主题后面的更详细地对项目进行了。</span><span class="sxs-lookup"><span data-stu-id="3080d-106">Artifacts are described in more detail later in this topic.</span></span>  
  
 <span data-ttu-id="3080d-107">新设计的管理和监视 BizTalk Server 工具充分利用这一新概念，以便可以管理和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务解决方案应用程序级别而不只是在各项目级别。</span><span class="sxs-lookup"><span data-stu-id="3080d-107">The newly designed administration and monitoring tools of BizTalk Server take advantage of this new concept, so that you can manage and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solutions at the application level, and not just at the individual artifact level.</span></span> <span data-ttu-id="3080d-108">通过创建应用程序并向其添加项目，可以查看、 打包、 部署和管理一组作为单个实体的解决方案中的项目。</span><span class="sxs-lookup"><span data-stu-id="3080d-108">By creating an application and adding artifacts to it, you can view, package, deploy, and manage a group of artifacts in a solution as a single entity.</span></span> <span data-ttu-id="3080d-109">因此，随着复杂应用程序数量的增加您仍可以管理它们单独中以简单且直观的方式。</span><span class="sxs-lookup"><span data-stu-id="3080d-109">Therefore, as the number of complex applications increases you can still manage them individually in a simple and intuitive manner.</span></span>  
  
 <span data-ttu-id="3080d-110">有几种工具可用于创建和管理应用程序中所述[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3080d-110">There are several tools you can use to create and manage applications, which are described in [Application Deployment and Management Tools](../core/application-deployment-and-management-tools.md).</span></span>  
  
 <span data-ttu-id="3080d-111">下图描绘了两个 BizTalk 应用程序和它们所包含的项目。</span><span class="sxs-lookup"><span data-stu-id="3080d-111">The following diagram depicts two BizTalk applications and the artifacts that they contain.</span></span>  
  
 <span data-ttu-id="3080d-112">![BizTalk 应用程序和项目](../core/media/biztalkapplication.gif "BizTalkApplication")</span><span class="sxs-lookup"><span data-stu-id="3080d-112">![BizTalk applications and artifacts](../core/media/biztalkapplication.gif "BizTalkApplication")</span></span>  
  
## <a name="artifacts"></a><span data-ttu-id="3080d-113">项目</span><span class="sxs-lookup"><span data-stu-id="3080d-113">Artifacts</span></span>  
 <span data-ttu-id="3080d-114">项目包括：</span><span class="sxs-lookup"><span data-stu-id="3080d-114">Artifacts include the following:</span></span>  
  
- <span data-ttu-id="3080d-115">BizTalk 程序集和特定于 BizTalk 的资源，它们包含 – 业务流程、 管道、 架构和映射</span><span class="sxs-lookup"><span data-stu-id="3080d-115">BizTalk assemblies and the BizTalk-specific resources that they contain – orchestrations, pipelines, schemas, and maps</span></span>  
  
- <span data-ttu-id="3080d-116">.NET 程序集不包含特定于 BizTalk 的资源</span><span class="sxs-lookup"><span data-stu-id="3080d-116">.NET assemblies that do not contain BizTalk-specific resources</span></span>  
  
- <span data-ttu-id="3080d-117">策略</span><span class="sxs-lookup"><span data-stu-id="3080d-117">Policies</span></span>  
  
- <span data-ttu-id="3080d-118">发送端口、 发送端口组、 接收位置和接收端口</span><span class="sxs-lookup"><span data-stu-id="3080d-118">Send ports, send port groups, receive locations, and receive ports</span></span>  
  
- <span data-ttu-id="3080d-119">使用该解决方案，如证书、 COM 组件和脚本的其他项</span><span class="sxs-lookup"><span data-stu-id="3080d-119">Other items that are used by the solution, such as certificates, COM components, and scripts</span></span>  
  
  <span data-ttu-id="3080d-120">有关每种类型的项目的背景信息，请参阅[运行时体系结构](../core/runtime-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="3080d-120">For background information about each type of artifact, see [Runtime Architecture](../core/runtime-architecture.md).</span></span> <span data-ttu-id="3080d-121">有关添加详细信息，删除和配置项目，请参阅[管理项目](../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="3080d-121">For more information about adding, removing, and configuring artifacts, see [Managing Artifacts](../core/managing-artifacts.md).</span></span>  
  
  <span data-ttu-id="3080d-122">应用程序可以包含的所有项目的业务解决方案或仅在部分中使用。</span><span class="sxs-lookup"><span data-stu-id="3080d-122">An application can contain all of the artifacts used in a business solution or only some of them.</span></span> <span data-ttu-id="3080d-123">具体取决于如何，你想要部署项目，你可能想要将其放置到单个应用程序或两个或多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="3080d-123">Depending on how you want to deploy the artifacts, you may want to place them into a single application or into two or more applications.</span></span> <span data-ttu-id="3080d-124">有关确定如何项目分组的详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3080d-124">For more information about deciding how to group artifacts, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span>  
  
## <a name="the-default-application"></a><span data-ttu-id="3080d-125">默认应用程序</span><span class="sxs-lookup"><span data-stu-id="3080d-125">The default application</span></span>  
 <span data-ttu-id="3080d-126">安装后配置 BizTalk Server 后，将自动创建名为 BizTalk 应用程序 1 的默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="3080d-126">When BizTalk Server is configured following installation, a default application named BizTalk Application 1 is automatically created.</span></span> <span data-ttu-id="3080d-127">有关最佳实践的项目分组到不同的应用程序的信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3080d-127">For information about best practices for grouping artifacts into different applications, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span> <span data-ttu-id="3080d-128">此外可以更改默认应用程序或重命名默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="3080d-128">You can also change the default application or rename the default application.</span></span>  
  
 <span data-ttu-id="3080d-129">在以下情况下，项目会自动添加到默认应用程序：</span><span class="sxs-lookup"><span data-stu-id="3080d-129">In the following scenarios, artifacts are automatically added to the default application:</span></span>  
  
- <span data-ttu-id="3080d-130">当部署中的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而无需指定应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="3080d-130">When you deploy an assembly from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] without specifying an application name.</span></span> <span data-ttu-id="3080d-131">有关详细信息，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="3080d-131">For more information, see [How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).</span></span>  
  
- <span data-ttu-id="3080d-132">当您使用 BTSTask 将项目添加到应用程序，而无需指定应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="3080d-132">When you use BTSTask to add an artifact to an application without specifying an application name.</span></span> <span data-ttu-id="3080d-133">有关详细信息，请参阅[AddResource 命令](../core/addresource-command.md)。</span><span class="sxs-lookup"><span data-stu-id="3080d-133">For more information, see [AddResource Command](../core/addresource-command.md).</span></span>  
  
- <span data-ttu-id="3080d-134">当您使用 BTSTask 将应用程序.msi 文件导入而无需指定应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="3080d-134">When you use BTSTask to import an application .msi file without specifying an application name.</span></span> <span data-ttu-id="3080d-135">有关详细信息，请参阅[ImportApp 命令](../core/importapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="3080d-135">For more information, see [ImportApp Command](../core/importapp-command.md).</span></span>  
  
## <a name="the-biztalksystem-application"></a><span data-ttu-id="3080d-136">BizTalk.System 应用程序</span><span class="sxs-lookup"><span data-stu-id="3080d-136">The BizTalk.System application</span></span>  
 <span data-ttu-id="3080d-137">如果 BizTalk Server，配置以下安装名为 BizTalk.System 的应用程序自动创建并填充所有 BizTalk 应用程序，如默认架构和管道都使用的常见项目。</span><span class="sxs-lookup"><span data-stu-id="3080d-137">When BizTalk Server is configured following installation, an application named BizTalk.System is automatically created and populated with common artifacts that are used by all BizTalk applications, such as the default schemas and pipelines.</span></span> <span data-ttu-id="3080d-138">BizTalk.System 及其项目是只读的。</span><span class="sxs-lookup"><span data-stu-id="3080d-138">BizTalk.System and its artifacts are read-only.</span></span> <span data-ttu-id="3080d-139">不能删除或重命名 BizTalk.System，也可以在删除、 重命名或移动的任何项目，它包含。</span><span class="sxs-lookup"><span data-stu-id="3080d-139">You cannot delete or rename BizTalk.System, nor can you delete, rename, or move any of the artifacts that it contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3080d-140">在每个应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动包含对 BizTalk.System 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="3080d-140">Every application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically contains a reference to the BizTalk.System application.</span></span> <span data-ttu-id="3080d-141">这是因为 BizTalk.System 中的项目使用的每个 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3080d-141">This is because the artifacts in BizTalk.System are used by every BizTalk application.</span></span> <span data-ttu-id="3080d-142">您应永远不会删除对 BizTalk.System 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="3080d-142">You should never remove a reference to the BizTalk.System application.</span></span> <span data-ttu-id="3080d-143">如果这样做，你的应用程序可能无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="3080d-143">If you do, your application may not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3080d-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="3080d-144">See Also</span></span>  
 [<span data-ttu-id="3080d-145">了解 BizTalk 应用程序的部署和管理</span><span class="sxs-lookup"><span data-stu-id="3080d-145">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)