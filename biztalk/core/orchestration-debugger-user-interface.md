---
title: 业务流程调试器用户界面 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.hat.orchdebugger
helpviewer_keywords:
- Orchestration Debugger, debug mode
- Orchestration Debugger, Interactive mode
ms.assetid: ca18f1e2-63b7-4177-82ba-4accc3369a2a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c7292a5f6874752b3e10031af93d86063afbc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262802"
---
# <a name="orchestration-debugger-user-interface"></a><span data-ttu-id="4125f-102">业务流程调试器用户界面</span><span class="sxs-lookup"><span data-stu-id="4125f-102">Orchestration Debugger User Interface</span></span>
<span data-ttu-id="4125f-103">在交互 （调试） 模式下，业务流程调试器视图包含三个区域：服务窗格中，跟踪的事件窗格和业务流程窗格。</span><span class="sxs-lookup"><span data-stu-id="4125f-103">In interactive (debug) mode, the Orchestration Debugger view contains three areas: Service pane, Tracked Events pane, and the Orchestration pane.</span></span> <span data-ttu-id="4125f-104">此外，在交互模式下，变量列表和变量的属性显示在视图的底部。</span><span class="sxs-lookup"><span data-stu-id="4125f-104">In addition, in interactive mode, the Variable list and Variable properties display across the bottom of the view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4125f-105">业务流程调试器不能显示该服务的真实状态，除非它出现在**在断点处**模式并且您具有在附加到的实例。</span><span class="sxs-lookup"><span data-stu-id="4125f-105">The Orchestration Debugger cannot display the true state of the service unless it appears in **In Breakpoint** mode and you have attached it to the instance.</span></span>  
  
## <a name="service-pane-in-orchestration-debugger"></a><span data-ttu-id="4125f-106">业务流程调试器中的服务窗格</span><span class="sxs-lookup"><span data-stu-id="4125f-106">Service Pane in Orchestration Debugger</span></span>  
 <span data-ttu-id="4125f-107">业务流程调试器窗口的顶部窗格显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="4125f-107">The top pane of the Orchestration Debugger window displays the following information.</span></span>  
  
|<span data-ttu-id="4125f-108">标记</span><span class="sxs-lookup"><span data-stu-id="4125f-108">Tag</span></span>|<span data-ttu-id="4125f-109">“详细信息”</span><span class="sxs-lookup"><span data-stu-id="4125f-109">Detail</span></span>|  
|---------|------------|  
|<span data-ttu-id="4125f-110">“属性”</span><span class="sxs-lookup"><span data-stu-id="4125f-110">Name</span></span>|<span data-ttu-id="4125f-111">指示当前视图 （业务流程调试器），并允许您导航到消息流视图。</span><span class="sxs-lookup"><span data-stu-id="4125f-111">Indicates the current view (Orchestration Debugger), and allows you to navigate to the Message Flow view.</span></span>|  
|<span data-ttu-id="4125f-112">实例详细信息</span><span class="sxs-lookup"><span data-stu-id="4125f-112">Instance Details</span></span>|<span data-ttu-id="4125f-113">显示服务名称和唯一标识当前业务流程实例的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4125f-113">Displays the service name and the GUID that uniquely identifies the current orchestration instance.</span></span>|  
|<span data-ttu-id="4125f-114">模式</span><span class="sxs-lookup"><span data-stu-id="4125f-114">Modes</span></span>|<span data-ttu-id="4125f-115">调试模式 （重播/实时）、 业务流程的状态 （已启动、 挂起、 已完成、 等）、 （是或否）、 附加和断点模式 （在类或实例上）。</span><span class="sxs-lookup"><span data-stu-id="4125f-115">Debug mode (Replay/Live), Orchestration state (Started, Suspended, Completed, etc.), Attached (Yes or No), and Breakpoint mode (On Class or On Instance).</span></span>|  
|<span data-ttu-id="4125f-116">服务选项</span><span class="sxs-lookup"><span data-stu-id="4125f-116">Service Options</span></span>|<span data-ttu-id="4125f-117">可以执行的操作的下拉列表根据调试器和实例的状态。</span><span class="sxs-lookup"><span data-stu-id="4125f-117">Drop-down list of actions that you can perform based on the state of the debugger and the instance.</span></span>|  
  
 <span data-ttu-id="4125f-118">此信息下，业务流程调试器有两个窗格，在左侧，跟踪的事件窗格和右侧的业务流程窗格。</span><span class="sxs-lookup"><span data-stu-id="4125f-118">Below this information, the Orchestration Debugger has two panes—the Tracked Events pane on the left, and the Orchestration pane on the right.</span></span>  
  
