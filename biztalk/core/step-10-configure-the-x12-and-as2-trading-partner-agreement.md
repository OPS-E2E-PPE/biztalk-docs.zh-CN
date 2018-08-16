---
title: 步骤 10： 配置 X12 和 AS2 贸易合作伙伴协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8fcdb3af-727a-4d20-9dcf-cf162e7d3398
caps.latest.revision: 46
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beae325fa0a0cfcc2c4a63f3134ccb39e5e243d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996038"
---
# <a name="step-10-configure-the-x12-and-as2-trading-partner-agreement"></a><span data-ttu-id="9da30-102">步骤 10： 配置 X12 和 AS2 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="9da30-102">Step 10: Configure the X12 and AS2 Trading Partner Agreement</span></span>
<span data-ttu-id="9da30-103">![步骤 10 11](../core/media/tut-step10-of-11.gif "Tut_Step10_of_11")</span><span class="sxs-lookup"><span data-stu-id="9da30-103">![Step 10 of 11](../core/media/tut-step10-of-11.gif "Tut_Step10_of_11")</span></span>  

 <span data-ttu-id="9da30-104">在此步骤中，你将 X12 和 AS2 贸易合作伙伴协议设置为通过 HTTP 传输 EDIINT/AS2 编码消息。</span><span class="sxs-lookup"><span data-stu-id="9da30-104">In this step you set up X12 and AS2 trading partner agreements to transport an EDIINT/AS2-encoded message over HTTP.</span></span> <span data-ttu-id="9da30-105">该 Fabrikam 参与方将 EDI 交换发送至 Contoso，后者向 Fabrikam 返回 997 确认和异步 MDN。</span><span class="sxs-lookup"><span data-stu-id="9da30-105">This Fabrikam party sends the EDI interchange to Contoso, which returns the 997 acknowledgment and an asynchronous MDN to Fabrikam.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="9da30-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="9da30-106">Prerequisites</span></span>  
 <span data-ttu-id="9da30-107">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="9da30-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-create-an-as2-agreement"></a><span data-ttu-id="9da30-108">创建 AS2 协议</span><span class="sxs-lookup"><span data-stu-id="9da30-108">To create an AS2 agreement</span></span>  

1. <span data-ttu-id="9da30-109">单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9da30-109">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="9da30-110">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**在控制台树中，然后在**参与方和业务配置文件**页上，右键单击**Fabrikam_Profile**，指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="9da30-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

3. <span data-ttu-id="9da30-111">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="9da30-111">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

4. <span data-ttu-id="9da30-112">从**协议**下拉列表中，选择**AS2**。</span><span class="sxs-lookup"><span data-stu-id="9da30-112">From the **Protocol** drop-down list, select **AS2**.</span></span>  

5. <span data-ttu-id="9da30-113">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="9da30-113">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

6. <span data-ttu-id="9da30-114">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。</span><span class="sxs-lookup"><span data-stu-id="9da30-114">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="9da30-115">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="9da30-115">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  

7. <span data-ttu-id="9da30-116">在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**。</span><span class="sxs-lookup"><span data-stu-id="9da30-116">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**.</span></span>  

8. <span data-ttu-id="9da30-117">在执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9da30-117">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1.  <span data-ttu-id="9da30-118">上**标识符**页上，输入值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="9da30-118">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="9da30-119">有关**AS2-从**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="9da30-119">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="9da30-120">有关**AS2-To**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="9da30-120">For **AS2- To**, enter `Contoso`.</span></span>  

   2.  <span data-ttu-id="9da30-121">上**验证**页上，选择**使用的验证和 MDN 的协议设置而非消息标头**复选框</span><span class="sxs-lookup"><span data-stu-id="9da30-121">On the **Validation** page, select the **Use agreement settings for validation and MDN instead of message header** check box</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="9da30-122">设置本属性可以确保在生成 MDN 时会使用的参与方属性，而非接收的 AS2 消息的 AS2 标头。</span><span class="sxs-lookup"><span data-stu-id="9da30-122">Setting this property ensures that the party properties will be used when generating the MDN, rather than the AS2 headers of the received AS2 message.</span></span>  

   3.  <span data-ttu-id="9da30-123">在中**确认 (Mdn)** 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9da30-123">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  

       1.  <span data-ttu-id="9da30-124">选择**请求 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="9da30-124">Select the **Request MDN** check box.</span></span>  

       2.  <span data-ttu-id="9da30-125">请确保**请求经过签名的 MDN**清除复选框。</span><span class="sxs-lookup"><span data-stu-id="9da30-125">Make sure the **Request Signed MDN** check box is cleared.</span></span>  

       3.  <span data-ttu-id="9da30-126">选择**请求异步 MDN**复选框。</span><span class="sxs-lookup"><span data-stu-id="9da30-126">Select the **Request asynchronous MDN** check box.</span></span>  

       4.  <span data-ttu-id="9da30-127">在中**回执送达选项 (URL)** 文字框中，输入`http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`。</span><span class="sxs-lookup"><span data-stu-id="9da30-127">In the **Receipt-Delivery-Option (URL)** text box, enter `http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`.</span></span>  

