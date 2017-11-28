---
title: "实现外部批处理释放机制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5633a448-cc29-4931-a3ad-206ae25c989b
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88b6962cc0c83ab0ac4971f481b9ac1f185ca02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-an-external-batch-release-mechanism"></a><span data-ttu-id="bf718-102">实现外部批处理发布机制</span><span class="sxs-lookup"><span data-stu-id="bf718-102">Implementing an External Batch Release Mechanism</span></span>
<span data-ttu-id="bf718-103">您可以使用外部发布触发器触发批处理的发布。</span><span class="sxs-lookup"><span data-stu-id="bf718-103">You can trigger the release of a batch using an external release trigger.</span></span> <span data-ttu-id="bf718-104">可以通过后端业务线应用程序在达到某一阀值时自动触发此发布。</span><span class="sxs-lookup"><span data-stu-id="bf718-104">The release could be automatically triggered by a back-end, line-of-business application upon reaching a certain threshold.</span></span> <span data-ttu-id="bf718-105">此机制是除了自动触发的批次版本按计划或计数的事务集或字符，或手动触发批处理，通过单击**重写**按钮**批处理配置**单向协议选项卡页。</span><span class="sxs-lookup"><span data-stu-id="bf718-105">This mechanism is in addition to automatically triggering the batch release by a schedule or a count of transaction sets or characters, or manually triggering the batch by clicking the **Override** button in the **Batch Configuration** page of the one-way agreement tab.</span></span>  
  
 <span data-ttu-id="bf718-106">若要实现外部发布触发器，需要设置接收端口和位置，以便处理 OverrideControlMessage。</span><span class="sxs-lookup"><span data-stu-id="bf718-106">To implement an external release trigger, you need to set up a receive port and location to process the OverrideControlMessage.</span></span> <span data-ttu-id="bf718-107">接收位置必须使用 `Edi.BatchControlMessageRecvPipeline` 接收管道。</span><span class="sxs-lookup"><span data-stu-id="bf718-107">The receive location must use the `Edi.BatchControlMessageRecvPipeline` receive pipeline.</span></span> <span data-ttu-id="bf718-108">这与 BatchControlMessageRecvLoc 接收位置所使用的是同一管道，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用该位置处理手动替代消息。</span><span class="sxs-lookup"><span data-stu-id="bf718-108">This is the same pipeline that is used by the BatchControlMessageRecvLoc receive location that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to process manual override messages.</span></span> <span data-ttu-id="bf718-109">不过，BatchControlMessageRecvLoc 是 SQL 类型的接收位置，而为外部发布触发器设置的接收位置可以使用任何适配器类型。</span><span class="sxs-lookup"><span data-stu-id="bf718-109">However, BatchControlMessageRecvLoc is a SQL-type receive location, while the receive location that you set up for an external release trigger can use any adapter type.</span></span>  
  
 <span data-ttu-id="bf718-110">外部批处理发布触发器由 XML 控制消息触发。</span><span class="sxs-lookup"><span data-stu-id="bf718-110">An external batch release is triggered by an XML control message.</span></span> <span data-ttu-id="bf718-111">为触发批处理，后端应用程序会将控制消息路由到接收位置。</span><span class="sxs-lookup"><span data-stu-id="bf718-111">To trigger the batch, the back-end application routes the control message to the receive location.</span></span> <span data-ttu-id="bf718-112">您可以修改控制消息，以便激活、替代或终止批处理。</span><span class="sxs-lookup"><span data-stu-id="bf718-112">You can modify the control message to activate, override, or terminate the batch.</span></span> <span data-ttu-id="bf718-113">请参阅以下有关创建控制消息的过程。</span><span class="sxs-lookup"><span data-stu-id="bf718-113">See the procedure below for creating the control message.</span></span>  
  
 <span data-ttu-id="bf718-114">若要启用外部发布触发器，您必须选择**外部发布触发器**中的属性**批配置**页**协议属性**对话框X12 或 EDIFACT 框。</span><span class="sxs-lookup"><span data-stu-id="bf718-114">To enable the external release trigger, you must select the **External release trigger** property in the **Batch Configuration** page of the **Agreement Properties** dialog box for either X12 or EDIFACT.</span></span> <span data-ttu-id="bf718-115">此属性指明批处理发布需要外部发布消息。</span><span class="sxs-lookup"><span data-stu-id="bf718-115">This property indicates that an external release message is required for batch release.</span></span> <span data-ttu-id="bf718-116">**重写**按钮，**停止**按钮，和**激活**范围的控件保持有效如果**外部发布触发器**属性已选择。</span><span class="sxs-lookup"><span data-stu-id="bf718-116">The **Override** button, **Stop** button, and **Activation** range controls remain valid if the **External release trigger** property has been selected.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf718-117">先决条件</span><span class="sxs-lookup"><span data-stu-id="bf718-117">Prerequisites</span></span>  
 <span data-ttu-id="bf718-118">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="bf718-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-create-a-receive-location-for-the-external-batch-release-trigger-message"></a><span data-ttu-id="bf718-119">为外部批处理发布触发器消息创建接收位置</span><span class="sxs-lookup"><span data-stu-id="bf718-119">To create a receive location for the external batch release trigger message</span></span>  
  
