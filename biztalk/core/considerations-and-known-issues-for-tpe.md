---
title: 注意事项和已知的问题的 TPE |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, known issues
- planning, Tracking Profile Editor
- Tracking Profile Editor, planning
ms.assetid: e96d85e0-e9ae-434a-b54e-5950f4a2b9c6
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41f728126f14193ad8fc584a94574dab61f7140f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996870"
---
# <a name="considerations-and-known-issues-for-tpe"></a><span data-ttu-id="ef7a1-102">注意事项和 TPE 的已知的问题</span><span class="sxs-lookup"><span data-stu-id="ef7a1-102">Considerations and Known Issues for TPE</span></span>
<span data-ttu-id="ef7a1-103">使用跟踪配置文件和 TPE 时，应注意以下问题。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-103">You should consider the following issues when you work with tracking profiles and the TPE.</span></span>  
  
## <a name="naming-folders-in-the-tpe"></a><span data-ttu-id="ef7a1-104">在 TPE 中命名文件夹</span><span class="sxs-lookup"><span data-stu-id="ef7a1-104">Naming Folders in the TPE</span></span>  
 <span data-ttu-id="ef7a1-105">在跟踪配置文件编辑器中命名文件夹时，请注意以下命名要求：</span><span class="sxs-lookup"><span data-stu-id="ef7a1-105">Note the following naming requirements when naming folders in Tracking Profile Editor:</span></span>  
  
-   <span data-ttu-id="ef7a1-106">文件夹名和数据项实例值的组合的长度不得超过 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-106">The length of the combination of folder name and data item instance values must not exceed 128 characters.</span></span>  
  
-   <span data-ttu-id="ef7a1-107">对于 Continuation 和 ContinuationID 文件夹，文件夹的命名是将两个业务流程相关联的关键。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-107">For Continuation and ContinuationID folders, the naming of the folder is the key to correlating two orchestrations.</span></span> <span data-ttu-id="ef7a1-108">例如，业务流程 A 是业务流程 B 的父级，业务流程 A 包含一个 Continuation 文件夹，该文件夹的名称直接映射到业务流程 B 中的 ContinuationID 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-108">For example, if Orchestration A is the parent of Orchestration B, Orchestration A contains a continuation folder whose name maps directly to the ContinuationID folder in Orchestration B.</span></span>  
  
## <a name="developing-orchestrations-for-the-tpe"></a><span data-ttu-id="ef7a1-109">开发 TPE 的业务流程</span><span class="sxs-lookup"><span data-stu-id="ef7a1-109">Developing Orchestrations for the TPE</span></span>  
 <span data-ttu-id="ef7a1-110">如果某个业务流程的开始和结束形状无效，则您无法将该业务流程映射到业务活动。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-110">You cannot map an orchestration to a business activity if it starts or ends with an invalid shape.</span></span> <span data-ttu-id="ef7a1-111">业务流程引擎不允许跟踪某些形状。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-111">The Orchestration engine does not allow tracking for some shapes.</span></span> <span data-ttu-id="ef7a1-112">它们分别是：</span><span class="sxs-lookup"><span data-stu-id="ef7a1-112">They are:</span></span>  
  
- <span data-ttu-id="ef7a1-113">消息赋值</span><span class="sxs-lookup"><span data-stu-id="ef7a1-113">Message Assignment</span></span>  
  
- <span data-ttu-id="ef7a1-114">转换</span><span class="sxs-lookup"><span data-stu-id="ef7a1-114">Transform</span></span>  
  
- <span data-ttu-id="ef7a1-115">组（任务）</span><span class="sxs-lookup"><span data-stu-id="ef7a1-115">Group (Task)</span></span>  
  
- <span data-ttu-id="ef7a1-116">挂起</span><span class="sxs-lookup"><span data-stu-id="ef7a1-116">Suspend</span></span>  
  
- <span data-ttu-id="ef7a1-117">循环 (While)</span><span class="sxs-lookup"><span data-stu-id="ef7a1-117">Loop (While)</span></span>  
  
- <span data-ttu-id="ef7a1-118">Branch</span><span class="sxs-lookup"><span data-stu-id="ef7a1-118">Branch</span></span>  
  
- <span data-ttu-id="ef7a1-119">Terminate</span><span class="sxs-lookup"><span data-stu-id="ef7a1-119">Terminate</span></span>  
  
