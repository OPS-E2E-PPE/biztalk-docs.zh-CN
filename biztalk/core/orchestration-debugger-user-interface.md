---
title: 业务流程调试器用户界面 |Microsoft 文档
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
ms.openlocfilehash: 4663a642ffc960d969c994b5471d866a80fde828
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-debugger-user-interface"></a><span data-ttu-id="0f189-102">业务流程调试器用户界面</span><span class="sxs-lookup"><span data-stu-id="0f189-102">Orchestration Debugger User Interface</span></span>
<span data-ttu-id="0f189-103">在交互（调试）模式下，“业务流程调试器”视图包含三个区域：“服务”窗格、“跟踪的事件”窗格以及“业务流程”窗格。</span><span class="sxs-lookup"><span data-stu-id="0f189-103">In interactive (debug) mode, the Orchestration Debugger view contains three areas: Service pane, Tracked Events pane, and the Orchestration pane.</span></span> <span data-ttu-id="0f189-104">此外，在交互模式下，在视图底部会依次显示“变量列表”和“变量属性”。</span><span class="sxs-lookup"><span data-stu-id="0f189-104">In addition, in interactive mode, the Variable list and Variable properties display across the bottom of the view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f189-105">业务流程调试器不能显示服务的真实状态，除非它出现在**在断点处**模式，并且您已附加它到的实例。</span><span class="sxs-lookup"><span data-stu-id="0f189-105">The Orchestration Debugger cannot display the true state of the service unless it appears in **In Breakpoint** mode and you have attached it to the instance.</span></span>  
  
## <a name="service-pane-in-orchestration-debugger"></a><span data-ttu-id="0f189-106">业务流程调试器中的“服务”窗格</span><span class="sxs-lookup"><span data-stu-id="0f189-106">Service Pane in Orchestration Debugger</span></span>  
 <span data-ttu-id="0f189-107">“业务流程调试器”窗口的顶部窗格显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="0f189-107">The top pane of the Orchestration Debugger window displays the following information.</span></span>  
  
|<span data-ttu-id="0f189-108">标记</span><span class="sxs-lookup"><span data-stu-id="0f189-108">Tag</span></span>|<span data-ttu-id="0f189-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="0f189-109">Detail</span></span>|  
|---------|------------|  
|<span data-ttu-id="0f189-110">Name</span><span class="sxs-lookup"><span data-stu-id="0f189-110">Name</span></span>|<span data-ttu-id="0f189-111">指示当前视图（业务流程调试器），并可用于导航到“消息流”视图。</span><span class="sxs-lookup"><span data-stu-id="0f189-111">Indicates the current view (Orchestration Debugger), and allows you to navigate to the Message Flow view.</span></span>|  
|<span data-ttu-id="0f189-112">实例详细信息</span><span class="sxs-lookup"><span data-stu-id="0f189-112">Instance Details</span></span>|<span data-ttu-id="0f189-113">显示唯一标识当前业务流程实例的服务名称和 GUID。</span><span class="sxs-lookup"><span data-stu-id="0f189-113">Displays the service name and the GUID that uniquely identifies the current orchestration instance.</span></span>|  
|<span data-ttu-id="0f189-114">模式</span><span class="sxs-lookup"><span data-stu-id="0f189-114">Modes</span></span>|<span data-ttu-id="0f189-115">调试模式（重播/实时）、业务流程状态（已启动、已挂起和已完成等等）、已附加（是或否）和断点模式（在类上或在实例上）。</span><span class="sxs-lookup"><span data-stu-id="0f189-115">Debug mode (Replay/Live), Orchestration state (Started, Suspended, Completed, etc.), Attached (Yes or No), and Breakpoint mode (On Class or On Instance).</span></span>|  
|<span data-ttu-id="0f189-116">服务选项</span><span class="sxs-lookup"><span data-stu-id="0f189-116">Service Options</span></span>|<span data-ttu-id="0f189-117">该下拉列表根据调试器和实例的状态显示您可以执行的不同操作。</span><span class="sxs-lookup"><span data-stu-id="0f189-117">Drop-down list of actions that you can perform based on the state of the debugger and the instance.</span></span>|  
  
 <span data-ttu-id="0f189-118">在此信息下，业务流程调试器显示有两个窗格，即左侧的“跟踪的事件”窗格和右侧的“业务流程”窗格。</span><span class="sxs-lookup"><span data-stu-id="0f189-118">Below this information, the Orchestration Debugger has two panes—the Tracked Events pane on the left, and the Orchestration pane on the right.</span></span>  
  
