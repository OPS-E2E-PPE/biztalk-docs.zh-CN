---
title: 配置批处理 (X12) |Microsoft Docs
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
ms.openlocfilehash: b871f3c7a03c351d938b90a9d55b10035f50097c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356245"
---
# <a name="configuring-batching-x12"></a><span data-ttu-id="ff9b5-102">配置批处理 (X12)</span><span class="sxs-lookup"><span data-stu-id="ff9b5-102">Configuring Batching (X12)</span></span>
<span data-ttu-id="ff9b5-103">批处理定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成并发送 EDI 批到参与方。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-103">Batches define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates and sends an EDI batches to the party.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff9b5-104">此处所述的设置也适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-104">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff9b5-105">所有属性都禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-105">All properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span> <span data-ttu-id="ff9b5-106">**新的批处理**此页上禁用按钮。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-106">The **New Batch** button is disabled on this page.</span></span>  
>   
>  <span data-ttu-id="ff9b5-107">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="ff9b5-108">例如，如果两个参与方 Party A 和参与方 B 创建和参与方 a 清除该复选框，**新的批处理**上禁用按钮**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the **New Batch** button is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ff9b5-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="ff9b5-109">Prerequisites</span></span>  
 <span data-ttu-id="ff9b5-110">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-batching-settings"></a><span data-ttu-id="ff9b5-111">配置批处理设置</span><span class="sxs-lookup"><span data-stu-id="ff9b5-111">To configure batching settings</span></span>  
  
1.  <span data-ttu-id="ff9b5-112">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-112">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="ff9b5-113">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-113">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ff9b5-114">在单向协议选项卡下**交换设置**部分中，单击**批处理配置**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-114">On a one-way agreement tab, under **Interchange Settings** section, click **Batching Configuration**.</span></span>  
  
3.  <span data-ttu-id="ff9b5-115">从**批配置**页上，单击**新的批处理**若要创建新的批处理配置。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-115">From the **Batch Configuration** page click **New Batch** to create a new batch configuration.</span></span> <span data-ttu-id="ff9b5-116">一个**Batch1**添加选项卡。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-116">A **Batch1** tab is added.</span></span>  
  
4.  <span data-ttu-id="ff9b5-117">在中**标识**部分的选项卡中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ff9b5-117">In the **Identification** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="ff9b5-118">输入**批处理**名称。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-118">Enter the **Batch** name.</span></span> <span data-ttu-id="ff9b5-119">此值用作此批处理配置的选项卡标识符。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-119">This value is used as the tab identifier for this batch configuration.</span></span>  
  
    2.  <span data-ttu-id="ff9b5-120">输入在此批处理配置的说明**批处理说明**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-120">Enter a description of this batch configuration in **Batch description**.</span></span>  
  
    3.  <span data-ttu-id="ff9b5-121">**批处理 ID**是应用批处理设置后，会显示的唯一批处理 ID 的只读文本框。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-121">**Batch ID** is a read-only text box that displays a unique batch ID after you apply the settings for the batch.</span></span>  
  
    4.  <span data-ttu-id="ff9b5-122">**业务流程实例 ID**是显示批处理与之关联的批处理业务流程实例 ID 的只读文本框。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-122">**Orchestration instance ID** is a read-only text box that displays the batching orchestration instance ID that the batch is associated with.</span></span> <span data-ttu-id="ff9b5-123">在批启动后，将显示业务流程实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-123">An orchestration instance ID is displayed after a batch is started.</span></span>  
  
