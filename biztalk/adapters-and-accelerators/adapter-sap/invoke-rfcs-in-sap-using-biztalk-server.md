---
title: 调用中使用 BizTalk Server SAP Rfc |Microsoft 文档
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
ms.openlocfilehash: a3db5180d8b4183a2a48c726fd5e73b3347f82dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-rfcs-in-sap-using-biztalk-server"></a><span data-ttu-id="0b0c7-102">调用中使用 BizTalk Server SAP Rfc</span><span class="sxs-lookup"><span data-stu-id="0b0c7-102">Invoke RFCs in SAP using BizTalk Server</span></span>
<span data-ttu-id="0b0c7-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现作为适配器客户端可以调用的操作公开 SAP 系统的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces the RFCs exposed by an SAP system as operations that can be invoked by an adapter client.</span></span> <span data-ttu-id="0b0c7-104">本部分说明了通过使用调用中某个 SAP 系统的 RFC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-104">This section provides instructions on invoking an RFC in an SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0b0c7-105">有关详细信息，如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 RFC 调用在 SAP 系统中，请参阅[操作中 SAP Rfc](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-105">For more information about how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports invoking an RFC in an SAP system, see [Operations on RFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).</span></span> <span data-ttu-id="0b0c7-106">有关用于调用 RFC 的 SOAP 消息的结构的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-106">For more information about the structure of SOAP message for invoking an RFC, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="how-to-invoke-an-rfc-in-an-sap-system"></a><span data-ttu-id="0b0c7-107">如何在某个 SAP 系统调用 RFC？</span><span class="sxs-lookup"><span data-stu-id="0b0c7-107">How to Invoke an RFC in an SAP system?</span></span>  
 <span data-ttu-id="0b0c7-108">执行对 SAP 系统使用的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-108">Performing an operation on an SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create SAP applications](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md).</span></span> <span data-ttu-id="0b0c7-109">若要调用 RFC SAP 系统中，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="0b0c7-109">To invoke an RFC in an SAP system, these tasks are:</span></span>  
  
1.  <span data-ttu-id="0b0c7-110">创建 BizTalk 项目，并为你想要调用 SAP 系统中的 RFC 生成架构。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-110">Create a BizTalk project and generate schema for the RFC you want to invoke in the SAP system.</span></span>  
  
2.  <span data-ttu-id="0b0c7-111">在发送和接收消息从 SAP 系统的 BizTalk 项目中创建消息。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-111">Create messages in the BizTalk project for sending and receiving messages from the SAP system.</span></span>  
  
3.  <span data-ttu-id="0b0c7-112">创建业务流程来调用 RFC SAP 系统中。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-112">Create an orchestration to invoke an RFC in the SAP system.</span></span>  
  
4.  <span data-ttu-id="0b0c7-113">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-113">Build and deploy the BizTalk project.</span></span>  
  