## <a name="tracked-events-pane-in-orchestration-debugger"></a><span data-ttu-id="0f189-119">业务流程调试器 -“跟踪的事件”窗格</span><span class="sxs-lookup"><span data-stu-id="0f189-119">Tracked Events Pane in Orchestration Debugger</span></span>  
 <span data-ttu-id="0f189-120">“跟踪的事件”窗格列出了业务流程中所执行的每个操作的状态，例如操作是已启动还是已完成。</span><span class="sxs-lookup"><span data-stu-id="0f189-120">The Tracked Events pane lists the status of every action performed in the orchestration, such as whether it started or completed.</span></span> <span data-ttu-id="0f189-121">选择此窗格中的每一行时，“业务流程”窗格中的相应形状将以绿色突出显示该形状的开始时间，并以蓝色突出显示该形状的结束时间。</span><span class="sxs-lookup"><span data-stu-id="0f189-121">As you select each of the rows in this pane, the corresponding shape in the Orchestration pane appears highlighted in green when the shape starts and blue when the shape finishes.</span></span>  
  
 <span data-ttu-id="0f189-122">“跟踪的事件”窗格显示了以下列：</span><span class="sxs-lookup"><span data-stu-id="0f189-122">The Tracked Events pane shows the following columns.</span></span>  
  
|<span data-ttu-id="0f189-123">选项</span><span class="sxs-lookup"><span data-stu-id="0f189-123">Option</span></span>|<span data-ttu-id="0f189-124">操作</span><span class="sxs-lookup"><span data-stu-id="0f189-124">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="0f189-125">操作状态（左列）</span><span class="sxs-lookup"><span data-stu-id="0f189-125">Action Status (left column)</span></span>|<span data-ttu-id="0f189-126">特定操作的状态。</span><span class="sxs-lookup"><span data-stu-id="0f189-126">Status of the particular action.</span></span> <span data-ttu-id="0f189-127">箭头表示该操作已开始，终止形状则表示该操作已完成。</span><span class="sxs-lookup"><span data-stu-id="0f189-127">An arrow indicates the action has started and a termination shape indicates it has completed.</span></span>|  
|<span data-ttu-id="0f189-128">操作名称</span><span class="sxs-lookup"><span data-stu-id="0f189-128">Action Name</span></span>|<span data-ttu-id="0f189-129">业务流程中操作的名称。</span><span class="sxs-lookup"><span data-stu-id="0f189-129">Name of the action in the orchestration.</span></span>|  
|<span data-ttu-id="0f189-130">操作类型</span><span class="sxs-lookup"><span data-stu-id="0f189-130">Action Type</span></span>|<span data-ttu-id="0f189-131">表示操作的形状类型。</span><span class="sxs-lookup"><span data-stu-id="0f189-131">Type of shape that represents the action.</span></span> <span data-ttu-id="0f189-132">箭头指示操作已启动和终止形状指示它已完成。</span><span class="sxs-lookup"><span data-stu-id="0f189-132">An arrow indicates that the action has started and a termination shape indicates it has completed.</span></span>|  
|<span data-ttu-id="0f189-133">Time</span><span class="sxs-lookup"><span data-stu-id="0f189-133">Time</span></span>|<span data-ttu-id="0f189-134">执行操作的时间。</span><span class="sxs-lookup"><span data-stu-id="0f189-134">Time the action was performed.</span></span>|  
|<span data-ttu-id="0f189-135">日期</span><span class="sxs-lookup"><span data-stu-id="0f189-135">Date</span></span>|<span data-ttu-id="0f189-136">执行操作的日期。</span><span class="sxs-lookup"><span data-stu-id="0f189-136">Date the action was performed.</span></span>|  
  
## <a name="orchestration-pane-in-orchestration-debugger"></a><span data-ttu-id="0f189-137">业务流程调试器中的“业务流程”窗格</span><span class="sxs-lookup"><span data-stu-id="0f189-137">Orchestration Pane in Orchestration Debugger</span></span>  
 <span data-ttu-id="0f189-138">“组中心”页中消息事件和服务实例跟踪输出中的“业务流程”窗格是业务流程实例呈现其所有形状的区域。</span><span class="sxs-lookup"><span data-stu-id="0f189-138">The Orchestration pane in message event and service instance tracking output in the Group Hub page is the area where the orchestration instance renders with all of its shapes.</span></span> <span data-ttu-id="0f189-139">下表列出了“业务流程”窗格的各种上下文菜单操作：</span><span class="sxs-lookup"><span data-stu-id="0f189-139">The following table shows the Context menu actions for the Orchestration pane.</span></span>  
  