1.  <span data-ttu-id="bf718-120">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建一个单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="bf718-120">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a one-way receive port.</span></span> <span data-ttu-id="bf718-121">有关如何创建接收端口的说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="bf718-121">For instructions on how to create a receive port, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  
  
2.  <span data-ttu-id="bf718-122">在接收端口中创建一个单向接收位置。</span><span class="sxs-lookup"><span data-stu-id="bf718-122">Create a one-way receive location in the receive port.</span></span>  
  
3.  <span data-ttu-id="bf718-123">选择传输类型。</span><span class="sxs-lookup"><span data-stu-id="bf718-123">Select the transport type.</span></span> <span data-ttu-id="bf718-124">您可以为此接收位置选择任意类型。</span><span class="sxs-lookup"><span data-stu-id="bf718-124">You can select any type for this receive location.</span></span> <span data-ttu-id="bf718-125">通常是选择“FILE”类型，然后输入用于接收文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf718-125">A common solution is to select the FILE type, and enter a folder to receive the file.</span></span>  
  
4.  <span data-ttu-id="bf718-126">对于“接收管道”，请选择 `BatchControlMessageRecvPipeline`。</span><span class="sxs-lookup"><span data-stu-id="bf718-126">For Receive pipeline, select `BatchControlMessageRecvPipeline`.</span></span>  
  
5.  <span data-ttu-id="bf718-127">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bf718-127">Click **OK**.</span></span>  
  
### <a name="to-create-the-external-batch-release-trigger-message"></a><span data-ttu-id="bf718-128">创建外部批处理发布触发器消息</span><span class="sxs-lookup"><span data-stu-id="bf718-128">To create the external batch release trigger message</span></span>  
  
1.  <span data-ttu-id="bf718-129">在记事本中新建一个文件，然后使用 .xml 扩展名对其进行命名。</span><span class="sxs-lookup"><span data-stu-id="bf718-129">In Notepad, create a new file and name it with an .xml extension.</span></span>  
  