9. <span data-ttu-id="9da30-128">在执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9da30-128">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   1. <span data-ttu-id="9da30-129">上**标识符**页上，输入值**AS2-从**并**AS2-到**。</span><span class="sxs-lookup"><span data-stu-id="9da30-129">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="9da30-130">有关**AS2-从**，输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="9da30-130">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="9da30-131">有关**AS2-To**，输入`Fabrikam`。</span><span class="sxs-lookup"><span data-stu-id="9da30-131">For **AS2- To**, enter `Fabrikam`.</span></span>  

   2. <span data-ttu-id="9da30-132">上**发送端口**页**交换设置**部分的**发送端口**列表中，为**名称**选择**Send_Async_997**。</span><span class="sxs-lookup"><span data-stu-id="9da30-132">On the **Send Ports** page under the **Interchange Settings** section, in the **Send Ports** list, for **Name** select **Send_Async_997**.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="9da30-133">Send_Async_997 发送端口需要输入到**发送端口**列表，以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以解析传出 997 消息的参与方。</span><span class="sxs-lookup"><span data-stu-id="9da30-133">The Send_Async_997 send port needs to be entered into the **Send Ports** list so that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can resolve the party for the outgoing 997 message.</span></span> <span data-ttu-id="9da30-134">发送管道将发送端口的名称与协议属性中的发送端口进行匹配。</span><span class="sxs-lookup"><span data-stu-id="9da30-134">The send pipeline matches the name of the send port with the send port in the agreement properties.</span></span> <span data-ttu-id="9da30-135">这是必要的，因为在这种情况下，揂“AS2 收件人”属性在消息上下文中是不会升级的，该属性是发送管道解析参与方时首先要尝试进行的匹配。</span><span class="sxs-lookup"><span data-stu-id="9da30-135">This is necessary because in this case, the AS2-To property is not promoted in the context of the message, which is the first match that the send pipeline attempts to make to resolve the party.</span></span> <span data-ttu-id="9da30-136">有关详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9da30-136">For more information, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  

10. <span data-ttu-id="9da30-137">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="9da30-137">Click **Apply**.</span></span>  

11. <span data-ttu-id="9da30-138">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9da30-138">Click **OK**.</span></span> <span data-ttu-id="9da30-139">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="9da30-139">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="9da30-140">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="9da30-140">The newly added agreement is enabled by default.</span></span>  

### <a name="to-create-an-x12-agreement"></a><span data-ttu-id="9da30-141">创建 X12 协议</span><span class="sxs-lookup"><span data-stu-id="9da30-141">To create an X12 agreement</span></span>  

1. <span data-ttu-id="9da30-142">右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="9da30-142">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="9da30-143">在**常规属性**页上，对于**名称**文字框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="9da30-143">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3. <span data-ttu-id="9da30-144">从**协议**下拉列表中，选择**X12**。</span><span class="sxs-lookup"><span data-stu-id="9da30-144">From the **Protocol** drop-down list, select **X12**.</span></span>  

4. <span data-ttu-id="9da30-145">在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="9da30-145">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5. <span data-ttu-id="9da30-146">在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。</span><span class="sxs-lookup"><span data-stu-id="9da30-146">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="9da30-147">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡可用于配置一个单向 X12 协议。</span><span class="sxs-lookup"><span data-stu-id="9da30-147">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way X12 agreement.</span></span>  

6. <span data-ttu-id="9da30-148">在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。</span><span class="sxs-lookup"><span data-stu-id="9da30-148">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  