## <a name="tracked-events-pane-in-orchestration-debugger"></a><span data-ttu-id="4125f-119">业务流程调试器中的跟踪的事件窗格</span><span class="sxs-lookup"><span data-stu-id="4125f-119">Tracked Events Pane in Orchestration Debugger</span></span>  
 <span data-ttu-id="4125f-120">跟踪的事件窗格中列出了在业务流程，如是否已启动还是已完成执行每个操作的状态。</span><span class="sxs-lookup"><span data-stu-id="4125f-120">The Tracked Events pane lists the status of every action performed in the orchestration, such as whether it started or completed.</span></span> <span data-ttu-id="4125f-121">在此窗格中选择的每一行时，业务流程窗格中的相应形状以绿色突出显示该形状的开始和蓝色形状完成时。</span><span class="sxs-lookup"><span data-stu-id="4125f-121">As you select each of the rows in this pane, the corresponding shape in the Orchestration pane appears highlighted in green when the shape starts and blue when the shape finishes.</span></span>  
  
 <span data-ttu-id="4125f-122">跟踪的事件窗格中显示了以下列。</span><span class="sxs-lookup"><span data-stu-id="4125f-122">The Tracked Events pane shows the following columns.</span></span>  
  
|<span data-ttu-id="4125f-123">Option</span><span class="sxs-lookup"><span data-stu-id="4125f-123">Option</span></span>|<span data-ttu-id="4125f-124">操作</span><span class="sxs-lookup"><span data-stu-id="4125f-124">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="4125f-125">操作状态 （左列）</span><span class="sxs-lookup"><span data-stu-id="4125f-125">Action Status (left column)</span></span>|<span data-ttu-id="4125f-126">特定操作的状态。</span><span class="sxs-lookup"><span data-stu-id="4125f-126">Status of the particular action.</span></span> <span data-ttu-id="4125f-127">箭头指示操作已启动和终止形状则表示它已完成。</span><span class="sxs-lookup"><span data-stu-id="4125f-127">An arrow indicates the action has started and a termination shape indicates it has completed.</span></span>|  
|<span data-ttu-id="4125f-128">操作名称</span><span class="sxs-lookup"><span data-stu-id="4125f-128">Action Name</span></span>|<span data-ttu-id="4125f-129">在业务流程中操作的名称。</span><span class="sxs-lookup"><span data-stu-id="4125f-129">Name of the action in the orchestration.</span></span>|  
|<span data-ttu-id="4125f-130">操作类型</span><span class="sxs-lookup"><span data-stu-id="4125f-130">Action Type</span></span>|<span data-ttu-id="4125f-131">表示操作的形状的类型。</span><span class="sxs-lookup"><span data-stu-id="4125f-131">Type of shape that represents the action.</span></span> <span data-ttu-id="4125f-132">箭头指示操作已启动和终止形状则表示它已完成。</span><span class="sxs-lookup"><span data-stu-id="4125f-132">An arrow indicates that the action has started and a termination shape indicates it has completed.</span></span>|  
|<span data-ttu-id="4125f-133">Time</span><span class="sxs-lookup"><span data-stu-id="4125f-133">Time</span></span>|<span data-ttu-id="4125f-134">执行操作的时间。</span><span class="sxs-lookup"><span data-stu-id="4125f-134">Time the action was performed.</span></span>|  
|<span data-ttu-id="4125f-135">Date</span><span class="sxs-lookup"><span data-stu-id="4125f-135">Date</span></span>|<span data-ttu-id="4125f-136">执行操作的日期。</span><span class="sxs-lookup"><span data-stu-id="4125f-136">Date the action was performed.</span></span>|  
  
## <a name="orchestration-pane-in-orchestration-debugger"></a><span data-ttu-id="4125f-137">业务流程调试器中的业务流程窗格</span><span class="sxs-lookup"><span data-stu-id="4125f-137">Orchestration Pane in Orchestration Debugger</span></span>  
 <span data-ttu-id="4125f-138">消息事件和服务实例跟踪输出中的组中心页中的业务流程窗格是业务流程实例及其所有形状的呈现位置的区域。</span><span class="sxs-lookup"><span data-stu-id="4125f-138">The Orchestration pane in message event and service instance tracking output in the Group Hub page is the area where the orchestration instance renders with all of its shapes.</span></span> <span data-ttu-id="4125f-139">下表显示了业务流程窗格中的上下文菜单操作。</span><span class="sxs-lookup"><span data-stu-id="4125f-139">The following table shows the Context menu actions for the Orchestration pane.</span></span>  
  