- <span data-ttu-id="ef7a1-120">引发</span><span class="sxs-lookup"><span data-stu-id="ef7a1-120">Throw</span></span>  
  
- <span data-ttu-id="ef7a1-121">捕获</span><span class="sxs-lookup"><span data-stu-id="ef7a1-121">Catch</span></span>  
  
- <span data-ttu-id="ef7a1-122">循环形状</span><span class="sxs-lookup"><span data-stu-id="ef7a1-122">While shape</span></span>  
  
  <span data-ttu-id="ef7a1-123">当映射到业务活动时，请按照以下准则执行操作，以便跟踪配置文件编辑器和其他 BAM 工具可以使用它们：</span><span class="sxs-lookup"><span data-stu-id="ef7a1-123">Use the following guidelines when mapping to business activities so that the Tracking Profile Editor and other BAM tools can use them:</span></span>  
  
- <span data-ttu-id="ef7a1-124">对于组形状，请使用非事务性作用域形状。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-124">For the Group shape, use a non-transactional Scope shape.</span></span>  
  
- <span data-ttu-id="ef7a1-125">对于循环形状，请将它包装到非事务性作用域形状中。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-125">For the While shape, wrap it in a non-transactional Scope shape.</span></span>  
  
- <span data-ttu-id="ef7a1-126">对于终止形状，没有任何解决办法，因为在正常情况下，此形状的结束事件从不发生。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-126">For the Terminate shapes, there is no workaround, because the end event of this shape never occurs in a normal scenario.</span></span>  
  
- <span data-ttu-id="ef7a1-127">在计划的开始或结束时，不要使用不允许执行拖放操作的任何形状。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-127">Do not start or end schedules with any of the shapes for which drag-and-drop operations are not permitted.</span></span>  
  
## <a name="applying-tracking-profiles-that-monitor-running-processes"></a><span data-ttu-id="ef7a1-128">应用监视运行的进程的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ef7a1-128">Applying Tracking Profiles that Monitor Running Processes</span></span>  
 <span data-ttu-id="ef7a1-129">如果活动中包含 BAM 继续符，则更新跟踪配置文件可能会影响正在进行的活动实例。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-129">Updating a tracking profile can impact activity instances in progress if the activity includes a BAM continuation.</span></span> <span data-ttu-id="ef7a1-130">具体而言，如果在更新跟踪配置文件时指定在下游对已记录的某个活动项进行数据侦听，则原始值可能会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-130">Specifically, if the update to the tracking profile specifies a downstream interception of data for an activity item already recorded, it is possible that the original value will be overwritten.</span></span> <span data-ttu-id="ef7a1-131">从本质而言，任何单个事件流将不会受跟踪配置文件更新的应用程序的影响，因为每个流对象是与活动/流开始时处于就绪状态的特定版本的配置文件相联系。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-131">In essence, any single event stream will not be affected by the application of tracking profile updates because each stream object is tied to the specific version of the profile which was in place at the time the activity/stream started.</span></span> <span data-ttu-id="ef7a1-132">但是，使用继续符就意味着将多个事件流相关联，在更新配置文件时还尚未开始的流将提取更新中所做的更改，从而导致上述可能出现的覆盖数据的情况。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-132">However, because continuations are the means of correlating multiple event streams, streams not yet begun at the time of a profile update will pick up the changes in the update, thus introducing the possible data overwrite described.</span></span> <span data-ttu-id="ef7a1-133">有关继续符的详细信息，请参阅[活动继续符](../core/activity-continuation.md)并[如何创建一个继续符](../core/how-to-create-a-continuation.md)。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-133">For more information about continuations, see [Activity Continuation](../core/activity-continuation.md) and [How to Create a Continuation](../core/how-to-create-a-continuation.md).</span></span>  
  