7. <span data-ttu-id="9da30-149">在执行以下任务**Fabrikam-> Contoso**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9da30-149">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1. <span data-ttu-id="9da30-150">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="9da30-150">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span> <span data-ttu-id="9da30-151">对于本教程中，设置**ISA5**到**ZZ**， **ISA6**到**7654321**， **ISA7**到**ZZ**，并**ISA8**到**1234567**。</span><span class="sxs-lookup"><span data-stu-id="9da30-151">For this tutorial, set **ISA5** to **ZZ**, **ISA6** to **7654321**, **ISA7** to **ZZ**, and **ISA8** to **1234567**.</span></span>  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9da30-152"> 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。</span><span class="sxs-lookup"><span data-stu-id="9da30-152"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="9da30-153">它将匹配的值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**与协议属性中的交换标头中。</span><span class="sxs-lookup"><span data-stu-id="9da30-153">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9da30-154"> 此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。</span><span class="sxs-lookup"><span data-stu-id="9da30-154"> will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="9da30-155">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="9da30-155">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  

   2. <span data-ttu-id="9da30-156">上**确认**页**交换设置**部分中，选择**预期的 997**复选框。</span><span class="sxs-lookup"><span data-stu-id="9da30-156">On the **Acknowledgements** page under the **Interchange Settings** section, select the **997 Expected** check box.</span></span>  

   3. <span data-ttu-id="9da30-157">上**验证**页**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="9da30-157">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="9da30-158">清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。</span><span class="sxs-lookup"><span data-stu-id="9da30-158">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  

   4. <span data-ttu-id="9da30-159">上**本地主机设置**页**交换设置**部分中，在**接收方设置**，则清除**将确认路由到发送管道请求-响应接收端口**。</span><span class="sxs-lookup"><span data-stu-id="9da30-159">On the **Local Host Settings** page under the **Interchange Settings** section, under **Receiver’s Settings**, clear **Route ACK to send pipeline on request-response receive port**.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="9da30-160">清除此属性将使你可通过单独的发送端口发送 997 确认，而不是通过与双向接收端口关联的发送端口发送该确认。</span><span class="sxs-lookup"><span data-stu-id="9da30-160">Clearing this property enables you to send the 997 acknowledgment via a separate send port, rather than sending it over the send port associated with the two-way receive port.</span></span>  