5.  <span data-ttu-id="0b0c7-114">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-114">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
6.  <span data-ttu-id="0b0c7-115">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-115">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="0b0c7-116">本主题提供执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-116">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="0b0c7-117">生成架构</span><span class="sxs-lookup"><span data-stu-id="0b0c7-117">Generating Schema</span></span>  
 <span data-ttu-id="0b0c7-118">在本主题中，若要演示如何调用 RFC 在 SAP 系统中，我们生成的架构*RFC_CUSTOMER_GET*。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-118">In this topic, to demonstrate how to invoke an RFC in an SAP system, we generate the schema for *RFC_CUSTOMER_GET*.</span></span> <span data-ttu-id="0b0c7-119">请参阅[浏览，搜索，并为 SAP 中的 RFC 操作获取元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-119">See [Browse, Search, and get Metadata for RFC Operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) for more information about how to generate schema.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="0b0c7-120">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="0b0c7-120">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="0b0c7-121">你先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-121">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="0b0c7-122">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-122">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="0b0c7-123">你必须从 BizTalk 项目的业务流程视图来链接到消息的你生成的架构。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-123">You must link the schema you generated to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="0b0c7-124">对于本主题中，你必须创建两条消息，另一个用于将请求发送到 SAP 系统，另一个用于接收响应。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-124">For this topic, you must create two messages—one to send a request to the SAP system and the other to receive a response.</span></span>  
  
 <span data-ttu-id="0b0c7-125">执行以下步骤以创建消息并将它们链接到该架构。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-125">Perform the following steps to create messages and link them to the schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="0b0c7-126">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="0b0c7-126">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="0b0c7-127">打开业务流程视图 BizTalk 项目中，如果不是已打开。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-127">Open the orchestration view the BizTalk project, if not already open.</span></span> <span data-ttu-id="0b0c7-128">单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-128">Click **View**, point to **Other Windows**, and click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="0b0c7-129">在**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-129">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="0b0c7-130">右键单击新创建消息，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-130">Right-click the newly create message and select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="0b0c7-131">在**属性**窗格**Message_1**，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-131">In the **Properties** pane for **Message_1**, do the following.</span></span>  
  
    |<span data-ttu-id="0b0c7-132">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0b0c7-132">Use this</span></span>|<span data-ttu-id="0b0c7-133">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0b0c7-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0b0c7-134">Identifier</span><span class="sxs-lookup"><span data-stu-id="0b0c7-134">Identifier</span></span>|<span data-ttu-id="0b0c7-135">类型**请求**。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-135">Type **Request**.</span></span>|  
    |<span data-ttu-id="0b0c7-136">消息类型</span><span class="sxs-lookup"><span data-stu-id="0b0c7-136">Message Type</span></span>|<span data-ttu-id="0b0c7-137">从下拉列表中，展开**架构**，然后选择*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*，其中*InvokeRFC*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-137">From the drop-down list, expand **Schemas**, and select *InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*, where *InvokeRFC* is the name of your BizTalk project.</span></span>  <span data-ttu-id="0b0c7-138">*SAPBindingSchema*是为生成的架构*RFC_CUSTOMER_GET*。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-138">*SAPBindingSchema* is the schema generated for *RFC_CUSTOMER_GET*.</span></span>|  
  
5.  <span data-ttu-id="0b0c7-139">重复上述步骤以创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-139">Repeat the previous step to create a new message.</span></span> <span data-ttu-id="0b0c7-140">在**属性**窗格中，为新的消息中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-140">In the **Properties** pane for the new message, do the following.</span></span>  
  
    |<span data-ttu-id="0b0c7-141">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0b0c7-141">Use this</span></span>|<span data-ttu-id="0b0c7-142">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0b0c7-142">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0b0c7-143">Identifier</span><span class="sxs-lookup"><span data-stu-id="0b0c7-143">Identifier</span></span>|<span data-ttu-id="0b0c7-144">类型**响应**。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-144">Type **Response**.</span></span>|  
    |<span data-ttu-id="0b0c7-145">消息类型</span><span class="sxs-lookup"><span data-stu-id="0b0c7-145">Message Type</span></span>|<span data-ttu-id="0b0c7-146">从下拉列表中，展开**架构**，然后选择*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-146">From the drop-down list, expand **Schemas**, and select *InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="0b0c7-147">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="0b0c7-147">Setting up the Orchestration</span></span>  
 <span data-ttu-id="0b0c7-148">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用 Rfc SAP 系统中。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-148">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for invoking RFCs in the SAP system.</span></span> <span data-ttu-id="0b0c7-149">此业务流程，在你删除时的请求消息的定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-149">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="0b0c7-150">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用该消息并将其传递到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-150">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] consumes the message and passes it on to the SAP system.</span></span> <span data-ttu-id="0b0c7-151">从 SAP 系统的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-151">The response from the SAP system is saved to another location.</span></span> <span data-ttu-id="0b0c7-152">将包含 SAP 系统中的调用 Rfc 典型业务流程：</span><span class="sxs-lookup"><span data-stu-id="0b0c7-152">A typical orchestration for invoking RFCs in an SAP system would contain:</span></span>  
  
-   <span data-ttu-id="0b0c7-153">发送和接收形状来将消息发送到 SAP 系统并接收响应。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-153">Send and Receive shapes to send messages to the SAP system and receive responses.</span></span>  
  
-   <span data-ttu-id="0b0c7-154">单向接收端口接收请求消息将发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-154">A one-way receive port to receive request messages to send to the SAP system.</span></span>  
  
-   <span data-ttu-id="0b0c7-155">双向发送端口将请求消息发送到 SAP 系统和接收响应。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-155">A two-way send port to send request messages to the SAP system and receive responses.</span></span>  
  
