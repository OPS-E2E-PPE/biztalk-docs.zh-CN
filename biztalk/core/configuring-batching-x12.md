---
title: 配置批处理 (X12) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f4f9e7b-262d-488e-9a04-088aad289d70
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7912aad3610b7c05ddc0db37f6c7989be3bc04a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234773"
---
# <a name="configuring-batching-x12"></a><span data-ttu-id="58b72-102">配置批处理 (X12)</span><span class="sxs-lookup"><span data-stu-id="58b72-102">Configuring Batching (X12)</span></span>
<span data-ttu-id="58b72-103">批处理定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何生成 EDI 批处理并将其发送给参与方。</span><span class="sxs-lookup"><span data-stu-id="58b72-103">Batches define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates and sends an EDI batches to the party.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58b72-104">此处所述的设置同样适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="58b72-104">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58b72-105">所有属性都禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="58b72-105">All properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span> <span data-ttu-id="58b72-106">**新的批处理**此页面上的按钮被禁用。</span><span class="sxs-lookup"><span data-stu-id="58b72-106">The **New Batch** button is disabled on this page.</span></span>  
>   
>  <span data-ttu-id="58b72-107">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="58b72-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="58b72-108">例如，如果创建两个参与方 A 方和方 B 和 A 方，你清除该复选框，**新的批处理**上按钮被禁用**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="58b72-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the **New Batch** button is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58b72-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="58b72-109">Prerequisites</span></span>  
 <span data-ttu-id="58b72-110">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="58b72-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-batching-settings"></a><span data-ttu-id="58b72-111">配置批处理设置</span><span class="sxs-lookup"><span data-stu-id="58b72-111">To configure batching settings</span></span>  
  
1.  <span data-ttu-id="58b72-112">创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="58b72-112">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="58b72-113">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="58b72-113">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="58b72-114">单向协议选项卡上，在**交换设置**部分中，单击**批处理配置**。</span><span class="sxs-lookup"><span data-stu-id="58b72-114">On a one-way agreement tab, under **Interchange Settings** section, click **Batching Configuration**.</span></span>  
  
3.  <span data-ttu-id="58b72-115">从**批配置**页上，单击**新的批处理**若要创建新的批配置。</span><span class="sxs-lookup"><span data-stu-id="58b72-115">From the **Batch Configuration** page click **New Batch** to create a new batch configuration.</span></span> <span data-ttu-id="58b72-116">A **Batch1**添加选项卡。</span><span class="sxs-lookup"><span data-stu-id="58b72-116">A **Batch1** tab is added.</span></span>  
  
4.  <span data-ttu-id="58b72-117">在**标识**选项卡的部分执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="58b72-117">In the **Identification** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="58b72-118">输入**批处理**名称。</span><span class="sxs-lookup"><span data-stu-id="58b72-118">Enter the **Batch** name.</span></span> <span data-ttu-id="58b72-119">该值用作此批处理配置的选项卡标识符。</span><span class="sxs-lookup"><span data-stu-id="58b72-119">This value is used as the tab identifier for this batch configuration.</span></span>  
  
    2.  <span data-ttu-id="58b72-120">输入此批配置中的描述**批处理说明**。</span><span class="sxs-lookup"><span data-stu-id="58b72-120">Enter a description of this batch configuration in **Batch description**.</span></span>  
  
    3.  <span data-ttu-id="58b72-121">**批 ID**是只读的文本框应用批处理设置后显示唯一的批次 ID。</span><span class="sxs-lookup"><span data-stu-id="58b72-121">**Batch ID** is a read-only text box that displays a unique batch ID after you apply the settings for the batch.</span></span>  
  
    4.  <span data-ttu-id="58b72-122">**业务流程实例 ID**是只读的文本框显示与关联批处理的批处理 orchestration 实例 ID。</span><span class="sxs-lookup"><span data-stu-id="58b72-122">**Orchestration instance ID** is a read-only text box that displays the batching orchestration instance ID that the batch is associated with.</span></span> <span data-ttu-id="58b72-123">在批启动之后，显示业务流程实例 ID。</span><span class="sxs-lookup"><span data-stu-id="58b72-123">An orchestration instance ID is displayed after a batch is started.</span></span>  
  
