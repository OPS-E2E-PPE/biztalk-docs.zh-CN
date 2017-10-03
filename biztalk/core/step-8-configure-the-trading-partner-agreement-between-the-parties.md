---
title: "步骤 8： 配置参与方之间贸易合作伙伴协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f532f85-3f09-4b60-b7bb-817ee3c79899
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25e49bf5dcae7324fa3b68fe5080d094b4a2f603
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-configure-the-trading-partner-agreement-between-the-parties"></a><span data-ttu-id="0395a-102">步骤 8： 配置参与方之间贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="0395a-102">Step 8: Configure the Trading Partner Agreement between the Parties</span></span>
<span data-ttu-id="0395a-103">![步骤 8 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span><span class="sxs-lookup"><span data-stu-id="0395a-103">![Step 8 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span></span>  
  
 <span data-ttu-id="0395a-104">在此步骤中，你可以配置 X12 贸易合作伙伴协议，以为两个贸易合作伙伴 OrderSystem 和 Fabrikam 之间交换 X12 消息定义参数。</span><span class="sxs-lookup"><span data-stu-id="0395a-104">In this step, you configure an X12 trading partner agreement to define the parameters for exchanging X12 messages between the two trading partners, OrderSystem and Fabrikam.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0395a-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="0395a-105">Prerequisites</span></span>  
 <span data-ttu-id="0395a-106">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="0395a-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-an-agreement"></a><span data-ttu-id="0395a-107">配置协议</span><span class="sxs-lookup"><span data-stu-id="0395a-107">To configure an agreement</span></span>  
  
1.  <span data-ttu-id="0395a-108">单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="0395a-108">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0395a-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**在控制台树中，然后在**方和业务配置文件**页上，右键单击**Fabrikam_Profile**，指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="0395a-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
3.  <span data-ttu-id="0395a-110">在**常规属性**页上，为**名称**文本框中，输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="0395a-110">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
4.  <span data-ttu-id="0395a-111">从**协议**下拉列表中，选择**X12**。</span><span class="sxs-lookup"><span data-stu-id="0395a-111">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
5.  <span data-ttu-id="0395a-112">在**第二个方**部分中，从**方**下拉列表中，选择**OrderSystem**。</span><span class="sxs-lookup"><span data-stu-id="0395a-112">In the **Second Party** section, from the **Party** drop-down list, select **OrderSystem**.</span></span>  
  
6.  <span data-ttu-id="0395a-113">在**第二个方**部分中，从**业务**下拉列表中，选择**OrderSystem_Profile**。</span><span class="sxs-lookup"><span data-stu-id="0395a-113">In the **Second Party** section, from the **Business** drop-down list, select **OrderSystem_Profile**.</span></span>  
  
     <span data-ttu-id="0395a-114">你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。</span><span class="sxs-lookup"><span data-stu-id="0395a-114">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  
  
7.  <span data-ttu-id="0395a-115">在**常规**选项卡上，在**常规属性**页上，在**常见主机设置**部分中，选择**打开 reporting**，，然后选择**用于报告的应用商店消息负载**。</span><span class="sxs-lookup"><span data-stu-id="0395a-115">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
8.  <span data-ttu-id="0395a-116">在上执行以下任务**Fabrikam-> OrderSystem**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0395a-116">Perform the following tasks on the **Fabrikam->OrderSystem** tab.</span></span>  
  
    1.  <span data-ttu-id="0395a-117">上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="0395a-117">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        |<span data-ttu-id="0395a-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0395a-118">Use this</span></span>|<span data-ttu-id="0395a-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0395a-119">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0395a-120">**发件人限定符 (ISA5)**</span><span class="sxs-lookup"><span data-stu-id="0395a-120">**Sender qualifier (ISA5)**</span></span>|<span data-ttu-id="0395a-121">选择**ZZ-双方约定**。</span><span class="sxs-lookup"><span data-stu-id="0395a-121">Select **ZZ - Mutually Defined**.</span></span>|  
        |<span data-ttu-id="0395a-122">**发件人标识符 (ISA6)**</span><span class="sxs-lookup"><span data-stu-id="0395a-122">**Sender identifier (ISA6)**</span></span>|<span data-ttu-id="0395a-123">输入**THEM**。</span><span class="sxs-lookup"><span data-stu-id="0395a-123">Enter **THEM**.</span></span>|  
        |<span data-ttu-id="0395a-124">**接收方限定符 (ISA7)**</span><span class="sxs-lookup"><span data-stu-id="0395a-124">**Receiver qualifier (ISA7)**</span></span>|<span data-ttu-id="0395a-125">选择**ZZ-双方约定**。</span><span class="sxs-lookup"><span data-stu-id="0395a-125">Select **ZZ - Mutually Defined**.</span></span>|  
        |<span data-ttu-id="0395a-126">**接收方标识符 (ISA8)**</span><span class="sxs-lookup"><span data-stu-id="0395a-126">**Receiver identifier (ISA8)**</span></span>|<span data-ttu-id="0395a-127">输入**美国**。</span><span class="sxs-lookup"><span data-stu-id="0395a-127">Enter **US**.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0395a-128"> 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。</span><span class="sxs-lookup"><span data-stu-id="0395a-128"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="0395a-129">它将与匹配的值**ISA5**， **ISA6**， **ISA7**，和**ISA8**与协议的属性中的交换标头中。</span><span class="sxs-lookup"><span data-stu-id="0395a-129">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0395a-130">此外将匹配的发件人限定符和 （而不是收件人限定符和标识符） 的标识符来解析协议。</span><span class="sxs-lookup"><span data-stu-id="0395a-130"> will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="0395a-131">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="0395a-131">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
    2.  <span data-ttu-id="0395a-132">上**确认**页上，在**交换设置**部分中，单击**997 预期**。</span><span class="sxs-lookup"><span data-stu-id="0395a-132">On the **Acknowledgements** page, under the **Interchange Settings** section, click **997 Expected**.</span></span> <span data-ttu-id="0395a-133">选择此复选框可以在收到 850 交换时提示接收管道生成 997 确认。</span><span class="sxs-lookup"><span data-stu-id="0395a-133">Selecting this check box prompts the receive pipeline to generate a 997 acknowledgment when it receives the 850 interchange..</span></span>  
  
    3.  <span data-ttu-id="0395a-134">上**验证**下页上**交换设置**部分中，请确保**交换控制编号 （检查重复的 isa13）**选项处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="0395a-134">On the **Validation** page under the **Interchange Settings** section, make sure **Interchange Control Number (Check for duplicate ISA13)** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0395a-135">清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。</span><span class="sxs-lookup"><span data-stu-id="0395a-135">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    4.  <span data-ttu-id="0395a-136">上**本地主机设置**页上，在**交换设置**部分中，清除**路由 ACK 发送管道请求-响应接收端口**。</span><span class="sxs-lookup"><span data-stu-id="0395a-136">On the **Local Host Settings** page, under the **Interchange Settings** section, clear **Route ACK to send pipeline on request-response receive port**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0395a-137">清除**路由 ACK**属性是必需的因为此解决方案返回通过单独的异步确认发送端口，而不是通过与双向关联的发送端口将同步确认接收端口。</span><span class="sxs-lookup"><span data-stu-id="0395a-137">Clearing the **Route ACK** property is required because this solution returns an asynchronous acknowledgment via a separate send port, rather than a synchronous acknowledgment via the send port associated with a two-way receive port.</span></span>  
  
    5.  <span data-ttu-id="0395a-138">上**本地主机设置**下页上**事务设置设置**部分中，选择要用于处理传入的交换的架构命名空间。</span><span class="sxs-lookup"><span data-stu-id="0395a-138">On the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span>  
  
        |<span data-ttu-id="0395a-139">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0395a-139">Use this</span></span>|<span data-ttu-id="0395a-140">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0395a-140">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0395a-141">**Default**</span><span class="sxs-lookup"><span data-stu-id="0395a-141">**Default**</span></span>|<span data-ttu-id="0395a-142">选中列中的复选框</span><span class="sxs-lookup"><span data-stu-id="0395a-142">Select the checkbox in the column</span></span>|  
        |<span data-ttu-id="0395a-143">**有关 ST1**</span><span class="sxs-lookup"><span data-stu-id="0395a-143">**For ST1**</span></span>|<span data-ttu-id="0395a-144">选择**850-采购订单**。</span><span class="sxs-lookup"><span data-stu-id="0395a-144">Select **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="0395a-145">**GS2**</span><span class="sxs-lookup"><span data-stu-id="0395a-145">**GS2**</span></span>|<span data-ttu-id="0395a-146">输入**THEM**。</span><span class="sxs-lookup"><span data-stu-id="0395a-146">Enter **THEM**.</span></span>|  
        |<span data-ttu-id="0395a-147">**目标 Namespace**</span><span class="sxs-lookup"><span data-stu-id="0395a-147">**Target Namespace**</span></span>|<span data-ttu-id="0395a-148">选择**http://schemas.microsoft.com/BizTalk/EDI/X12/2006**。</span><span class="sxs-lookup"><span data-stu-id="0395a-148">Select **http://schemas.microsoft.com/BizTalk/EDI/X12/2006**.</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="0395a-149">设置属性可以使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定处理传入 850 交换时使用的架构。</span><span class="sxs-lookup"><span data-stu-id="0395a-149">Setting the properties enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to determine the schema to be used in processing the incoming 850 interchange.</span></span> <span data-ttu-id="0395a-150">如果某一交换的 GS02 和 ST01 的值是在网格行上输入的，则将使用同一行的目标命名空间来确定要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="0395a-150">If an interchange has the values of GS02 and ST01 that are entered on a line of the grid, then the target namespace for the same line will be used to determine the schema to be used.</span></span>  
  
9. <span data-ttu-id="0395a-151">在上执行以下任务**OrderSystem-> Fabrikam**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0395a-151">Perform the following tasks on the **OrderSystem->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="0395a-152">上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="0395a-152">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        |<span data-ttu-id="0395a-153">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0395a-153">Use this</span></span>|<span data-ttu-id="0395a-154">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0395a-154">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0395a-155">**发件人限定符 (ISA5)**</span><span class="sxs-lookup"><span data-stu-id="0395a-155">**Sender qualifier (ISA5)**</span></span>|<span data-ttu-id="0395a-156">选择**ZZ-双方约定**。</span><span class="sxs-lookup"><span data-stu-id="0395a-156">Select **ZZ - Mutually Defined**.</span></span>|  
        |<span data-ttu-id="0395a-157">**发件人标识符 (ISA6)**</span><span class="sxs-lookup"><span data-stu-id="0395a-157">**Sender identifier (ISA6)**</span></span>|<span data-ttu-id="0395a-158">输入**美国**。</span><span class="sxs-lookup"><span data-stu-id="0395a-158">Enter **US**.</span></span>|  
        |<span data-ttu-id="0395a-159">**接收方限定符 (ISA7)**</span><span class="sxs-lookup"><span data-stu-id="0395a-159">**Receiver qualifier (ISA7)**</span></span>|<span data-ttu-id="0395a-160">选择**ZZ-双方约定**。</span><span class="sxs-lookup"><span data-stu-id="0395a-160">Select **ZZ - Mutually Defined**.</span></span>|  
        |<span data-ttu-id="0395a-161">**接收方标识符 (ISA8)**</span><span class="sxs-lookup"><span data-stu-id="0395a-161">**Receiver identifier (ISA8)**</span></span>|<span data-ttu-id="0395a-162">输入**THEM**。</span><span class="sxs-lookup"><span data-stu-id="0395a-162">Enter **THEM**.</span></span>|  
  
    2.  <span data-ttu-id="0395a-163">上**字符集和分隔符**页上，在**交换设置**部分中，选择**CR LF**为**后缀**属性。</span><span class="sxs-lookup"><span data-stu-id="0395a-163">On the **Charset and Separators** page, under the **Interchange Settings** section, select **CR LF** for the **Suffix** property.</span></span>  
  
    3.  <span data-ttu-id="0395a-164">上**发送端口**下页上**交换设置**部分中，将会将确认发送回 Fabrikam 发送端口相关联。</span><span class="sxs-lookup"><span data-stu-id="0395a-164">On the **Send Ports** page under the **Interchange Settings** section, associate the send port that will be sending the acknowledgement back to Fabrikam.</span></span> <span data-ttu-id="0395a-165">在**发送端口**网格下**名称**列中，单击空单元格，然后从下拉列表列表中，选择发送端口 (**toTHEM_997**) 创建用于发送 997到 Fabrikam 的确认。</span><span class="sxs-lookup"><span data-stu-id="0395a-165">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port (**toTHEM_997**) created for sending the 997 acknowledgement to Fabrikam.</span></span>  
  
    4.  <span data-ttu-id="0395a-166">上**包络线**下页上**事务设置设置**部分中，输入网格的第一行中的所有列的值。</span><span class="sxs-lookup"><span data-stu-id="0395a-166">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  
  
        |<span data-ttu-id="0395a-167">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0395a-167">Use this</span></span>|<span data-ttu-id="0395a-168">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0395a-168">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0395a-169">**Default**</span><span class="sxs-lookup"><span data-stu-id="0395a-169">**Default**</span></span>|<span data-ttu-id="0395a-170">选择中的复选框**默认**列。</span><span class="sxs-lookup"><span data-stu-id="0395a-170">Select the checkbox in the **Default** column.</span></span> <span data-ttu-id="0395a-171">**注意：**当作为默认值的值选择此行**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，和**目标命名空间**不的匹配项消息。</span><span class="sxs-lookup"><span data-stu-id="0395a-171">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="0395a-172">**事务类型**</span><span class="sxs-lookup"><span data-stu-id="0395a-172">**Transaction Type**</span></span>|<span data-ttu-id="0395a-173">选择你的测试消息的消息类型**850-采购订单**。</span><span class="sxs-lookup"><span data-stu-id="0395a-173">Select the message type of your test message, **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="0395a-174">**版本/发行版**</span><span class="sxs-lookup"><span data-stu-id="0395a-174">**Version/Release**</span></span>|<span data-ttu-id="0395a-175">输入的 EDI 版本中， **00401**。</span><span class="sxs-lookup"><span data-stu-id="0395a-175">Enter the EDI version, **00401**.</span></span>|  
        |<span data-ttu-id="0395a-176">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="0395a-176">**Target namespace**</span></span>|<span data-ttu-id="0395a-177">选择**http://schemas.microsoft.com/Edi/X12**。</span><span class="sxs-lookup"><span data-stu-id="0395a-177">Select **http://schemas.microsoft.com/Edi/X12**.</span></span>|  
        |<span data-ttu-id="0395a-178">**GS1**</span><span class="sxs-lookup"><span data-stu-id="0395a-178">**GS1**</span></span>|<span data-ttu-id="0395a-179">验证**PO-采购订单 (850)**选择。</span><span class="sxs-lookup"><span data-stu-id="0395a-179">Verify that **PO - Purchase Order (850)** is selected.</span></span>|  
        |<span data-ttu-id="0395a-180">**GS2**</span><span class="sxs-lookup"><span data-stu-id="0395a-180">**GS2**</span></span>|<span data-ttu-id="0395a-181">输入**1234567**。</span><span class="sxs-lookup"><span data-stu-id="0395a-181">Enter **1234567**.</span></span><br /><br /> <span data-ttu-id="0395a-182">**发件人应用程序 id。**</span><span class="sxs-lookup"><span data-stu-id="0395a-182">**Sender Application ID.**</span></span>|  
        |<span data-ttu-id="0395a-183">**GS3**</span><span class="sxs-lookup"><span data-stu-id="0395a-183">**GS3**</span></span>|<span data-ttu-id="0395a-184">输入**0000000**。</span><span class="sxs-lookup"><span data-stu-id="0395a-184">Enter **0000000**.</span></span><br /><br /> <span data-ttu-id="0395a-185">**接收方应用程序 id。**</span><span class="sxs-lookup"><span data-stu-id="0395a-185">**Receiver Application ID.**</span></span>|  
        |<span data-ttu-id="0395a-186">**GS4**</span><span class="sxs-lookup"><span data-stu-id="0395a-186">**GS4**</span></span>|<span data-ttu-id="0395a-187">选择**CCYYMMDD**。</span><span class="sxs-lookup"><span data-stu-id="0395a-187">Select **CCYYMMDD**.</span></span> <span data-ttu-id="0395a-188">**注意：**你需要在下拉列表中选择值，而不仅仅是在要显示默认值的字段中单击。</span><span class="sxs-lookup"><span data-stu-id="0395a-188">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="0395a-189">如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。</span><span class="sxs-lookup"><span data-stu-id="0395a-189">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="0395a-190">**GS5**</span><span class="sxs-lookup"><span data-stu-id="0395a-190">**GS5**</span></span>|<span data-ttu-id="0395a-191">选择**HHMM**。</span><span class="sxs-lookup"><span data-stu-id="0395a-191">Select **HHMM**.</span></span>|  
        |<span data-ttu-id="0395a-192">**GS7**</span><span class="sxs-lookup"><span data-stu-id="0395a-192">**GS7**</span></span>|<span data-ttu-id="0395a-193">选择**X 的公认的标准委员会 X12**。</span><span class="sxs-lookup"><span data-stu-id="0395a-193">Select **X - Accredited Standards Committee X12**.</span></span>|  
        |<span data-ttu-id="0395a-194">**GS8**</span><span class="sxs-lookup"><span data-stu-id="0395a-194">**GS8**</span></span>|<span data-ttu-id="0395a-195">验证**00401**已输入。</span><span class="sxs-lookup"><span data-stu-id="0395a-195">Verify that **00401** has been entered.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0395a-196">将为 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值的出站确认 GS08 设置值**事务类型**，**版本/发行版**，和**目标命名空间**。</span><span class="sxs-lookup"><span data-stu-id="0395a-196"> will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="0395a-197">发送管道尝试将事务集类型、X12 版本和目标命名空间与消息标头中的对应值相匹配。</span><span class="sxs-lookup"><span data-stu-id="0395a-197">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="0395a-198">如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，和**目标命名空间**值。</span><span class="sxs-lookup"><span data-stu-id="0395a-198">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  
  
10. <span data-ttu-id="0395a-199">单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="0395a-199">Click **Apply**.</span></span>  
  
11. <span data-ttu-id="0395a-200">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0395a-200">Click **OK**.</span></span> <span data-ttu-id="0395a-201">新添加的协议被列入**协议**部分**方和业务配置文件**窗格。</span><span class="sxs-lookup"><span data-stu-id="0395a-201">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="0395a-202">默认情况下，启用新添加的协议。</span><span class="sxs-lookup"><span data-stu-id="0395a-202">The newly added agreement is enabled by default.</span></span>  
  
12. <span data-ttu-id="0395a-203">重新启动 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="0395a-203">Restart the BizTalk Service.</span></span> <span data-ttu-id="0395a-204">在 BizTalk Server 管理控制台中，在**平台设置**，单击**主机实例**，右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="0395a-204">In the BizTalk Server Administration Console, under **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0395a-205">激活或停用 EDI 状态报告功能后，需要重新启动 BizTalk 服务，以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="0395a-205">The BizTalk Service needs to be restarted after EDI status reporting has been activated or deactivated for the change to take effect.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0395a-206">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0395a-206">Next Steps</span></span>  
 <span data-ttu-id="0395a-207">测试 EDI 解决方案中所述[步骤 9： 测试 EDI 解决方案](../core/step-9-test-the-edi-solution.md)</span><span class="sxs-lookup"><span data-stu-id="0395a-207">Test the EDI solution as described in [Step 9: Test the EDI Solution](../core/step-9-test-the-edi-solution.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0395a-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0395a-208">See Also</span></span>  
 [<span data-ttu-id="0395a-209">配置编码协议属性</span><span class="sxs-lookup"><span data-stu-id="0395a-209">Configuring Encoding Agreement Properties</span></span>](../core/configuring-encoding-agreement-properties.md)