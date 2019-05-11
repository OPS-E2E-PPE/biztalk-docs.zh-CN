---
title: 使用 BizTalk 项目系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, opening
- BizTalk Mapper, opening
- Orchestration Designer, opening
- Pipeline Designer, opening
ms.assetid: a28c715e-128c-463a-b421-9b3efe76a530
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2401048d928a628a4dd4063d6a3e207c78e2155f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320890"
---
# <a name="using-the-biztalk-project-system"></a><span data-ttu-id="a6913-102">使用 BizTalk 项目系统</span><span class="sxs-lookup"><span data-stu-id="a6913-102">Using the BizTalk Project System</span></span>
<span data-ttu-id="a6913-103">BizTalk 项目系统可用于创建、 组织和配置 Microsoft BizTalk 解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="a6913-103">You can use the BizTalk project system to create, organize, and configure BizTalk solutions in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="a6913-104">主题和此部分中的过程介绍如何使用 BizTalk 项目系统执行各种任务。</span><span class="sxs-lookup"><span data-stu-id="a6913-104">The topics and procedures in this section describe how to perform various tasks by using the BizTalk project system.</span></span>  
  
 <span data-ttu-id="a6913-105">BizTalk Server 项目系统使用的相同的项目管理原则和过程，与其他 Microsoft Build Engine (MSBuild) 项目中使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a6913-105">The BizTalk Server project system uses the same project management principles and procedures that you use with other Microsoft Build Engine (MSBuild) projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="a6913-106">本部分详细介绍在 Microsoft 上创建应用程序运行时可能使用的常见过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a6913-106">This section details common procedures that you might use when creating an application that runs on Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a6913-107">有关 MSBuild 的详细信息，请参阅中的 MSBuild 参考部分[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]网址[ http://go.microsoft.com/fwlink/?LinkId=193567 ](http://go.microsoft.com/fwlink/?LinkId=193567)。</span><span class="sxs-lookup"><span data-stu-id="a6913-107">For more information about MSBuild, see the MSBuild reference section in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="a6913-108">有关使用详细信息[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境中，请参阅中的"管理解决方案、 项目和文件"[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]网址[ http://msdn.microsoft.com/library/wbzbtw81.aspx ](http://msdn.microsoft.com/library/wbzbtw81.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6913-108">For more information about using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment, see "Managing Solutions, Projects, and Files" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx).</span></span>  
  
 <span data-ttu-id="a6913-109">下图显示了使用的 BizTalk 项目系统设计环境**新的项目**对话框打开。</span><span class="sxs-lookup"><span data-stu-id="a6913-109">The following figure shows the BizTalk project system design environment with the **New Project** dialog box open.</span></span>  
  
 <span data-ttu-id="a6913-110">![Project Systems](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span><span class="sxs-lookup"><span data-stu-id="a6913-110">![Project Systems](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span></span>  
<span data-ttu-id="a6913-111">描述了项目系统设计环境</span><span class="sxs-lookup"><span data-stu-id="a6913-111">Depicts the Project System Design Environment</span></span>  
  
### <a name="to-open-biztalk-editor"></a><span data-ttu-id="a6913-112">若要打开 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="a6913-112">To open BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="a6913-113">在解决方案资源管理器，单击架构。</span><span class="sxs-lookup"><span data-stu-id="a6913-113">In Solution Explorer, click a schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6913-114">若要打开 BizTalk 编辑器中，必须首先创建架构，或打开以前创建的架构。</span><span class="sxs-lookup"><span data-stu-id="a6913-114">To open BizTalk Editor, you must first create a schema or open a previously created schema.</span></span> <span data-ttu-id="a6913-115">有关创建架构的信息，请参阅[如何创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-115">For information about creating a schema, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="a6913-116">另请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-116">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="a6913-117">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="a6913-117">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="a6913-118">-或-</span><span class="sxs-lookup"><span data-stu-id="a6913-118">—Or—</span></span>  
  
     <span data-ttu-id="a6913-119">右键单击架构，然后依次**打开**。</span><span class="sxs-lookup"><span data-stu-id="a6913-119">Right-click the schema, and then click **Open**.</span></span>  
  
     <span data-ttu-id="a6913-120">-或-</span><span class="sxs-lookup"><span data-stu-id="a6913-120">—Or—</span></span>  
  
     <span data-ttu-id="a6913-121">双击架构。</span><span class="sxs-lookup"><span data-stu-id="a6913-121">Double-click the schema.</span></span>  
  
     <span data-ttu-id="a6913-122">所选的架构将在 BizTalk 编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="a6913-122">The selected schema opens in BizTalk Editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6913-123">若要创建架构，必须打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="a6913-123">To create a schema, you must have a project open.</span></span> <span data-ttu-id="a6913-124">有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-124">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="a6913-125">有关将项添加到项目的信息，请参阅[如何创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-125">For information about adding items to a project, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="a6913-126">另请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-126">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
### <a name="to-open-biztalk-mapper"></a><span data-ttu-id="a6913-127">若要打开 BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="a6913-127">To open BizTalk Mapper</span></span>  
  
1.  <span data-ttu-id="a6913-128">在解决方案资源管理器，单击映射。</span><span class="sxs-lookup"><span data-stu-id="a6913-128">In Solution Explorer, click a map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6913-129">若要打开 BizTalk 映射器，必须首先创建映射，或打开以前创建的映射。</span><span class="sxs-lookup"><span data-stu-id="a6913-129">To open BizTalk Mapper, you must first create a map or open a previously created map.</span></span> <span data-ttu-id="a6913-130">有关创建映射的信息，请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-130">For information about creating a map, see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span> <span data-ttu-id="a6913-131">另请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-131">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="a6913-132">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="a6913-132">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="a6913-133">-或-</span><span class="sxs-lookup"><span data-stu-id="a6913-133">—Or—</span></span>  
  
     <span data-ttu-id="a6913-134">右键单击该映射，然后依次**打开**。</span><span class="sxs-lookup"><span data-stu-id="a6913-134">Right-click the map, and then click **Open**.</span></span>  
  
     <span data-ttu-id="a6913-135">-或-</span><span class="sxs-lookup"><span data-stu-id="a6913-135">—Or—</span></span>  
  
     <span data-ttu-id="a6913-136">双击某个映射。</span><span class="sxs-lookup"><span data-stu-id="a6913-136">Double-click a map.</span></span>  
  
     <span data-ttu-id="a6913-137">在 BizTalk 映射器中打开所选的映射。</span><span class="sxs-lookup"><span data-stu-id="a6913-137">The selected map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6913-138">若要创建映射时，必须打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="a6913-138">To create a map, you must have a project open.</span></span> <span data-ttu-id="a6913-139">有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-139">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="a6913-140">有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-140">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="a6913-141">另请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-141">Also see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span>  
  
### <a name="to-open-orchestration-designer"></a><span data-ttu-id="a6913-142">若要打开业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="a6913-142">To open Orchestration Designer</span></span>  
  
1.  <span data-ttu-id="a6913-143">在解决方案资源管理器，单击业务流程 (.odx)。</span><span class="sxs-lookup"><span data-stu-id="a6913-143">In Solution Explorer, click an orchestration (.odx).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6913-144">若要打开业务流程设计器，必须首先创建一个业务流程或打开以前创建的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a6913-144">To open Orchestration Designer, you must first create an orchestration or open a previously created orchestration.</span></span> <span data-ttu-id="a6913-145">有关如何创建业务流程的信息，请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-145">For information about how to create an orchestration, see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
2.  <span data-ttu-id="a6913-146">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="a6913-146">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="a6913-147">-或-</span><span class="sxs-lookup"><span data-stu-id="a6913-147">—Or—</span></span>  
  
     <span data-ttu-id="a6913-148">右键单击业务流程，然后依次**打开**。</span><span class="sxs-lookup"><span data-stu-id="a6913-148">Right-click the orchestration, and then click **Open**.</span></span>  
  
     <span data-ttu-id="a6913-149">-或-</span><span class="sxs-lookup"><span data-stu-id="a6913-149">—Or—</span></span>  
  
     <span data-ttu-id="a6913-150">双击业务流程。</span><span class="sxs-lookup"><span data-stu-id="a6913-150">Double-click the orchestration.</span></span>  
  
     <span data-ttu-id="a6913-151">业务流程设计器随即打开。</span><span class="sxs-lookup"><span data-stu-id="a6913-151">Orchestration Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6913-152">若要创建业务流程，你必须打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="a6913-152">To create an orchestration, you must have a project open.</span></span> <span data-ttu-id="a6913-153">有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-153">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="a6913-154">有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-154">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="a6913-155">另请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-155">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
### <a name="to-open-pipeline-designer"></a><span data-ttu-id="a6913-156">若要打开管道设计器</span><span class="sxs-lookup"><span data-stu-id="a6913-156">To open Pipeline Designer</span></span>  
  
1.  <span data-ttu-id="a6913-157">在解决方案资源管理器，单击管道。</span><span class="sxs-lookup"><span data-stu-id="a6913-157">In Solution Explorer, click a pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6913-158">若要打开管道设计器，首先要创建的管道，或打开先前创建的管道。</span><span class="sxs-lookup"><span data-stu-id="a6913-158">To open Pipeline Designer, you must first create a pipeline or open a previously created pipeline.</span></span> <span data-ttu-id="a6913-159">有关如何创建管道的信息，请参阅[如何创建新的管道](../core/how-to-create-a-new-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-159">For information about how to create a pipeline, see [How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md).</span></span>  
  
2.  <span data-ttu-id="a6913-160">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="a6913-160">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="a6913-161">-或-</span><span class="sxs-lookup"><span data-stu-id="a6913-161">—Or—</span></span>  
  
     <span data-ttu-id="a6913-162">右键单击管道，然后依次**打开**。</span><span class="sxs-lookup"><span data-stu-id="a6913-162">Right-click the pipeline, and then click **Open**.</span></span>  
  
     <span data-ttu-id="a6913-163">-或-</span><span class="sxs-lookup"><span data-stu-id="a6913-163">—Or—</span></span>  
  
     <span data-ttu-id="a6913-164">双击该管道。</span><span class="sxs-lookup"><span data-stu-id="a6913-164">Double-click the pipeline.</span></span>  
  
     <span data-ttu-id="a6913-165">管道设计器随即打开。</span><span class="sxs-lookup"><span data-stu-id="a6913-165">Pipeline Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6913-166">若要创建的管道，必须打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="a6913-166">To create a pipeline, you must have a project open.</span></span> <span data-ttu-id="a6913-167">有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-167">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="a6913-168">有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-168">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="a6913-169">另请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="a6913-169">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6913-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6913-170">See Also</span></span>  
 <span data-ttu-id="a6913-171">[创建业务流程使用业务流程设计器](../core/creating-orchestrations-using-orchestration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a6913-171">[Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md) </span></span>  
 <span data-ttu-id="a6913-172">[使用管道设计器](../core/using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a6913-172">[Using Pipeline Designer](../core/using-pipeline-designer.md) </span></span>  
 <span data-ttu-id="a6913-173">[Windows 业务规则编辑器](../core/windows-of-the-business-rule-composer.md) </span><span class="sxs-lookup"><span data-stu-id="a6913-173">[Windows of the Business Rule Composer](../core/windows-of-the-business-rule-composer.md) </span></span>  
 <span data-ttu-id="a6913-174">[使用 BizTalk 编辑器](../core/using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="a6913-174">[Using BizTalk Editor](../core/using-biztalk-editor.md) </span></span>  
 <span data-ttu-id="a6913-175">[使用 BizTalk 映射器](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="a6913-175">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="a6913-176">开发人员工具</span><span class="sxs-lookup"><span data-stu-id="a6913-176">Developer Tools</span></span>](../core/developer-tools.md)