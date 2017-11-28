---
title: "什么是活动视图？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], Activity view [Tracking Profile Editor]
- activities [BAM], definitions
- Tracking Profile Editor, Activity view
- Activity view [Tracking Profile Editor]
ms.assetid: ae6bcdc8-e426-4148-b83d-08a1a5e99ca3
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fd27a4de6b2ac86f94b105aabe679df3c88c06d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-an-activity-view"></a><span data-ttu-id="633c5-103">什么是活动视图？</span><span class="sxs-lookup"><span data-stu-id="633c5-103">What Is an Activity View?</span></span>
<span data-ttu-id="633c5-104">活动视图包含导入的 BAM 活动定义，该定义是使用 Excel BAM 外接程序创建的。</span><span class="sxs-lookup"><span data-stu-id="633c5-104">An activity view contains the imported BAM activity definition that you create with the BAM Add-In for Excel.</span></span> <span data-ttu-id="633c5-105">BAM 活动定义是业务流程的跟踪要求的摘要。</span><span class="sxs-lookup"><span data-stu-id="633c5-105">The BAM activity definition is an abstract of your trace requirements for your business process.</span></span> <span data-ttu-id="633c5-106">一个活动可以跨多个业务流程和端口。</span><span class="sxs-lookup"><span data-stu-id="633c5-106">An activity can span multiple orchestrations and ports.</span></span> <span data-ttu-id="633c5-107">您可以导入活动定义一次，然后将其映射到实现定义某些部分的每个业务流程或消息传送项目。</span><span class="sxs-lookup"><span data-stu-id="633c5-107">You import the activity definition once and map it to each orchestration or messaging artifact that fulfills some part of the definition.</span></span>  
  
 <span data-ttu-id="633c5-108">活动视图链接位于跟踪配置文件编辑器 (TPE) 用户界面的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="633c5-108">The Activity View link is on the left pane of Tracking Profile Editor (TPE) user interface.</span></span>  
  
## <a name="activity-view-elements"></a><span data-ttu-id="633c5-109">活动视图元素</span><span class="sxs-lookup"><span data-stu-id="633c5-109">Activity view elements</span></span>  
 <span data-ttu-id="633c5-110">活动视图以树视图的形式显示跟踪配置文件的整体结构，它包括下列元素：</span><span class="sxs-lookup"><span data-stu-id="633c5-110">The activity view displays the overall structure of the tracking profile in tree view and includes the following elements:</span></span>  
  
-   <span data-ttu-id="633c5-111">里程碑</span><span class="sxs-lookup"><span data-stu-id="633c5-111">Milestones</span></span>  
  
-   <span data-ttu-id="633c5-112">活动的数据项</span><span class="sxs-lookup"><span data-stu-id="633c5-112">Data items for the activity</span></span>  
  
-   <span data-ttu-id="633c5-113">事件源</span><span class="sxs-lookup"><span data-stu-id="633c5-113">Event sources</span></span>  
  
-   <span data-ttu-id="633c5-114">数据源</span><span class="sxs-lookup"><span data-stu-id="633c5-114">Data sources</span></span>  
  
 <span data-ttu-id="633c5-115">**里程碑**： 里程碑是在给定进程中定义的点的对象。</span><span class="sxs-lookup"><span data-stu-id="633c5-115">**Milestones**: Milestones are objects which define a point in a given process.</span></span> <span data-ttu-id="633c5-116">里程碑的访问方法有以下三种：</span><span class="sxs-lookup"><span data-stu-id="633c5-116">Milestones are accessed in one of three ways:</span></span>  
  
-   <span data-ttu-id="633c5-117">可以从业务流程计划中拖动相应形状，BAM 会将该形状的执行结束时间报告为里程碑值。</span><span class="sxs-lookup"><span data-stu-id="633c5-117">You can drag a shape from an orchestration schedule, and the end-time for that shape’s execution is reported by BAM as the milestone value.</span></span>  
  
-   <span data-ttu-id="633c5-118">可以将消息传送属性从右侧的示意表示形式中拖至目标里程碑。</span><span class="sxs-lookup"><span data-stu-id="633c5-118">You can drag a messaging property, from a schematic representation on the right, to a target milestone.</span></span>  
  