## <a name="tracking-profiles-without-a-send-or-receive-shape-from-which-to-draw-message-properties"></a><span data-ttu-id="ef7a1-134">不具有从中提取消息属性的发送形状或接收形状的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ef7a1-134">Tracking Profiles Without a Send or Receive Shape from Which to Draw Message Properties</span></span>  
 <span data-ttu-id="ef7a1-135">继续符通过在多个活动中具有相同值的上下文属性或负载数据来跟踪活动。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-135">Continuations track activities through context properties or payload data that are the same between activities.</span></span> <span data-ttu-id="ef7a1-136">有些属性在各个活动中的值是不同的，例如消息 ID、服务 ID 和实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-136">Properties such as Message ID, Service ID, and Instance ID change value between activities.</span></span>  
  
 <span data-ttu-id="ef7a1-137">您可以使用以下方法创建跟踪配置文件来处理此情况：</span><span class="sxs-lookup"><span data-stu-id="ef7a1-137">You can create tracking profiles to handle this scenario by using the following methods:</span></span>  
  
-   <span data-ttu-id="ef7a1-138">如果业务流程通过动态绑定向另一个业务流程发送消息，则继续符可以使用全局唯一负载数据。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-138">If an orchestration sends a message through a dynamic binding to another orchestration, then a globally unique payload data value can be used for the continuation.</span></span>  
  
-   <span data-ttu-id="ef7a1-139">如果消息中没有任何唯一负载数据，则可以使用消息的交换 ID。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-139">If there is no unique payload data in the message, then the interchange ID of the message can be used.</span></span> <span data-ttu-id="ef7a1-140">要使用交换 ID，您必须在同一接收形状上跟踪它。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-140">To use the interchange ID, you must track it on the same Receive shape.</span></span> <span data-ttu-id="ef7a1-141">如果您创建了新消息，则无法使用交换 ID，因为创建新消息时，交换 ID 即发生了更改。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-141">You cannot use the interchange ID if you create a new message, as the interchange ID changes when the new message is created.</span></span> <span data-ttu-id="ef7a1-142">从接收形状或发送形状之外的任何形状跟踪交换 ID 都是不可靠的。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-142">Tracking the interchange ID from any shape other than a Receive or Send shape is not reliable.</span></span>  
  
-   <span data-ttu-id="ef7a1-143">只要业务流程中使用的是从管道接收的消息（也就是说，业务流程端口绑定到一个管道，且从该位置跟踪接收形状和消息 ID），则您也可以使用消息 ID。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-143">You can also use message ID as long as the exact same message that is received from the pipeline is used in the orchestration, that is, the orchestration port is bound to a pipeline and a Receive shape and the message ID are tracked from that location.</span></span> <span data-ttu-id="ef7a1-144">如果您从其他形状跟踪消息 ID，则将无法在继续符中使用消息 ID。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-144">If you track the message ID from a different shape, then the message ID will be invalid for use in continuations.</span></span>  
  
-   <span data-ttu-id="ef7a1-145">如果业务流程调用另一个业务流程和未传递任何消息，或业务流程调用另一个业务流程，但被调用方不具有任何构造、 接收或发送形状，可以检索负载数据值，则用户可以使用实例 id。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-145">If an orchestration calls another orchestration and no message is passed, or an orchestration calls another orchestration but the callee does not have any Construct, Receive, or Send shape where payload data values can be retrieved, the user can use the instance ID.</span></span> <span data-ttu-id="ef7a1-146">调用的业务流程的实例 ID 不会更改。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-146">The instance ID for the called orchestrations does not change.</span></span>  
  
-   <span data-ttu-id="ef7a1-147">如果业务流程通过执行调用来加载另一个业务流程，而没有直接调用它，则无法使用任何静态消息属性来跟踪活动。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-147">If the orchestration loads another orchestration through an execution call rather than calling it directly, then there is no way to use any static message properties to track the activity.</span></span> <span data-ttu-id="ef7a1-148">用户无法启用继续符。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-148">The user cannot enable a continuation.</span></span> <span data-ttu-id="ef7a1-149">在这种情况下，只有当消息通过包含对其执行跟踪的唯一负载数据的管道来传递时，才能执行跟踪。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-149">The only way to perform tracking in this instance is if a message is passed through the pipeline that contains unique payload data on which to perform the tracking.</span></span>  
  
