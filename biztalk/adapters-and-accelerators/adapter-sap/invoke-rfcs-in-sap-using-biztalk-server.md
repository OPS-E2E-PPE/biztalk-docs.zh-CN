---
title: 调用中使用 BizTalk Server 的 SAP Rfc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFCs, invoking using BizTalk Server
ms.assetid: cc859ca2-aa9a-48fd-a941-ae28bee96f06
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35d27d21a147aef162bed6a7920aab2a086f0a00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373291"
---
# <a name="invoke-rfcs-in-sap-using-biztalk-server"></a><span data-ttu-id="75976-102">调用中使用 BizTalk Server 的 SAP Rfc</span><span class="sxs-lookup"><span data-stu-id="75976-102">Invoke RFCs in SAP using BizTalk Server</span></span>
<span data-ttu-id="75976-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现为可由适配器客户端调用的操作公开的 SAP 系统的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="75976-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces the RFCs exposed by an SAP system as operations that can be invoked by an adapter client.</span></span> <span data-ttu-id="75976-104">本部分说明了通过使用 SAP 系统中调用 RFC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="75976-104">This section provides instructions on invoking an RFC in an SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="75976-105">详细了解如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 RFC 调用在 SAP 系统中，请参阅[Rfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-105">For more information about how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports invoking an RFC in an SAP system, see [Operations on RFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).</span></span> <span data-ttu-id="75976-106">有关以调用 RFC 的 SOAP 消息的结构的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-106">For more information about the structure of SOAP message for invoking an RFC, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="how-to-invoke-an-rfc-in-an-sap-system"></a><span data-ttu-id="75976-107">如何调用 RFC，SAP 系统中？</span><span class="sxs-lookup"><span data-stu-id="75976-107">How to Invoke an RFC in an SAP system?</span></span>  
 <span data-ttu-id="75976-108">对 SAP 系统使用执行操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要创建的 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-108">Performing an operation on an SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create SAP applications](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md).</span></span> <span data-ttu-id="75976-109">若要在 SAP 系统中调用 RFC，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="75976-109">To invoke an RFC in an SAP system, these tasks are:</span></span>  
  
1. <span data-ttu-id="75976-110">创建 BizTalk 项目，并为你想要在 SAP 系统中调用的 RFC 生成架构。</span><span class="sxs-lookup"><span data-stu-id="75976-110">Create a BizTalk project and generate schema for the RFC you want to invoke in the SAP system.</span></span>  
  
2. <span data-ttu-id="75976-111">用于发送和接收来自 SAP 系统的消息在 BizTalk 项目中创建的消息。</span><span class="sxs-lookup"><span data-stu-id="75976-111">Create messages in the BizTalk project for sending and receiving messages from the SAP system.</span></span>  
  
3. <span data-ttu-id="75976-112">创建一个业务流程调用 RFC，SAP 系统中。</span><span class="sxs-lookup"><span data-stu-id="75976-112">Create an orchestration to invoke an RFC in the SAP system.</span></span>  
  
4. <span data-ttu-id="75976-113">生成并部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="75976-113">Build and deploy the BizTalk project.</span></span>  
  
5. <span data-ttu-id="75976-114">配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="75976-114">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
6. <span data-ttu-id="75976-115">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="75976-115">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="75976-116">本主题介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="75976-116">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="75976-117">生成架构</span><span class="sxs-lookup"><span data-stu-id="75976-117">Generating Schema</span></span>  
 <span data-ttu-id="75976-118">本主题演示如何调用 RFC 在 SAP 系统中，我们生成的架构*RFC_CUSTOMER_GET*。</span><span class="sxs-lookup"><span data-stu-id="75976-118">In this topic, to demonstrate how to invoke an RFC in an SAP system, we generate the schema for *RFC_CUSTOMER_GET*.</span></span> <span data-ttu-id="75976-119">请参阅[浏览、 搜索和获取 RFC 操作在 SAP 中的元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="75976-119">See [Browse, Search, and get Metadata for RFC Operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) for more information about how to generate schema.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="75976-120">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="75976-120">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="75976-121">先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="75976-121">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="75976-122">一条消息通常是一个变量，要为其类型定义由相应的架构。</span><span class="sxs-lookup"><span data-stu-id="75976-122">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="75976-123">必须从 BizTalk 项目的业务流程视图中的消息链接你生成的架构。</span><span class="sxs-lookup"><span data-stu-id="75976-123">You must link the schema you generated to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="75976-124">对于本主题中，您必须创建两条消息，另一个用于将请求发送到 SAP 系统，另一个用于接收响应。</span><span class="sxs-lookup"><span data-stu-id="75976-124">For this topic, you must create two messages—one to send a request to the SAP system and the other to receive a response.</span></span>  
  
 <span data-ttu-id="75976-125">执行以下步骤来创建消息并将其链接到该架构。</span><span class="sxs-lookup"><span data-stu-id="75976-125">Perform the following steps to create messages and link them to the schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="75976-126">若要创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="75976-126">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="75976-127">打开业务流程视图 BizTalk 项目中，如果还没有打开。</span><span class="sxs-lookup"><span data-stu-id="75976-127">Open the orchestration view the BizTalk project, if not already open.</span></span> <span data-ttu-id="75976-128">单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="75976-128">Click **View**, point to **Other Windows**, and click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="75976-129">在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="75976-129">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="75976-130">右键单击新创建消息，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="75976-130">Right-click the newly create message and select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="75976-131">在中**属性**窗格**Message_1**，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="75976-131">In the **Properties** pane for **Message_1**, do the following.</span></span>  
  
    |<span data-ttu-id="75976-132">使用此选项</span><span class="sxs-lookup"><span data-stu-id="75976-132">Use this</span></span>|<span data-ttu-id="75976-133">执行的操作</span><span class="sxs-lookup"><span data-stu-id="75976-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="75976-134">Identifier</span><span class="sxs-lookup"><span data-stu-id="75976-134">Identifier</span></span>|<span data-ttu-id="75976-135">类型**请求**。</span><span class="sxs-lookup"><span data-stu-id="75976-135">Type **Request**.</span></span>|  
    |<span data-ttu-id="75976-136">消息类型</span><span class="sxs-lookup"><span data-stu-id="75976-136">Message Type</span></span>|<span data-ttu-id="75976-137">从下拉列表中，展开**架构**，然后选择*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*，其中*InvokeRFC*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="75976-137">From the drop-down list, expand **Schemas**, and select *InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*, where *InvokeRFC* is the name of your BizTalk project.</span></span>  <span data-ttu-id="75976-138">*SAPBindingSchema*是为生成的架构*RFC_CUSTOMER_GET*。</span><span class="sxs-lookup"><span data-stu-id="75976-138">*SAPBindingSchema* is the schema generated for *RFC_CUSTOMER_GET*.</span></span>|  
  
5.  <span data-ttu-id="75976-139">重复上述步骤以创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="75976-139">Repeat the previous step to create a new message.</span></span> <span data-ttu-id="75976-140">在中**属性**窗格中的新消息，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="75976-140">In the **Properties** pane for the new message, do the following.</span></span>  
  
    |<span data-ttu-id="75976-141">使用此选项</span><span class="sxs-lookup"><span data-stu-id="75976-141">Use this</span></span>|<span data-ttu-id="75976-142">执行的操作</span><span class="sxs-lookup"><span data-stu-id="75976-142">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="75976-143">Identifier</span><span class="sxs-lookup"><span data-stu-id="75976-143">Identifier</span></span>|<span data-ttu-id="75976-144">类型**响应**。</span><span class="sxs-lookup"><span data-stu-id="75976-144">Type **Response**.</span></span>|  
    |<span data-ttu-id="75976-145">消息类型</span><span class="sxs-lookup"><span data-stu-id="75976-145">Message Type</span></span>|<span data-ttu-id="75976-146">从下拉列表中，展开**架构**，然后选择*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*。</span><span class="sxs-lookup"><span data-stu-id="75976-146">From the drop-down list, expand **Schemas**, and select *InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="75976-147">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="75976-147">Setting up the Orchestration</span></span>  
 <span data-ttu-id="75976-148">必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于调用 Rfc，SAP 系统中。</span><span class="sxs-lookup"><span data-stu-id="75976-148">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for invoking RFCs in the SAP system.</span></span> <span data-ttu-id="75976-149">在将请求消息放在此业务流程，定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="75976-149">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="75976-150">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用该消息并将其传递到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="75976-150">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] consumes the message and passes it on to the SAP system.</span></span> <span data-ttu-id="75976-151">从 SAP 系统的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="75976-151">The response from the SAP system is saved to another location.</span></span> <span data-ttu-id="75976-152">调用 Rfc，SAP 系统中的一个典型的业务流程将包含：</span><span class="sxs-lookup"><span data-stu-id="75976-152">A typical orchestration for invoking RFCs in an SAP system would contain:</span></span>  
  
- <span data-ttu-id="75976-153">发送和接收形状来将消息发送到 SAP 系统和接收响应。</span><span class="sxs-lookup"><span data-stu-id="75976-153">Send and Receive shapes to send messages to the SAP system and receive responses.</span></span>  
  
- <span data-ttu-id="75976-154">一个单向接收端口接收请求消息发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="75976-154">A one-way receive port to receive request messages to send to the SAP system.</span></span>  
  
- <span data-ttu-id="75976-155">一个双向发送端口以将请求消息发送到 SAP 系统和接收响应。</span><span class="sxs-lookup"><span data-stu-id="75976-155">A two-way send port to send request messages to the SAP system and receive responses.</span></span>  
  
- <span data-ttu-id="75976-156">一个单向发送端口用于从 SAP 系统将响应发送到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="75976-156">A one-way send port to send the responses from the SAP system to a folder.</span></span>  
  
  <span data-ttu-id="75976-157">示例业务流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="75976-157">A sample orchestration resembles the following:</span></span>  
  
  <span data-ttu-id="75976-158">![已连接端口的业务流程](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")</span><span class="sxs-lookup"><span data-stu-id="75976-158">![Orchestration with ports connected](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="75976-159">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="75976-159">Adding Message Shapes</span></span>  
 <span data-ttu-id="75976-160">请确保为每个消息形状中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="75976-160">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="75976-161">中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="75976-161">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="75976-162">形状</span><span class="sxs-lookup"><span data-stu-id="75976-162">Shape</span></span>|<span data-ttu-id="75976-163">形状类型</span><span class="sxs-lookup"><span data-stu-id="75976-163">Shape Type</span></span>|<span data-ttu-id="75976-164">属性</span><span class="sxs-lookup"><span data-stu-id="75976-164">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="75976-165">Receive_Request</span><span class="sxs-lookup"><span data-stu-id="75976-165">Receive_Request</span></span>|<span data-ttu-id="75976-166">Receive</span><span class="sxs-lookup"><span data-stu-id="75976-166">Receive</span></span>|<span data-ttu-id="75976-167">-设置**名称**到*Receive_Request*</span><span class="sxs-lookup"><span data-stu-id="75976-167">-   Set **Name** to *Receive_Request*</span></span><br /><span data-ttu-id="75976-168">-设置**激活**到 *，则返回 True*</span><span class="sxs-lookup"><span data-stu-id="75976-168">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="75976-169">Send_LOB</span><span class="sxs-lookup"><span data-stu-id="75976-169">Send_LOB</span></span>|<span data-ttu-id="75976-170">Send</span><span class="sxs-lookup"><span data-stu-id="75976-170">Send</span></span>|<span data-ttu-id="75976-171">-设置**名称**到*Send_LOB*</span><span class="sxs-lookup"><span data-stu-id="75976-171">-   Set **Name** to *Send_LOB*</span></span>|  
|<span data-ttu-id="75976-172">Receive_LOB</span><span class="sxs-lookup"><span data-stu-id="75976-172">Receive_LOB</span></span>|<span data-ttu-id="75976-173">Receive</span><span class="sxs-lookup"><span data-stu-id="75976-173">Receive</span></span>|<span data-ttu-id="75976-174">-设置**名称**到*Receive_LOB*</span><span class="sxs-lookup"><span data-stu-id="75976-174">-   Set **Name** to *Receive_LOB*</span></span><br /><span data-ttu-id="75976-175">-设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="75976-175">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="75976-176">Send_Response</span><span class="sxs-lookup"><span data-stu-id="75976-176">Send_Response</span></span>|<span data-ttu-id="75976-177">Send</span><span class="sxs-lookup"><span data-stu-id="75976-177">Send</span></span>|<span data-ttu-id="75976-178">-设置**名称**到*Send_Response*</span><span class="sxs-lookup"><span data-stu-id="75976-178">-   Set **Name** to *Send_Response*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="75976-179">添加端口</span><span class="sxs-lookup"><span data-stu-id="75976-179">Adding Ports</span></span>  
 <span data-ttu-id="75976-180">为每个逻辑端口中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="75976-180">Specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="75976-181">中列出的名称*端口*列是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="75976-181">The names listed in the *Port* column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="75976-182">Port</span><span class="sxs-lookup"><span data-stu-id="75976-182">Port</span></span>|<span data-ttu-id="75976-183">属性</span><span class="sxs-lookup"><span data-stu-id="75976-183">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="75976-184">ReceiveMsgPort</span><span class="sxs-lookup"><span data-stu-id="75976-184">ReceiveMsgPort</span></span>|<span data-ttu-id="75976-185">-设置**标识符**到*ReceiveMsgPort*</span><span class="sxs-lookup"><span data-stu-id="75976-185">-   Set **Identifier** to *ReceiveMsgPort*</span></span><br /><span data-ttu-id="75976-186">-设置**类型**到*ReceiveMsgPortType*</span><span class="sxs-lookup"><span data-stu-id="75976-186">-   Set **Type** to *ReceiveMsgPortType*</span></span><br /><span data-ttu-id="75976-187">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="75976-187">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="75976-188">-设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="75976-188">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="75976-189">SendToLOBPort</span><span class="sxs-lookup"><span data-stu-id="75976-189">SendToLOBPort</span></span>|<span data-ttu-id="75976-190">-设置**标识符**到*SendToLOBPort*</span><span class="sxs-lookup"><span data-stu-id="75976-190">-   Set **Identifier** to *SendToLOBPort*</span></span><br /><span data-ttu-id="75976-191">-设置**类型**到*SendToLOBPortType*</span><span class="sxs-lookup"><span data-stu-id="75976-191">-   Set **Type** to *SendToLOBPortType*</span></span><br /><span data-ttu-id="75976-192">-设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="75976-192">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="75976-193">-设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="75976-193">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="75976-194">SendMsgPort</span><span class="sxs-lookup"><span data-stu-id="75976-194">SendMsgPort</span></span>|<span data-ttu-id="75976-195">-设置**标识符**到*SendMsgPort*</span><span class="sxs-lookup"><span data-stu-id="75976-195">-   Set **Identifier** to *SendMsgPort*</span></span><br /><span data-ttu-id="75976-196">-设置**类型**到*SendMsgPortType*</span><span class="sxs-lookup"><span data-stu-id="75976-196">-   Set **Type** to *SendMsgPortType*</span></span><br /><span data-ttu-id="75976-197">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="75976-197">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="75976-198">-设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="75976-198">-   Set **Communication Direction** to *Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="75976-199">为操作形状指定消息并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="75976-199">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="75976-200">下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。</span><span class="sxs-lookup"><span data-stu-id="75976-200">The following table specifies the properties and their values to be set to specify messages for action shapes and linking them to the ports.</span></span> <span data-ttu-id="75976-201">中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="75976-201">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="75976-202">形状</span><span class="sxs-lookup"><span data-stu-id="75976-202">Shape</span></span>|<span data-ttu-id="75976-203">属性</span><span class="sxs-lookup"><span data-stu-id="75976-203">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="75976-204">Receive_Request</span><span class="sxs-lookup"><span data-stu-id="75976-204">Receive_Request</span></span>|<span data-ttu-id="75976-205">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="75976-205">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="75976-206">-设置**操作**到*ReceiveMsgPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="75976-206">-   Set **Operation** to *ReceiveMsgPort.Operation_1.Request*</span></span>|  
|<span data-ttu-id="75976-207">Send_LOB</span><span class="sxs-lookup"><span data-stu-id="75976-207">Send_LOB</span></span>|<span data-ttu-id="75976-208">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="75976-208">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="75976-209">-设置**操作**到*SendToLOBPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="75976-209">-   Set **Operation** to *SendToLOBPort.Operation_1.Request*</span></span>|  
|<span data-ttu-id="75976-210">Receive_LOB</span><span class="sxs-lookup"><span data-stu-id="75976-210">Receive_LOB</span></span>|<span data-ttu-id="75976-211">-设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="75976-211">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="75976-212">-设置**操作**到*SendToLOBPort.Operation_1.Response*</span><span class="sxs-lookup"><span data-stu-id="75976-212">-   Set **Operation** to *SendToLOBPort.Operation_1.Response*</span></span>|  
|<span data-ttu-id="75976-213">Send_Response</span><span class="sxs-lookup"><span data-stu-id="75976-213">Send_Response</span></span>|<span data-ttu-id="75976-214">-设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="75976-214">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="75976-215">-设置**操作**到*SendMsgPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="75976-215">-   Set **Operation** to *SendMsgPort.Operation_1.Request*</span></span>|  
  
 <span data-ttu-id="75976-216">指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="75976-216">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="75976-217">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="75976-217">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="75976-218">有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-218">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="75976-219">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="75976-219">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="75976-220">部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="75976-220">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="75976-221">必须使用 BizTalk Server 管理控制台来配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="75976-221">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="75976-222">有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-222">For more information about configuring an application, see [How to Configure an Application](../../core/how-to-configure-an-application.md).</span></span>
  
 <span data-ttu-id="75976-223">配置应用程序包括：</span><span class="sxs-lookup"><span data-stu-id="75976-223">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="75976-224">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="75976-224">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="75976-225">映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="75976-225">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="75976-226">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="75976-226">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="75976-227">硬盘和相应 file 端口将放置请求消息的位置上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="75976-227">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="75976-228">BizTalk 业务流程将使用请求消息并将其发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="75976-228">The BizTalk orchestration will consume the request message and send it to the SAP system.</span></span>  
  
  - <span data-ttu-id="75976-229">硬盘和相应的 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="75976-229">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the SAP system.</span></span>  
  
  - <span data-ttu-id="75976-230">定义一个物理 WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="75976-230">Define a physical WCF-Custom or WCF-SAP send port to send messages to the SAP system.</span></span> <span data-ttu-id="75976-231">您必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="75976-231">You must also specify the action in the send port.</span></span> <span data-ttu-id="75976-232">有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-232">For information about how to create ports, see [Manually configure a physical port binding to the SAP adapter](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="75976-233">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="75976-233">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file containing information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="75976-234">从 BizTalk Server 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。</span><span class="sxs-lookup"><span data-stu-id="75976-234">You can import this binding file from the BizTalk Server Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="75976-235">有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-235">For more information, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
## <a name="starting-the-application"></a><span data-ttu-id="75976-236">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="75976-236">Starting the Application</span></span>  
 <span data-ttu-id="75976-237">必须启动以调用 RFC，SAP 系统中的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="75976-237">You must start the BizTalk application for invoking an RFC in the SAP system.</span></span> <span data-ttu-id="75976-238">在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)或[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-238">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md) or [how to start an application](../../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>
  
 <span data-ttu-id="75976-239">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="75976-239">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="75976-240">文件接收端口接收请求消息的业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="75976-240">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="75976-241">运行文件发送端口以接收来自业务流程的响应消息。</span><span class="sxs-lookup"><span data-stu-id="75976-241">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="75976-242">WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统正在运行。</span><span class="sxs-lookup"><span data-stu-id="75976-242">The WCF-Custom or WCF-SAP send port to send messages to the SAP system is running.</span></span>  
  
-   <span data-ttu-id="75976-243">该操作的 BizTalk 业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="75976-243">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="75976-244">执行该操作</span><span class="sxs-lookup"><span data-stu-id="75976-244">Executing the Operation</span></span>  
 <span data-ttu-id="75976-245">运行应用程序后，必须在预定义的位置删除该业务流程的请求消息。</span><span class="sxs-lookup"><span data-stu-id="75976-245">After you run the application, you must drop a request message for the orchestration at a predefined location.</span></span> <span data-ttu-id="75976-246">请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)需要了解的有关为 SAP 系统中调用 RFC 的请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="75976-246">See [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md) to know about the schema for the request message for invoking an RFC in an SAP system.</span></span> <span data-ttu-id="75976-247">例如，要调用 RFC_CUSTOMER_GET 的请求消息是：</span><span class="sxs-lookup"><span data-stu-id="75976-247">For example, the request message to invoke RFC_CUSTOMER_GET is:</span></span>  
  
```  
<RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <KUNNR>0000001390</KUNNR>  
  <NAME1>*</NAME1>  
  <CUSTOMER_T/>  
</RFC_CUSTOMER_GET>  
```  
  
 <span data-ttu-id="75976-248">业务流程使用该消息并将其发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="75976-248">The orchestration consumes the message and sends it to the SAP system.</span></span> <span data-ttu-id="75976-249">来自 SAP 系统的响应被保存在定义为业务流程的一部分的其他文件位置。</span><span class="sxs-lookup"><span data-stu-id="75976-249">The response from the SAP system is saved at other file location defined as part of the orchestration.</span></span> <span data-ttu-id="75976-250">例如，来自 SAP 系统的更高版本的请求消息的响应是：</span><span class="sxs-lookup"><span data-stu-id="75976-250">For example, the response from the SAP system for the above request message is:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RFC_CUSTOMER_GETResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <CUSTOMER_T>  
    <RFCCUST xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <KUNNR>0000001390</KUNNR>   
      <ANRED>Firma</ANRED>   
      <NAME1>Contoso, Ltd.</NAME1>   
      <PFACH />   
      <STRAS>4567 Main Street</STRAS>   
      <PSTLZ>98052</PSTLZ>   
      <ORT01>USA</ORT01>   
      <TELF1>555-0101</TELF1>   
      <TELFX>555-0102</TELFX>   
    </RFCCUST>  
  </CUSTOMER_T>  
</RFC_CUSTOMER_GETResponse>  
```  
  
## <a name="possible-exceptions"></a><span data-ttu-id="75976-251">可能的异常</span><span class="sxs-lookup"><span data-stu-id="75976-251">Possible Exceptions</span></span>  
 <span data-ttu-id="75976-252">在 SAP 系统中使用 BizTalk Server 调用 RFC 时可能遇到的异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-252">For information about the exceptions you might encounter while invoking an RFC in an SAP system using BizTalk Server, see [Exceptions and Error Handling with the SAP adapter](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="75976-253">最佳实践</span><span class="sxs-lookup"><span data-stu-id="75976-253">Best Practices</span></span>  
 <span data-ttu-id="75976-254">部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="75976-254">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the bindings file.</span></span> <span data-ttu-id="75976-255">一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。</span><span class="sxs-lookup"><span data-stu-id="75976-255">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="75976-256">有关绑定文件的详细信息，请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="75976-256">For more information about binding files, see [Reuse SAP adapter bindings](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75976-257">请参阅</span><span class="sxs-lookup"><span data-stu-id="75976-257">See Also</span></span>  
[<span data-ttu-id="75976-258">开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="75976-258">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)