|<span data-ttu-id="0f189-140">选项</span><span class="sxs-lookup"><span data-stu-id="0f189-140">Option</span></span>|<span data-ttu-id="0f189-141">操作</span><span class="sxs-lookup"><span data-stu-id="0f189-141">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="0f189-142">在类上设置断点</span><span class="sxs-lookup"><span data-stu-id="0f189-142">Set Breakpoint on Class</span></span>|<span data-ttu-id="0f189-143">右键单击形状**类上设置的断点**选项。</span><span class="sxs-lookup"><span data-stu-id="0f189-143">Right-click a shape for the **Set Breakpoint on Class** option.</span></span> <span data-ttu-id="0f189-144">该形状上将显示一个红点，指示已设置断点。</span><span class="sxs-lookup"><span data-stu-id="0f189-144">A red dot appears on the shape indicating the breakpoint has been set.</span></span>|  
|<span data-ttu-id="0f189-145">在实例上设置断点</span><span class="sxs-lookup"><span data-stu-id="0f189-145">Set Breakpoint on Instance</span></span>|<span data-ttu-id="0f189-146">右键单击形状**实例上设置断点**选项。</span><span class="sxs-lookup"><span data-stu-id="0f189-146">Right-click a shape for the **Set Breakpoint on Instance** option.</span></span> <span data-ttu-id="0f189-147">该形状上将显示一个红点，指示已设置断点。</span><span class="sxs-lookup"><span data-stu-id="0f189-147">A red dot appears on the shape indicating the breakpoint has been set.</span></span>|  
|<span data-ttu-id="0f189-148">删除类上的断点</span><span class="sxs-lookup"><span data-stu-id="0f189-148">Remove Breakpoint on Class</span></span>|<span data-ttu-id="0f189-149">右键单击形状**删除断点**选项。</span><span class="sxs-lookup"><span data-stu-id="0f189-149">Right-click a shape for the **Remove Breakpoint** option.</span></span> <span data-ttu-id="0f189-150">该形状的红点将消失，指示断点已删除。</span><span class="sxs-lookup"><span data-stu-id="0f189-150">The red dot disappears from the shape indicating the breakpoint has been removed.</span></span>|  
|<span data-ttu-id="0f189-151">删除实例上的断点</span><span class="sxs-lookup"><span data-stu-id="0f189-151">Remove Breakpoint on Instance</span></span>|<span data-ttu-id="0f189-152">右键单击形状**实例上设置断点**选项。</span><span class="sxs-lookup"><span data-stu-id="0f189-152">Right-click a shape for the **Set Breakpoint on Instance** option.</span></span> <span data-ttu-id="0f189-153">该形状的红点将消失，指示断点已删除。</span><span class="sxs-lookup"><span data-stu-id="0f189-153">The red dot disappears from the shape indicating the breakpoint has been removed.</span></span>|  
  
### <a name="variable-list-and-variable-properties-panes"></a><span data-ttu-id="0f189-154">“变量列表”和“变量属性”窗格</span><span class="sxs-lookup"><span data-stu-id="0f189-154">Variable List and Variable Properties panes</span></span>  
 <span data-ttu-id="0f189-155">为时附加到业务流程的运行时使用的交互式调试仅显示这些窗格**附加**服务选项。</span><span class="sxs-lookup"><span data-stu-id="0f189-155">These panes only appear for interactive debugging when attached to the Orchestration runtime using the **Attach** service option.</span></span> <span data-ttu-id="0f189-156">这两个窗格显示在屏幕底部。</span><span class="sxs-lookup"><span data-stu-id="0f189-156">These panes appear at the bottom of the screen.</span></span>  
  
 <span data-ttu-id="0f189-157">“变量列表”显示变量的名称、值和类型。</span><span class="sxs-lookup"><span data-stu-id="0f189-157">The Variable List displays the Name, Value, and Type of the variable.</span></span> <span data-ttu-id="0f189-158">变量的值指示变量是否为空值，如果不是空值，则指示它包含的对象种类。</span><span class="sxs-lookup"><span data-stu-id="0f189-158">The Value indicates if the variable is Null or, if not, then what kind of object it contains.</span></span> <span data-ttu-id="0f189-159">类型是**Assembly.Namespace.Name**的对象。</span><span class="sxs-lookup"><span data-stu-id="0f189-159">Type is the **Assembly.Namespace.Name** of the object.</span></span>  
  
 <span data-ttu-id="0f189-160">“变量属性”窗格显示随对象类型而异的变量属性。</span><span class="sxs-lookup"><span data-stu-id="0f189-160">The Variable Properties pane displays properties for the variable that vary according to the type of object.</span></span> <span data-ttu-id="0f189-161">例如，对于端口，该窗格将包含地址、名称、作用域、类型和值。</span><span class="sxs-lookup"><span data-stu-id="0f189-161">For example, for ports this includes Address, Name, Scope, Type, and Value.</span></span> <span data-ttu-id="0f189-162">对于消息，则显示快捷方式；对消息的每个部分都会显示相应的名称、大小、属性、类型和值。</span><span class="sxs-lookup"><span data-stu-id="0f189-162">Messages show the shortcut; for each part in the message, there is Name, Size, Properties, Type, and Value.</span></span> <span data-ttu-id="0f189-163">诸如上下文和属性之类的集合以弹出方式显示。</span><span class="sxs-lookup"><span data-stu-id="0f189-163">Collections such as Context and Properties display in a pop-up.</span></span> <span data-ttu-id="0f189-164">另外，会使用值的部分显示作为工具提示。</span><span class="sxs-lookup"><span data-stu-id="0f189-164">A partial display of the Value appears as a ToolTip.</span></span>  
  
 <span data-ttu-id="0f189-165">用户可以在不同断点之间对调度进行调试，并检查这些变量的状态。</span><span class="sxs-lookup"><span data-stu-id="0f189-165">The user advances through the schedule from breakpoint to breakpoint and examines the state of these variables.</span></span>  
  
 <span data-ttu-id="0f189-166">下表列出了“变量列表”的上下文菜单操作：</span><span class="sxs-lookup"><span data-stu-id="0f189-166">The following table shows the Context menu actions for the Variable List.</span></span>  
  