## <a name="you-cannot-use-a-session-id-as-a-continuation-token-for-pass-through-pipelines"></a><span data-ttu-id="ef7a1-150">您无法将会话 ID 用作直通管道的继续符</span><span class="sxs-lookup"><span data-stu-id="ef7a1-150">You Cannot Use a Session ID as a Continuation Token for Pass-Through Pipelines</span></span>  
 <span data-ttu-id="ef7a1-151">在跟踪配置文件中，当您从某个消息负载中选择项时，跟踪配置文件将绑定到该消息的架构。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-151">In a tracking profile, when you select items from a message payload, the tracking profile is bound to the schema of that message.</span></span> <span data-ttu-id="ef7a1-152">在直通管道中，架构名称值是空值。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-152">In a pass-through pipeline, the schema name value is a null value.</span></span> <span data-ttu-id="ef7a1-153">当 BAM 尝试按端口名和架构名来加载配置时，它将找不到与会话 ID 架构相匹配的项，而且引擎将不跟踪任何数据。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-153">When BAM attempts to load the configuration by port name and schema name it cannot make the match to the session ID schema and no data is tracked by the engine.</span></span>  
  
 <span data-ttu-id="ef7a1-154">对于直通管道，您可以从跟踪配置文件中删除所有负载跟踪；或者，如果您确实需要跟踪负载数据，则可以使用 XML 管道。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-154">For pass-through pipelines, you can either remove all payload tracking from the tracking profile or use XML pipelines if you do need to track the payload data.</span></span>  
  
## <a name="using-unique-port-names"></a><span data-ttu-id="ef7a1-155">使用唯一端口名</span><span class="sxs-lookup"><span data-stu-id="ef7a1-155">Using Unique Port Names</span></span>  
 <span data-ttu-id="ef7a1-156">当枚举双向端口时，TPE 将它们显示为两个逻辑端口，即一个发送端口和一个接收端口。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-156">When enumerating two-way ports, the TPE displays them as two logical ports, a send and a receive port.</span></span> <span data-ttu-id="ef7a1-157">两个逻辑端口的显示名称相同。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-157">Each of these logical ports is displayed with the same name.</span></span> <span data-ttu-id="ef7a1-158">您可以使用 BizTalk Server 创建具有相同名称的单向端口和双向端口。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-158">BizTalk Server allows you to create one-way and two-way ports with the same name.</span></span> <span data-ttu-id="ef7a1-159">例如，您可以创建一个名为“Port1”的双向端口，然后创建一个具有相同名称的接收端口。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-159">For example, you can create a two-way port named "Port1" and then create a receive port with the same name.</span></span> <span data-ttu-id="ef7a1-160">在这些情况下，TPE 显示接收端口一次，显示双向端口两次，一次显示为接收端口，一次显示为发送端口。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-160">In these cases the TPE displays the receive port once and the two-way port twice, once as a receive port and once as a send port.</span></span>  
  
 <span data-ttu-id="ef7a1-161">在这种情况下，TPE 将对两个接收端口都应用跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-161">TPE will apply tracking profiles to both receive ports in this case.</span></span> <span data-ttu-id="ef7a1-162">我们建议为端口指定唯一名称，以帮助正确标识它们。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-162">We recommend that ports be given unique names to help identify them properly.</span></span>  
  
## <a name="using-tpe-orchestrations-with-a-parallel-shape-as-the-first-shape"></a><span data-ttu-id="ef7a1-163">使用第一个形状为并行形状的 TPE 业务流程</span><span class="sxs-lookup"><span data-stu-id="ef7a1-163">Using TPE Orchestrations with a Parallel Shape as the First Shape</span></span>  
 <span data-ttu-id="ef7a1-164">如果业务流程以分叉、并行或侦听形状开始，则您将无法在其中一个分支上映射活动 ID。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-164">If you begin an orchestration with a Fork, Parallel, or Listen shape, you cannot map an activity ID on one of the branches.</span></span> <span data-ttu-id="ef7a1-165">在并行处理的情况下，您可以在分叉形状上映射 ActivityID。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-165">In cases of parallel processing you can map the ActivityID above the Fork shape.</span></span> <span data-ttu-id="ef7a1-166">您也可以让 BAM 生成活动 ID，以避免并行形状出现在业务流程的顶部。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-166">You can also let BAM generate the activity ID to avoid the issue of a parallel shape at the top of the orchestration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ef7a1-167">如果将一个活动映射到多个路径，且将 ActivityID 映射到分叉形状的一个路径，则当沿着未映射 ActivityID 的路径进行处理时，将导致错误。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-167">Mapping an activity to more than one path and also mapping the ActivityID to one path of the Fork shape causes an error when processing follows the path on which the ActivityID is not mapped.</span></span>  
  
