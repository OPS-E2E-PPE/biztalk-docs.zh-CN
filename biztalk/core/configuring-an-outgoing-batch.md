---
title: 配置传出批 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75e6f41a-0e24-47bf-9234-125791c62044
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0413da7cb3d3dc328abbfd6916dd598b174244ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391356"
---
# <a name="configuring-an-outgoing-batch"></a><span data-ttu-id="f2801-102">配置传出批</span><span class="sxs-lookup"><span data-stu-id="f2801-102">Configuring an Outgoing Batch</span></span>
<span data-ttu-id="f2801-103">若要定义的方式，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]事务集批处理成 EDI 交换，必须创建协议的一个或多个批处理配置。</span><span class="sxs-lookup"><span data-stu-id="f2801-103">To define the way that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] batches transaction sets into an EDI interchange, you must create one or more batch configurations for an agreement.</span></span> <span data-ttu-id="f2801-104">所有交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为该协议，并且将符合筛选条件。 将进行批处理并根据该批配置的发布条件发布批。</span><span class="sxs-lookup"><span data-stu-id="f2801-104">All interchanges that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] associates to that agreement and that meet the filter criteria for a batch will be batched and released according to the same release criteria for that batch configuration.</span></span>  
  
 <span data-ttu-id="f2801-105">批处理配置由批名称、 批 ID、 筛选器定义、 组定义、 批处理发布条件和批处理激活条件组成。</span><span class="sxs-lookup"><span data-stu-id="f2801-105">Batch configuration consists of a batch name, batch ID, filter definition, group definition, batch release criteria, and batch activation criteria.</span></span> <span data-ttu-id="f2801-106">所有属性和与批处理相关的选项都位于**批配置**页中的单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f2801-106">All properties and options related to batches are available on the **Batch Configuration** page of the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="f2801-107">若要创建协议的批配置，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="f2801-107">To create a batch configuration for an agreement, see [Configuring Batching (X12)](../core/configuring-batching-x12.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2801-108">标准批处理文档是已确定协议属性本身。</span><span class="sxs-lookup"><span data-stu-id="f2801-108">The document standard for the batch is ascertained from the agreement properties itself.</span></span> <span data-ttu-id="f2801-109">例如，如果协议适用于 X12 消息的文档标准批将为 X12。</span><span class="sxs-lookup"><span data-stu-id="f2801-109">For example, if the agreement is for X12 messages, the document standard for the batches will be X12.</span></span>  
  
## <a name="batch-categories"></a><span data-ttu-id="f2801-110">批处理类别</span><span class="sxs-lookup"><span data-stu-id="f2801-110">Batch Categories</span></span>  
 <span data-ttu-id="f2801-111">使用上的右上角的下拉列表**批配置**页，确定显示哪个批配置。</span><span class="sxs-lookup"><span data-stu-id="f2801-111">Use the drop-down list on the top-right corner of the **Batch Configuration** page to determine which batch configurations are displayed.</span></span>  
  
-   <span data-ttu-id="f2801-112">**全部**：显示所有批处理配置。</span><span class="sxs-lookup"><span data-stu-id="f2801-112">**All**: Display all batch configurations.</span></span>  
  
-   <span data-ttu-id="f2801-113">**活动**：显示仅活动批配置。</span><span class="sxs-lookup"><span data-stu-id="f2801-113">**Active**: Display only the active batch configurations.</span></span>  
  
-   <span data-ttu-id="f2801-114">**非活动**:显示仅的不活动的批配置。</span><span class="sxs-lookup"><span data-stu-id="f2801-114">**Inactive**: Display only the inactive batch configurations.</span></span>  
  
## <a name="batch-identification"></a><span data-ttu-id="f2801-115">批处理标识</span><span class="sxs-lookup"><span data-stu-id="f2801-115">Batch Identification</span></span>  
 <span data-ttu-id="f2801-116">批处理标识包含批名称、 说明、 批处理 ID 和批处理业务流程实例 id。</span><span class="sxs-lookup"><span data-stu-id="f2801-116">Batch identification contains batch name, description, batch ID, and the batching orchestration instance ID.</span></span>  
  