|<span data-ttu-id="4125f-140">Option</span><span class="sxs-lookup"><span data-stu-id="4125f-140">Option</span></span>|<span data-ttu-id="4125f-141">操作</span><span class="sxs-lookup"><span data-stu-id="4125f-141">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="4125f-142">在类上设置断点</span><span class="sxs-lookup"><span data-stu-id="4125f-142">Set Breakpoint on Class</span></span>|<span data-ttu-id="4125f-143">右键单击某个形状**类上设置断点**选项。</span><span class="sxs-lookup"><span data-stu-id="4125f-143">Right-click a shape for the **Set Breakpoint on Class** option.</span></span> <span data-ttu-id="4125f-144">设置断点，该值指示该形状上显示的红点。</span><span class="sxs-lookup"><span data-stu-id="4125f-144">A red dot appears on the shape indicating the breakpoint has been set.</span></span>|  
|<span data-ttu-id="4125f-145">在实例上设置断点</span><span class="sxs-lookup"><span data-stu-id="4125f-145">Set Breakpoint on Instance</span></span>|<span data-ttu-id="4125f-146">右键单击某个形状**实例上设置断点**选项。</span><span class="sxs-lookup"><span data-stu-id="4125f-146">Right-click a shape for the **Set Breakpoint on Instance** option.</span></span> <span data-ttu-id="4125f-147">设置断点，该值指示该形状上显示的红点。</span><span class="sxs-lookup"><span data-stu-id="4125f-147">A red dot appears on the shape indicating the breakpoint has been set.</span></span>|  
|<span data-ttu-id="4125f-148">删除类上的断点</span><span class="sxs-lookup"><span data-stu-id="4125f-148">Remove Breakpoint on Class</span></span>|<span data-ttu-id="4125f-149">右键单击某个形状**删除断点**选项。</span><span class="sxs-lookup"><span data-stu-id="4125f-149">Right-click a shape for the **Remove Breakpoint** option.</span></span> <span data-ttu-id="4125f-150">红点将消失，该值指示断点已删除的形状。</span><span class="sxs-lookup"><span data-stu-id="4125f-150">The red dot disappears from the shape indicating the breakpoint has been removed.</span></span>|  
|<span data-ttu-id="4125f-151">删除实例上的断点</span><span class="sxs-lookup"><span data-stu-id="4125f-151">Remove Breakpoint on Instance</span></span>|<span data-ttu-id="4125f-152">右键单击某个形状**实例上设置断点**选项。</span><span class="sxs-lookup"><span data-stu-id="4125f-152">Right-click a shape for the **Set Breakpoint on Instance** option.</span></span> <span data-ttu-id="4125f-153">红点将消失，该值指示断点已删除的形状。</span><span class="sxs-lookup"><span data-stu-id="4125f-153">The red dot disappears from the shape indicating the breakpoint has been removed.</span></span>|  
  
### <a name="variable-list-and-variable-properties-panes"></a><span data-ttu-id="4125f-154">变量列表和变量属性窗格</span><span class="sxs-lookup"><span data-stu-id="4125f-154">Variable List and Variable Properties panes</span></span>  
 <span data-ttu-id="4125f-155">这些窗格仅显示以进行交互调试时附加到业务流程运行时使用**附加**服务选项。</span><span class="sxs-lookup"><span data-stu-id="4125f-155">These panes only appear for interactive debugging when attached to the Orchestration runtime using the **Attach** service option.</span></span> <span data-ttu-id="4125f-156">两个窗格显示在屏幕的底部。</span><span class="sxs-lookup"><span data-stu-id="4125f-156">These panes appear at the bottom of the screen.</span></span>  
  
 <span data-ttu-id="4125f-157">变量列表显示名称、 值和变量的类型。</span><span class="sxs-lookup"><span data-stu-id="4125f-157">The Variable List displays the Name, Value, and Type of the variable.</span></span> <span data-ttu-id="4125f-158">值指示是否变量为 Null 或者，如果没有，则何种类型的对象包含。</span><span class="sxs-lookup"><span data-stu-id="4125f-158">The Value indicates if the variable is Null or, if not, then what kind of object it contains.</span></span> <span data-ttu-id="4125f-159">类型是**Assembly.Namespace.Name**的对象。</span><span class="sxs-lookup"><span data-stu-id="4125f-159">Type is the **Assembly.Namespace.Name** of the object.</span></span>  
  
 <span data-ttu-id="4125f-160">变量属性窗格显示对象的类型而异的变量的属性。</span><span class="sxs-lookup"><span data-stu-id="4125f-160">The Variable Properties pane displays properties for the variable that vary according to the type of object.</span></span> <span data-ttu-id="4125f-161">例如，对于端口这包括地址、 名称、 作用域、 类型和值。</span><span class="sxs-lookup"><span data-stu-id="4125f-161">For example, for ports this includes Address, Name, Scope, Type, and Value.</span></span> <span data-ttu-id="4125f-162">消息会显示该快捷方式;消息中的每个部分，对于没有名称、 大小、 属性、 类型和值。</span><span class="sxs-lookup"><span data-stu-id="4125f-162">Messages show the shortcut; for each part in the message, there is Name, Size, Properties, Type, and Value.</span></span> <span data-ttu-id="4125f-163">例如，上下文和属性的集合显示一个弹出窗口中。</span><span class="sxs-lookup"><span data-stu-id="4125f-163">Collections such as Context and Properties display in a pop-up.</span></span> <span data-ttu-id="4125f-164">部分显示的值显示为工具提示。</span><span class="sxs-lookup"><span data-stu-id="4125f-164">A partial display of the Value appears as a ToolTip.</span></span>  
  
 <span data-ttu-id="4125f-165">用户通过计划推进断点断点，并检查这些变量的状态。</span><span class="sxs-lookup"><span data-stu-id="4125f-165">The user advances through the schedule from breakpoint to breakpoint and examines the state of these variables.</span></span>  
  
 <span data-ttu-id="4125f-166">下表显示变量列表的上下文菜单操作。</span><span class="sxs-lookup"><span data-stu-id="4125f-166">The following table shows the Context menu actions for the Variable List.</span></span>  
  
