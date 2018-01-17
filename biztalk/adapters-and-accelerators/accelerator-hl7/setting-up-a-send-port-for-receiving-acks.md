---
title: "设置发送端口用于接收确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df0988a9edc2af81970237aad363315a778f821b
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a><span data-ttu-id="182fe-102">设置发送端口用于接收确认</span><span class="sxs-lookup"><span data-stu-id="182fe-102">Setting Up a Send Port for Receiving ACKs</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="182fe-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 可以在单向发送端口上接收确认 (ACK)。</span><span class="sxs-lookup"><span data-stu-id="182fe-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) can receive acknowledgments (ACK) on a one-way send port.</span></span> <span data-ttu-id="182fe-104">如果你设置了新的单向发送端口用于同一连接上接收确认，你必须将关联该发送端口使用单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="182fe-104">When you set up a new one-way send port for receiving ACKs on the same connection, you must associate that send port with a one-way receive port.</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="182fe-105">安装程序创建单向接收端口 (调用**TwoWayAckReceivePort**) 和接收位置 (称为**TwoWayAckReceiveLocation**)。</span><span class="sxs-lookup"><span data-stu-id="182fe-105"> setup creates a one-way receive port (called **TwoWayAckReceivePort**) and receive location (called **TwoWayAckReceiveLocation**).</span></span> <span data-ttu-id="182fe-106">接收位置使用的最小较低层协议 (MLLP) 传输类型、 具有 URI 的"127.0.0.1:65535"，并使用**BTAHL72XReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="182fe-106">The receive location uses the Minimal Lower Layer Protocol (MLLP) transport type, has a URI of "127.0.0.1:65535", and uses the **BTAHL72XReceivePipeline**.</span></span> <span data-ttu-id="182fe-107">这些是用于接收所需的设置和处理针对一条消息接收的 ACK 由发送出去[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送适配器，在双向模式下。</span><span class="sxs-lookup"><span data-stu-id="182fe-107">These are the settings required for receiving and processing an ACK received against a message sent out by the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] send adapter, in two-way mode.</span></span> <span data-ttu-id="182fe-108">此接收位置不应删除或任何其他用途。</span><span class="sxs-lookup"><span data-stu-id="182fe-108">This receive location should not be deleted or used for any other purposes.</span></span> <span data-ttu-id="182fe-109">永远不会将数据发送到此接收位置。</span><span class="sxs-lookup"><span data-stu-id="182fe-109">Never send data to this receive location.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="182fe-110">将默认的启用此 receive 按列出的位置。</span><span class="sxs-lookup"><span data-stu-id="182fe-110"> enables this receive location by default.</span></span>  
  
 <span data-ttu-id="182fe-111">**TwoWayAckReceiveLocation**，后者[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装向导创建，使用**BizTalkServerApplication**作为接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="182fe-111">**TwoWayAckReceiveLocation**, which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Setup Wizard creates, uses the **BizTalkServerApplication** as the receive handler.</span></span> <span data-ttu-id="182fe-112">但是，如果你选择创建新的主机并将其用作接收处理程序 MLLP，则你必须执行以下操作来创建一个新**TwoWayAckReceiveLocation**:</span><span class="sxs-lookup"><span data-stu-id="182fe-112">However, if you choose to create a new host and use it as the receive handler for MLLP, then you must do the following to create a new **TwoWayAckReceiveLocation**:</span></span>  
  
1.  <span data-ttu-id="182fe-113">创建单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="182fe-113">Create a one-way receive port.</span></span>  
  
2.  <span data-ttu-id="182fe-114">创建单向 MLLP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="182fe-114">Create a one-way MLLP receive location.</span></span>  
  
3.  <span data-ttu-id="182fe-115">指定 MLLP 传输属性的相应值。</span><span class="sxs-lookup"><span data-stu-id="182fe-115">Specify the appropriate values for the MLLP transport properties.</span></span>  
  
4.  <span data-ttu-id="182fe-116">指定相应接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="182fe-116">Specify the appropriate receive handler.</span></span>  
  
5.  <span data-ttu-id="182fe-117">启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="182fe-117">Enable the receive location.</span></span>  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a><span data-ttu-id="182fe-118">若要创建启用接收同一套接字上的 ACK 发送端口</span><span class="sxs-lookup"><span data-stu-id="182fe-118">To create a send port enabled to receive an ACK on the same socket</span></span>  
  
1.  <span data-ttu-id="182fe-119">打开 BizTalk 管理控制台中，，然后展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="182fe-119">Open the BizTalk Administration Console, and then expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="182fe-120">右键单击**发送端口**，指向新建，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="182fe-120">Right-click **Send Ports**, point to New, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="182fe-121">在**名称**框中，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="182fe-121">In the **Name** box, type the name of the send port.</span></span>  
  
3.  <span data-ttu-id="182fe-122">在**传输**部分中，为**类型**，选择**MLLP**。</span><span class="sxs-lookup"><span data-stu-id="182fe-122">In the **Transport** section, for **Type**, select **MLLP**.</span></span>  
  
4.  <span data-ttu-id="182fe-123">单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="182fe-123">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="182fe-124">在 MLLP 传输属性对话框中，键入连接名称和主机 (例如， **localhost**)。</span><span class="sxs-lookup"><span data-stu-id="182fe-124">In the MLLP Transport Properties dialog box, type a connection name and host (for instance, **localhost**).</span></span>  
  
6.  <span data-ttu-id="182fe-125">有关**请求作出响应启用**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="182fe-125">For **Solicit Response Enabled**, select **Yes**.</span></span> <span data-ttu-id="182fe-126">保留**提交接收位置 (URI) ACK**为空，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="182fe-126">Leave **Submit Receive Location (URI) for ACK** blank, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="182fe-127">当你退出**提交接收位置**保留为空，BTAHL7 输入 URI 默认**TwoWayAckReceiveLocation**。</span><span class="sxs-lookup"><span data-stu-id="182fe-127">When you leave **Submit Receive Location** blank, BTAHL7 enters the URI for the default **TwoWayAckReceiveLocation**.</span></span> <span data-ttu-id="182fe-128">你可以验证，之后单击**确定**第 6 步中，通过单击**配置**试。</span><span class="sxs-lookup"><span data-stu-id="182fe-128">You can verify that after clicking **OK** in step 6, by clicking **Configuration** again.</span></span> <span data-ttu-id="182fe-129">Uri，该 URI **TwoWayAckReceiveLocation** (127.0.0.1:65535) 将被放入**提交接收位置 (URI) ACK**。</span><span class="sxs-lookup"><span data-stu-id="182fe-129">The URI for **TwoWayAckReceiveLocation** (127.0.0.1:65535) will be entered in **Submit Receive Location (URI) for ACK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="182fe-130">你必须创建订阅接收，ACK 发送端口或 ACK 将会被发现处于挂起状态，因为未找到的订阅。</span><span class="sxs-lookup"><span data-stu-id="182fe-130">You must create a send port to subscribe to the ACK received, or the ACK will be seen in a suspended state, because no subscriptions were found.</span></span> <span data-ttu-id="182fe-131">若要订阅发送端口收到 ACK，使用筛选器，例如， **BTS。MessageType = = \< *MessageType* \>** 和**BTS。ReceivePortName = = \<*接收端口*\>**。</span><span class="sxs-lookup"><span data-stu-id="182fe-131">To subscribe to the ACK received by the send port, use filters, for example, **BTS.MessageType == \<*MessageType*\>** and **BTS.ReceivePortName == \<*ReceivePort*\>**.</span></span> <span data-ttu-id="182fe-132">对于静态 Ack 消息类型是**StaticAck**。</span><span class="sxs-lookup"><span data-stu-id="182fe-132">For static ACKs, the message type is **StaticAck**.</span></span>  
  
7.  <span data-ttu-id="182fe-133">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="182fe-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="182fe-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="182fe-134">See Also</span></span>  
 <span data-ttu-id="182fe-135">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="182fe-135">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="182fe-136">[ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="182fe-136">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="182fe-137">[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="182fe-137">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="182fe-138">错误条件确认</span><span class="sxs-lookup"><span data-stu-id="182fe-138">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)