-   <span data-ttu-id="0b0c7-156">单向发送端口将响应从 SAP 系统发送到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-156">A one-way send port to send the responses from the SAP system to a folder.</span></span>  
  
 <span data-ttu-id="0b0c7-157">示例业务流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="0b0c7-157">A sample orchestration resembles the following:</span></span>  
  
 <span data-ttu-id="0b0c7-158">![与连接端口的协调](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")</span><span class="sxs-lookup"><span data-stu-id="0b0c7-158">![Orchestration with ports connected](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="0b0c7-159">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="0b0c7-159">Adding Message Shapes</span></span>  
 <span data-ttu-id="0b0c7-160">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-160">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="0b0c7-161">中列出的名称*形状*列是前面的业务流程中显示的消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-161">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="0b0c7-162">形状</span><span class="sxs-lookup"><span data-stu-id="0b0c7-162">Shape</span></span>|<span data-ttu-id="0b0c7-163">形状类型</span><span class="sxs-lookup"><span data-stu-id="0b0c7-163">Shape Type</span></span>|<span data-ttu-id="0b0c7-164">属性</span><span class="sxs-lookup"><span data-stu-id="0b0c7-164">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="0b0c7-165">Receive_Request</span><span class="sxs-lookup"><span data-stu-id="0b0c7-165">Receive_Request</span></span>|<span data-ttu-id="0b0c7-166">Receive</span><span class="sxs-lookup"><span data-stu-id="0b0c7-166">Receive</span></span>|<span data-ttu-id="0b0c7-167">-将设置**名称**到*Receive_Request*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-167">-   Set **Name** to *Receive_Request*</span></span><br /><span data-ttu-id="0b0c7-168">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-168">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="0b0c7-169">Send_LOB</span><span class="sxs-lookup"><span data-stu-id="0b0c7-169">Send_LOB</span></span>|<span data-ttu-id="0b0c7-170">Send</span><span class="sxs-lookup"><span data-stu-id="0b0c7-170">Send</span></span>|<span data-ttu-id="0b0c7-171">-将设置**名称**到*Send_LOB*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-171">-   Set **Name** to *Send_LOB*</span></span>|  
|<span data-ttu-id="0b0c7-172">Receive_LOB</span><span class="sxs-lookup"><span data-stu-id="0b0c7-172">Receive_LOB</span></span>|<span data-ttu-id="0b0c7-173">Receive</span><span class="sxs-lookup"><span data-stu-id="0b0c7-173">Receive</span></span>|<span data-ttu-id="0b0c7-174">-将设置**名称**到*Receive_LOB*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-174">-   Set **Name** to *Receive_LOB*</span></span><br /><span data-ttu-id="0b0c7-175">-将设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-175">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="0b0c7-176">Send_Response</span><span class="sxs-lookup"><span data-stu-id="0b0c7-176">Send_Response</span></span>|<span data-ttu-id="0b0c7-177">Send</span><span class="sxs-lookup"><span data-stu-id="0b0c7-177">Send</span></span>|<span data-ttu-id="0b0c7-178">-将设置**名称**到*Send_Response*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-178">-   Set **Name** to *Send_Response*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="0b0c7-179">添加端口</span><span class="sxs-lookup"><span data-stu-id="0b0c7-179">Adding Ports</span></span>  
 <span data-ttu-id="0b0c7-180">为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-180">Specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="0b0c7-181">中列出的名称*端口*列是业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-181">The names listed in the *Port* column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="0b0c7-182">端口</span><span class="sxs-lookup"><span data-stu-id="0b0c7-182">Port</span></span>|<span data-ttu-id="0b0c7-183">属性</span><span class="sxs-lookup"><span data-stu-id="0b0c7-183">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="0b0c7-184">ReceiveMsgPort</span><span class="sxs-lookup"><span data-stu-id="0b0c7-184">ReceiveMsgPort</span></span>|<span data-ttu-id="0b0c7-185">-将设置**标识符**到*ReceiveMsgPort*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-185">-   Set **Identifier** to *ReceiveMsgPort*</span></span><br /><span data-ttu-id="0b0c7-186">-将设置**类型**到*ReceiveMsgPortType*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-186">-   Set **Type** to *ReceiveMsgPortType*</span></span><br /><span data-ttu-id="0b0c7-187">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-187">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="0b0c7-188">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-188">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="0b0c7-189">SendToLOBPort</span><span class="sxs-lookup"><span data-stu-id="0b0c7-189">SendToLOBPort</span></span>|<span data-ttu-id="0b0c7-190">-将设置**标识符**到*SendToLOBPort*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-190">-   Set **Identifier** to *SendToLOBPort*</span></span><br /><span data-ttu-id="0b0c7-191">-将设置**类型**到*SendToLOBPortType*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-191">-   Set **Type** to *SendToLOBPortType*</span></span><br /><span data-ttu-id="0b0c7-192">-将设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-192">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="0b0c7-193">-将设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-193">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="0b0c7-194">SendMsgPort</span><span class="sxs-lookup"><span data-stu-id="0b0c7-194">SendMsgPort</span></span>|<span data-ttu-id="0b0c7-195">-将设置**标识符**到*SendMsgPort*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-195">-   Set **Identifier** to *SendMsgPort*</span></span><br /><span data-ttu-id="0b0c7-196">-将设置**类型**到*SendMsgPortType*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-196">-   Set **Type** to *SendMsgPortType*</span></span><br /><span data-ttu-id="0b0c7-197">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-197">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="0b0c7-198">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-198">-   Set **Communication Direction** to *Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="0b0c7-199">指定消息的操作形状并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="0b0c7-199">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="0b0c7-200">下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-200">The following table specifies the properties and their values to be set to specify messages for action shapes and linking them to the ports.</span></span> <span data-ttu-id="0b0c7-201">中列出的名称*形状*列是前面的业务流程中显示的消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-201">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="0b0c7-202">形状</span><span class="sxs-lookup"><span data-stu-id="0b0c7-202">Shape</span></span>|<span data-ttu-id="0b0c7-203">属性</span><span class="sxs-lookup"><span data-stu-id="0b0c7-203">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="0b0c7-204">Receive_Request</span><span class="sxs-lookup"><span data-stu-id="0b0c7-204">Receive_Request</span></span>|<span data-ttu-id="0b0c7-205">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-205">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="0b0c7-206">-将设置**操作**到*ReceiveMsgPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-206">-   Set **Operation** to *ReceiveMsgPort.Operation_1.Request*</span></span>|  
|<span data-ttu-id="0b0c7-207">Send_LOB</span><span class="sxs-lookup"><span data-stu-id="0b0c7-207">Send_LOB</span></span>|<span data-ttu-id="0b0c7-208">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-208">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="0b0c7-209">-将设置**操作**到*SendToLOBPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-209">-   Set **Operation** to *SendToLOBPort.Operation_1.Request*</span></span>|  
|<span data-ttu-id="0b0c7-210">Receive_LOB</span><span class="sxs-lookup"><span data-stu-id="0b0c7-210">Receive_LOB</span></span>|<span data-ttu-id="0b0c7-211">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-211">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="0b0c7-212">-将设置**操作**到*SendToLOBPort.Operation_1.Response*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-212">-   Set **Operation** to *SendToLOBPort.Operation_1.Response*</span></span>|  
|<span data-ttu-id="0b0c7-213">Send_Response</span><span class="sxs-lookup"><span data-stu-id="0b0c7-213">Send_Response</span></span>|<span data-ttu-id="0b0c7-214">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-214">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="0b0c7-215">-将设置**操作**到*SendMsgPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="0b0c7-215">-   Set **Operation** to *SendMsgPort.Operation_1.Request*</span></span>|  
  
 <span data-ttu-id="0b0c7-216">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-216">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="0b0c7-217">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-217">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0b0c7-218">有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-218">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="0b0c7-219">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="0b0c7-219">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="0b0c7-220">部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-220">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="0b0c7-221">必须使用 BizTalk Server 管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-221">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="0b0c7-222">有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-222">For more information about configuring an application, see [How to Configure an Application](../../core/how-to-configure-an-application.md).</span></span>
  
 <span data-ttu-id="0b0c7-223">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="0b0c7-223">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="0b0c7-224">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-224">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="0b0c7-225">映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-225">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="0b0c7-226">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="0b0c7-226">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="0b0c7-227">硬盘和放置请求消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-227">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="0b0c7-228">BizTalk 业务流程将使用请求消息并将其发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-228">The BizTalk orchestration will consume the request message and send it to the SAP system.</span></span>  
  
    -   <span data-ttu-id="0b0c7-229">硬盘和 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-229">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the SAP system.</span></span>  
  
    -   <span data-ttu-id="0b0c7-230">定义物理 WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-230">Define a physical WCF-Custom or WCF-SAP send port to send messages to the SAP system.</span></span> <span data-ttu-id="0b0c7-231">你必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-231">You must also specify the action in the send port.</span></span> <span data-ttu-id="0b0c7-232">有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-232">For information about how to create ports, see [Manually configure a physical port binding to the SAP adapter](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).</span></span>
  
        > [!NOTE]
        >  <span data-ttu-id="0b0c7-233">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-233">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file containing information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="0b0c7-234">从 BizTalk Server 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-234">You can import this binding file from the BizTalk Server Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="0b0c7-235">有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-235">For more information, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
## <a name="starting-the-application"></a><span data-ttu-id="0b0c7-236">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="0b0c7-236">Starting the Application</span></span>  
 <span data-ttu-id="0b0c7-237">你必须启动调用 RFC SAP 系统中的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-237">You must start the BizTalk application for invoking an RFC in the SAP system.</span></span> <span data-ttu-id="0b0c7-238">有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)或[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-238">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md) or [how to start an application](../../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>
  
 <span data-ttu-id="0b0c7-239">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="0b0c7-239">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="0b0c7-240">FILE 接收端口，以便运行业务流程的是接收请求消息。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-240">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="0b0c7-241">要从业务流程接收响应消息的文件发送端口正在运行。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-241">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="0b0c7-242">WCF 自定义或 WCF SAP 发送端口将消息发送到 SAP 系统正在运行。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-242">The WCF-Custom or WCF-SAP send port to send messages to the SAP system is running.</span></span>  
  
-   <span data-ttu-id="0b0c7-243">BizTalk 业务流程操作正在运行。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-243">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="0b0c7-244">执行该操作</span><span class="sxs-lookup"><span data-stu-id="0b0c7-244">Executing the Operation</span></span>  
 <span data-ttu-id="0b0c7-245">运行应用程序后，必须在预定义位置删除业务流程的请求消息。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-245">After you run the application, you must drop a request message for the orchestration at a predefined location.</span></span> <span data-ttu-id="0b0c7-246">请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)需要了解的有关调用 RFC SAP 系统中的请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-246">See [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md) to know about the schema for the request message for invoking an RFC in an SAP system.</span></span> <span data-ttu-id="0b0c7-247">例如，要调用 RFC_CUSTOMER_GET 的请求消息是：</span><span class="sxs-lookup"><span data-stu-id="0b0c7-247">For example, the request message to invoke RFC_CUSTOMER_GET is:</span></span>  
  
```  
<RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <KUNNR>0000001390</KUNNR>  
  <NAME1>*</NAME1>  
  <CUSTOMER_T/>  
</RFC_CUSTOMER_GET>  
```  
  
 <span data-ttu-id="0b0c7-248">业务流程使用该消息，并将其发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-248">The orchestration consumes the message and sends it to the SAP system.</span></span> <span data-ttu-id="0b0c7-249">从 SAP 系统的响应保存在定义为业务流程的一部分的其他文件位置中。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-249">The response from the SAP system is saved at other file location defined as part of the orchestration.</span></span> <span data-ttu-id="0b0c7-250">例如，来自以上的请求消息的 SAP 系统的响应是：</span><span class="sxs-lookup"><span data-stu-id="0b0c7-250">For example, the response from the SAP system for the above request message is:</span></span>  
  
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
  
## <a name="possible-exceptions"></a><span data-ttu-id="0b0c7-251">可能的异常</span><span class="sxs-lookup"><span data-stu-id="0b0c7-251">Possible Exceptions</span></span>  
 <span data-ttu-id="0b0c7-252">调用中使用 BizTalk Server 某个 SAP 系统的 RFC 时可能遇到的异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-252">For information about the exceptions you might encounter while invoking an RFC in an SAP system using BizTalk Server, see [Exceptions and Error Handling with the SAP adapter](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="0b0c7-253">最佳实践</span><span class="sxs-lookup"><span data-stu-id="0b0c7-253">Best Practices</span></span>  
 <span data-ttu-id="0b0c7-254">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-254">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the bindings file.</span></span> <span data-ttu-id="0b0c7-255">一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-255">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="0b0c7-256">有关绑定文件的详细信息，请参阅[重用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="0b0c7-256">For more information about binding files, see [Reuse SAP adapter bindings](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0c7-257">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b0c7-257">See Also</span></span>  
[<span data-ttu-id="0b0c7-258">开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="0b0c7-258">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)