## <a name="availability-of-message-properties-at-design-time"></a><span data-ttu-id="ef7a1-168">消息属性在设计时的可用性</span><span class="sxs-lookup"><span data-stu-id="ef7a1-168">Availability of Message Properties at Design Time</span></span>  
 <span data-ttu-id="ef7a1-169">创建跟踪配置文件时，并非所有消息属性都是可用的。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-169">When creating tracking profiles, not all message properties are available.</span></span> <span data-ttu-id="ef7a1-170">当从其映射消息属性的形状位于业务流程顶部时，最有可能遇到这个问题。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-170">This is most likely to be encountered when the shape where the message properties are mapped from is at the top of an orchestration.</span></span> <span data-ttu-id="ef7a1-171">在这些情况下，消息属性的值为空。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-171">In these instances, the value of the message properties is null.</span></span>  
  
 <span data-ttu-id="ef7a1-172">例如，当侦听形状是业务流程中的第一个形状。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-172">An example of this is where the Listen shape is the first shape in an orchestration.</span></span> <span data-ttu-id="ef7a1-173">当消息属性被映射中的此形状，仅以下属性具有值： InstanceID、 ServiceID 和 ServiceClassID。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-173">When message properties are mapped from this shape, only the following properties have values: InstanceID, ServiceID and ServiceClassID.</span></span> <span data-ttu-id="ef7a1-174">（此时，消息 ID 不在作用域中，它具有空值。）</span><span class="sxs-lookup"><span data-stu-id="ef7a1-174">(MessageID is not in scope at this point and has a null value.)</span></span>  
  
## <a name="you-cannot-map-shapes-inside-a-loop-shape-to-report-a-milestone"></a><span data-ttu-id="ef7a1-175">您无法映射循环形状内部的形状来报告里程碑</span><span class="sxs-lookup"><span data-stu-id="ef7a1-175">You Cannot Map Shapes Inside a Loop Shape to Report a Milestone</span></span>  
 <span data-ttu-id="ef7a1-176">TPE 将阻止从循环形状中包含的源映射到循环外的项的活动。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-176">The TPE blocks mapping sources contained from within a Loop shape to activities that are mapped to items that are outside of the loop.</span></span>  
  
 <span data-ttu-id="ef7a1-177">循环活动是指在业务流程内循环（即重复）的操作。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-177">Looping activities refers to actions that loop, or repeat, within an orchestration.</span></span> <span data-ttu-id="ef7a1-178">可以从在业务流程内循环的操作中捕获事件。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-178">It is possible to capture the events from actions that loop within an orchestration.</span></span> <span data-ttu-id="ef7a1-179">为此，需要创建另一个活动，并映射该循环内的所有新活动里程碑和数据。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-179">To do this, you create another activity and map all of the new activity milestones and data inside the loop.</span></span> <span data-ttu-id="ef7a1-180">这样做是有必要的，因为在循环中数据处理在每次计划的执行中将发生多次。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-180">This is necessary because the data processing in the loop will occur more than once per scheduled execution.</span></span>  
  
 <span data-ttu-id="ef7a1-181">例如，如果您有包含在循环中处理的多个行项的采购订单，问题，如"哪些采购订单的货物价格为 $100？"</span><span class="sxs-lookup"><span data-stu-id="ef7a1-181">For example, if you have a purchase order with multiple line items that process in a loop, questions like “Which purchase orders have item prices of $100?"</span></span> <span data-ttu-id="ef7a1-182">是不明确。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-182">are ambiguous.</span></span> <span data-ttu-id="ef7a1-183">下面的问题则含义明确：</span><span class="sxs-lookup"><span data-stu-id="ef7a1-183">Unambiguous questions are:</span></span>  
  
 <span data-ttu-id="ef7a1-184">哪些采购订单包含价格为 $100 的货物行？</span><span class="sxs-lookup"><span data-stu-id="ef7a1-184">Which purchase orders have line items with a price of $100?</span></span>  
  
 <span data-ttu-id="ef7a1-185">哪些采购订单的货物的总计/最小/最大价格为 $100？</span><span class="sxs-lookup"><span data-stu-id="ef7a1-185">Which purchase orders have Total/Min/Max item prices of $100?</span></span>  
  
 <span data-ttu-id="ef7a1-186">要提出含义明确的问题，则需要将货物行同采购订单分开考虑。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-186">Creating unambiguous questions requires thinking of the line items as something separate from the purchase order.</span></span> <span data-ttu-id="ef7a1-187">在跟踪配置文件编辑器中，根活动（例如，采购订单）映射到循环外的所有操作。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-187">In the Tracking Profile Editor, the root activity (for example, a purchase order) maps to all actions outside the loop.</span></span> <span data-ttu-id="ef7a1-188">子活动（例如，货物行）映射到循环内的操作。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-188">The child activity (for example, a line item) maps to the actions inside the loop.</span></span>  
  
 <span data-ttu-id="ef7a1-189">使用这些类型的构造的通常方法是分解重复的循环，然后使相关活动基于与外部活动相关的内部活动。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-189">The typical approach to working with these types of constructs is to decompose the repeating loop and to have a related activity based on the inner activity that is related to the outer activity.</span></span>  
  
 <span data-ttu-id="ef7a1-190">您需要将一个负载项用作根活动的活动 ID，并使此负载项在循环内的某些消息中可用。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-190">You need to use a payload item as the ActivityID for the root activity and have this payload item available in some of the messages inside the loop.</span></span> <span data-ttu-id="ef7a1-191">还需要将该活动映射到子活动下的关系节点，并将它命名为根活动。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-191">Map the activity to the relationship node that displays under the child activity and name it as the root activity.</span></span>  
  
