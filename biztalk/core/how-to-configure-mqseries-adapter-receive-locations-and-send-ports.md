---
title: 如何配置 MQSeries 适配器接收位置和发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, receive ports
- receive ports, MQSeries adapters
- MQSeries adapters, send ports
- configuring [MQSeries adapters], send ports
- configuring [MQSeries adapters], receive ports
- send ports, MQSeries adapters
- configuring [MQSeries adapters], receive locations
- MQSeries adapters, receive locations
- receive locations, MQSeries adapters
ms.assetid: 552aacde-9ec0-4459-b369-073676b6f926
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c31a15615d74a2ca1471559aa25772725821889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250509"
---
# <a name="how-to-configure-mqseries-adapter-receive-locations-and-send-ports"></a><span data-ttu-id="ec547-102">如何配置 MQSeries 适配器接收位置和发送端口</span><span class="sxs-lookup"><span data-stu-id="ec547-102">How to Configure MQSeries Adapter Receive Locations and Send Ports</span></span>
<span data-ttu-id="ec547-103">对接收位置和发送端口均可配置 MQSeries 适配器。</span><span class="sxs-lookup"><span data-stu-id="ec547-103">You can configure the MQSeries adapter for both receive locations and send ports.</span></span>  
  
## <a name="to-configure-receive-locations-and-send-ports"></a><span data-ttu-id="ec547-104">配置接收位置和发送端口</span><span class="sxs-lookup"><span data-stu-id="ec547-104">To configure receive locations and send ports</span></span>  
 <span data-ttu-id="ec547-105">**创建接收端口和接收位置：**</span><span class="sxs-lookup"><span data-stu-id="ec547-105">**To create the receive port and receive location:**</span></span>  
  
1.  <span data-ttu-id="ec547-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你要在其中创建接收位置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec547-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application in which you want to create a receive location.</span></span>  
  
2.  <span data-ttu-id="ec547-107">右键单击**接收端口**节点，单击**新建，** 和指向**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="ec547-107">Right-click the **Receive Ports** node, click **New,** and point to **One-Way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="ec547-108">输入中的相应值**端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="ec547-108">Enter the appropriate values in the **Port Properties** dialog box.</span></span> <span data-ttu-id="ec547-109">璝惠**端口属性**对话框中，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="ec547-109">For information about the **Port Properties** dialog box, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  
  
4.  <span data-ttu-id="ec547-110">在 BizTalk Server 管理控制台中，右键单击**接收端口**节点你创建，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ec547-110">In the BizTalk Server Administration console, right-click the **Receive Port** node you created and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="ec547-111">在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，然后单击**新建**右窗格中。</span><span class="sxs-lookup"><span data-stu-id="ec547-111">In the **Receive Port Properties** dialog box, in the left pane, select **Receive Locations**, and then click **New** in the right pane.</span></span>  
  