5.  <span data-ttu-id="ff9b5-124">在中**筛选器**部分的选项卡中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ff9b5-124">In the **Filter** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="ff9b5-125">单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-125">Click **Filter**.</span></span>  
  
    2.  <span data-ttu-id="ff9b5-126">在中**批处理筛选器**对话框框中，输入属性、 运算符和值以生成批处理业务流程订阅筛选器。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-126">In the **Batch Filter** dialog box, enter the property, operator and values to build the subscription filter for the batching orchestration.</span></span> <span data-ttu-id="ff9b5-127">这些筛选器子句用于确定路由业务流程将路由到 MessageBox 进行批处理的事务集。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-127">These filter clauses determine which transaction sets the routing orchestration will route to the MessageBox for batching.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ff9b5-128">若要指定给组的所有消息将进行都批处理，批处理将筛选器中的参与方名称设置的参与方属性。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-128">To specify that all messages to a group will be batched, set the party property in the batch filter to the party name.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ff9b5-129">有关批处理过程的详细信息，请参阅[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-129">For more information about the batching process, see [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
    3.  <span data-ttu-id="ff9b5-130">若要删除的行，选择的行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-130">To delete a row, select the row and click **Delete**.</span></span>  
  
    4.  <span data-ttu-id="ff9b5-131">若要向上或向下移动一行，请单击**移**或**下移**按钮。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-131">To move a row up or down, click the **Move Up** or **Move Down** buttons.</span></span>  
  
6.  <span data-ttu-id="ff9b5-132">在中**版本**部分的选项卡中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ff9b5-132">In the **Release** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="ff9b5-133">选择**计划**创建并发送一批根据预先确定的计划。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-133">Select **Schedule** to create and send a batch according to a predetermined schedule.</span></span> <span data-ttu-id="ff9b5-134">若要定义计划，请单击**计划程序**，然后继续按如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff9b5-134">To define the schedule, click **Scheduler** and then proceed as follows:</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ff9b5-135">批处理计划可能会受到特殊事件。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-135">A batch schedule may be affected by special events.</span></span> <span data-ttu-id="ff9b5-136">例如，夏时制的开始。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-136">An example is the onset of daylight savings time.</span></span> <span data-ttu-id="ff9b5-137">如果一批已计划按小时计费小于一小时的夏时制开始后，将不创建并发送后时钟已通过递增小时重置批处理。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-137">If a batch were scheduled on an hourly basis less than an hour after the onset of daylight savings time, the batch would not be created and sent after clocks were reset by incrementing the hour.</span></span> <span data-ttu-id="ff9b5-138">可以通过单击结果中跳过批处理的特殊事件的补偿**启动**按钮**批处理**页后，可以手动开始批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-138">You can compensate for special events that result in a skipped batch by clicking the **Start** button on the **Batches** page to start the batching orchestration manually.</span></span> <span data-ttu-id="ff9b5-139">您可能还需要停止重复的批处理。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-139">You may also have to stop a duplicated batch.</span></span>  
  
        -   <span data-ttu-id="ff9b5-140">若要按小时发送一批，请选择**每小时**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-140">To send a batch on an hourly basis, select **Hourly**.</span></span> <span data-ttu-id="ff9b5-141">从下拉列表中为**首次发布**，选择首次发布批的日期，然后输入时间。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-141">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="ff9b5-142">有关**后续发布每个**，从下拉列表中选择时间是否处于**小时**或**分钟**，然后输入小时数或将分钟数每次批。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-142">For **Subsequent release every**, select from the drop-down list whether the period is in **Hours** or **Minutes**, and then enter the number of hours or minutes that will separate each batch.</span></span>  
  
        -   <span data-ttu-id="ff9b5-143">每天发送一批，请选择**每日**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-143">To send a batch on a daily basis, select **Daily**.</span></span> <span data-ttu-id="ff9b5-144">从下拉列表中为**首次发布**，选择首次发布批的日期，然后输入时间。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-144">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="ff9b5-145">有关**后续发布每个**，输入的每次批的天数。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-145">For **Subsequent release every**, enter the number of days that will separate each batch.</span></span>  
  
        -   <span data-ttu-id="ff9b5-146">每周都会发送一批，请选择**每周**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-146">To send a batch on a weekly basis, select **Weekly**.</span></span> <span data-ttu-id="ff9b5-147">从下拉列表中为**首次发布**，选择首次发布批的日期，然后输入时间。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-147">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="ff9b5-148">有关**后续发布每个**，输入之间的周的第一次发布和各后续发布的一周的周数。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-148">For **Subsequent release every**, enter the number of weeks between the week of the first release and the week of each subsequent release.</span></span> <span data-ttu-id="ff9b5-149">然后，选择在发布批内容每周天数。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-149">Then select the days of the week that the batch will be released on.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="ff9b5-150">将所做的日期和设置首次发布**首次发布**字段中，即使未在对话框中选择该日期是星期几。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-150">The first release will be made at the date and set in the **First release at** field, even if that day of the week was not selected in the dialog box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="ff9b5-151">如果在对话框中选择一个或多个星期几，将在第一周的第一个版本之后的任何所选一天进行发布。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-151">If you selected one or more days of the week in the dialog box, a release will be made on any selected day of that first week that comes after the first release.</span></span> <span data-ttu-id="ff9b5-152">例如，如果已选择星期一和星期五，并且首次发布时间是星期三，将在第一周的星期五进行发布。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-152">For example, if Monday and Friday have been selected, and the first release was on a Wednesday, a release will be made on Friday of the first week.</span></span> <span data-ttu-id="ff9b5-153">后续版本将发生*n*周后第一周，与*n*中的值由决定**后续发布每个**字段。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-153">Subsequent releases will occur *n* weeks after the first week, with *n* determined by the value in the **Subsequent release every** field.</span></span> <span data-ttu-id="ff9b5-154">版本将在对话框中选择一周中的每一天。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-154">Release will occur on each day of the week selected in the dialog box.</span></span>  
  
        -   <span data-ttu-id="ff9b5-155">选择**发送空的批处理信号**根据计划发送批时批处理业务流程不收到任何消息发送空的批处理信号。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-155">Select **Send empty batch signal** to send an empty batch signal if no messages have been received by the batching orchestration when the batch is scheduled to be sent.</span></span>  
  
    2.  <span data-ttu-id="ff9b5-156">选择**最大数量的事务集**来创建和发送批时一定数量的事务集或消息已路由到 MessageBox 进行批处理。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-156">Select **Maximum number of transaction sets in** to create and send a batch whenever a certain number of transaction sets or messages has been routed to the MessageBox for batching.</span></span> <span data-ttu-id="ff9b5-157">选择要计算其中事务的消息的一部分设置中 (任一**组**或**交换**)，然后输入批处理的组或交换中事务集的最大数目。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-157">Select the part of the message to count the transaction sets in (either **Group** or **Interchange**), and then enter the maximum number of transaction sets to be in the batched group or interchange.</span></span>  
  
         <span data-ttu-id="ff9b5-158">例如，如果你想要两个交换组成一个批次选择**交换**从下拉列表，然后输入`2`在文本框中。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-158">For example, if you want to batch two interchanges into one batch select **Interchange** from the drop-down and enter `2` in the text box.</span></span>  
  
    3.  <span data-ttu-id="ff9b5-159">选择**交换中的字符的最大数量**来创建和发送批时特定数目的字符是可用于批处理。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-159">Select **Maximum number of characters in an interchange** to create and send a batch when a specific number of characters are available for batch processing.</span></span> <span data-ttu-id="ff9b5-160">输入批处理的组或交换中的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-160">Enter the maximum number of characters in the batched group or interchange.</span></span>  
  
         <span data-ttu-id="ff9b5-161">批处理业务流程将累计批处理元素，直到这些元素 （减去信封中的计数） 中的字符数超过最大计数。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-161">The batching orchestration will accumulate batching elements until the character count in those elements (minus the count in the envelope) exceeds the maximum count.</span></span> <span data-ttu-id="ff9b5-162">它然后将除最后一个元素 （会导致计数超过最大计数） 之外的所有批处理。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-162">It will then batch all but the last element (which caused the count to exceed the maximum count).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ff9b5-163">对于最大字符数，输入足够大，以生成有意义的批。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-163">For the maximum number of characters, enter a number large enough that you will generate meaningful batches.</span></span> <span data-ttu-id="ff9b5-164">该数字至少应大于批头部中的字符总数和最大消息中的字符数。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-164">That number should at least be greater than the total number of characters in the batch headers and the maximum number of characters in a message.</span></span> <span data-ttu-id="ff9b5-165">太小的数字可能会导致空的批处理。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-165">A number that is too small could result in empty batches.</span></span>  
  
    4.  <span data-ttu-id="ff9b5-166">选择**外部发布触发器**创建并随后发送批时由 BizTalk Server 外部的应用程序执行外部触发器。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-166">Select **External release trigger** to create and then send a batch when an external trigger is executed by an application external to BizTalk Server.</span></span> <span data-ttu-id="ff9b5-167">有关如何设置此机制的详细信息，请参阅[实现外部批处理发布机制](../core/implementing-an-external-batch-release-mechanism.md)。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-167">For more information about how to set up this mechanism, see [Implementing an External Batch Release Mechanism](../core/implementing-an-external-batch-release-mechanism.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ff9b5-168">**重写**按钮并**激活范围**控件仍将有效如果**外部发布**选择触发器属性。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-168">The **Override** button and **Activation range** controls remain valid if the **External release** trigger property has been selected.</span></span>  
  
7.  <span data-ttu-id="ff9b5-169">在中**激活**部分的选项卡中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ff9b5-169">In the **Activation** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="ff9b5-170">选择**立即开始**以让批处理业务流程立即开始批处理消息。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-170">Select **Start Immediately** to have the batching orchestration begin batching messages immediately.</span></span>  
  
         <span data-ttu-id="ff9b5-171">若要在特定日期开始批处理业务流程，清除**立即开始**框并选择一个日期和时间来激活批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-171">To start the batching orchestration on a specific date, clear the **Start Immediately** box and select a date and time to activate the batching orchestration.</span></span>  
  
8.  <span data-ttu-id="ff9b5-172">在中**终止**部分的选项卡中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ff9b5-172">In the **Termination** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="ff9b5-173">保持**无结束日期**选择如果不想指定将停用批处理业务流程的结束日期。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-173">Keep **No end date** selected if you do not want to specify an end date for the batching orchestration to be deactivated.</span></span>  
  
    2.  <span data-ttu-id="ff9b5-174">选择**结束前的 （出现）** 指定批处理业务流程，将生成一定数量的批之后停用状态。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-174">Select **End after (occurrences)** to specify that the batching orchestration will be deactivated after a certain number of batches have been generated.</span></span> <span data-ttu-id="ff9b5-175">输入所需在文本框中的编号。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-175">Enter the number desired in the text box.</span></span>  
  
    3.  <span data-ttu-id="ff9b5-176">选择**结束**以指定将停用批处理业务流程的结束日期。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-176">Select **End by** to specify an end date that the batching orchestration will be deactivated.</span></span> <span data-ttu-id="ff9b5-177">消息将不再收集用于批处理截至这一次。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-177">Messages will no longer be collected for batching as of this time.</span></span> <span data-ttu-id="ff9b5-178">从日历中选择的结束日期或直接在文本框中更改的日期或时间。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-178">Select an end date from the calendar or change the date or time directly in the text box.</span></span>  
  
9. <span data-ttu-id="ff9b5-179">单击**应用**以便将你在上一步骤中提供的批处理设置。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-179">Click **Apply** to apply the batch settings you provided in the previous steps.</span></span> <span data-ttu-id="ff9b5-180">单击后**Apply**，批处理 ID 创建和显示在**批处理 ID**中的文本字段**标识**部分。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-180">After you click **Apply**, a batch ID is created and is displayed in the **Batch ID** text field in the **Identification** section.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff9b5-181">一条消息**激活批处理**下将显示**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-181">A message **Batching is not activated** will be displayed under the **Start** button.</span></span>  
  
10. <span data-ttu-id="ff9b5-182">单击**启动**手动激活批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-182">Click **Start** to activate a batching orchestration manually.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff9b5-183">若要确保，批处理业务流程将立即激活单击时**启动**按钮，更新 BatchControlMessageReccvLoc 中的 SQL 适配器接收位置的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-183">To make sure that the batching orchestration will be promptly activated when you click the **Start** button, update the polling interval for the SQL adapter in the BatchControlMessageReccvLoc receive location.</span></span> <span data-ttu-id="ff9b5-184">有关详细信息，请参阅[演练 (X12):发送批处理 EDI 交换](../core/walkthrough-x12-sending-batched-edi-interchanges.md)。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-184">For more information, see [Walkthrough (X12): Sending Batched EDI Interchanges](../core/walkthrough-x12-sending-batched-edi-interchanges.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff9b5-185">单击后**启动**，单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-185">After you click **Start**, click **Refresh**.</span></span> <span data-ttu-id="ff9b5-186">可能需要一段时间才能将批与业务流程实例相关联。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-186">It can take a while to associate the batch with the orchestration instance.</span></span> <span data-ttu-id="ff9b5-187">如果单击**刷新**批与业务流程关联之前，请参阅消息**批处理已激活批处理业务流程尚未实例化**。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-187">If you click **Refresh** before the batch is associated with the orchestration, you see the message **Batching is activated, Batching orchestration not instantiated yet**.</span></span> <span data-ttu-id="ff9b5-188">单击**刷新**再次以查看关联的业务流程实例 ID**业务流程实例 ID**文本框。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-188">Click **Refresh** again to see the associated orchestration’s instance ID in the **Orchestration instance ID** text box.</span></span> <span data-ttu-id="ff9b5-189">消息**激活批处理**下显示**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-189">The message **Batching is activated** is displayed under the **Start** button.</span></span>  
  
11. <span data-ttu-id="ff9b5-190">单击**重写**到强制批处理业务流程发送一批，指示是否已满足发布条件。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-190">Click **Override** to forces the batching orchestration to send a batch, whether or not the release criteria have been met.</span></span> <span data-ttu-id="ff9b5-191">使用此选项将重写现有批条件，使用结果一批是使用现有元素创建并立即发送。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-191">Using this option overrides the existing batch criteria, with the result that a batch is created using existing elements and then sent immediately.</span></span> <span data-ttu-id="ff9b5-192">在此之后，批处理业务流程继续进行批处理根据已建立的设置。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-192">After this, the batching orchestration resumes batch processing according to the established settings.</span></span>  
  
12. <span data-ttu-id="ff9b5-193">单击**停止**而无需发送一批终止活动批处理业务流程，然后手动停用批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-193">Click **Stop** to terminate an active batching orchestration without sending a batch and deactivate the batching orchestration manually.</span></span>  
  
13. <span data-ttu-id="ff9b5-194">单击**刷新**刷新批处理业务流程的状态。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-194">Click **Refresh** to refresh the status of the batching orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff9b5-195">您可以使用顶部的下拉列表**批配置**页来筛选显示选择的批处理配置选项卡**所有**（若要查看所有批的选项卡），**活动**（若要查看活动的批处理的选项卡），或**非活动**（若要查看用于非活动批的选项卡）。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-195">You can use the drop-down list at the top of **the Batch Configuration** page to filter the batch configuration tabs displayed by selecting **All** (to see tabs for all batches), **Active** (to see tabs for active batches), or **Inactive** (to see tabs for inactive batches).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff9b5-196">如果在业务流程正在处理一批更改配置设置，新设置将不会应用到该批。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-196">If you change the configuration settings while the orchestration is processing a batch, the new settings will not be applied to that batch.</span></span> <span data-ttu-id="ff9b5-197">这可能导致发送管道中的验证错误。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-197">This can result in validation errors in the send pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff9b5-198">若要激活批处理业务流程参与方的加速开发服务器上，可以缩短轮询间隔为批处理 SQL 适配器接收位置 (BatchControlMessageRecvLoc) 该服务器上。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-198">To speed up activation of the batching orchestration party on a development server, you can decrease the polling interval for the batching SQL adapter receive location (BatchControlMessageRecvLoc) on that server.</span></span> <span data-ttu-id="ff9b5-199">我们建议你将开发服务器将轮询间隔设置为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-199">We recommend you set the polling interval for a development server to 30 seconds.</span></span>  
  
14. <span data-ttu-id="ff9b5-200">单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="ff9b5-200">Click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9b5-201">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff9b5-201">See Also</span></span>  
 <span data-ttu-id="ff9b5-202">[配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md) </span><span class="sxs-lookup"><span data-stu-id="ff9b5-202">[Configuring Interchange Settings (X12)](../core/configuring-interchange-settings-x12.md) </span></span>  
 <span data-ttu-id="ff9b5-203">[配置传出批](../core/configuring-an-outgoing-batch.md) </span><span class="sxs-lookup"><span data-stu-id="ff9b5-203">[Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md) </span></span>  
 <span data-ttu-id="ff9b5-204">[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="ff9b5-204">[Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md) </span></span>  
 [<span data-ttu-id="ff9b5-205">实现外部批发布机制</span><span class="sxs-lookup"><span data-stu-id="ff9b5-205">Implementing an External Batch Release Mechanism</span></span>](../core/implementing-an-external-batch-release-mechanism.md)