## <a name="tracking-profiles-spanning-multiple-applications"></a><span data-ttu-id="ef7a1-192">跨多个应用程序的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ef7a1-192">Tracking Profiles Spanning Multiple Applications</span></span>  
 <span data-ttu-id="ef7a1-193">如果跟踪配置文件横跨多个应用程序，则必须在解决方案中的所有应用程序均部署完毕后再部署该跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-193">If a tracking profile spans multiple applications, the tracking profile must be deployed after all applications in the solution are deployed.</span></span> <span data-ttu-id="ef7a1-194">如果跟踪配置文件不是部署的最后一项，将收到以下消息"**找不到映射源。**"，在部署向导调用 BTTDeploy.exe 时。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-194">If the tracking profile is not the last item deployed, you will receive the following message, "**Mapping source not found.**", when the deployment wizard calls BTTDeploy.exe.</span></span>  
  
## <a name="mapping-multiple-biztalk-server-artifacts-to-a-document-reference-url-or-messageid-nodes"></a><span data-ttu-id="ef7a1-195">将多个 BizTalk Server 项目映射到一个文档引用 URL 或消息 ID 节点</span><span class="sxs-lookup"><span data-stu-id="ef7a1-195">Mapping Multiple BizTalk Server Artifacts to a Document Reference URL or MessageID Nodes</span></span>  
 <span data-ttu-id="ef7a1-196">您可以使用 TPE 将多个 BizTalk Server 项目拖放到同一文档引用 URL 或消息 ID 节点。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-196">The TPE allows you to drag and drop from multiple BizTalk Server artifacts onto the same document reference URL or MessageID node.</span></span>  
  
 <span data-ttu-id="ef7a1-197">在多个源映射到 BAM 活动中的同一个项时，在 BAM 处理过程中遇到的最后一个项目为跟踪数据中保留的项目，并可以在 BAM 门户中进行查看。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-197">In cases where multiple sources are mapped to the same item in a BAM activity, the last artifact that was encountered during BAM processing is the one that persists in the tracking data and can be viewed in the BAM portal.</span></span>  
  
## <a name="updating-btt-versions-to-match-biztalk-solution-versions"></a><span data-ttu-id="ef7a1-198">更新 BTT 版本以与 BizTalk 解决方案版本相匹配</span><span class="sxs-lookup"><span data-stu-id="ef7a1-198">Updating BTT Versions to Match BizTalk Solution Versions</span></span>  
 <span data-ttu-id="ef7a1-199">通过将 BTT 文件的更新自动化，BAM 开发人员和管理员可以保持跟踪配置文件与 BizTalk 解决方案之间的版本同步。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-199">BAM developers and administrators can maintain version synchronization between tracking profiles and BizTalk solutions by automating the update to the BTT file.</span></span> <span data-ttu-id="ef7a1-200">若要执行此操作，修改**版本**属性中**DataLevel** BTT 文件的元素。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-200">To do this, modify the **Version** attribute in the **DataLevel** element of the BTT file.</span></span> <span data-ttu-id="ef7a1-201">在下面的元素示例中，您将修改 TargetAssemblyName 和 SchemaName 属性中的版本信息。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-201">In the following sample element, you would modify the version information in the TargetAssemblyName and SchemaName attributes.</span></span>  
  