6.  <span data-ttu-id="ec547-112">在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**MQSeries**从下拉列表列表，，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ec547-112">In the **Receive Location Properties** dialog box, in the **Transport** section next to **Type**, select **MQSeries** from the drop-down list, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="ec547-113">在**MQSeries 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec547-113">In the **MQSeries Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ec547-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ec547-114">Use this</span></span>|<span data-ttu-id="ec547-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ec547-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ec547-116">**批大小**</span><span class="sxs-lookup"><span data-stu-id="ec547-116">**Batch Size**</span></span>|<span data-ttu-id="ec547-117">确定消息批的最大大小 (KB)。</span><span class="sxs-lookup"><span data-stu-id="ec547-117">Determine the maximum size of a batch of messages in KB.</span></span> <span data-ttu-id="ec547-118">**注意：** 如果**事务支持**接收位置的属性设置为**是**; 每个消息批提交到 MessageBox 数据库的 Microsoft 上下文分布式的事务处理协调器 (MSDTC) 事务。</span><span class="sxs-lookup"><span data-stu-id="ec547-118">**Note:**  If the **Transaction Supported** property for the receive location is set to **Yes**; each message batch is submitted to the MessageBox database under the context of a Microsoft Distributed Transaction Coordinator (MSDTC) transaction.</span></span> <span data-ttu-id="ec547-119">为消息批创建的 MSDTC 事务将始终处于打开状态，直到该批中的所有消息都已保存到 MessageBox 数据库并已放置到相应的订户队列中为止。</span><span class="sxs-lookup"><span data-stu-id="ec547-119">The MSDTC transaction that is created for a message batch remains open until every message in the batch has been persisted to the MessageBox and placed in the appropriate subscriber queue.</span></span> <span data-ttu-id="ec547-120">因此此 MSDTC 事务的持续时间增加作为**最大批处理大小**增加参数。</span><span class="sxs-lookup"><span data-stu-id="ec547-120">Therefore the duration of this MSDTC transaction is increased as the **Maximum Batch Size** parameter is increased.</span></span> <span data-ttu-id="ec547-121">因为同时具有大量的 MSDTC 事务打开可以对总体性能带来负面影响**最大批处理大小**参数不应设置为非常大的值如果启用事务支持。</span><span class="sxs-lookup"><span data-stu-id="ec547-121">Since having a large number of MSDTC transactions open simultaneously can negatively impact overall performance, the **Maximum Batch Size** parameter should not be set to a very large value when transaction support is enabled.</span></span>|  
    |<span data-ttu-id="ec547-122">**有序的处理**</span><span class="sxs-lookup"><span data-stu-id="ec547-122">**Ordered Processing**</span></span>|<span data-ttu-id="ec547-123">将 MQSeries 设置为从 MQSeries 队列接收消息时保持消息的顺序。</span><span class="sxs-lookup"><span data-stu-id="ec547-123">Set MQSeries to maintain the order of the messages as they are received from the MQSeries queue.</span></span> <span data-ttu-id="ec547-124">**注意：** 为了保持顺序特定队列的消息，只有一个 BizTalk 主机实例可能会从队列接收消息该 MQSeries。</span><span class="sxs-lookup"><span data-stu-id="ec547-124">**Note:**  To maintain message ordering for a specific queue, only one BizTalk Host instance may be receiving messages from that MQSeries queue.</span></span> <br /><br /> <span data-ttu-id="ec547-125">**默认值：** False</span><span class="sxs-lookup"><span data-stu-id="ec547-125">**Default:** False</span></span>|  
    |<span data-ttu-id="ec547-126">**队列**</span><span class="sxs-lookup"><span data-stu-id="ec547-126">**Queue**</span></span>|<span data-ttu-id="ec547-127">使用中的信息填充**队列定义**对话框。</span><span class="sxs-lookup"><span data-stu-id="ec547-127">Filled in with information from the **Queue Definition** dialog box.</span></span> <span data-ttu-id="ec547-128">**注意：** 对要发送的 URI 端口或接收位置不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="ec547-128">**Note:**  The URI for a send port or receive location cannot exceed 256 characters.</span></span>|  
    |<span data-ttu-id="ec547-129">**事务性**</span><span class="sxs-lookup"><span data-stu-id="ec547-129">**Transactional**</span></span>|<span data-ttu-id="ec547-130">此适配器将在 BizTalk Server 和 MQSeries 服务器之间开始 Microsoft 分布式事务处理协调器 (DTC) 事务。</span><span class="sxs-lookup"><span data-stu-id="ec547-130">The adapter begins a Microsoft Distributed Transaction Coordinator (DTC) transaction between BizTalk Server and MQSeries Server.</span></span> <span data-ttu-id="ec547-131">当设置为**否**，就不能保证的消息传递。</span><span class="sxs-lookup"><span data-stu-id="ec547-131">When set to **No**, there is no guarantee of message delivery.</span></span><br /><br /> <span data-ttu-id="ec547-132">**默认值：** False</span><span class="sxs-lookup"><span data-stu-id="ec547-132">**Default:** False</span></span>|  
  