-   <span data-ttu-id="633c5-119">可以拖动包含里程碑值的消息负载架构节点。</span><span class="sxs-lookup"><span data-stu-id="633c5-119">You can drag a message payload schema node which contains a milestone value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="633c5-120">DATETIME ONLY 类型的架构节点在运行时进行计算。</span><span class="sxs-lookup"><span data-stu-id="633c5-120">The DATETIME ONLY type schema nodes are evaluated at run time.</span></span> <span data-ttu-id="633c5-121">不论运行时出现任何转换或强制转换问题，都会导致在事件日志中记录一条相应的跟踪错误。</span><span class="sxs-lookup"><span data-stu-id="633c5-121">Any conversion or casting problem at run time results in a tracking error being placed in the event log.</span></span>  
  
 <span data-ttu-id="633c5-122">**数据项**： 数据项是用于定义特定元素从消息实例、 系统或提升的属性的 XML 架构的对象。</span><span class="sxs-lookup"><span data-stu-id="633c5-122">**Data items**: Data items are objects which define a particular element from an XML schema for a message instance, system, or promoted property.</span></span> <span data-ttu-id="633c5-123">访问数据项的方法是，展开架构，找到并选择感兴趣的元素，然后将该元素拖至相应的数据项类型文件夹。</span><span class="sxs-lookup"><span data-stu-id="633c5-123">You access the data item by expanding the schema to find and select the element you are interested in and dragging the element to the correct data item type folder.</span></span> <span data-ttu-id="633c5-124">有关数据项（例如 XPath）的信息存储在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="633c5-124">Information about the data items (for example, XPath) is stored in the profile.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="633c5-125">TPE 只支持无表示法或仅有一种表示法的数据项，这是在消息架构中为特定数据字段定义的。</span><span class="sxs-lookup"><span data-stu-id="633c5-125">TPE supports only data items that have a zero-to-one representation as defined in the message schema for a particular data field.</span></span> <span data-ttu-id="633c5-126">如果存在有一种或多种表示法的数据项，业务流程跟踪过程中可能会出现错误。</span><span class="sxs-lookup"><span data-stu-id="633c5-126">Errors may occur in orchestration tracking when there are data items that have one-to-many representations.</span></span> <span data-ttu-id="633c5-127">在这些情况下，不在 BAM 主导入数据库中存储任何数据。</span><span class="sxs-lookup"><span data-stu-id="633c5-127">In these situations no data is stored in the BAM Primary Import database.</span></span> <span data-ttu-id="633c5-128">即使没有出现错误，也无法保证跟踪了哪个数据项。</span><span class="sxs-lookup"><span data-stu-id="633c5-128">If an error does not occur, then there is no guarantee which of the data item is tracked.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="633c5-129">BAM 开发人员需要注意，属性是根据 BizTalk Server 流程规则而不是根据 BAM 填充的。</span><span class="sxs-lookup"><span data-stu-id="633c5-129">BAM developers need to be aware that properties are populated according to BizTalk Server process rules, and not BAM.</span></span>  
>   
>  <span data-ttu-id="633c5-130">例如，SMTP 适配器的上下文属性 SMTPServer、CC 和 From 不包含任何值，直到它们被显式填充。</span><span class="sxs-lookup"><span data-stu-id="633c5-130">For example, in the SMTP adapter the context properties, such as SMTPServer, CC, and From, do not contain any values until they are explicitly populated.</span></span> <span data-ttu-id="633c5-131">填充这些属性之后，这些属性的值将出现在 BAM 主导入数据库中，并且可以开始对它们进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="633c5-131">Once they have been populated their values will appear in the BAM Primary Import database and they will be available for tracking.</span></span>  
  
## <a name="activity-view-context-menus"></a><span data-ttu-id="633c5-132">活动视图上下文菜单</span><span class="sxs-lookup"><span data-stu-id="633c5-132">Activity view context menus</span></span>  
 <span data-ttu-id="633c5-133">活动视图的可用操作的上下文菜单随业务流程视图中所选节点的不同而动态变化。</span><span class="sxs-lookup"><span data-stu-id="633c5-133">The context menus of available actions for the activity view dynamically change depending on the node selected in the Orchestration View.</span></span> <span data-ttu-id="633c5-134">例如，如果选择活动文件夹节点，则快捷菜单将包含该活动文件夹的快捷菜单项。</span><span class="sxs-lookup"><span data-stu-id="633c5-134">For example, if you select an activity folder node, the shortcut menu will contain the shortcut menu items for that activity folder.</span></span>  
  
 <span data-ttu-id="633c5-135">可以将事件和数据与业务活动中的项相关联，方法是，将事件和数据从右侧的源事件窗格中拖至活动视图的事件或数据节点。</span><span class="sxs-lookup"><span data-stu-id="633c5-135">You associate events and data to the items in the business activity by dragging them from the source event pane on the right to the event or data node in the Activity view.</span></span>  
  
 <span data-ttu-id="633c5-136">右键单击活动视图树中的某个节点，可以访问该节点的上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="633c5-136">The context menus for the nodes in the activity view are accessible by right-clicking a node in the tree.</span></span> <span data-ttu-id="633c5-137">以下屏幕显示的是活动视图的根节点。</span><span class="sxs-lookup"><span data-stu-id="633c5-137">The following screen shows the root node for activity views.</span></span> <span data-ttu-id="633c5-138">下表介绍了活动视图不同节点的上下文菜单中的项。</span><span class="sxs-lookup"><span data-stu-id="633c5-138">The following tables describe the items in the context menus for the different nodes for an activity view.</span></span>  
  
 <span data-ttu-id="633c5-139">**活动定义树的根节点**</span><span class="sxs-lookup"><span data-stu-id="633c5-139">**Activity Definition Tree root node**</span></span>  
  
 ![](../core/media/activityviewcontextmenu.gif "activityviewcontextmenu")  
  