```  
<DataLevel Name="City" SourceTypeSelected="Messaging Payload" TargetAssemblyName="TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SchemaName="TheImplementationOfOrderMgmt.PurchaseOrder,TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SomXPath="/*[local-name()='<Schema>' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" XPath="/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" IsBeginActivity="true" IsEndActivity="false">  
```  
  
## <a name="some-orchestration-shapes-cannot-be-tracked-in-the-tpe"></a><span data-ttu-id="ef7a1-202">在 TPE 中无法跟踪某些业务流程形状</span><span class="sxs-lookup"><span data-stu-id="ef7a1-202">Some Orchestration Shapes Cannot be Tracked in the TPE</span></span>  
 <span data-ttu-id="ef7a1-203">业务流程引擎不生成以下形状的事件，因此无法在 TPE 中跟踪或映射这些形状：</span><span class="sxs-lookup"><span data-stu-id="ef7a1-203">The orchestration ongine does not generate events for the following shapes and thus these shapes cannot be tracked or mapped in the TPE:</span></span>  
  
-   <span data-ttu-id="ef7a1-204">任务</span><span class="sxs-lookup"><span data-stu-id="ef7a1-204">Task</span></span>  
  
-   <span data-ttu-id="ef7a1-205">全部分支</span><span class="sxs-lookup"><span data-stu-id="ef7a1-205">All Branches</span></span>  
  
-   <span data-ttu-id="ef7a1-206">挂起</span><span class="sxs-lookup"><span data-stu-id="ef7a1-206">Suspend</span></span>  
  
-   <span data-ttu-id="ef7a1-207">Terminate</span><span class="sxs-lookup"><span data-stu-id="ef7a1-207">Terminate</span></span>  
  
-   <span data-ttu-id="ef7a1-208">引发</span><span class="sxs-lookup"><span data-stu-id="ef7a1-208">Throw</span></span>  
  
-   <span data-ttu-id="ef7a1-209">捕获</span><span class="sxs-lookup"><span data-stu-id="ef7a1-209">Catch</span></span>  
  
-   <span data-ttu-id="ef7a1-210">消息赋值（因为它是构造形状的一部分）</span><span class="sxs-lookup"><span data-stu-id="ef7a1-210">MessageAssignment (because it is part of the Construct shape)</span></span>  
  
-   <span data-ttu-id="ef7a1-211">转换（因为它是构造形状的一部分）</span><span class="sxs-lookup"><span data-stu-id="ef7a1-211">Transform (because it is part of the Construct shape)</span></span>  
  
-   <span data-ttu-id="ef7a1-212">循环</span><span class="sxs-lookup"><span data-stu-id="ef7a1-212">Loop</span></span>  
  
## <a name="tpe-not-retrieving-deployed-tracking-profiles"></a><span data-ttu-id="ef7a1-213">TPE 不检索已部署的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ef7a1-213">TPE Not Retrieving Deployed Tracking Profiles</span></span>  
 <span data-ttu-id="ef7a1-214">在升级或重新部署之后，您可能会在检索已部署的跟踪配置文件时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-214">After an upgrade or redeployment you may experience difficulties in retrieving deployed tracking profiles.</span></span> <span data-ttu-id="ef7a1-215">这可能是因为 BizTalkMgmtDb 数据库所在服务器的名称在注册表中的存储方式不匹配。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-215">This can be caused by a mismatch in the manner in which the server name on which BizTalkMgmtDb database is stored in the registry.</span></span>  
  
 <span data-ttu-id="ef7a1-216">BizTalkMgmtDb 在组配置期间写入注册表。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-216">The BizTalkMgmtDb is written to the registry during Group configuration.</span></span> <span data-ttu-id="ef7a1-217">TPE 使用此注册表项查找主导入数据库和筛选跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-217">The TPE uses the entry to find the Primary Import database and to filter the tracking profiles.</span></span>  
  
 <span data-ttu-id="ef7a1-218">在配置期间，可以用多种格式输入服务器名称。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-218">During configuration it is possible to enter the server name in several formats.</span></span> <span data-ttu-id="ef7a1-219">例如：</span><span class="sxs-lookup"><span data-stu-id="ef7a1-219">For example:</span></span>  
  