8.  <span data-ttu-id="ec547-133">在**MQSeries 传输属性**对话框中，单击**确定**来填充**地址 (URI)** 框中**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="ec547-133">In the **MQSeries Transport Properties** dialog box, click **OK** to populate the **Address (URI)** box in the **Receive Location Properties** dialog box.</span></span>  
  
9. <span data-ttu-id="ec547-134">在**接收位置属性**对话框框中，输入适当的值来完成接收位置的配置，然后单击**确定**以保存设置。</span><span class="sxs-lookup"><span data-stu-id="ec547-134">In the **Receive Location Properties** dialog box, enter the appropriate values to complete the configuration of the receive location, and click **OK** to save settings.</span></span> <span data-ttu-id="ec547-135">璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="ec547-135">For information about the **Receive Locations Properties** dialog box, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
 <span data-ttu-id="ec547-136">**若要创建发送端口：**</span><span class="sxs-lookup"><span data-stu-id="ec547-136">**To create the send port:**</span></span>  
  
1.  <span data-ttu-id="ec547-137">在 BizTalk Server 管理控制台中，创建一个新的静态发送端口。</span><span class="sxs-lookup"><span data-stu-id="ec547-137">In the BizTalk Server Administration console, create a new static send port.</span></span> <span data-ttu-id="ec547-138">请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ec547-138">See [How to Create a Send Port](../core/how-to-create-a-send-port2.md) for more information.</span></span> <span data-ttu-id="ec547-139">配置所有发送端口选项并指定**MQSeries**为**类型**选项**传输**部分**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ec547-139">Configure all of the send port options and specify **MQSeries** for the **Type** option in the **Transport** section of the **General** tab.</span></span>  
  
2.  <span data-ttu-id="ec547-140">上**常规**选项卡上，在**传输**部分中，单击**配置**按钮旁边**类型**。</span><span class="sxs-lookup"><span data-stu-id="ec547-140">On the **General** tab, in the **Transport** section, click the **Configure** button next to **Type**.</span></span>  
  
