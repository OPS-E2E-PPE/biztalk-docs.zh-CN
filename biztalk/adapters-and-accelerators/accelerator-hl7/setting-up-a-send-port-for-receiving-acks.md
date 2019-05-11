---
title: 设置发送端口用于接收 Ack |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2489a8c26d418782e661629afd65f3bafd3b03ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289589"
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a><span data-ttu-id="ca199-102">设置用于接收 Ack 的发送端口</span><span class="sxs-lookup"><span data-stu-id="ca199-102">Setting Up a Send Port for Receiving ACKs</span></span>
<span data-ttu-id="ca199-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 可以在一个单向发送端口上接收确认 (ACK)。</span><span class="sxs-lookup"><span data-stu-id="ca199-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) can receive acknowledgments (ACK) on a one-way send port.</span></span> <span data-ttu-id="ca199-104">如果设置了新的单向发送端口用于接收 Ack 的同一连接上时，必须将关联该发送端口使用一个单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="ca199-104">When you set up a new one-way send port for receiving ACKs on the same connection, you must associate that send port with a one-way receive port.</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="ca199-105">安装程序将创建一个单向接收端口 (称为**TwoWayAckReceivePort**) 和接收位置 (称为**TwoWayAckReceiveLocation**)。</span><span class="sxs-lookup"><span data-stu-id="ca199-105">setup creates a one-way receive port (called **TwoWayAckReceivePort**) and receive location (called **TwoWayAckReceiveLocation**).</span></span> <span data-ttu-id="ca199-106">接收位置使用的最小的较低层协议 (MLLP) 传输类型、 uri 为"127.0.0.1:65535"，并使用**BTAHL72XReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="ca199-106">The receive location uses the Minimal Lower Layer Protocol (MLLP) transport type, has a URI of "127.0.0.1:65535", and uses the **BTAHL72XReceivePipeline**.</span></span> <span data-ttu-id="ca199-107">这些是用于接收所需的设置和处理对消息接收到 ACK 发送的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送适配器，在双向模式下。</span><span class="sxs-lookup"><span data-stu-id="ca199-107">These are the settings required for receiving and processing an ACK received against a message sent out by the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] send adapter, in two-way mode.</span></span> <span data-ttu-id="ca199-108">此接收位置不应删除或任何其他用途。</span><span class="sxs-lookup"><span data-stu-id="ca199-108">This receive location should not be deleted or used for any other purposes.</span></span> <span data-ttu-id="ca199-109">永远不会将数据发送到此接收位置。</span><span class="sxs-lookup"><span data-stu-id="ca199-109">Never send data to this receive location.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="ca199-110">允许此接收位置的默认值。</span><span class="sxs-lookup"><span data-stu-id="ca199-110">enables this receive location by default.</span></span>  
  
 <span data-ttu-id="ca199-111">**TwoWayAckReceiveLocation**，后者[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序向导创建，使用**BizTalkServerApplication**为接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="ca199-111">**TwoWayAckReceiveLocation**, which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Setup Wizard creates, uses the **BizTalkServerApplication** as the receive handler.</span></span> <span data-ttu-id="ca199-112">但是，如果您选择创建新的主机，并为 MLLP 的接收处理程序使用它，然后你必须执行以下操作来创建一个新**TwoWayAckReceiveLocation**:</span><span class="sxs-lookup"><span data-stu-id="ca199-112">However, if you choose to create a new host and use it as the receive handler for MLLP, then you must do the following to create a new **TwoWayAckReceiveLocation**:</span></span>  
  
1.  <span data-ttu-id="ca199-113">创建一个单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="ca199-113">Create a one-way receive port.</span></span>  
  
2.  <span data-ttu-id="ca199-114">创建一个单向 MLLP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="ca199-114">Create a one-way MLLP receive location.</span></span>  
  
3.  <span data-ttu-id="ca199-115">指定为 MLLP 传输属性的相应值。</span><span class="sxs-lookup"><span data-stu-id="ca199-115">Specify the appropriate values for the MLLP transport properties.</span></span>  
  
4.  <span data-ttu-id="ca199-116">指定相应的接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="ca199-116">Specify the appropriate receive handler.</span></span>  
  
5.  <span data-ttu-id="ca199-117">启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="ca199-117">Enable the receive location.</span></span>  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a><span data-ttu-id="ca199-118">若要创建启用了接收相同的套接字上的 ACK 的发送端口</span><span class="sxs-lookup"><span data-stu-id="ca199-118">To create a send port enabled to receive an ACK on the same socket</span></span>  
  
1.  <span data-ttu-id="ca199-119">打开 BizTalk 管理控制台，然后展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="ca199-119">Open the BizTalk Administration Console, and then expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="ca199-120">右键单击**发送端口**，指向新建，，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ca199-120">Right-click **Send Ports**, point to New, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ca199-121">在中**名称**框中，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="ca199-121">In the **Name** box, type the name of the send port.</span></span>  
  
3.  <span data-ttu-id="ca199-122">在中**传输**部分中，对于**类型**，选择**MLLP**。</span><span class="sxs-lookup"><span data-stu-id="ca199-122">In the **Transport** section, for **Type**, select **MLLP**.</span></span>  
  
4.  <span data-ttu-id="ca199-123">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ca199-123">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="ca199-124">在处的 MLLP 传输属性对话框中，键入连接名称和主机 (例如， **localhost**)。</span><span class="sxs-lookup"><span data-stu-id="ca199-124">In the MLLP Transport Properties dialog box, type a connection name and host (for instance, **localhost**).</span></span>  
  
6.  <span data-ttu-id="ca199-125">有关**要求响应启用**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="ca199-125">For **Solicit Response Enabled**, select **Yes**.</span></span> <span data-ttu-id="ca199-126">将保留**提交接收位置 (URI) ACK**保留为空，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca199-126">Leave **Submit Receive Location (URI) for ACK** blank, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca199-127">当你退出**提交接收位置**保留为空，BTAHL7 进入 URI 默认**TwoWayAckReceiveLocation**。</span><span class="sxs-lookup"><span data-stu-id="ca199-127">When you leave **Submit Receive Location** blank, BTAHL7 enters the URI for the default **TwoWayAckReceiveLocation**.</span></span> <span data-ttu-id="ca199-128">你可以验证该后单击**确定**第 6 步中，通过单击**配置**试。</span><span class="sxs-lookup"><span data-stu-id="ca199-128">You can verify that after clicking **OK** in step 6, by clicking **Configuration** again.</span></span> <span data-ttu-id="ca199-129">URI **TwoWayAckReceiveLocation** (127.0.0.1:65535) 将被放入**提交接收位置 (URI) 确认**。</span><span class="sxs-lookup"><span data-stu-id="ca199-129">The URI for **TwoWayAckReceiveLocation** (127.0.0.1:65535) will be entered in **Submit Receive Location (URI) for ACK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca199-130">必须创建用于订阅接收确认的发送端口或确认将会看到处于挂起状态，因为未找到订阅。</span><span class="sxs-lookup"><span data-stu-id="ca199-130">You must create a send port to subscribe to the ACK received, or the ACK will be seen in a suspended state, because no subscriptions were found.</span></span> <span data-ttu-id="ca199-131">若要订阅发送端口接收的确认，请使用筛选器，例如， **BTS。MessageType = = \< *MessageType* \>** 和**BTS。ReceivePortName = = \< *ReceivePort*\>**。</span><span class="sxs-lookup"><span data-stu-id="ca199-131">To subscribe to the ACK received by the send port, use filters, for example, **BTS.MessageType == \<*MessageType*\>** and **BTS.ReceivePortName == \<*ReceivePort*\>**.</span></span> <span data-ttu-id="ca199-132">对于静态确认消息类型是**StaticAck**。</span><span class="sxs-lookup"><span data-stu-id="ca199-132">For static ACKs, the message type is **StaticAck**.</span></span>  
  
7.  <span data-ttu-id="ca199-133">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ca199-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca199-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca199-134">See Also</span></span>  
 <span data-ttu-id="ca199-135">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="ca199-135">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="ca199-136">[ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="ca199-136">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="ca199-137">[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="ca199-137">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="ca199-138">错误条件确认</span><span class="sxs-lookup"><span data-stu-id="ca199-138">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)