- <span data-ttu-id="ef7a1-220">mgmtsvr1316267,15001\inst</span><span class="sxs-lookup"><span data-stu-id="ef7a1-220">mgmtsvr1316267,15001\inst</span></span>  
  
- <span data-ttu-id="ef7a1-221">MGMTSVR1316267\inst,15001</span><span class="sxs-lookup"><span data-stu-id="ef7a1-221">MGMTSVR1316267\inst,15001</span></span>  
  
  <span data-ttu-id="ef7a1-222">TPE 在使用注册表项时会执行简单的字符串比较。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-222">The TPE performs a basic string comparison when using the registry entry.</span></span> <span data-ttu-id="ef7a1-223">若要检索已部署的跟踪配置文件是检查存储的服务器和数据库名称和输入在 TPE 中所需**设置管理数据库**对话框。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-223">To retrieve the deployed tracking profiles it is necessary to inspect the stored server and database names and enter them in the TPE **Set Management Database** dialog box.</span></span>  
  
#### <a name="to-determine-the-syntax-for-server-and-database-names-and-enter-it-in-the-biztalk-management-database"></a><span data-ttu-id="ef7a1-224">确定服务器和数据库名称的语法，并将其输入到 BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-224">To determine the syntax for server and database names and enter it in the BizTalk Management database.</span></span>  
  
1. <span data-ttu-id="ef7a1-225">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**自定义配置管理器**。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-225">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**Custom Configuration Manager**.</span></span> <span data-ttu-id="ef7a1-226">有关使用信息**自定义配置管理器**，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-226">For information about using the **Custom Configuration Manager**, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>  
  
2. <span data-ttu-id="ef7a1-227">在导航窗格中，选择**组**打开组配置页。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-227">In the navigation pane, select **Group** to open the group configuration page.</span></span>  
  
3. <span data-ttu-id="ef7a1-228">在中**数据存储**网格中，观察到的格式**服务器名称**并**数据库名称**。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-228">In the **Data Stores** grid, observe the formats of the **Server Name** and the **Database Name**.</span></span>  
  
4. <span data-ttu-id="ef7a1-229">打开 TPE，然后选择**工具**菜单项。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-229">Open the TPE and select the **Tools** menu item.</span></span>  
  
5. <span data-ttu-id="ef7a1-230">选择**设置管理数据库**菜单项以打开**设置管理数据库**对话框。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-230">Select the **Set Management Database** menu item to open the **Set Management Database** dialog box.</span></span>  
  
6. <span data-ttu-id="ef7a1-231">中**SQL Server**文字框中，输入中使用的服务器名称**服务器名称**字段**数据存储**gridon**自定义配置管理器**组页。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-231">In the **SQL Server** text box, enter the server name that was used in the **Server Name** field of the **Data Stores** gridon the **Custom Configuration Manager** group page.</span></span>  
  
7. <span data-ttu-id="ef7a1-232">中**数据库名称**文字框中，输入数据库名称中使用过**数据库名称**字段**数据存储**gridon**自定义配置管理器**组页。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-232">In the **Database name** text box, enter the database name that was used in the **Database Name** field of the **Data Stores** gridon the **Custom Configuration Manager** group page.</span></span>  
  
8. <span data-ttu-id="ef7a1-233">单击**确定**按钮以保存这些条目。</span><span class="sxs-lookup"><span data-stu-id="ef7a1-233">Click the **OK** button to save the entries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7a1-234">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef7a1-234">See Also</span></span>  
 <span data-ttu-id="ef7a1-235">[使用 TPE](../core/using-the-tpe.md) </span><span class="sxs-lookup"><span data-stu-id="ef7a1-235">[Using the TPE](../core/using-the-tpe.md) </span></span>  
 [<span data-ttu-id="ef7a1-236">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="ef7a1-236">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)