3.  <span data-ttu-id="ec547-141">在**MQSeries 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ec547-141">In the **MQSeries Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ec547-142">属性</span><span class="sxs-lookup"><span data-stu-id="ec547-142">Property</span></span>|<span data-ttu-id="ec547-143">Description</span><span class="sxs-lookup"><span data-stu-id="ec547-143">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="ec547-144">**碎片大小**</span><span class="sxs-lookup"><span data-stu-id="ec547-144">**Fragmentation Size**</span></span>|<span data-ttu-id="ec547-145">设置在适配器和 MQSAgent 之间发送消息时消息块的大小（KB）</span><span class="sxs-lookup"><span data-stu-id="ec547-145">Sets the message chunk size in KB for messages as they are sent between the adapter and MQSAgent</span></span>|  
    |<span data-ttu-id="ec547-146">**SSO 关联应用程序**</span><span class="sxs-lookup"><span data-stu-id="ec547-146">**SSO Affiliate Application**</span></span>|<span data-ttu-id="ec547-147">设置单一登录 (SSO) 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec547-147">Sets the Single Sign-On (SSO) affiliate application.</span></span> <span data-ttu-id="ec547-148">用于的用户 ID 和密码 SSO **MQMD_UserIdentifier**，和**MQIIH_Authenticator** (或**MQCIH_Authenticator**) 属性分别。</span><span class="sxs-lookup"><span data-stu-id="ec547-148">The user ID and password from SSO are used for the **MQMD_UserIdentifier**, and the **MQIIH_Authenticator** (or **MQCIH_Authenticator**) property respectively.</span></span><br /><br /> <span data-ttu-id="ec547-149">**默认值：** 空白</span><span class="sxs-lookup"><span data-stu-id="ec547-149">**Default:** Blank</span></span>|  
    |<span data-ttu-id="ec547-150">**数据转换**</span><span class="sxs-lookup"><span data-stu-id="ec547-150">**Data Conversion**</span></span>|<span data-ttu-id="ec547-151">将消息转换为用于 Windows Server 的 MQSeries 的 ANSI 代码页。</span><span class="sxs-lookup"><span data-stu-id="ec547-151">Converts the message to the ANSI code page of MQSeries for Windows server.</span></span><br /><br /> <span data-ttu-id="ec547-152">选择**是**来执行从 Unicode 此转换为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="ec547-152">Select **Yes** to perform this conversion from Unicode to ANSI.</span></span><br /><br /> <span data-ttu-id="ec547-153">**默认值：** 否</span><span class="sxs-lookup"><span data-stu-id="ec547-153">**Default:** No</span></span>|  
    |<span data-ttu-id="ec547-154">**排序**</span><span class="sxs-lookup"><span data-stu-id="ec547-154">**Ordered**</span></span>|<span data-ttu-id="ec547-155">将 MQSeries 设置为向 MQSeries 队列发送消息时保持消息的顺序。</span><span class="sxs-lookup"><span data-stu-id="ec547-155">Sets MQSeries to maintain the order of messages as they are sent to the MQSeries queue.</span></span><br /><br /> <span data-ttu-id="ec547-156">选择**是**维护消息顺序。</span><span class="sxs-lookup"><span data-stu-id="ec547-156">Select **Yes** to maintain message order.</span></span> <span data-ttu-id="ec547-157">**注意：** 必须设置**传递通知**到业务流程中的属性**传输**发送端口。</span><span class="sxs-lookup"><span data-stu-id="ec547-157">**Note:**  You must set the **Delivery Notification** property in your orchestration to **Transmitted** for the send port.</span></span> <br /><br /> <span data-ttu-id="ec547-158">**默认值：** 否</span><span class="sxs-lookup"><span data-stu-id="ec547-158">**Default:** No</span></span>|  
    |<span data-ttu-id="ec547-159">**队列定义**</span><span class="sxs-lookup"><span data-stu-id="ec547-159">**Queue Definition**</span></span>|<span data-ttu-id="ec547-160">使用中的信息填充**队列定义**对话框中或直接在该字段。</span><span class="sxs-lookup"><span data-stu-id="ec547-160">Populated with information from the **Queue Definition** dialog box or directly in the field.</span></span> <span data-ttu-id="ec547-161">**注意：** 对要发送的 URI 端口或接收位置不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="ec547-161">**Note:**  The URI for a send port or receive location cannot exceed 256 characters.</span></span>|  
    |<span data-ttu-id="ec547-162">**允许的分段**</span><span class="sxs-lookup"><span data-stu-id="ec547-162">**Segmentation Allowed**</span></span>|<span data-ttu-id="ec547-163">如果单个消息超出了 MQSeries 队列的最大消息长度，则使用 MQSeries 队列管理器分段功能。</span><span class="sxs-lookup"><span data-stu-id="ec547-163">Uses MQSeries Queue Manager segmentation if an individual message exceeds the MQSeries queue maximum message length.</span></span> <span data-ttu-id="ec547-164">如果你选择**是**，MQSeries 将分段的消息放入队列。</span><span class="sxs-lookup"><span data-stu-id="ec547-164">If you select **Yes**, MQSeries puts segmented messages into the queue.</span></span><br /><br /> <span data-ttu-id="ec547-165">**默认值：** 否</span><span class="sxs-lookup"><span data-stu-id="ec547-165">**Default:** No</span></span>|  
    |<span data-ttu-id="ec547-166">**事务支持**</span><span class="sxs-lookup"><span data-stu-id="ec547-166">**Transaction Supported**</span></span>|<span data-ttu-id="ec547-167">适配器在 BizTalk Server 和 MQSeries 服务器之间执行 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="ec547-167">The adapter begins a DTC transaction between BizTalk Server and MQSeries Server.</span></span> <span data-ttu-id="ec547-168">当设置为**否**，就不能保证的消息传递。</span><span class="sxs-lookup"><span data-stu-id="ec547-168">When set to **No**, there is no guarantee of message delivery.</span></span><br /><br /> <span data-ttu-id="ec547-169">**默认值：** 是**注意：** 没有配置发送端口和不同**事务支持**设置将消息发送到同一个 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="ec547-169">**Default:** Yes **Note:**  Do not configure send ports with different **Transaction Supported** settings to send messages to the same MQSeries queue.</span></span> <span data-ttu-id="ec547-170">**注意：** 除了测试方案中，此属性应始终设置为默认值的**是**。</span><span class="sxs-lookup"><span data-stu-id="ec547-170">**Note:**  With the exception of test scenarios, this property should always be set to the default value of **Yes**.</span></span> <span data-ttu-id="ec547-171">此属性设置为值为**否**在生产环境可能会导致意外的问题。</span><span class="sxs-lookup"><span data-stu-id="ec547-171">Setting this property to a value of **No** in a production environment may cause unexpected problems.</span></span>|  
  
     <span data-ttu-id="ec547-172">下图显示了这些属性的可能配置：</span><span class="sxs-lookup"><span data-stu-id="ec547-172">The following figure shows how you might configure these properties.</span></span>  
  
     <span data-ttu-id="ec547-173">![MQSeries 传输属性对话框中](../core/media/bts-dev-mqsendtransportprops.gif "BTS_Dev_MQSendTransportProps")</span><span class="sxs-lookup"><span data-stu-id="ec547-173">![MQSeries Transport Properties dialog box](../core/media/bts-dev-mqsendtransportprops.gif "BTS_Dev_MQSendTransportProps")</span></span>  
  