2.  <span data-ttu-id="bf718-130">向文件中添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="bf718-130">Add the following to the file:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ControlMessage xmlns="http://SQLControlMessage.IssueSelect">  
      <PAM_Control xmlns="http://SQLControlMessage.IssueSelect">  
        <DestinationParty>[Party ID]</DestinationParty>  
        <EdiMessageType>[0 for X12\HIPAA|1 for Edifact]</EdiMessageType>  
        <ActionType>EdiBatchOverride</ActionType>  
        <ActionDateTime>[yyyy-mm-ddThh:mm:ss.sss]</ActionDateTime>  
        <UsedOnce>0</UsedOnce>  
        <BatchId>[Batch ID]</BatchId>  
        <BatchName>[Batch Name]</BatchName>  
        <DestinationPartyName>[Destination Party/Partner name]</DestinationPartyName>  
        <SenderPartyName>[Sender Party/Partner name]</SenderPartyName>  
        <AgreementName>[Agreement Name]</AgreementName>  
        <ReceiverPartyNameType>[Receiver Party/Partner name]</ReceiverPartyNameType>  
        <ToBeBatched>1</ToBeBatched>  
      </PAM_Control>  
    </ControlMessage>  
    ```  
  
     <span data-ttu-id="bf718-131">替换以上摘录中的值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf718-131">Replace the values in the above excerpt as follows:</span></span>  
  
    -   <span data-ttu-id="bf718-132">指定操作类型。</span><span class="sxs-lookup"><span data-stu-id="bf718-132">Specify the action type.</span></span> <span data-ttu-id="bf718-133">通常情况下， **ActionType**必须设置为**EdiBatchOverride**重写协议中进行的批处理设置。</span><span class="sxs-lookup"><span data-stu-id="bf718-133">Typically, the **ActionType** must be set to **EdiBatchOverride** to override the batch settings done in the agreement.</span></span> <span data-ttu-id="bf718-134">你还可以将此设**EdiBatchTerminate**通过外部触发器批处理终止。</span><span class="sxs-lookup"><span data-stu-id="bf718-134">You can also set this to **EdiBatchTerminate** to terminate the batch through an external trigger.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bf718-135">Microsoft 建议您不要使用外部发布触发器来激活批处理。</span><span class="sxs-lookup"><span data-stu-id="bf718-135">Microsoft recommends you should not use external release trigger to activate a batch.</span></span> <span data-ttu-id="bf718-136">因此，不应指定**ActionType**作为**EdiBatchActivate**。</span><span class="sxs-lookup"><span data-stu-id="bf718-136">So, you should not specify **ActionType** as **EdiBatchActivate**.</span></span>  
  
    -   <span data-ttu-id="bf718-137">确定批次 ID 和批处理名称。</span><span class="sxs-lookup"><span data-stu-id="bf718-137">Determine the Batch ID and Batch Name.</span></span> <span data-ttu-id="bf718-138">为此，请打开**协议属性**对话框框中，然后在单向协议选项卡上，单击**批配置**。</span><span class="sxs-lookup"><span data-stu-id="bf718-138">To do so, open the **Agreement Properties** dialog box, and on the one-way agreement tab, click **Batch Configuration**.</span></span> <span data-ttu-id="bf718-139">单击要重写并输入的值的批的选项卡**批名称**和**批次 ID**字段到**BatchName**和**BatchID**控制消息的节点。</span><span class="sxs-lookup"><span data-stu-id="bf718-139">Click the tab for the batch to be overridden and enter the value of **Batch name** and **Batch ID** fields into the **BatchName** and **BatchID** nodes of the control message.</span></span>  
  
    -   <span data-ttu-id="bf718-140">指定目标参与方名称。</span><span class="sxs-lookup"><span data-stu-id="bf718-140">Specify the destination party name.</span></span> <span data-ttu-id="bf718-141">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**方和业务配置文件**页上，获取将在批处理接收方/伙伴的名称交换。</span><span class="sxs-lookup"><span data-stu-id="bf718-141">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Parties** node, and from the **Parties and Business Profiles** page, get the name of the party/partner that will be receiving the batched interchanges.</span></span> <span data-ttu-id="bf718-142">输入中的名称**ReceiverPartyNameType**控制消息的节点。</span><span class="sxs-lookup"><span data-stu-id="bf718-142">Enter the name in the **ReceiverPartyNameType** node of the control message.</span></span>  
  
    -   <span data-ttu-id="bf718-143">指定发件人方名称。</span><span class="sxs-lookup"><span data-stu-id="bf718-143">Specify the sender party name.</span></span> <span data-ttu-id="bf718-144">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**方和业务配置文件**页上，获取批处理的交换将要发送方/伙伴的名称.</span><span class="sxs-lookup"><span data-stu-id="bf718-144">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Parties** node, and from the **Parties and Business Profiles** page, get the name of the party/partner that will be sending the batched interchanges.</span></span> <span data-ttu-id="bf718-145">输入中的名称**SenderPartyName**控制消息的节点。</span><span class="sxs-lookup"><span data-stu-id="bf718-145">Enter the name in the **SenderPartyName** node of the control message.</span></span>  
  
    -   <span data-ttu-id="bf718-146">指定协议名称。</span><span class="sxs-lookup"><span data-stu-id="bf718-146">Specify the agreement name.</span></span> <span data-ttu-id="bf718-147">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**方和业务配置文件**页上，在**协议**部分中，右键单击具有批配置，需要到使用重写控制消息中，然后单击协议**属性**。</span><span class="sxs-lookup"><span data-stu-id="bf718-147">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Parties** node, and from the **Parties and Business Profiles** page, in the **Agreements** section, right-click the agreement that has the batch configuration that needs be to overridden using the control message, and then click **Properties**.</span></span> <span data-ttu-id="bf718-148">在**协议属性**对话框中，在**常规**选项卡上，在**常规属性**页上，复制的值从**名称**字段**协议参数**部分，并将其粘贴中**AgreementName**控制消息的节点。</span><span class="sxs-lookup"><span data-stu-id="bf718-148">In the **Agreement Properties** dialog box, in the **General** tab, on the **General Properties** page, copy the value from the **Name** field in the **Agreement Parameters** section, and paste it in the **AgreementName** node of the control message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf718-149">无需指定目标方 ID。</span><span class="sxs-lookup"><span data-stu-id="bf718-149">You do not need to specify a destination party ID.</span></span> <span data-ttu-id="bf718-150">控制消息中需要此元素只是为了实现向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="bf718-150">The element is required in the control message only for backward compatibility.</span></span>  
  
3.  <span data-ttu-id="bf718-151">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="bf718-151">Save the file.</span></span>  
  
### <a name="to-enable-the-external-release-trigger"></a><span data-ttu-id="bf718-152">启用外部发布触发器</span><span class="sxs-lookup"><span data-stu-id="bf718-152">To enable the external release trigger</span></span>  
  
1.  <span data-ttu-id="bf718-153">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**方和业务配置文件**页上，在**协议**部分中，右键单击具有批配置，需要到使用重写控制消息中，然后单击协议**属性**。</span><span class="sxs-lookup"><span data-stu-id="bf718-153">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Parties** node, and from the **Parties and Business Profiles** page, in the **Agreements** section, right-click the agreement that has the batch configuration that needs be to overridden using the control message, and then click **Properties**.</span></span> <span data-ttu-id="bf718-154">在**协议属性**对话框中，在单向协议选项卡上，单击**批配置**。</span><span class="sxs-lookup"><span data-stu-id="bf718-154">In the **Agreement Properties** dialog box, on the one-way agreement tab, click **Batch Configuration**.</span></span>  
  
2.  <span data-ttu-id="bf718-155">在**批配置**页上，单击想要有一个外部发布触发器，然后在批处理的选项卡**释放**部分中，选择**外部发布触发器**.</span><span class="sxs-lookup"><span data-stu-id="bf718-155">In the **Batch Configuration** page, click the tab for the batch for which you want to have an external release trigger, and then under the **Release** section, select **External release trigger**.</span></span>  
  
3.  <span data-ttu-id="bf718-156">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bf718-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf718-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf718-157">See Also</span></span>  
 <span data-ttu-id="bf718-158">[配置 EDI 批处理](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="bf718-158">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="bf718-159">如何创建接收位置</span><span class="sxs-lookup"><span data-stu-id="bf718-159">How to Create a Receive Location</span></span>](../core/how-to-create-a-receive-location.md)