|<span data-ttu-id="4125f-167">Option</span><span class="sxs-lookup"><span data-stu-id="4125f-167">Option</span></span>|<span data-ttu-id="4125f-168">操作</span><span class="sxs-lookup"><span data-stu-id="4125f-168">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="4125f-169">保存消息</span><span class="sxs-lookup"><span data-stu-id="4125f-169">Save Message</span></span>|<span data-ttu-id="4125f-170">右键单击一条消息，不为 null 的变量列表窗格中的**保存消息**选项。</span><span class="sxs-lookup"><span data-stu-id="4125f-170">Right-click a Message that is non-null in the Variable List pane for the **Save Message** option.</span></span> <span data-ttu-id="4125f-171">一条消息会显示提示您选择要将其保存到一个目录。</span><span class="sxs-lookup"><span data-stu-id="4125f-171">A message appears prompting you to select a directory to which to save it.</span></span>|  
  
### <a name="service-options-drop-down-list"></a><span data-ttu-id="4125f-172">服务选项下拉列表</span><span class="sxs-lookup"><span data-stu-id="4125f-172">Service Options drop-down list</span></span>  
 <span data-ttu-id="4125f-173">服务选项下拉列表显示了基于状态的实例和调试器的有效操作。</span><span class="sxs-lookup"><span data-stu-id="4125f-173">The Service Options drop-down list shows you the valid actions based on the state of the instance and the debugger.</span></span> <span data-ttu-id="4125f-174">下表显示在服务选项下拉列表中的可用操作。</span><span class="sxs-lookup"><span data-stu-id="4125f-174">The following table shows the available actions in the Service Options drop-down list.</span></span>  
  