8. <span data-ttu-id="9da30-161">在执行以下任务**Contoso-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9da30-161">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   1. <span data-ttu-id="9da30-162">上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="9da30-162">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  <span data-ttu-id="9da30-163">对于本演练中，设置**ISA5**到**ZZ**， **ISA6**到**1234567**， **ISA7**到**ZZ**，并**ISA8**到**7654321**。</span><span class="sxs-lookup"><span data-stu-id="9da30-163">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **1234567**, **ISA7** to **ZZ**, and **ISA8** to **7654321**.</span></span>  

   2. <span data-ttu-id="9da30-164">上**字符集和分隔符**页**交换设置**部分中，对于**后缀**，选择**CR LF**。</span><span class="sxs-lookup"><span data-stu-id="9da30-164">On the **Charset and Separators** page under the **Interchange Settings** section, for **Suffix**, select **CR LF**.</span></span>  

   3. <span data-ttu-id="9da30-165">上**信封**页**事务集设置**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9da30-165">On the **Envelopes** page under the **Transaction Set Settings** section, do the following:</span></span>  


      |       <span data-ttu-id="9da30-166">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9da30-166">Use this</span></span>       |                                                                                                                                              <span data-ttu-id="9da30-167">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9da30-167">To do this</span></span>                                                                                                                                               |
      |----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     <span data-ttu-id="9da30-168">**Default**</span><span class="sxs-lookup"><span data-stu-id="9da30-168">**Default**</span></span>      |              <span data-ttu-id="9da30-169">选择**默认**。</span><span class="sxs-lookup"><span data-stu-id="9da30-169">Select **Default**.</span></span> <span data-ttu-id="9da30-170">**注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，并且**目标命名空间**不是消息的匹配项。</span><span class="sxs-lookup"><span data-stu-id="9da30-170">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>              |
      | <span data-ttu-id="9da30-171">**事务类型**</span><span class="sxs-lookup"><span data-stu-id="9da30-171">**Transaction Type**</span></span> |                                                                                                          <span data-ttu-id="9da30-172">例如，选择你的测试消息的消息类型**864 – 文本消息**。</span><span class="sxs-lookup"><span data-stu-id="9da30-172">Select the message type of your test message, for example, **864 – Text Message**.</span></span>                                                                                                           |
      | <span data-ttu-id="9da30-173">**版本/发行版**</span><span class="sxs-lookup"><span data-stu-id="9da30-173">**Version/Release**</span></span>  |                                                                                                                                           <span data-ttu-id="9da30-174">输入**00401**。</span><span class="sxs-lookup"><span data-stu-id="9da30-174">Enter **00401**.</span></span>                                                                                                                                            |
      | <span data-ttu-id="9da30-175">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="9da30-175">**Target namespace**</span></span> |                                                                                                                    <span data-ttu-id="9da30-176">选择**<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**。</span><span class="sxs-lookup"><span data-stu-id="9da30-176">Select **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**.</span></span>                                                                                                                    |
      |       <span data-ttu-id="9da30-177">**GS1**</span><span class="sxs-lookup"><span data-stu-id="9da30-177">**GS1**</span></span>        |                                                                                                <span data-ttu-id="9da30-178">验证是否选择测试消息的消息类型，例如， **TX-文本消息 (864)**。</span><span class="sxs-lookup"><span data-stu-id="9da30-178">Verify that the message type of the test message is selected, for example, **TX - Text Message (864)**.</span></span>                                                                                                |
      |       <span data-ttu-id="9da30-179">**GS2**</span><span class="sxs-lookup"><span data-stu-id="9da30-179">**GS2**</span></span>        |                                                                                                                                             <span data-ttu-id="9da30-180">输入**01**。</span><span class="sxs-lookup"><span data-stu-id="9da30-180">Enter **01**.</span></span>                                                                                                                                             |
      |       <span data-ttu-id="9da30-181">**GS3**</span><span class="sxs-lookup"><span data-stu-id="9da30-181">**GS3**</span></span>        |                                                                                                                                          <span data-ttu-id="9da30-182">输入**7654321**。</span><span class="sxs-lookup"><span data-stu-id="9da30-182">Enter **7654321**.</span></span>                                                                                                                                           |
      |       <span data-ttu-id="9da30-183">**GS4**</span><span class="sxs-lookup"><span data-stu-id="9da30-183">**GS4**</span></span>        | <span data-ttu-id="9da30-184">选择所需的日期格式。</span><span class="sxs-lookup"><span data-stu-id="9da30-184">Select the date format that you want.</span></span> <span data-ttu-id="9da30-185">选择**CCYYMMDD**。</span><span class="sxs-lookup"><span data-stu-id="9da30-185">Select **CCYYMMDD**.</span></span> <span data-ttu-id="9da30-186">**注意：** 需要下拉列表中选择一个值，而不仅仅是单击该字段以显示默认值。</span><span class="sxs-lookup"><span data-stu-id="9da30-186">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="9da30-187">如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。</span><span class="sxs-lookup"><span data-stu-id="9da30-187">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span> |
      |       <span data-ttu-id="9da30-188">**GS5**</span><span class="sxs-lookup"><span data-stu-id="9da30-188">**GS5**</span></span>        |                                                                                                                      <span data-ttu-id="9da30-189">选择所需的时间格式。</span><span class="sxs-lookup"><span data-stu-id="9da30-189">Select the time format that you want.</span></span> <span data-ttu-id="9da30-190">选择**HHMMSSdd**。</span><span class="sxs-lookup"><span data-stu-id="9da30-190">Select **HHMMSSdd**.</span></span>                                                                                                                       |
      |       <span data-ttu-id="9da30-191">**GS7**</span><span class="sxs-lookup"><span data-stu-id="9da30-191">**GS7**</span></span>        |                                                                                                                   <span data-ttu-id="9da30-192">选择**揟-运输数据协调委员会 (TDCC)**。</span><span class="sxs-lookup"><span data-stu-id="9da30-192">Select **T - Transportation Data Coordinating Committee (TDCC)**.</span></span>                                                                                                                   |
      |       <span data-ttu-id="9da30-193">**GS8**</span><span class="sxs-lookup"><span data-stu-id="9da30-193">**GS8**</span></span>        |                                                                                                                      <span data-ttu-id="9da30-194">验证是否已作为输入 EDI 版本**00401**。</span><span class="sxs-lookup"><span data-stu-id="9da30-194">Verify that the EDI version has been entered as **00401**.</span></span>                                                                                                                       |


9. <span data-ttu-id="9da30-195">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="9da30-195">Click **Apply**.</span></span>  

10. <span data-ttu-id="9da30-196">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9da30-196">Click **OK**.</span></span> <span data-ttu-id="9da30-197">中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="9da30-197">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="9da30-198">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="9da30-198">The newly added agreement is enabled by default.</span></span>  

11. <span data-ttu-id="9da30-199">重新启动 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="9da30-199">Restart the BizTalk service.</span></span> <span data-ttu-id="9da30-200">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**平台设置**，单击**主机实例**，右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="9da30-200">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="9da30-201">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9da30-201">Next Steps</span></span>  
 <span data-ttu-id="9da30-202">您将测试 AS2 解决方案，如中所述[步骤 11： 测试 AS2 解决方案](../core/step-11-test-the-as2-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="9da30-202">You test the AS2 solution, as described in [Step 11: Test the AS2 Solution](../core/step-11-test-the-as2-solution.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="9da30-203">请参阅</span><span class="sxs-lookup"><span data-stu-id="9da30-203">See Also</span></span>  
 <span data-ttu-id="9da30-204">[配置 AS2 属性](../core/configuring-as2-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9da30-204">[Configuring AS2 Properties](../core/configuring-as2-properties.md) </span></span>  
 [<span data-ttu-id="9da30-205">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="9da30-205">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)