5.  <span data-ttu-id="58b72-124">在**筛选器**选项卡的部分执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="58b72-124">In the **Filter** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="58b72-125">单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="58b72-125">Click **Filter**.</span></span>  
  
    2.  <span data-ttu-id="58b72-126">在**批处理筛选器**对话框框中，输入生成批处理业务流程的订阅筛选器的属性、 运算符和值。</span><span class="sxs-lookup"><span data-stu-id="58b72-126">In the **Batch Filter** dialog box, enter the property, operator and values to build the subscription filter for the batching orchestration.</span></span> <span data-ttu-id="58b72-127">这些筛选器子句用于确定路由业务流程将路由到 MessageBox 以对哪些事务集进行批处理。</span><span class="sxs-lookup"><span data-stu-id="58b72-127">These filter clauses determine which transaction sets the routing orchestration will route to the MessageBox for batching.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="58b72-128">若要指定对组的所有消息都进行批处理，请将批处理筛选器中的参与方属性设置为参与方名称。</span><span class="sxs-lookup"><span data-stu-id="58b72-128">To specify that all messages to a group will be batched, set the party property in the batch filter to the party name.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="58b72-129">有关批处理的过程的详细信息，请参阅[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="58b72-129">For more information about the batching process, see [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
    3.  <span data-ttu-id="58b72-130">若要删除的行，选择行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="58b72-130">To delete a row, select the row and click **Delete**.</span></span>  
  
    4.  <span data-ttu-id="58b72-131">若要向上或向下移动一行，请单击**移**或**下移**按钮。</span><span class="sxs-lookup"><span data-stu-id="58b72-131">To move a row up or down, click the **Move Up** or **Move Down** buttons.</span></span>  
  
6.  <span data-ttu-id="58b72-132">在**版本**选项卡的部分执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="58b72-132">In the **Release** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="58b72-133">选择**计划**用于创建和发送一批根据预先确定的计划。</span><span class="sxs-lookup"><span data-stu-id="58b72-133">Select **Schedule** to create and send a batch according to a predetermined schedule.</span></span> <span data-ttu-id="58b72-134">若要定义计划，请单击**计划程序**，然后继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="58b72-134">To define the schedule, click **Scheduler** and then proceed as follows:</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="58b72-135">批处理计划可能会受到特殊事件的影响。</span><span class="sxs-lookup"><span data-stu-id="58b72-135">A batch schedule may be affected by special events.</span></span> <span data-ttu-id="58b72-136">例如，夏时制的开始实行就会影响批处理计划。</span><span class="sxs-lookup"><span data-stu-id="58b72-136">An example is the onset of daylight savings time.</span></span> <span data-ttu-id="58b72-137">如果在开始实行夏时制后的一个小时内，计划每小时运行一次批处理，那么在时钟拨快一个小时后，将不会创建并发送该批。</span><span class="sxs-lookup"><span data-stu-id="58b72-137">If a batch were scheduled on an hourly basis less than an hour after the onset of daylight savings time, the batch would not be created and sent after clocks were reset by incrementing the hour.</span></span> <span data-ttu-id="58b72-138">你可以通过单击导致跳过的批次中的特殊事件补偿**启动**按钮上**批处理**页后，可以手动启动批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="58b72-138">You can compensate for special events that result in a skipped batch by clicking the **Start** button on the **Batches** page to start the batching orchestration manually.</span></span> <span data-ttu-id="58b72-139">你还可能需要停止重复的批处理。</span><span class="sxs-lookup"><span data-stu-id="58b72-139">You may also have to stop a duplicated batch.</span></span>  
  
        -   <span data-ttu-id="58b72-140">每小时发送一批，选择**每小时**。</span><span class="sxs-lookup"><span data-stu-id="58b72-140">To send a batch on an hourly basis, select **Hourly**.</span></span> <span data-ttu-id="58b72-141">从下拉列表中为**在首次发布**，选择批处理的第一个版本的日期，然后输入时间。</span><span class="sxs-lookup"><span data-stu-id="58b72-141">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="58b72-142">有关**后续版本每个**，从下拉列表选择是否期间正在中**小时**或**分钟**，然后输入的小时数或将的分钟数分隔每个批次。</span><span class="sxs-lookup"><span data-stu-id="58b72-142">For **Subsequent release every**, select from the drop-down list whether the period is in **Hours** or **Minutes**, and then enter the number of hours or minutes that will separate each batch.</span></span>  
  
        -   <span data-ttu-id="58b72-143">每天发送一批，选择**每日**。</span><span class="sxs-lookup"><span data-stu-id="58b72-143">To send a batch on a daily basis, select **Daily**.</span></span> <span data-ttu-id="58b72-144">从下拉列表中为**在首次发布**，选择批处理的第一个版本的日期，然后输入时间。</span><span class="sxs-lookup"><span data-stu-id="58b72-144">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="58b72-145">有关**后续版本每个**，输入的将分隔每个批的天数。</span><span class="sxs-lookup"><span data-stu-id="58b72-145">For **Subsequent release every**, enter the number of days that will separate each batch.</span></span>  
  
        -   <span data-ttu-id="58b72-146">若要按周发送一批，选择**每周**。</span><span class="sxs-lookup"><span data-stu-id="58b72-146">To send a batch on a weekly basis, select **Weekly**.</span></span> <span data-ttu-id="58b72-147">从下拉列表中为**在首次发布**，选择批处理的第一个版本的日期，然后输入时间。</span><span class="sxs-lookup"><span data-stu-id="58b72-147">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="58b72-148">有关**后续版本每个**，输入第一个版本中的周和每个后续版本中的周之间的周数。</span><span class="sxs-lookup"><span data-stu-id="58b72-148">For **Subsequent release every**, enter the number of weeks between the week of the first release and the week of each subsequent release.</span></span> <span data-ttu-id="58b72-149">然后选择将在星期几发布批。</span><span class="sxs-lookup"><span data-stu-id="58b72-149">Then select the days of the week that the batch will be released on.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="58b72-150">将在日期的第一个版本，并将其设置**在首次发布**字段，即使未在对话框中选择该日期是星期几。</span><span class="sxs-lookup"><span data-stu-id="58b72-150">The first release will be made at the date and set in the **First release at** field, even if that day of the week was not selected in the dialog box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="58b72-151">如果您在该对话框中选择了一个或多个星期几，则将在首次发布后第一周中选定的任意一天（星期几）进行发布。</span><span class="sxs-lookup"><span data-stu-id="58b72-151">If you selected one or more days of the week in the dialog box, a release will be made on any selected day of that first week that comes after the first release.</span></span> <span data-ttu-id="58b72-152">例如，如果选择了“星期一”和“星期五”，并且首次发布的时间是星期三，则将在第一周的星期五进行发布。</span><span class="sxs-lookup"><span data-stu-id="58b72-152">For example, if Monday and Friday have been selected, and the first release was on a Wednesday, a release will be made on Friday of the first week.</span></span> <span data-ttu-id="58b72-153">后续版本将发生 *n* 后的第一周的周内与 *n* 中的值确定**后续版本每个**字段。</span><span class="sxs-lookup"><span data-stu-id="58b72-153">Subsequent releases will occur *n* weeks after the first week, with *n* determined by the value in the **Subsequent release every** field.</span></span> <span data-ttu-id="58b72-154">发布将在该对话框中所选的每个星期几进行。</span><span class="sxs-lookup"><span data-stu-id="58b72-154">Release will occur on each day of the week selected in the dialog box.</span></span>  
  
        -   <span data-ttu-id="58b72-155">选择**发送空批处理信号**发送一个空的批处理信号，如果当批处理计划要发送的批处理的业务流程不收到任何消息。</span><span class="sxs-lookup"><span data-stu-id="58b72-155">Select **Send empty batch signal** to send an empty batch signal if no messages have been received by the batching orchestration when the batch is scheduled to be sent.</span></span>  
  
    2.  <span data-ttu-id="58b72-156">选择**事务的最大数量设置中**用于创建和发送一批，每当一定数量的事务集或消息已传送至批处理 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="58b72-156">Select **Maximum number of transaction sets in** to create and send a batch whenever a certain number of transaction sets or messages has been routed to the MessageBox for batching.</span></span> <span data-ttu-id="58b72-157">选择要计数的事务的消息的一部分设置中 (任一**组**或**交换**)，然后输入的最大事务集在批处理的组或交换数。</span><span class="sxs-lookup"><span data-stu-id="58b72-157">Select the part of the message to count the transaction sets in (either **Group** or **Interchange**), and then enter the maximum number of transaction sets to be in the batched group or interchange.</span></span>  
  
         <span data-ttu-id="58b72-158">例如，如果你想要批处理到一个批次的两个交换选择**交换**从下拉列表，然后输入`2`在文本框中。</span><span class="sxs-lookup"><span data-stu-id="58b72-158">For example, if you want to batch two interchanges into one batch select **Interchange** from the drop-down and enter `2` in the text box.</span></span>  
  
    3.  <span data-ttu-id="58b72-159">选择**将交换中的字符的最大数量**用于创建和发送一批，批处理有特定数量的字符时。</span><span class="sxs-lookup"><span data-stu-id="58b72-159">Select **Maximum number of characters in an interchange** to create and send a batch when a specific number of characters are available for batch processing.</span></span> <span data-ttu-id="58b72-160">输入批处理组或交换中的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="58b72-160">Enter the maximum number of characters in the batched group or interchange.</span></span>  
  
         <span data-ttu-id="58b72-161">批处理业务流程将累计批处理元素，直到这些元素中的字符计数（减去信封中的计数）超过最大计数。</span><span class="sxs-lookup"><span data-stu-id="58b72-161">The batching orchestration will accumulate batching elements until the character count in those elements (minus the count in the envelope) exceeds the maximum count.</span></span> <span data-ttu-id="58b72-162">然后将对除最后一个元素（会导致计数超过最大计数）以外的所有元素进行批处理。</span><span class="sxs-lookup"><span data-stu-id="58b72-162">It will then batch all but the last element (which caused the count to exceed the maximum count).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="58b72-163">输入的最大字符数应足够大，以生成有意义的批。</span><span class="sxs-lookup"><span data-stu-id="58b72-163">For the maximum number of characters, enter a number large enough that you will generate meaningful batches.</span></span> <span data-ttu-id="58b72-164">该数至少应大于批头部中的字符数和消息中的最大字符数的总和。</span><span class="sxs-lookup"><span data-stu-id="58b72-164">That number should at least be greater than the total number of characters in the batch headers and the maximum number of characters in a message.</span></span> <span data-ttu-id="58b72-165">数太小可能会产生空批。</span><span class="sxs-lookup"><span data-stu-id="58b72-165">A number that is too small could result in empty batches.</span></span>  
  
    4.  <span data-ttu-id="58b72-166">选择**外部发布触发器**创建并由给 BizTalk Server 应用程序外部执行一个外部触发器时将发送一批。</span><span class="sxs-lookup"><span data-stu-id="58b72-166">Select **External release trigger** to create and then send a batch when an external trigger is executed by an application external to BizTalk Server.</span></span> <span data-ttu-id="58b72-167">有关如何设置此机制的详细信息，请参阅[实现外部的批处理释放机制](../core/implementing-an-external-batch-release-mechanism.md)。</span><span class="sxs-lookup"><span data-stu-id="58b72-167">For more information about how to set up this mechanism, see [Implementing an External Batch Release Mechanism](../core/implementing-an-external-batch-release-mechanism.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="58b72-168">**重写**按钮和**激活范围**控件仍有效，如果**外部发布**选择触发器属性。</span><span class="sxs-lookup"><span data-stu-id="58b72-168">The **Override** button and **Activation range** controls remain valid if the **External release** trigger property has been selected.</span></span>  
  
7.  <span data-ttu-id="58b72-169">在**激活**选项卡的部分执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="58b72-169">In the **Activation** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="58b72-170">选择**立即启动**能够批处理业务流程开始立即对消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="58b72-170">Select **Start Immediately** to have the batching orchestration begin batching messages immediately.</span></span>  
  
         <span data-ttu-id="58b72-171">若要在特定日期开始批处理业务流程，清除**立即启动**框中选择一个日期和时间来激活批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="58b72-171">To start the batching orchestration on a specific date, clear the **Start Immediately** box and select a date and time to activate the batching orchestration.</span></span>  
  
8.  <span data-ttu-id="58b72-172">在**终止**选项卡的部分执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="58b72-172">In the **Termination** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="58b72-173">保留**无结束日期**选择如果你不想要指定为批处理的业务流程，以将其停用的结束日期。</span><span class="sxs-lookup"><span data-stu-id="58b72-173">Keep **No end date** selected if you do not want to specify an end date for the batching orchestration to be deactivated.</span></span>  
  
    2.  <span data-ttu-id="58b72-174">选择 **（匹配项） 后的结束**指定批处理业务流程，将生成一定数量的批处理后停用状态。</span><span class="sxs-lookup"><span data-stu-id="58b72-174">Select **End after (occurrences)** to specify that the batching orchestration will be deactivated after a certain number of batches have been generated.</span></span> <span data-ttu-id="58b72-175">在“次数” 文本框中输入所需数目。</span><span class="sxs-lookup"><span data-stu-id="58b72-175">Enter the number desired in the text box.</span></span>  
  
    3.  <span data-ttu-id="58b72-176">选择**结束**指定批处理业务流程将停用的结束日期。</span><span class="sxs-lookup"><span data-stu-id="58b72-176">Select **End by** to specify an end date that the batching orchestration will be deactivated.</span></span> <span data-ttu-id="58b72-177">此后，将不再收集用于批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="58b72-177">Messages will no longer be collected for batching as of this time.</span></span> <span data-ttu-id="58b72-178">从日历选择结束日期，或直接在文本框中更改日期或时间。</span><span class="sxs-lookup"><span data-stu-id="58b72-178">Select an end date from the calendar or change the date or time directly in the text box.</span></span>  
  
9. <span data-ttu-id="58b72-179">单击**应用**来应用你在前面的步骤中提供的批处理设置。</span><span class="sxs-lookup"><span data-stu-id="58b72-179">Click **Apply** to apply the batch settings you provided in the previous steps.</span></span> <span data-ttu-id="58b72-180">单击后**应用**，批处理 ID 创建并显示在**批次 ID**中的文本字段**标识**部分。</span><span class="sxs-lookup"><span data-stu-id="58b72-180">After you click **Apply**, a batch ID is created and is displayed in the **Batch ID** text field in the **Identification** section.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58b72-181">一条消息**未激活批处理**将显示在**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="58b72-181">A message **Batching is not activated** will be displayed under the **Start** button.</span></span>  
  
10. <span data-ttu-id="58b72-182">单击**启动**手动激活批处理的业务流程。</span><span class="sxs-lookup"><span data-stu-id="58b72-182">Click **Start** to activate a batching orchestration manually.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58b72-183">若要确保，批处理业务流程将被立即激活单击时**启动**按钮，更新 BatchControlMessageReccvLoc 中的 SQL 适配器接收位置的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="58b72-183">To make sure that the batching orchestration will be promptly activated when you click the **Start** button, update the polling interval for the SQL adapter in the BatchControlMessageReccvLoc receive location.</span></span> <span data-ttu-id="58b72-184">有关详细信息，请参阅[演练 (X12)： 发送批处理的 EDI 交换](../core/walkthrough-x12-sending-batched-edi-interchanges.md)。</span><span class="sxs-lookup"><span data-stu-id="58b72-184">For more information, see [Walkthrough (X12): Sending Batched EDI Interchanges](../core/walkthrough-x12-sending-batched-edi-interchanges.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58b72-185">单击后**启动**，单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="58b72-185">After you click **Start**, click **Refresh**.</span></span> <span data-ttu-id="58b72-186">可能需要一段时间将批与业务流程实例相关联。</span><span class="sxs-lookup"><span data-stu-id="58b72-186">It can take a while to associate the batch with the orchestration instance.</span></span> <span data-ttu-id="58b72-187">如果你单击**刷新**批处理程序与业务流程之前，你将看到消息**批处理已激活，批处理尚未未实例化的业务流程**。</span><span class="sxs-lookup"><span data-stu-id="58b72-187">If you click **Refresh** before the batch is associated with the orchestration, you see the message **Batching is activated, Batching orchestration not instantiated yet**.</span></span> <span data-ttu-id="58b72-188">单击**刷新**试以查看关联的业务流程中的实例 ID **Orchestration 实例 ID**文本框。</span><span class="sxs-lookup"><span data-stu-id="58b72-188">Click **Refresh** again to see the associated orchestration’s instance ID in the **Orchestration instance ID** text box.</span></span> <span data-ttu-id="58b72-189">消息**激活批处理**下显示**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="58b72-189">The message **Batching is activated** is displayed under the **Start** button.</span></span>  
  
11. <span data-ttu-id="58b72-190">单击**重写**到强制批处理业务流程发送一批，无论是否均已满足释放条件。</span><span class="sxs-lookup"><span data-stu-id="58b72-190">Click **Override** to forces the batching orchestration to send a batch, whether or not the release criteria have been met.</span></span> <span data-ttu-id="58b72-191">使用此选项可替代现有批条件，还将使用现有元素创建一个批并立即发送。</span><span class="sxs-lookup"><span data-stu-id="58b72-191">Using this option overrides the existing batch criteria, with the result that a batch is created using existing elements and then sent immediately.</span></span> <span data-ttu-id="58b72-192">执行完此操作后，批处理业务流程将根据已建立的设置，继续进行批处理。</span><span class="sxs-lookup"><span data-stu-id="58b72-192">After this, the batching orchestration resumes batch processing according to the established settings.</span></span>  
  
12. <span data-ttu-id="58b72-193">单击**停止**而无需发送一批中止该活动的批处理业务流程和手动停用批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="58b72-193">Click **Stop** to terminate an active batching orchestration without sending a batch and deactivate the batching orchestration manually.</span></span>  
  
13. <span data-ttu-id="58b72-194">单击**刷新**可以刷新批处理的业务流程的状态。</span><span class="sxs-lookup"><span data-stu-id="58b72-194">Click **Refresh** to refresh the status of the batching orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58b72-195">你可以使用下拉列表的顶部**批配置**页后，可以筛选批处理配置选项卡显示通过选择**所有**（若要查看所有批次的选项卡），**活动**（若要查看活动的批处理数的选项卡），或**非活动**（若要查看处于非活动状态的批次的选项卡）。</span><span class="sxs-lookup"><span data-stu-id="58b72-195">You can use the drop-down list at the top of **the Batch Configuration** page to filter the batch configuration tabs displayed by selecting **All** (to see tabs for all batches), **Active** (to see tabs for active batches), or **Inactive** (to see tabs for inactive batches).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58b72-196">如果在业务流程处理批的过程中更改配置设置，则新设置不会应用于该批。</span><span class="sxs-lookup"><span data-stu-id="58b72-196">If you change the configuration settings while the orchestration is processing a batch, the new settings will not be applied to that batch.</span></span> <span data-ttu-id="58b72-197">这会导致发送管道中产生验证错误。</span><span class="sxs-lookup"><span data-stu-id="58b72-197">This can result in validation errors in the send pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58b72-198">如果要加速开发服务器上的批处理业务流程参与方的激活，可以缩短该服务器上的批处理 SQL 适配器接收位置 (BatchControlMessageRecvLoc) 的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="58b72-198">To speed up activation of the batching orchestration party on a development server, you can decrease the polling interval for the batching SQL adapter receive location (BatchControlMessageRecvLoc) on that server.</span></span> <span data-ttu-id="58b72-199">我们建议你为开发服务器将轮询间隔设置为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="58b72-199">We recommend you set the polling interval for a development server to 30 seconds.</span></span>  
  
14. <span data-ttu-id="58b72-200">单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="58b72-200">Click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b72-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58b72-201">See Also</span></span>  
 <span data-ttu-id="58b72-202">[配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md) </span><span class="sxs-lookup"><span data-stu-id="58b72-202">[Configuring Interchange Settings (X12)](../core/configuring-interchange-settings-x12.md) </span></span>  
 <span data-ttu-id="58b72-203">[配置传出批处理](../core/configuring-an-outgoing-batch.md) </span><span class="sxs-lookup"><span data-stu-id="58b72-203">[Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md) </span></span>  
 <span data-ttu-id="58b72-204">[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="58b72-204">[Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md) </span></span>  
 [<span data-ttu-id="58b72-205">实现外部批处理释放机制</span><span class="sxs-lookup"><span data-stu-id="58b72-205">Implementing an External Batch Release Mechanism</span></span>](../core/implementing-an-external-batch-release-mechanism.md)