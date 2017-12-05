---
title: "使用 BizTalk 项目系统 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, opening
- BizTalk Mapper, opening
- Orchestration Designer, opening
- Pipeline Designer, opening
ms.assetid: a28c715e-128c-463a-b421-9b3efe76a530
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5b8c3a83d75219b9e52fd2ab13124480d772832
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="using-the-biztalk-project-system"></a><span data-ttu-id="342d4-102">使用 BizTalk 项目系统</span><span class="sxs-lookup"><span data-stu-id="342d4-102">Using the BizTalk Project System</span></span>
<span data-ttu-id="342d4-103">使用 BizTalk 项目系统可以在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 环境下创建、组织和配置 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="342d4-103">You can use the BizTalk project system to create, organize, and configure BizTalk solutions in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="342d4-104">主题和此部分中的过程介绍如何使用 BizTalk 项目系统执行各种任务。</span><span class="sxs-lookup"><span data-stu-id="342d4-104">The topics and procedures in this section describe how to perform various tasks by using the BizTalk project system.</span></span>  
  
 <span data-ttu-id="342d4-105">BizTalk Server 项目系统使用的相同项目管理原则和与其他 Microsoft Build Engine (MSBuild) 项目中使用的过程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="342d4-105">The BizTalk Server project system uses the same project management principles and procedures that you use with other Microsoft Build Engine (MSBuild) projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="342d4-106">本部分详细介绍了在创建运行于 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的应用程序时可能使用的通用步骤。</span><span class="sxs-lookup"><span data-stu-id="342d4-106">This section details common procedures that you might use when creating an application that runs on Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="342d4-107">有关 MSBuild 的详细信息，请参阅中的 MSBuild 参考部分[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]结合使用集合中位置[http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)。</span><span class="sxs-lookup"><span data-stu-id="342d4-107">For more information about MSBuild, see the MSBuild reference section in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="342d4-108">有关使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境，请参阅中的"管理解决方案、 项目和文件"[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]结合使用集合中位置[http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx)。</span><span class="sxs-lookup"><span data-stu-id="342d4-108">For more information about using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment, see "Managing Solutions, Projects, and Files" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx).</span></span>  
  
 <span data-ttu-id="342d4-109">下图显示了 BizTalk 项目系统设计环境与**新项目**对话框中打开。</span><span class="sxs-lookup"><span data-stu-id="342d4-109">The following figure shows the BizTalk project system design environment with the **New Project** dialog box open.</span></span>  
  
 <span data-ttu-id="342d4-110">![项目系统](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span><span class="sxs-lookup"><span data-stu-id="342d4-110">![Project Systems](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span></span>  
<span data-ttu-id="342d4-111">描述了项目系统设计环境</span><span class="sxs-lookup"><span data-stu-id="342d4-111">Depicts the Project System Design Environment</span></span>  
  
### <a name="to-open-biztalk-editor"></a><span data-ttu-id="342d4-112">若要打开 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="342d4-112">To open BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="342d4-113">在解决方案资源管理器，单击架构。</span><span class="sxs-lookup"><span data-stu-id="342d4-113">In Solution Explorer, click a schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="342d4-114">若要打开 BizTalk 编辑器，必须首先创建架构，或打开以前创建的架构。</span><span class="sxs-lookup"><span data-stu-id="342d4-114">To open BizTalk Editor, you must first create a schema or open a previously created schema.</span></span> <span data-ttu-id="342d4-115">有关创建架构的信息，请参阅[如何创建 XML 消息的架构](../core/how-to-create-schemas-for-xml-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-115">For information about creating a schema, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="342d4-116">另请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-116">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="342d4-117">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="342d4-117">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="342d4-118">-或者-</span><span class="sxs-lookup"><span data-stu-id="342d4-118">—Or—</span></span>  
  
     <span data-ttu-id="342d4-119">右键单击的架构，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="342d4-119">Right-click the schema, and then click **Open**.</span></span>  
  
     <span data-ttu-id="342d4-120">-或者-</span><span class="sxs-lookup"><span data-stu-id="342d4-120">—Or—</span></span>  
  
     <span data-ttu-id="342d4-121">双击架构。</span><span class="sxs-lookup"><span data-stu-id="342d4-121">Double-click the schema.</span></span>  
  
     <span data-ttu-id="342d4-122">在 BizTalk 编辑器中打开所选的架构。</span><span class="sxs-lookup"><span data-stu-id="342d4-122">The selected schema opens in BizTalk Editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="342d4-123">若要创建架构，你必须打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="342d4-123">To create a schema, you must have a project open.</span></span> <span data-ttu-id="342d4-124">有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-124">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="342d4-125">有关将项添加到项目的信息，请参阅[如何创建 XML 消息的架构](../core/how-to-create-schemas-for-xml-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-125">For information about adding items to a project, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="342d4-126">另请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-126">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
### <a name="to-open-biztalk-mapper"></a><span data-ttu-id="342d4-127">若要打开 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="342d4-127">To open BizTalk Mapper</span></span>  
  
1.  <span data-ttu-id="342d4-128">在解决方案资源管理器，单击映射。</span><span class="sxs-lookup"><span data-stu-id="342d4-128">In Solution Explorer, click a map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="342d4-129">若要打开 BizTalk 映射程序，必须首先创建一个映射中，或打开以前创建的映射。</span><span class="sxs-lookup"><span data-stu-id="342d4-129">To open BizTalk Mapper, you must first create a map or open a previously created map.</span></span> <span data-ttu-id="342d4-130">有关创建地图的信息，请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-130">For information about creating a map, see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span> <span data-ttu-id="342d4-131">另请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-131">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="342d4-132">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="342d4-132">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="342d4-133">-或者-</span><span class="sxs-lookup"><span data-stu-id="342d4-133">—Or—</span></span>  
  
     <span data-ttu-id="342d4-134">右键单击图，并依次**打开**。</span><span class="sxs-lookup"><span data-stu-id="342d4-134">Right-click the map, and then click **Open**.</span></span>  
  
     <span data-ttu-id="342d4-135">-或者-</span><span class="sxs-lookup"><span data-stu-id="342d4-135">—Or—</span></span>  
  
     <span data-ttu-id="342d4-136">双击一个映射。</span><span class="sxs-lookup"><span data-stu-id="342d4-136">Double-click a map.</span></span>  
  
     <span data-ttu-id="342d4-137">在 BizTalk 映射程序中打开所选的映射。</span><span class="sxs-lookup"><span data-stu-id="342d4-137">The selected map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="342d4-138">若要创建映射时，你必须打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="342d4-138">To create a map, you must have a project open.</span></span> <span data-ttu-id="342d4-139">有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-139">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="342d4-140">有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-140">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="342d4-141">另请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-141">Also see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span>  
  
### <a name="to-open-orchestration-designer"></a><span data-ttu-id="342d4-142">若要打开业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="342d4-142">To open Orchestration Designer</span></span>  
  
1.  <span data-ttu-id="342d4-143">在解决方案资源管理器，单击业务流程 (.odx)。</span><span class="sxs-lookup"><span data-stu-id="342d4-143">In Solution Explorer, click an orchestration (.odx).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="342d4-144">若要打开业务流程设计器，必须首先创建一个业务流程中，或打开以前创建的业务流程。</span><span class="sxs-lookup"><span data-stu-id="342d4-144">To open Orchestration Designer, you must first create an orchestration or open a previously created orchestration.</span></span> <span data-ttu-id="342d4-145">有关如何创建业务流程的信息，请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-145">For information about how to create an orchestration, see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
2.  <span data-ttu-id="342d4-146">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="342d4-146">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="342d4-147">-或者-</span><span class="sxs-lookup"><span data-stu-id="342d4-147">—Or—</span></span>  
  
     <span data-ttu-id="342d4-148">右键单击业务流程，并依次**打开**。</span><span class="sxs-lookup"><span data-stu-id="342d4-148">Right-click the orchestration, and then click **Open**.</span></span>  
  
     <span data-ttu-id="342d4-149">-或者-</span><span class="sxs-lookup"><span data-stu-id="342d4-149">—Or—</span></span>  
  
     <span data-ttu-id="342d4-150">双击业务流程。</span><span class="sxs-lookup"><span data-stu-id="342d4-150">Double-click the orchestration.</span></span>  
  
     <span data-ttu-id="342d4-151">此时，将打开业务流程设计器。</span><span class="sxs-lookup"><span data-stu-id="342d4-151">Orchestration Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="342d4-152">若要创建业务流程，你必须打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="342d4-152">To create an orchestration, you must have a project open.</span></span> <span data-ttu-id="342d4-153">有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-153">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="342d4-154">有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-154">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="342d4-155">另请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-155">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
### <a name="to-open-pipeline-designer"></a><span data-ttu-id="342d4-156">若要打开管道设计器</span><span class="sxs-lookup"><span data-stu-id="342d4-156">To open Pipeline Designer</span></span>  
  
1.  <span data-ttu-id="342d4-157">在解决方案资源管理器，单击管道。</span><span class="sxs-lookup"><span data-stu-id="342d4-157">In Solution Explorer, click a pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="342d4-158">若要打开管道设计器，则必须首先创建一个管道，或打开一个先前创建的管道。</span><span class="sxs-lookup"><span data-stu-id="342d4-158">To open Pipeline Designer, you must first create a pipeline or open a previously created pipeline.</span></span> <span data-ttu-id="342d4-159">有关如何创建管道的信息，请参阅[如何创建一条新管道](../core/how-to-create-a-new-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-159">For information about how to create a pipeline, see [How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md).</span></span>  
  
2.  <span data-ttu-id="342d4-160">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="342d4-160">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="342d4-161">-或者-</span><span class="sxs-lookup"><span data-stu-id="342d4-161">—Or—</span></span>  
  
     <span data-ttu-id="342d4-162">右击管道，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="342d4-162">Right-click the pipeline, and then click **Open**.</span></span>  
  
     <span data-ttu-id="342d4-163">-或者-</span><span class="sxs-lookup"><span data-stu-id="342d4-163">—Or—</span></span>  
  
     <span data-ttu-id="342d4-164">双击该管道。</span><span class="sxs-lookup"><span data-stu-id="342d4-164">Double-click the pipeline.</span></span>  
  
     <span data-ttu-id="342d4-165">此时，将打开管道设计器。</span><span class="sxs-lookup"><span data-stu-id="342d4-165">Pipeline Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="342d4-166">若要创建管道，则必须打开项目。</span><span class="sxs-lookup"><span data-stu-id="342d4-166">To create a pipeline, you must have a project open.</span></span> <span data-ttu-id="342d4-167">有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-167">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="342d4-168">有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-168">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="342d4-169">另请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="342d4-169">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="342d4-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="342d4-170">See Also</span></span>  
 <span data-ttu-id="342d4-171">[创建使用业务流程设计器的业务流程](../core/creating-orchestrations-using-orchestration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="342d4-171">[Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md) </span></span>  
 <span data-ttu-id="342d4-172">[使用管道设计器](../core/using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="342d4-172">[Using Pipeline Designer](../core/using-pipeline-designer.md) </span></span>  
 <span data-ttu-id="342d4-173">[业务规则编辑器的窗口](../core/windows-of-the-business-rule-composer.md) </span><span class="sxs-lookup"><span data-stu-id="342d4-173">[Windows of the Business Rule Composer](../core/windows-of-the-business-rule-composer.md) </span></span>  
 <span data-ttu-id="342d4-174">[使用 BizTalk 编辑器](../core/using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="342d4-174">[Using BizTalk Editor](../core/using-biztalk-editor.md) </span></span>  
 <span data-ttu-id="342d4-175">[使用 BizTalk 映射程序](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="342d4-175">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="342d4-176">开发人员工具</span><span class="sxs-lookup"><span data-stu-id="342d4-176">Developer Tools</span></span>](../core/developer-tools.md)