|<span data-ttu-id="633c5-140">菜单项</span><span class="sxs-lookup"><span data-stu-id="633c5-140">Menu Item</span></span>|<span data-ttu-id="633c5-141">用法</span><span class="sxs-lookup"><span data-stu-id="633c5-141">Usage</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="633c5-142">新建继续符</span><span class="sxs-lookup"><span data-stu-id="633c5-142">New Continuation</span></span>|<span data-ttu-id="633c5-143">将新的继续符文件夹插入“活动”树中。</span><span class="sxs-lookup"><span data-stu-id="633c5-143">Inserts a new Continuation folder into the Activity tree.</span></span> <span data-ttu-id="633c5-144">从继续符的源段中映射此文件夹的值。</span><span class="sxs-lookup"><span data-stu-id="633c5-144">You map the value for this folder from the source segment of a continuation.</span></span><br /><br /> <span data-ttu-id="633c5-145">与 ContinuationID 文件夹结合使用，提供一种在填充同一活动的多个组件之间移交处理的方法。</span><span class="sxs-lookup"><span data-stu-id="633c5-145">Used in conjunction with a ContinuationID folder to provide a means to hand off processing between multiple components that populate the same activity.</span></span> <span data-ttu-id="633c5-146">这些组件包括 BizTalk 业务流程、端口、BufferedEventStreams 和 DirectEventStreams。</span><span class="sxs-lookup"><span data-stu-id="633c5-146">Examples of these components are BizTalk orchestrations, ports, BufferedEventStreams, and DirectEventStreams.</span></span> <span data-ttu-id="633c5-147">**注意：**延续文件夹名称可以包含最多 127 个字符。</span><span class="sxs-lookup"><span data-stu-id="633c5-147">**Note:**  Continuation folder names can contain a maximum of 127 characters.</span></span>|  
|<span data-ttu-id="633c5-148">新建 ContinuationID</span><span class="sxs-lookup"><span data-stu-id="633c5-148">New ContinuationID</span></span>|<span data-ttu-id="633c5-149">将 ContinuationID 文件夹插入“活动”树中。</span><span class="sxs-lookup"><span data-stu-id="633c5-149">Inserts a ContinuationID folder into the Activity tree.</span></span> <span data-ttu-id="633c5-150">将此文件夹映射到继续符的 continued-to 段。</span><span class="sxs-lookup"><span data-stu-id="633c5-150">You map this folder to continued-to segment of a continuation.</span></span> <span data-ttu-id="633c5-151">例如，如果业务流程 A 继续执行业务流程 B，则此文件夹必须映射到业务流程 B 中的项。</span><span class="sxs-lookup"><span data-stu-id="633c5-151">For example, if orchestration A continues to Orchestration B, this folder must be mapped to an item from Orchestration B.</span></span><br /><br /> <span data-ttu-id="633c5-152">与继续符文件夹结合使用，提供一种在填充同一活动的多个组件之间移交处理的方法。</span><span class="sxs-lookup"><span data-stu-id="633c5-152">Used in conjunction with a Continuation folder to provide a means to hand off processing between multiple components that populate the same activity.</span></span> <span data-ttu-id="633c5-153">这些组件包括 BizTalk 业务流程、端口、BufferedEventStreams 和 DirectEventStreams。</span><span class="sxs-lookup"><span data-stu-id="633c5-153">Examples of these components are BizTalk orchestrations, ports, BufferedEventStreams, and DirectEventStreams.</span></span> <span data-ttu-id="633c5-154">**注意：** ContinuationID 文件夹名称可以包含最多 127 个字符。</span><span class="sxs-lookup"><span data-stu-id="633c5-154">**Note:**  ContinuationID folder names can contain a maximum of 127 characters.</span></span>|  
|<span data-ttu-id="633c5-155">新建关系</span><span class="sxs-lookup"><span data-stu-id="633c5-155">New Relationship</span></span>|<span data-ttu-id="633c5-156">将新的关系文件夹插入“活动”树中。</span><span class="sxs-lookup"><span data-stu-id="633c5-156">Inserts a new relationship folder into the Activity tree.</span></span> <span data-ttu-id="633c5-157">用于发布构成视图的两个活动之间的关系。</span><span class="sxs-lookup"><span data-stu-id="633c5-157">Used to publish the relationship between activities that form a view.</span></span> <span data-ttu-id="633c5-158">**注意：**关系文件夹名称可以包含最多 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="633c5-158">**Note:**  Relationship folder names can contain a maximum of 128 characters.</span></span> <span data-ttu-id="633c5-159">其中包括服务器名称和 BizTalk 管理数据库名称。</span><span class="sxs-lookup"><span data-stu-id="633c5-159">The includes the server name and BizTalk Management database name.</span></span>|  
|<span data-ttu-id="633c5-160">新建文档引用 URL</span><span class="sxs-lookup"><span data-stu-id="633c5-160">New Document Reference URL</span></span>|<span data-ttu-id="633c5-161">将新的文档引用 URL 文件夹插入“活动”树中。</span><span class="sxs-lookup"><span data-stu-id="633c5-161">Inserts a new Document Reference URL folder into the Activity tree.</span></span> <span data-ttu-id="633c5-162">用于设置指向存储此活动的相关文档的位置的引用 URL。</span><span class="sxs-lookup"><span data-stu-id="633c5-162">Used to set a reference URL to a location that contains a document that is related to this activity.</span></span> <span data-ttu-id="633c5-163">**注意：**文档引用 URL 文件夹名称可以包含最多 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="633c5-163">**Note:**  Document Reference URL folder names can contain a maximum of 128 characters.</span></span>|  
  
 <span data-ttu-id="633c5-164">**属性节点**</span><span class="sxs-lookup"><span data-stu-id="633c5-164">**Property Node**</span></span>  
  