### <a name="batch-name"></a><span data-ttu-id="f2801-117">批处理名称</span><span class="sxs-lookup"><span data-stu-id="f2801-117">Batch Name</span></span>  
 <span data-ttu-id="f2801-118">根据中指定的批处理名称创建批配置**批配置**页中的单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f2801-118">A batch configuration is created based on the batch name specified in **Batch Configuration** page of the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="f2801-119">多个批处理可以共享相同的配置设置，但必须具有唯一的批处理的名称。</span><span class="sxs-lookup"><span data-stu-id="f2801-119">Multiple batches can share the same configuration settings, but must have a unique batch name.</span></span>  
  
### <a name="batch-description"></a><span data-ttu-id="f2801-120">批说明</span><span class="sxs-lookup"><span data-stu-id="f2801-120">Batch Description</span></span>  
 <span data-ttu-id="f2801-121">批处理说明文本框中提供的批处理配置的说明。</span><span class="sxs-lookup"><span data-stu-id="f2801-121">Batch description text box provides a description of the batch configuration.</span></span>  
  
### <a name="batch-id"></a><span data-ttu-id="f2801-122">批次 ID</span><span class="sxs-lookup"><span data-stu-id="f2801-122">Batch ID</span></span>  
 <span data-ttu-id="f2801-123">自动生成的批处理 ID[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中创建新的批配置时**批配置**页。</span><span class="sxs-lookup"><span data-stu-id="f2801-123">The batch ID is generated automatically by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when a new batch configuration is created in the **Batch Configuration** page.</span></span> <span data-ttu-id="f2801-124">BatchMarker 管道组件使用此值来标记特定的批处理配置的批处理筛选器匹配的传入的交换。</span><span class="sxs-lookup"><span data-stu-id="f2801-124">This value is used by the BatchMarker pipeline component to flag incoming interchanges that match the batch filter of a specific batch configuration.</span></span> <span data-ttu-id="f2801-125">此值还用作批处理业务流程与特定的批处理配置关联的订阅筛选器。</span><span class="sxs-lookup"><span data-stu-id="f2801-125">This value is also used as a subscription filter of the batching orchestration associated with a specific batch configuration.</span></span>  
  
### <a name="orchestration-instance-id"></a><span data-ttu-id="f2801-126">业务流程实例 ID</span><span class="sxs-lookup"><span data-stu-id="f2801-126">Orchestration Instance ID</span></span>  
 <span data-ttu-id="f2801-127">为此批处理配置激活批处理业务流程实例的业务流程实例 ID。</span><span class="sxs-lookup"><span data-stu-id="f2801-127">The orchestration instance ID of the batch orchestration instance that is activated for this batch configuration.</span></span>  
  
## <a name="batch-filter"></a><span data-ttu-id="f2801-128">批处理筛选器</span><span class="sxs-lookup"><span data-stu-id="f2801-128">Batch Filter</span></span>  
 <span data-ttu-id="f2801-129">创建批处理时在应用中的批处理筛选器定义的基础**批配置**页中的单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f2801-129">A batch is created based upon the batch filter definition applied in the **Batch Configuration** page of the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="f2801-130">在此筛选器，您可以确定哪些事务集或消息将进行批处理。</span><span class="sxs-lookup"><span data-stu-id="f2801-130">In this filter, you determine which transaction sets or messages will be batched.</span></span> <span data-ttu-id="f2801-131">在激活批处理业务流程实例，您可以更改此筛选器的值。</span><span class="sxs-lookup"><span data-stu-id="f2801-131">You can change the value of this filter while an instance of the batch orchestration is activated.</span></span> <span data-ttu-id="f2801-132">更改筛选器不会影响批处理发布条件。</span><span class="sxs-lookup"><span data-stu-id="f2801-132">Changing the filter does not affect the batch release criteria.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2801-133">如果更改活动批的批筛选器，它将需要为新的筛选条件，因为此信息缓存由 Biztalk Server 变为活动状态 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="f2801-133">If you change the batch filter for an active batch, it will take 15 minutes for the new filter criteria to become active as this information is cached by Biztalk Server.</span></span> <span data-ttu-id="f2801-134">无法修改此刷新时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f2801-134">This refresh interval cannot be modified.</span></span>  
> 
>  <span data-ttu-id="f2801-135">若要强制立即处于活动状态的新筛选器，请重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机进程。</span><span class="sxs-lookup"><span data-stu-id="f2801-135">To force the new filter to become active immediately, restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host process.</span></span>  
  
 <span data-ttu-id="f2801-136">传出批处理可包含多个组，但每个事务类型只有一个组。</span><span class="sxs-lookup"><span data-stu-id="f2801-136">Outgoing batches can include multiple groups, but only one group per transaction type.</span></span> <span data-ttu-id="f2801-137">一个组可以包含多个事务集，但每个必须具有相同的事务类型。</span><span class="sxs-lookup"><span data-stu-id="f2801-137">A group can contain multiple transaction sets, but each must have the same transaction type.</span></span>  
  
 <span data-ttu-id="f2801-138">多个批处理配置可以共享同一个批处理筛选器，如果文档与多个批处理筛选器会将其路由到所有匹配的批处理相匹配。</span><span class="sxs-lookup"><span data-stu-id="f2801-138">Multiple batch configurations can share the same batch filter, if a document matches more than one batch filter it will be routed to all matching batches.</span></span>  
  
## <a name="group-definition"></a><span data-ttu-id="f2801-139">组定义</span><span class="sxs-lookup"><span data-stu-id="f2801-139">Group Definition</span></span>  
 <span data-ttu-id="f2801-140">您确定如何组将按照在 batch 输出通过定义功能组标头 (对于 X12 为 GS) 和 UNG edifact 协议属性中。</span><span class="sxs-lookup"><span data-stu-id="f2801-140">You determine how groups will be composed in the batch output by defining the Functional Group Headers (GS for X12 and UNG for EDIFACT) in the agreement properties.</span></span> <span data-ttu-id="f2801-141">组为 EDIFACT、 其版本和目标命名空间定义根据其事务集标识符 (ST1) 对于 X12 或消息类型 (UNH2.1)。</span><span class="sxs-lookup"><span data-stu-id="f2801-141">Groups are defined according to their Transaction Set Identifier (ST1) for X12 or the Message Type (UNH2.1) for EDIFACT, their version, and their target namespace.</span></span> <span data-ttu-id="f2801-142">例如，交换可包含一个组构成的一种消息类型，而第二个组组成的另一种消息类型。</span><span class="sxs-lookup"><span data-stu-id="f2801-142">For example, an interchange can contain one group composed of one message type, and a second group composed of another message type.</span></span> <span data-ttu-id="f2801-143">有关配置组的详细信息，请参阅[配置 EDI 属性](../core/configuring-edi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f2801-143">For more information on configuring groups, see [Configuring EDI Properties](../core/configuring-edi-properties.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2801-144">未定义交换中组的顺序。</span><span class="sxs-lookup"><span data-stu-id="f2801-144">The order of groups within an interchange is not defined.</span></span>  
  
## <a name="batch-release-criteria"></a><span data-ttu-id="f2801-145">批处理发布条件</span><span class="sxs-lookup"><span data-stu-id="f2801-145">Batch Release Criteria</span></span>  
 <span data-ttu-id="f2801-146">将根据在中设置的条件发布批处理**批配置**页中的单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f2801-146">Batches will be released according to criteria set in the **Batch Configuration** page of the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="f2801-147">可以在任何通过以下方式发布批处理：</span><span class="sxs-lookup"><span data-stu-id="f2801-147">Batches can be released in any of the following ways:</span></span>  
  
- <span data-ttu-id="f2801-148">根据计划，每小时、 每天或每周。</span><span class="sxs-lookup"><span data-stu-id="f2801-148">According to a schedule, on an hourly, daily, or weekly basis.</span></span>  
  
- <span data-ttu-id="f2801-149">特定数量的事务集时可用于一组。</span><span class="sxs-lookup"><span data-stu-id="f2801-149">When a specific number of transaction sets is available for a group.</span></span>  
  
- <span data-ttu-id="f2801-150">特定数量的事务集时可供交换。</span><span class="sxs-lookup"><span data-stu-id="f2801-150">When a specific number of transaction sets is available for an interchange.</span></span>  
  
- <span data-ttu-id="f2801-151">当特定数目的字符是可用于批处理。</span><span class="sxs-lookup"><span data-stu-id="f2801-151">When a specific number of characters is available for batch processing.</span></span>  
  
- <span data-ttu-id="f2801-152">到外部应用程序执行外部触发器时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f2801-152">When an external trigger is executed by an application external to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
  <span data-ttu-id="f2801-153">如果选择**发送空的批处理信号**上的属性**批处理计划**对话框中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]批处理计划即使没有消息已发送时将发送一个空的批处理消息由批处理业务流程接收。</span><span class="sxs-lookup"><span data-stu-id="f2801-153">If you select the **Send empty batch signal** property on the **Batch Schedule** dialog box, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will send an empty batch message when the batch is scheduled to be sent even if no messages have been received by the batching orchestration.</span></span>  
  
## <a name="batch-activation-criteria"></a><span data-ttu-id="f2801-154">批处理激活条件</span><span class="sxs-lookup"><span data-stu-id="f2801-154">Batch Activation Criteria</span></span>  
 <span data-ttu-id="f2801-155">仅当已满足批处理激活条件时，将根据批发布条件发布批处理。</span><span class="sxs-lookup"><span data-stu-id="f2801-155">Batches will be released according to the batch release criteria only when the batch activation criterion has been met.</span></span> <span data-ttu-id="f2801-156">若要激活业务流程的实例，必须按下**启动**按钮**批配置**中的单向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f2801-156">To activate an instance of the orchestration, you must press the **Start** button in the **Batch Configuration** page of the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="f2801-157">这将创建批配置的业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="f2801-157">This creates an instance of the orchestration for the batch configuration.</span></span> <span data-ttu-id="f2801-158">如果**启动**按钮可供单击，则当前尚未激活的批处理配置业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="f2801-158">If the **Start** button is available for clicking, an instance of the orchestration for the batch configuration is not currently activated.</span></span>  
  
 <span data-ttu-id="f2801-159">按后**启动**按钮，将为批处理收集消息，仅当满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="f2801-159">After you press the **Start** button, messages will be collected for a batch only if the following are true:</span></span>  
  
- <span data-ttu-id="f2801-160">消息符合批处理筛选器中的条件。</span><span class="sxs-lookup"><span data-stu-id="f2801-160">The messages meet the criteria in the batch filter.</span></span>  
  
- <span data-ttu-id="f2801-161">日期和时间是在输入中的日期时间后**启动**字段。</span><span class="sxs-lookup"><span data-stu-id="f2801-161">The date and time are after the datetime entered in the **Start** field.</span></span>  
  
- <span data-ttu-id="f2801-162">日期和时间之前中输入的值是**结束**字段中或处理的批数是小于或等于的中的出现次数**结束前的 （出现）** 字段或**无结束日期**选择选项。</span><span class="sxs-lookup"><span data-stu-id="f2801-162">The date and time are before the value entered in the **End by** field, or the numbers of batches processed is less than or equal to the number of occurrences in the **End after (occurrences)** field, or the **No end date** option is selected.</span></span> <span data-ttu-id="f2801-163">所有三个选项都位于**终止**部分。</span><span class="sxs-lookup"><span data-stu-id="f2801-163">All the three options are available under the **Termination** section.</span></span>  
  
  <span data-ttu-id="f2801-164">激活条件中设置**批配置**页中的单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f2801-164">The activation criteria are set in the **Batch Configuration** page of the one-way agreement tab in the **Agreement Properties** dialog box.</span></span>  
  
  <span data-ttu-id="f2801-165">已按下后**启动**按钮以激活批处理业务流程的实例，消息之前提到的时间不会为批处理收集**启动**属性传递。</span><span class="sxs-lookup"><span data-stu-id="f2801-165">After you have pressed the **Start** button to activate an instance of the batching orchestration, messages will not be collected for a batch until the time mentioned for the **Start** property has passed.</span></span>  <span data-ttu-id="f2801-166">在**批配置**页上，如果**立即启动**未选择并**启动**日期时间设置为之前在其中按的时间值**启动**按钮时，批处理将启动业务流程处于活动状态时。</span><span class="sxs-lookup"><span data-stu-id="f2801-166">In the **Batch Configuration** page, if **Start immediately** is not selected and the **Start** datetime is set to a value prior to the time at which you press the **Start** button, batching will start as soon as the orchestration is active.</span></span> <span data-ttu-id="f2801-167">如果激活日期时间在将来，在该时间将启动批处理。</span><span class="sxs-lookup"><span data-stu-id="f2801-167">If the activation datetime is in the future, batching will start at that time.</span></span>  
  
  <span data-ttu-id="f2801-168">可以设置**启动**是将来的日期时间的 datetime。</span><span class="sxs-lookup"><span data-stu-id="f2801-168">You can set the **Start** datetime to be a datetime in the future.</span></span> <span data-ttu-id="f2801-169">但是，如果单击**启动**按钮时**启动**日期时间是将来，将激活业务流程实例，但会收集任何消息，直到开始日期时间。</span><span class="sxs-lookup"><span data-stu-id="f2801-169">However, if you click the **Start** button when the **Start** datetime is in the future, the orchestration instance will be activated, but no messages will be collected until the start datetime occurs.</span></span> <span data-ttu-id="f2801-170">BatchMarker 管道组件不会升级将消息路由到路由业务流程或批处理业务流程的开始日期时间之前所需的相应属性。</span><span class="sxs-lookup"><span data-stu-id="f2801-170">The BatchMarker pipeline component will not promote the appropriate properties needed to route a message to the routing orchestration or the batching orchestration until the start datetime.</span></span> <span data-ttu-id="f2801-171">因此，消息将不进行批处理。</span><span class="sxs-lookup"><span data-stu-id="f2801-171">As a result, the message will not be batched.</span></span> <span data-ttu-id="f2801-172">但是，将会拾取消息的任何发送端口或业务流程是作为单条消息订阅。</span><span class="sxs-lookup"><span data-stu-id="f2801-172">However, the messages will be picked up by any send port or orchestration subscribing to them as individual messages.</span></span> <span data-ttu-id="f2801-173">BatchMarker 管道组件执行的详细信息，请参阅[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="f2801-173">For more information on what the BatchMarker pipeline component does, see [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
## <a name="batch-termination-criteria"></a><span data-ttu-id="f2801-174">批处理终止条件</span><span class="sxs-lookup"><span data-stu-id="f2801-174">Batch Termination Criteria</span></span>  
 <span data-ttu-id="f2801-175">消息将停止收集后一批**结束**日期时间或之后的中的出现次数**结束前的 （出现）** 属性。</span><span class="sxs-lookup"><span data-stu-id="f2801-175">Messages will cease to be collected for a batch after the **End by** datetime or after the number of occurrences in the **End after (occurrences)** property.</span></span> <span data-ttu-id="f2801-176">如果不希望将停用批处理业务流程，请选择**无结束日期**选项。</span><span class="sxs-lookup"><span data-stu-id="f2801-176">If you do not want the batching orchestration to be deactivated, select the **No end date** option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2801-177">如果**结束前的 （出现）** 选择属性，空的批处理信号计入结束该批处理激活范围所需的次数。</span><span class="sxs-lookup"><span data-stu-id="f2801-177">If the **End after (occurrences)** property has been selected, empty batch signals count toward the number of occurrences required to end the batch activation range.</span></span> <span data-ttu-id="f2801-178">如果通常会导致空的批处理信号的条件发生，也将递增的出现次数 （收到任何消息已由批处理业务流程计划发送批时），但因为没有任何空的批处理信号发送未配置该信号。</span><span class="sxs-lookup"><span data-stu-id="f2801-178">The number of occurrences will also be incremented if the conditions that would normally lead to an empty batch signal occur (no messages have been received by the batching orchestration when the batch is scheduled to be sent), but no empty batch signal is sent because the signal is not configured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2801-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2801-179">See Also</span></span>  
 [<span data-ttu-id="f2801-180">对传出 EDI 消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="f2801-180">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)