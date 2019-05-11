---
title: 升级和版本的应用程序策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e881def2-c407-4205-a6b3-5c1fa5144bb4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdf9484d04ff895af42a3321d7ff44651c9bb26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261323"
---
# <a name="upgrading-and-versioning-strategies-for-applications"></a><span data-ttu-id="950ce-102">升级和应用程序的版本控制策略</span><span class="sxs-lookup"><span data-stu-id="950ce-102">Upgrading and Versioning Strategies for Applications</span></span>
<span data-ttu-id="950ce-103">BizTalk 应用程序版本控制可能会成为问题，当您需要运行两个版本的 BizTalk 解决方案的并排方案，或者无法使用 BizTalk 应用程序停机时间来部署新版本。</span><span class="sxs-lookup"><span data-stu-id="950ce-103">BizTalk application versioning can become an issue when you need to run two versions of a BizTalk solution side-by-side, or if you cannot use BizTalk application downtime to deploy a new version.</span></span> <span data-ttu-id="950ce-104">如果不需要运行两个版本的同时 （例如，其中有任何长时间运行的业务流程），解决方案和服务维护时段是否可用，则它是完全可以接受要取消部署旧版本，并将其部署新版本作为版本控制策略 （无程序集版本控制）。</span><span class="sxs-lookup"><span data-stu-id="950ce-104">If you do not need to run two versions of the solution simultaneously (for example, where you have no long-running orchestrations), and service maintenance windows are available, then it is perfectly acceptable to undeploy the old version, and deploy the new version as a versioning strategy (no assembly versioning).</span></span> <span data-ttu-id="950ce-105">这是一种可能的版本控制策略，但我们仍建议使用的文件版本号递增 (若要让你知道是哪个版本部署在运行的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="950ce-105">This is a possible versioning strategy, although we still recommend incrementing the file version number (to let you know what version is deployed on the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span></span>  
  
## <a name="when-to-use-versioning"></a><span data-ttu-id="950ce-106">何时使用版本控制</span><span class="sxs-lookup"><span data-stu-id="950ce-106">When to Use Versioning</span></span>  
 <span data-ttu-id="950ce-107">如果你需要支持长时间运行的业务流程，和/或需要执行任何 BizTalk 应用程序停机的情况下，BizTalk 应用程序部署，则需要实现和练习实线、 端到端[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本控制的策略不同的版本控制方案。</span><span class="sxs-lookup"><span data-stu-id="950ce-107">If you need to support long-running orchestrations, and/or you need to perform BizTalk application deployments with no BizTalk application downtime, then you need to implement and practice a solid, end-to-end [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versioning strategy for the different versioning scenarios.</span></span> <span data-ttu-id="950ce-108">这包括.NET 程序集版本控制和版本控制所有 BizTalk 项目，其中包括架构、 映射、 管道、 管道组件、 业务流程、 自定义适配器、 自定义类中调用的业务流程和映射、 业务规则和 BAM。</span><span class="sxs-lookup"><span data-stu-id="950ce-108">This includes .NET assembly versioning and versioning of all BizTalk artifacts, which includes schemas, maps, pipelines, pipeline components, orchestrations, custom adapters, custom classes called in orchestrations and maps, business rules, and BAM.</span></span>  
  
 <span data-ttu-id="950ce-109">架构版本控制中是唯一的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管道确定目标命名空间加上根节点上基于消息的消息类型在架构中定义的名称。</span><span class="sxs-lookup"><span data-stu-id="950ce-109">Schema versioning is unique in that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines determine the message type of a message based on the target namespace plus root node name defined in the schema.</span></span> <span data-ttu-id="950ce-110">有关详细信息，请参阅[管道组件中的架构解析](../core/schema-resolution-in-pipeline-components.md)。</span><span class="sxs-lookup"><span data-stu-id="950ce-110">For more information, see [Schema Resolution in Pipeline Components](../core/schema-resolution-in-pipeline-components.md).</span></span> <span data-ttu-id="950ce-111">如果需要版本您的架构，版本指示器必须是目标命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="950ce-111">If you need to version your schemas, a version indicator must be part of the target namespace.</span></span> <span data-ttu-id="950ce-112">更改架构版本产生波纹效果在你的解决方案，并因此应该事先计划。</span><span class="sxs-lookup"><span data-stu-id="950ce-112">Changing the schema version has a ripple effect throughout your solution, and therefore should be planned in advance.</span></span> <span data-ttu-id="950ce-113">在创建业务流程消息时，搜索**BizTalk Server:提高 BizTalk 编程的 8 提示和技巧**(提示 1:始终使用多部分消息类型）。</span><span class="sxs-lookup"><span data-stu-id="950ce-113">When creating orchestration messages, search for **BizTalk Server: 8 Tips And Tricks For Better BizTalk Programming** (tip 1: Always Use Multi-Part Message Types).</span></span> <span data-ttu-id="950ce-114">使用此方法提供了更大的灵活性时架构版本控制。</span><span class="sxs-lookup"><span data-stu-id="950ce-114">Use of this method provides greater flexibility when versioning schemas.</span></span>  
  
## <a name="using-factoring-for-assembly-versioning"></a><span data-ttu-id="950ce-115">使用分解为程序集版本控制</span><span class="sxs-lookup"><span data-stu-id="950ce-115">Using Factoring for Assembly Versioning</span></span>  
 <span data-ttu-id="950ce-116">如果你需要支持长时间运行的业务流程、 通过并行部署或无需停机的升级，，则应实现的程序集版本控制和打包策略。</span><span class="sxs-lookup"><span data-stu-id="950ce-116">If you need to support long-running orchestrations, side-by-side deployments, or no-downtime upgrades, then you should implement an assembly versioning and packaging strategy.</span></span> <span data-ttu-id="950ce-117">若要执行的 BizTalk 项目的程序集版本控制，您的 BizTalk 解决方案程序集需要考虑 （打包） 的方式以允许[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本控制。</span><span class="sxs-lookup"><span data-stu-id="950ce-117">In order to perform assembly versioning of BizTalk artifacts, your BizTalk solution assemblies need to be factored (packaged) in such a way to allow for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versioning.</span></span>  <span data-ttu-id="950ce-118">有三种类型的组成要素：</span><span class="sxs-lookup"><span data-stu-id="950ce-118">There are three types of factoring:</span></span>  
  
-   <span data-ttu-id="950ce-119">**没有分解**</span><span class="sxs-lookup"><span data-stu-id="950ce-119">**No factoring**</span></span>  
  
     <span data-ttu-id="950ce-120">所有 BizTalk 项目都是在一个程序集中。</span><span class="sxs-lookup"><span data-stu-id="950ce-120">All BizTalk artifacts are in one assembly.</span></span> <span data-ttu-id="950ce-121">这是最容易了解和部署，但可以最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="950ce-121">This is the easiest to understand and deploy, but provides the least amount of flexibility.</span></span>  
  
-   <span data-ttu-id="950ce-122">**完整分解**</span><span class="sxs-lookup"><span data-stu-id="950ce-122">**Full factoring**</span></span>  
  
     <span data-ttu-id="950ce-123">每个 BizTalk 项目是在自己的程序集。</span><span class="sxs-lookup"><span data-stu-id="950ce-123">Each BizTalk artifact is in its own assembly.</span></span> <span data-ttu-id="950ce-124">这提供了最大的灵活性，但最复杂部署和了解。</span><span class="sxs-lookup"><span data-stu-id="950ce-124">This provides the most flexibility, but is the most complex to deploy and understand.</span></span>  
  
-   <span data-ttu-id="950ce-125">**最佳分解**</span><span class="sxs-lookup"><span data-stu-id="950ce-125">**Optimal factoring**</span></span>  
  
     <span data-ttu-id="950ce-126">某处次"没有分解"和"完整分解"基础 BizTalk 应用程序的深入分析。</span><span class="sxs-lookup"><span data-stu-id="950ce-126">Somewhere in-between “no factoring” and “full factoring” based on in-depth analysis of your BizTalk applications.</span></span> <span data-ttu-id="950ce-127">除了版本控制，这允许您轻松地实现您的 BizTalk 主机的设计。</span><span class="sxs-lookup"><span data-stu-id="950ce-127">In addition to versioning, this allows you to easily implement your BizTalk Host design.</span></span> <span data-ttu-id="950ce-128">这被通过查找 BizTalk 项目之间的关系。</span><span class="sxs-lookup"><span data-stu-id="950ce-128">This is achieved by looking for relationships among BizTalk artifacts.</span></span> <span data-ttu-id="950ce-129">通常情况下可以在同一程序集中将一起始终进行版本控制的项目。</span><span class="sxs-lookup"><span data-stu-id="950ce-129">Artifacts that are always versioned together can typically be put in the same assembly.</span></span> <span data-ttu-id="950ce-130">如果需要独立的版本控制的项目，然后它们必须放入不同的程序集。</span><span class="sxs-lookup"><span data-stu-id="950ce-130">If independent versioning of the artifacts is required, then they must be put in different assemblies.</span></span> <span data-ttu-id="950ce-131">该级别为你想要实现的重构。</span><span class="sxs-lookup"><span data-stu-id="950ce-131">This is the level of factoring you want to achieve.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="950ce-132">其他资源</span><span class="sxs-lookup"><span data-stu-id="950ce-132">Additional Resources</span></span>  
  
 <span data-ttu-id="950ce-133">定义和练习 solid 版本控制策略，以确保它提供了可能需要任何通过并行部署策略。</span><span class="sxs-lookup"><span data-stu-id="950ce-133">Define and practice a solid versioning strategy to ensure it provides any side-by-side deployment strategies you might need.</span></span> <span data-ttu-id="950ce-134">BizTalk Server 应用程序升级和版本控制策略的资源包括：</span><span class="sxs-lookup"><span data-stu-id="950ce-134">Resources for BizTalk Server application upgrade and versioning strategies include the following:</span></span>  
  
-   [<span data-ttu-id="950ce-135">更新应用程序</span><span class="sxs-lookup"><span data-stu-id="950ce-135">Updating an Application</span></span>](../technical-guides/updating-an-application.md)  
  
-   [<span data-ttu-id="950ce-136">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="950ce-136">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)
  
-   [<span data-ttu-id="950ce-137">BizTalk Server 项目版本控制</span><span class="sxs-lookup"><span data-stu-id="950ce-137">BizTalk Server Project Versioning</span></span>](../core/biztalk-server-project-versioning.md)  
  
-   [<span data-ttu-id="950ce-138">了解 BizTalk Server 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="950ce-138">Understanding BizTalk Server Application Deployment</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)


  
## <a name="see-also"></a><span data-ttu-id="950ce-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="950ce-139">See Also</span></span>  
 [<span data-ttu-id="950ce-140">清单：配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="950ce-140">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)