|<span data-ttu-id="633c5-165">菜单项</span><span class="sxs-lookup"><span data-stu-id="633c5-165">Menu Item</span></span>|<span data-ttu-id="633c5-166">用法</span><span class="sxs-lookup"><span data-stu-id="633c5-166">Usage</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="633c5-167">与所选数据关联</span><span class="sxs-lookup"><span data-stu-id="633c5-167">Associate Selected Data</span></span>|<span data-ttu-id="633c5-168">用于在消息负载（或上下文属性数据项）和 BAM 活动数据项文件夹之间创建关联。</span><span class="sxs-lookup"><span data-stu-id="633c5-168">Used to create an association between a message payload or context property data item and the BAM Activity data item folder.</span></span>|  
  
 <span data-ttu-id="633c5-169">**事件节点**</span><span class="sxs-lookup"><span data-stu-id="633c5-169">**Event node**</span></span>  
  
|<span data-ttu-id="633c5-170">菜单项</span><span class="sxs-lookup"><span data-stu-id="633c5-170">Menu Item</span></span>|<span data-ttu-id="633c5-171">用法</span><span class="sxs-lookup"><span data-stu-id="633c5-171">Usage</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="633c5-172">与所选操作的端点关联</span><span class="sxs-lookup"><span data-stu-id="633c5-172">Associate with the end of the selected action</span></span>|<span data-ttu-id="633c5-173">用于在业务流程形状（DateTime 消息负载或 DateTime 上下文属性数据项）和 BAM 活动里程碑文件夹之间创建关联。</span><span class="sxs-lookup"><span data-stu-id="633c5-173">Used to create an association between an orchestration shape, DateTime message payload, or DateTime context property data item and the BAM Activity milestone folder.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="633c5-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="633c5-174">See Also</span></span>  
 <span data-ttu-id="633c5-175">[实现事件流 BAM 活动](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="633c5-175">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="633c5-176">[在 Excel 中定义的业务活动和视图](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="633c5-176">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 [<span data-ttu-id="633c5-177">键入的组件</span><span class="sxs-lookup"><span data-stu-id="633c5-177">Components of the TPE</span></span>](../core/components-of-the-tpe.md)