|<span data-ttu-id="0f189-167">选项</span><span class="sxs-lookup"><span data-stu-id="0f189-167">Option</span></span>|<span data-ttu-id="0f189-168">操作</span><span class="sxs-lookup"><span data-stu-id="0f189-168">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="0f189-169">将消息保存</span><span class="sxs-lookup"><span data-stu-id="0f189-169">Save Message</span></span>|<span data-ttu-id="0f189-170">右键单击一条消息，为非 null 的变量列表窗格中**保存消息**选项。</span><span class="sxs-lookup"><span data-stu-id="0f189-170">Right-click a Message that is non-null in the Variable List pane for the **Save Message** option.</span></span> <span data-ttu-id="0f189-171">此时，将显示一条消息，提示您选择保存消息的目录。</span><span class="sxs-lookup"><span data-stu-id="0f189-171">A message appears prompting you to select a directory to which to save it.</span></span>|  
  
### <a name="service-options-drop-down-list"></a><span data-ttu-id="0f189-172">“服务选项”下拉列表</span><span class="sxs-lookup"><span data-stu-id="0f189-172">Service Options drop-down list</span></span>  
 <span data-ttu-id="0f189-173">“服务选项”下拉列表将根据实例和调试器的状态显示有效的操作。</span><span class="sxs-lookup"><span data-stu-id="0f189-173">The Service Options drop-down list shows you the valid actions based on the state of the instance and the debugger.</span></span> <span data-ttu-id="0f189-174">下表列出了“服务选项”下拉列表中的可用操作：</span><span class="sxs-lookup"><span data-stu-id="0f189-174">The following table shows the available actions in the Service Options drop-down list.</span></span>  
  