4.  <span data-ttu-id="ec547-174">单击省略号 (**...**) 的右侧的按钮**队列定义**框可定义队列。</span><span class="sxs-lookup"><span data-stu-id="ec547-174">Click the ellipsis (**...**) button to the right of the **Queue Definition** box to define the queue.</span></span> <span data-ttu-id="ec547-175">你可以使用**导出**对话框中，您可能必须与接收位置，以立即创建队列，或将导出定义队列的脚本时相同。</span><span class="sxs-lookup"><span data-stu-id="ec547-175">You can use the **Export** dialog box, just as you may have with the receive location, to create the queue immediately or to export a script defining the queue.</span></span>  
  
5.  <span data-ttu-id="ec547-176">单击**确定**在每个对话框框中，以将其关闭并保存设置。</span><span class="sxs-lookup"><span data-stu-id="ec547-176">Click **OK** in each dialog box to close it and save the settings.</span></span>  
  
 <span data-ttu-id="ec547-177">**若要登记发送端口，启动发送端口，并启用接收位置：**</span><span class="sxs-lookup"><span data-stu-id="ec547-177">**To enlist the send port, start the send port, and enable the receive location:**</span></span>  
  
1.  <span data-ttu-id="ec547-178">右键单击发送端口，然后单击**Enlist**登记发送端口。</span><span class="sxs-lookup"><span data-stu-id="ec547-178">Right-click the send port and click **Enlist** to enlist the send port.</span></span>  
  
2.  <span data-ttu-id="ec547-179">右键单击发送端口，然后单击**启动**启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="ec547-179">Right-click the send port and click **Start** to start the send port.</span></span>  
  
3.  <span data-ttu-id="ec547-180">右键单击接收位置，然后单击**启用**以便接收位置。</span><span class="sxs-lookup"><span data-stu-id="ec547-180">Right-click the receive location and click **Enable** to enable the receive location.</span></span>  
  
4.  <span data-ttu-id="ec547-181">检查事件日志以确定是否存在 BizTalk Server 错误。</span><span class="sxs-lookup"><span data-stu-id="ec547-181">Review the event log to verify that there are no BizTalk Server errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec547-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec547-182">See Also</span></span>  
 <span data-ttu-id="ec547-183">[如何配置 MQSeries 适配器发送和接收处理程序](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="ec547-183">[How to Configure MQSeries Adapter Send and Receive Handlers](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span></span>  
 [<span data-ttu-id="ec547-184">配置 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="ec547-184">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)