|<span data-ttu-id="4125f-175">Option</span><span class="sxs-lookup"><span data-stu-id="4125f-175">Option</span></span>|<span data-ttu-id="4125f-176">操作</span><span class="sxs-lookup"><span data-stu-id="4125f-176">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="4125f-177">继续服务</span><span class="sxs-lookup"><span data-stu-id="4125f-177">Continue Service</span></span>|<span data-ttu-id="4125f-178">将继续在断点处停止，如果附加了服务业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="4125f-178">Continues an orchestration instance that stopped at a breakpoint if you attached the service.</span></span>|  
|<span data-ttu-id="4125f-179">恢复为调试模式</span><span class="sxs-lookup"><span data-stu-id="4125f-179">Resume in Debug mode</span></span>|<span data-ttu-id="4125f-180">恢复挂起的业务流程实例在调试模式下。</span><span class="sxs-lookup"><span data-stu-id="4125f-180">Resumes a suspended orchestration instance in debug mode.</span></span> <span data-ttu-id="4125f-181">这使您可以进入交互模式，将附加到该实例，并以交互方式对其进行调试。</span><span class="sxs-lookup"><span data-stu-id="4125f-181">This enables you to go into interactive mode, attach to the instance, and debug it interactively.</span></span><br /><br /> <span data-ttu-id="4125f-182">可从操作视图和业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="4125f-182">Available from the Operations views and the Orchestration Debugger.</span></span> <span data-ttu-id="4125f-183">它仅适用于业务流程。</span><span class="sxs-lookup"><span data-stu-id="4125f-183">It only applies to orchestrations.</span></span>|  
|<span data-ttu-id="4125f-184">终止服务</span><span class="sxs-lookup"><span data-stu-id="4125f-184">Terminate Service</span></span>|<span data-ttu-id="4125f-185">终止业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="4125f-185">Terminates an orchestration instance.</span></span>|  
|<span data-ttu-id="4125f-186">附加</span><span class="sxs-lookup"><span data-stu-id="4125f-186">Attach</span></span>|<span data-ttu-id="4125f-187">将该服务附加到业务流程实例并检索当前状态和变量</span><span class="sxs-lookup"><span data-stu-id="4125f-187">Attaches the service to the orchestration instance and retrieves the current state and variables</span></span>|  
|<span data-ttu-id="4125f-188">删除类上的所有断点</span><span class="sxs-lookup"><span data-stu-id="4125f-188">Remove all Breakpoints on Class</span></span>|<span data-ttu-id="4125f-189">在业务流程类中删除所有断点。</span><span class="sxs-lookup"><span data-stu-id="4125f-189">Removes all the breakpoints in the orchestration class.</span></span> <span data-ttu-id="4125f-190">仅当未附加时才可用。</span><span class="sxs-lookup"><span data-stu-id="4125f-190">Only available when not attached.</span></span>|  
|<span data-ttu-id="4125f-191">删除所有断点</span><span class="sxs-lookup"><span data-stu-id="4125f-191">Remove all Breakpoints</span></span>|<span data-ttu-id="4125f-192">业务流程实例中删除所有断点。</span><span class="sxs-lookup"><span data-stu-id="4125f-192">Removes all the breakpoints in the orchestration instance.</span></span> <span data-ttu-id="4125f-193">仅当连接时才可用。</span><span class="sxs-lookup"><span data-stu-id="4125f-193">Only available when attached.</span></span>|  
|<span data-ttu-id="4125f-194">保存所有消息</span><span class="sxs-lookup"><span data-stu-id="4125f-194">Save All Messages</span></span>|<span data-ttu-id="4125f-195">将保存，只要您已选择跟踪所有入站/出站消息与业务流程实例相关联的所有消息。</span><span class="sxs-lookup"><span data-stu-id="4125f-195">Saves all the messages associated with the orchestration instance as long as you have selected to track all inbound/outbound messages.</span></span>|  
|<span data-ttu-id="4125f-196">显示断点的操作</span><span class="sxs-lookup"><span data-stu-id="4125f-196">Show Action in Breakpoint</span></span>|<span data-ttu-id="4125f-197">突出显示为黄色的上一操作形状在中断前执行。</span><span class="sxs-lookup"><span data-stu-id="4125f-197">Highlights the shape as yellow for the last action executed before breaking.</span></span>|  
|<span data-ttu-id="4125f-198">查看调用业务流程</span><span class="sxs-lookup"><span data-stu-id="4125f-198">View Calling Orchestration</span></span>|<span data-ttu-id="4125f-199">返回到调用的业务流程实例的视图。</span><span class="sxs-lookup"><span data-stu-id="4125f-199">Returns the view to the orchestration instance that made the call.</span></span> <span data-ttu-id="4125f-200">也就是说，它将返回到父业务流程。</span><span class="sxs-lookup"><span data-stu-id="4125f-200">That is, it takes you back to the parent orchestration.</span></span><br /><br /> <span data-ttu-id="4125f-201">仅可调用的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="4125f-201">Only available on a called orchestration instance.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="4125f-202">本节内容</span><span class="sxs-lookup"><span data-stu-id="4125f-202">In This Section</span></span>  
  
-   [<span data-ttu-id="4125f-203">业务流程调试器中的“报告”模式</span><span class="sxs-lookup"><span data-stu-id="4125f-203">Reporting Mode in Orchestration Debugger</span></span>](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [<span data-ttu-id="4125f-204">业务流程调试器中的“交互”模式</span><span class="sxs-lookup"><span data-stu-id="4125f-204">Interactive Mode in Orchestration Debugger</span></span>](../core/interactive-mode-in-orchestration-debugger.md)  
  
## <a name="see-also"></a><span data-ttu-id="4125f-205">请参阅</span><span class="sxs-lookup"><span data-stu-id="4125f-205">See Also</span></span>  
 [<span data-ttu-id="4125f-206">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="4125f-206">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)