|<span data-ttu-id="0f189-175">选项</span><span class="sxs-lookup"><span data-stu-id="0f189-175">Option</span></span>|<span data-ttu-id="0f189-176">操作</span><span class="sxs-lookup"><span data-stu-id="0f189-176">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="0f189-177">继续服务</span><span class="sxs-lookup"><span data-stu-id="0f189-177">Continue Service</span></span>|<span data-ttu-id="0f189-178">如果附加了服务，则继续执行在断点处停止的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="0f189-178">Continues an orchestration instance that stopped at a breakpoint if you attached the service.</span></span>|  
|<span data-ttu-id="0f189-179">恢复为调试模式</span><span class="sxs-lookup"><span data-stu-id="0f189-179">Resume in Debug mode</span></span>|<span data-ttu-id="0f189-180">以调试模式恢复挂起的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="0f189-180">Resumes a suspended orchestration instance in debug mode.</span></span> <span data-ttu-id="0f189-181">这样您就可以进入交互模式，附加到实例，然后进行交互调试。</span><span class="sxs-lookup"><span data-stu-id="0f189-181">This enables you to go into interactive mode, attach to the instance, and debug it interactively.</span></span><br /><br /> <span data-ttu-id="0f189-182">可从操作视图和业务流程调试器中访问此选项。</span><span class="sxs-lookup"><span data-stu-id="0f189-182">Available from the Operations views and the Orchestration Debugger.</span></span> <span data-ttu-id="0f189-183">它仅适用于业务流程。</span><span class="sxs-lookup"><span data-stu-id="0f189-183">It only applies to orchestrations.</span></span>|  
|<span data-ttu-id="0f189-184">终止服务</span><span class="sxs-lookup"><span data-stu-id="0f189-184">Terminate Service</span></span>|<span data-ttu-id="0f189-185">终止业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="0f189-185">Terminates an orchestration instance.</span></span>|  
|<span data-ttu-id="0f189-186">附加</span><span class="sxs-lookup"><span data-stu-id="0f189-186">Attach</span></span>|<span data-ttu-id="0f189-187">将相应的服务附加到业务流程实例并检索当前状态和变量</span><span class="sxs-lookup"><span data-stu-id="0f189-187">Attaches the service to the orchestration instance and retrieves the current state and variables</span></span>|  
|<span data-ttu-id="0f189-188">删除类上的所有断点</span><span class="sxs-lookup"><span data-stu-id="0f189-188">Remove all Breakpoints on Class</span></span>|<span data-ttu-id="0f189-189">删除业务流程类中的所有断点。</span><span class="sxs-lookup"><span data-stu-id="0f189-189">Removes all the breakpoints in the orchestration class.</span></span> <span data-ttu-id="0f189-190">只有在没有附加服务的情况下才可用。</span><span class="sxs-lookup"><span data-stu-id="0f189-190">Only available when not attached.</span></span>|  
|<span data-ttu-id="0f189-191">移除所有断点</span><span class="sxs-lookup"><span data-stu-id="0f189-191">Remove all Breakpoints</span></span>|<span data-ttu-id="0f189-192">删除业务流程实例中的所有断点。</span><span class="sxs-lookup"><span data-stu-id="0f189-192">Removes all the breakpoints in the orchestration instance.</span></span> <span data-ttu-id="0f189-193">只有在附加服务的情况下才可用。</span><span class="sxs-lookup"><span data-stu-id="0f189-193">Only available when attached.</span></span>|  
|<span data-ttu-id="0f189-194">保存所有消息</span><span class="sxs-lookup"><span data-stu-id="0f189-194">Save All Messages</span></span>|<span data-ttu-id="0f189-195">在您选择了对所有入站/出站消息进行跟踪的情况下，保存与业务流程实例关联的所有消息。</span><span class="sxs-lookup"><span data-stu-id="0f189-195">Saves all the messages associated with the orchestration instance as long as you have selected to track all inbound/outbound messages.</span></span>|  
|<span data-ttu-id="0f189-196">显示断点处的操作</span><span class="sxs-lookup"><span data-stu-id="0f189-196">Show Action in Breakpoint</span></span>|<span data-ttu-id="0f189-197">用黄色突出显示形状在中断前执行的最后一次操作。</span><span class="sxs-lookup"><span data-stu-id="0f189-197">Highlights the shape as yellow for the last action executed before breaking.</span></span>|  
|<span data-ttu-id="0f189-198">查看调用业务流程</span><span class="sxs-lookup"><span data-stu-id="0f189-198">View Calling Orchestration</span></span>|<span data-ttu-id="0f189-199">返回到进行调用的业务流程实例的视图。</span><span class="sxs-lookup"><span data-stu-id="0f189-199">Returns the view to the orchestration instance that made the call.</span></span> <span data-ttu-id="0f189-200">也就是说，返回到父业务流程。</span><span class="sxs-lookup"><span data-stu-id="0f189-200">That is, it takes you back to the parent orchestration.</span></span><br /><br /> <span data-ttu-id="0f189-201">此选项只可用于被调用的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="0f189-201">Only available on a called orchestration instance.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="0f189-202">本节内容</span><span class="sxs-lookup"><span data-stu-id="0f189-202">In This Section</span></span>  
  
-   [<span data-ttu-id="0f189-203">报告在业务流程调试器中的模式</span><span class="sxs-lookup"><span data-stu-id="0f189-203">Reporting Mode in Orchestration Debugger</span></span>](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [<span data-ttu-id="0f189-204">在调试器中业务流程交互模式</span><span class="sxs-lookup"><span data-stu-id="0f189-204">Interactive Mode in Orchestration Debugger</span></span>](../core/interactive-mode-in-orchestration-debugger.md)  
  
## <a name="see-also"></a><span data-ttu-id="0f189-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f189-205">See Also</span></span>  
 [<span data-ttu-id="0f189-206">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="0f189-206">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)