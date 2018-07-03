---
title: 接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFC calls, receiving using BizTalk Server
ms.assetid: 822fd9fb-772f-4910-a11e-25c1d5dca6e1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e70e2b81fd71a01ef6eae9e77ae3efea8cbf494
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986982"
---
# <a name="receive-inbound-rfc-calls-from-sap-using-biztalk-server"></a><span data-ttu-id="8b0ae-102">接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用</span><span class="sxs-lookup"><span data-stu-id="8b0ae-102">Receive Inbound RFC Calls from SAP using BizTalk Server</span></span>
<span data-ttu-id="8b0ae-103">在 RFC 服务器方案中，有三个实体：</span><span class="sxs-lookup"><span data-stu-id="8b0ae-103">In an RFC server scenario, there are three entities:</span></span>  
  
- <span data-ttu-id="8b0ae-104">将请求发送到 SAP 调用 RFC SAP 客户端。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-104">An SAP client that sends a request to SAP to invoke an RFC.</span></span> <span data-ttu-id="8b0ae-105">这可以在使用 SAP GUI 或通过调用 RFC 客户端进行调用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-105">This could be invoked either by using the SAP GUI or by making an RFC client call through the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="8b0ae-106">SAP 系统，其中包含 SAP 客户端调用的 RFC 函数定义。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-106">The SAP system that contains an RFC function definition that the SAP client invokes.</span></span> <span data-ttu-id="8b0ae-107">在请求将传递该 SAP 系统到 RFC 服务器 （适配器）。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-107">The SAP system passes on the request to the RFC server (the adapter).</span></span> <span data-ttu-id="8b0ae-108">这用于在适配器获取 SAP 服务器使该适配器为 RFC 调用的元数据。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-108">This is used by the adapter to get the metadata of the RFC call that the SAP server makes into the adapter.</span></span>  
  
- <span data-ttu-id="8b0ae-109">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ，充当 RFC 服务器和承载实际的 RFC。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] that acts as the RFC server and hosts the actual RFC.</span></span>  
  
  <span data-ttu-id="8b0ae-110">第一个实体，SAP 客户端，不是本主题中讨论的。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-110">The first entity, the SAP client, is not discussed in this topic.</span></span> <span data-ttu-id="8b0ae-111">如果使用 SAP GUI 来调用 RFC，请参阅 SAP 文档。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-111">If you are using the SAP GUI to invoke an RFC, refer to SAP documentation.</span></span> <span data-ttu-id="8b0ae-112">如果使用的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]若要调用 RFC，请参阅[调用中使用 BizTalk server 的 SAP 的 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-112">If you are using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to invoke an RFC, see [Invoke RFCs in SAP by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="8b0ae-113">本部分将说明了如何使用适配器来接收 RFC 服务器调用，RFC 调用由 SAP 客户端之后。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-113">This section provides instructions on how to use the adapter to receive an RFC server call, once the RFC is invoked by an SAP client.</span></span> <span data-ttu-id="8b0ae-114">有关详细信息的适配器如何支持接收 RFC 服务器调用使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[Rfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-114">For more information on how the adapter supports receiving RFC server calls using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Operations on RFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).</span></span>  
  
## <a name="how-to-receive-an-inbound-rfc-call-from-the-sap-system"></a><span data-ttu-id="8b0ae-115">如何从 SAP 系统接收的入站的 RFC 调用？</span><span class="sxs-lookup"><span data-stu-id="8b0ae-115">How to Receive an Inbound RFC Call from the SAP System?</span></span>  
 <span data-ttu-id="8b0ae-116">对 SAP 系统使用执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-116">Performing an operation on an SAP system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create SAP applications](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md).</span></span> <span data-ttu-id="8b0ae-117">若要从 SAP 系统接收 RFC 调用，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="8b0ae-117">To receive an RFC call from the SAP system, these tasks are:</span></span>  
  
1. <span data-ttu-id="8b0ae-118">配置 SAP 系统将在这种情况下发送到外部应用程序，RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-118">Configure your SAP system to send RFC to an external application, in this case the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
2. <span data-ttu-id="8b0ae-119">创建 BizTalk 项目和生成的在 RFC 架构的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将接收来自 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-119">Create a BizTalk project and generate schema for the RFC that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] will be receiving from the SAP system.</span></span>  
  
3. <span data-ttu-id="8b0ae-120">创建在 BizTalk 项目中为接收来自 SAP 系统的消息和发送响应消息。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-120">Create messages in the BizTalk project for receiving messages from the SAP system and sending responses.</span></span>  
  
4. <span data-ttu-id="8b0ae-121">创建业务流程，以便接收来自 SAP 系统的 RFC、 处理它，并发送到 SAP 系统的响应。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-121">Create an orchestration to receive an RFC from the SAP system, process it, and send the response to the SAP system.</span></span>  
  
5. <span data-ttu-id="8b0ae-122">生成并部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-122">Build and deploy the BizTalk project.</span></span>  
  
6. <span data-ttu-id="8b0ae-123">配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-123">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
7. <span data-ttu-id="8b0ae-124">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-124">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="8b0ae-125">本主题介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-125">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="activities-on-the-sap-system"></a><span data-ttu-id="8b0ae-126">SAP 系统上的活动</span><span class="sxs-lookup"><span data-stu-id="8b0ae-126">Activities on the SAP System</span></span>  
 <span data-ttu-id="8b0ae-127">使用之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要接收来自 SAP 系统的入站的 RFC 调用，请确保完成 SAP 系统上的以下任务。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-127">Before using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to receive inbound RFC calls from the SAP system, make sure you complete the following tasks on the SAP system.</span></span>  
  
- <span data-ttu-id="8b0ae-128">SAP 适配器的 RFC 目标必须存在。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-128">An RFC destination for the SAP adapter must exist.</span></span> <span data-ttu-id="8b0ae-129">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收来自 SAP 系统通过 SAP 系统上定义的 RFC 目标的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-129">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] receives RFCs from the SAP system through an RFC destination defined on the SAP system.</span></span> <span data-ttu-id="8b0ae-130">RFC 目标包含 SAP 网关主机、 SAP 网关服务和 SAP 程序 ID，必须在代码中指定连接 URI 中。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-130">The RFC destination contains the SAP Gateway Host, the SAP Gateway Service, and the SAP Program ID that you must specify in the connection URI in your code.</span></span> <span data-ttu-id="8b0ae-131">有关如何设置上 SAP 的 RFC 目标的信息，请参阅[创建 RFC、 RFC 目标和发送从 SAP 系统的 RFC](creating-an-rfc-in-an-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-131">For information about how to setup an RFC destination on SAP, see [Create an RFC, RFC destination, and send an RFC from SAP system](creating-an-rfc-in-an-sap-system.md).</span></span>  
  
- <span data-ttu-id="8b0ae-132">必须创建 SAP 系统定义的 RFC 函数模块。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-132">You must create a function module that defines the RFC on the SAP system.</span></span> <span data-ttu-id="8b0ae-133">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 系统上使用 RFC 定义来检索有关 RFC （两者均在设计时和运行时） 的元数据。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-133">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the RFC definition on the SAP system to retrieve metadata about the RFC (both at design-time and at runtime).</span></span> <span data-ttu-id="8b0ae-134">有关详细信息请参阅[在 SAP 系统中创建 RFC](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-134">For more information see [Creating an RFC in an SAP System](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).</span></span>  
  
   <span data-ttu-id="8b0ae-135">下面是源代码的添加两个整数并返回其结果的 RFC SAP 系统上的示例。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-135">The following is an example of the source code on the SAP system for an RFC that adds two integers and returns their result.</span></span> <span data-ttu-id="8b0ae-136">该代码通过指定的目标只是调用 RFC。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-136">The code merely calls the RFC through a specified destination.</span></span> <span data-ttu-id="8b0ae-137">函数的实现是通过 SAP 适配器客户端代码。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-137">The implementation of the function is done by the SAP adapter client code.</span></span>  
  
  ```  
  FUNCTION Z_RFC_ADD.  
  *"------------------------------------------------------------------  
  *"  
  *"Local interface:  
  *"  IMPORTING  
  *"     VALUE(X) TYPE  INT4  
  *"     VALUE(Y) TYPE  INT4  
  *"     VALUE(DEST) TYPE  CHAR20 DEFAULT 'SAPADAPTER'  
  *"  EXPORTING  
  *"     VALUE(RESULT) TYPE  INT4  
  *"------------------------------------------------------------------  
  CALL FUNCTION 'Z_RFC_ADD' DESTINATION DEST  
    EXPORTING X = X  
              Y = Y  
    IMPORTING RESULT = RESULT.  
  
  ENDFUNCTION.  
  ```  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="8b0ae-138">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="8b0ae-138">Sample Based On This Topic</span></span>  
 <span data-ttu-id="8b0ae-139">示例中，RFCServer，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-139">A sample, RFCServer, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="8b0ae-140">有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-140">For more information, see [Samples for the SAP adapter](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).</span></span>  
  
## <a name="generating-the-schema"></a><span data-ttu-id="8b0ae-141">生成架构</span><span class="sxs-lookup"><span data-stu-id="8b0ae-141">Generating the Schema</span></span>  
 <span data-ttu-id="8b0ae-142">在本主题中，若要演示如何从 SAP 系统中，接收的入站的 RFC 调用我们生成的架构*Z_RFC_ADD* RFC。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-142">In this topic, to demonstrate how to receive an inbound RFC call from the SAP system, we generate the schema for *Z_RFC_ADD* RFC.</span></span> <span data-ttu-id="8b0ae-143">在上一步中创建此 RFC。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-143">You created this RFC in the previous step.</span></span> <span data-ttu-id="8b0ae-144">此 RFC 使用两个整数值作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-144">This RFC takes two integer values as input parameters.</span></span>  
  
 <span data-ttu-id="8b0ae-145">请参阅[浏览、 搜索和获取元数据中 SAP RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)有关如何为特定 RFC 生成架构的说明。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-145">See [Browse, search, and get Metadata for RFC Operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) for instructions on how to generate schema for a particular RFC.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b0ae-146">因为您正在生成的入站 RFC 调用的架构，请确保选择**服务 （入站操作）** 从**选择协定类型**下拉列表中的[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-146">Because you are generating the schema for an inbound RFC call, make sure you select **Service (Inbound operation)** from the **Select contract type** drop-down list in the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="8b0ae-147">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="8b0ae-147">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="8b0ae-148">先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-148">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="8b0ae-149">一条消息通常是一个变量，要为其类型定义由相应的架构。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-149">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="8b0ae-150">必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-150">You must link the schema you generated in the first step to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="8b0ae-151">对于本主题中，您必须创建两条消息，另一个用于接收来自 SAP 系统，另一个将发送到 SAP 系统的响应消息。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-151">For this topic, you must create two messages—one to receive messages from the SAP system and the other to send a response to the SAP system.</span></span>  
  
 <span data-ttu-id="8b0ae-152">执行以下步骤以创建消息并将其链接到该架构：</span><span class="sxs-lookup"><span data-stu-id="8b0ae-152">Perform the following steps to create messages and link them to the schema:</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="8b0ae-153">若要创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="8b0ae-153">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="8b0ae-154">将新的业务流程添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-154">Add a new orchestration to the BizTalk project.</span></span>  
  
2.  <span data-ttu-id="8b0ae-155">打开业务流程视图 BizTalk 项目中，如果还没有打开。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-155">Open the orchestration view the BizTalk project, if not already open.</span></span> <span data-ttu-id="8b0ae-156">单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-156">Click **View**, point to **Other Windows**, and click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="8b0ae-157">在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-157">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="8b0ae-158">右键单击新创建消息，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-158">Right-click the newly create message and select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="8b0ae-159">在中**属性**窗格**Message_1**，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-159">In the **Properties** pane for **Message_1**, do the following.</span></span>  
  
    |<span data-ttu-id="8b0ae-160">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8b0ae-160">Use this</span></span>|<span data-ttu-id="8b0ae-161">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8b0ae-161">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8b0ae-162">Identifier</span><span class="sxs-lookup"><span data-stu-id="8b0ae-162">Identifier</span></span>|<span data-ttu-id="8b0ae-163">类型**请求**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-163">Type **Request**.</span></span>|  
    |<span data-ttu-id="8b0ae-164">消息类型</span><span class="sxs-lookup"><span data-stu-id="8b0ae-164">Message Type</span></span>|<span data-ttu-id="8b0ae-165">从下拉列表中，展开**架构**，然后选择*RFCServer.SAPBindingSchema.Z_RFC_ADD*，其中*RFCServer*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-165">From the drop-down list, expand **Schemas**, and select *RFCServer.SAPBindingSchema.Z_RFC_ADD*, where *RFCServer* is the name of your BizTalk project.</span></span> <span data-ttu-id="8b0ae-166">*SAPBindingSchema*是为 RFC 生成的架构*Z_RFC_ADD*。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-166">*SAPBindingSchema* is the schema generated for the RFC *Z_RFC_ADD*.</span></span>|  
  
6.  <span data-ttu-id="8b0ae-167">重复步骤 2，以创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-167">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="8b0ae-168">在中**属性**窗格中的新消息，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-168">In the **Properties** pane for the new message, do the following.</span></span>  
  
    |<span data-ttu-id="8b0ae-169">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8b0ae-169">Use this</span></span>|<span data-ttu-id="8b0ae-170">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8b0ae-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8b0ae-171">Identifier</span><span class="sxs-lookup"><span data-stu-id="8b0ae-171">Identifier</span></span>|<span data-ttu-id="8b0ae-172">类型**响应**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-172">Type **Response**.</span></span>|  
    |<span data-ttu-id="8b0ae-173">消息类型</span><span class="sxs-lookup"><span data-stu-id="8b0ae-173">Message Type</span></span>|<span data-ttu-id="8b0ae-174">从下拉列表中，展开**架构**，然后选择*RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-174">From the drop-down list, expand **Schemas**, and select *RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="8b0ae-175">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="8b0ae-175">Setting up the Orchestration</span></span>  
 <span data-ttu-id="8b0ae-176">必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，接收来自 SAP 系统的 RFC 服务器调用。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-176">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving RFC server calls from the SAP system.</span></span> <span data-ttu-id="8b0ae-177">此示例中，请考虑其中 RFC 客户端将请求发送到 SAP 系统，以添加两个整数的方案。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-177">For this example, consider a scenario where an RFC client sends a request to the SAP system to add two integers.</span></span> <span data-ttu-id="8b0ae-178">SAP 系统接受请求，使用输入参数，并将其传递到托管的外部 RFC 服务器[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-178">The SAP system takes the request, with the input parameters, and passes it on to the external RFC server hosted by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="8b0ae-179">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收来自 SAP 系统、 过程添加两个整数的请求的请求，并生成响应。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-179">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] receives the request from the SAP system, process the request to add two integers, and generates a response.</span></span> <span data-ttu-id="8b0ae-180">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将传递到 SAP 系统，反过来，传递到 RFC 客户端的响应。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-180">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] passes the response to the SAP system, which in turn, is passed on to the RFC client.</span></span>  
  
 <span data-ttu-id="8b0ae-181">若要实现此业务流程的一部分，必须包含该业务流程：</span><span class="sxs-lookup"><span data-stu-id="8b0ae-181">To achieve this as part of an orchestration, the orchestration must contain:</span></span>  
  
- <span data-ttu-id="8b0ae-182">一个双向接收端口以接收来自 SAP 系统的 RFC 服务器请求并发送响应。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-182">A two-way receive port to receive the RFC server request from the SAP system and send the response.</span></span>  
  
- <span data-ttu-id="8b0ae-183">发送和接收形状。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-183">Send and Receive shapes.</span></span>  
  
- <span data-ttu-id="8b0ae-184">构造消息形状，以及在其中消息赋值形状，以处理 RFC 服务器请求来自 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-184">Construct Message shape, and within that a Message Assignment shape, to process the RFC server request coming from the SAP system.</span></span>  
  
  <span data-ttu-id="8b0ae-185">RFC 服务器调用的示例业务流程如下所示。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-185">A sample orchestration for an RFC server call resembles the following.</span></span>  
  
  <span data-ttu-id="8b0ae-186">![用于发出 RFC 服务器调用的业务流程](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")</span><span class="sxs-lookup"><span data-stu-id="8b0ae-186">![Orchestration to make RFC server call](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="8b0ae-187">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="8b0ae-187">Adding Message Shapes</span></span>  
 <span data-ttu-id="8b0ae-188">请确保为每个消息形状中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-188">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="8b0ae-189">中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-189">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="8b0ae-190">形状</span><span class="sxs-lookup"><span data-stu-id="8b0ae-190">Shape</span></span>|<span data-ttu-id="8b0ae-191">形状类型</span><span class="sxs-lookup"><span data-stu-id="8b0ae-191">Shape Type</span></span>|<span data-ttu-id="8b0ae-192">属性</span><span class="sxs-lookup"><span data-stu-id="8b0ae-192">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="8b0ae-193">ListenToSAP</span><span class="sxs-lookup"><span data-stu-id="8b0ae-193">ListenToSAP</span></span>|<span data-ttu-id="8b0ae-194">Receive</span><span class="sxs-lookup"><span data-stu-id="8b0ae-194">Receive</span></span>|<span data-ttu-id="8b0ae-195">-设置**名称**到*ListenToSAP*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-195">-   Set **Name** to *ListenToSAP*</span></span><br /><span data-ttu-id="8b0ae-196">-设置**激活**到 *，则返回 True*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-196">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="8b0ae-197">SendResponse</span><span class="sxs-lookup"><span data-stu-id="8b0ae-197">SendResponse</span></span>|<span data-ttu-id="8b0ae-198">Send</span><span class="sxs-lookup"><span data-stu-id="8b0ae-198">Send</span></span>|<span data-ttu-id="8b0ae-199">-设置**名称**到*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-199">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="8b0ae-200">添加构造消息形状</span><span class="sxs-lookup"><span data-stu-id="8b0ae-200">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="8b0ae-201">若要处理传入的 RFC 调用，以添加两个整数值，必须添加构造消息形状和在其中向业务流程，两者之间的消息赋值形状发送形状。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-201">To process the incoming RFC call to add two integer values, you must add a Construct Message shape and within that a Message Assignment shape to your orchestration, between the two send shapes.</span></span> <span data-ttu-id="8b0ae-202">此示例中，为消息赋值形状调用以添加两个整数。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-202">For this example, the Message Assignment shape invokes to add two integers.</span></span> <span data-ttu-id="8b0ae-203">消息赋值形状也设置为要发送到 SAP 系统的响应的操作。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-203">The Message Assignment shape also sets the action for the response to be sent to the SAP system.</span></span>  
  
 <span data-ttu-id="8b0ae-204">对于构造消息形状中，请设置**构造的消息**属性设置为**响应**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-204">For the Construct Message shape, set the **Message Constructed** property to **Response**.</span></span>  
  
 <span data-ttu-id="8b0ae-205">用于处理 RFC 请求的代码可能与您的 BizTalk 项目相同的 Visual Studio 解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-205">The code to process the RFC request could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="8b0ae-206">添加两个整数的示例代码如下所示。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-206">A sample code for adding two integers looks like this.</span></span>  
  
```  
namespace RFCServerResponseCreator  
{  
    public class RFCServerResponseCreator  
    {  
        private static XmlDocument messageIn;  
        private static XmlDocument messageOut;  
        public static XmlDocument CreateRequest(int a, int b, string destination)  
        {  
            messageIn = new XmlDocument();  
            messageIn.LoadXml(  "<Z_RFC_ADD xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<DEST>" + destination + "</DEST>" +  
                                "<X>" + a + "</X>" +  
                                "<Y>" + b + "</Y>" +   
                                "</Z_RFC_ADD>"  
                             );  
            return messageIn;  
        }  
        public static XmlDocument CreateResponse(int a, int b)  
        {  
            int c = a + b;  
            messageOut = new XmlDocument();  
            messageOut.LoadXml( "<Z_RFC_ADDResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<RESULT>" + c + "</RESULT>" +   
                                "</Z_RFC_ADDResponse>"  
                              );  
            return messageOut;  
        }  
    }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="8b0ae-207">生成项目后，将在项目目录中创建 RFCServerResponseCreator.dll。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-207">After you build the project, RFCServerResponseCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="8b0ae-208">必须将此 DLL 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-208">You must add this DLL to the global assembly cache (GAC).</span></span>  
  
 <span data-ttu-id="8b0ae-209">添加以下表达式调用来调用此代码从消息赋值形状以及设置发送到 SAP 系统的响应的操作。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-209">Add the following expression to invoke this code from the Message Assignment shape and to set the action for the response sent to the SAP system.</span></span> <span data-ttu-id="8b0ae-210">若要添加一个表达式，请双击消息赋值形状以打开表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-210">To add an expression, double-click the Message Assignment shape to open the Expression Editor.</span></span>  
  
```  
Response = RFCServerResponseCreator.RFCServerResponseCreator.CreateResponse(Request.X, Request.Y);  
Response(WCF.Action) = "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response";  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b0ae-211">在响应消息，必须显式设置该操作。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-211">You must explicitly set the action on the response message.</span></span> <span data-ttu-id="8b0ae-212">如果未设置操作，WCF 自定义适配器到达的操作消息，通过追加到请求的操作的"响应"。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-212">If you do not set the action, WCF-Custom adapter arrives at the action message by appending “Response” to the request action.</span></span> <span data-ttu-id="8b0ae-213">因此，响应消息的操作变得`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-213">So, the action for the response message becomes `http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`.</span></span> <span data-ttu-id="8b0ae-214">但是，sapBinding 要求响应操作通过追加"/ 响应"到请求的操作，例如`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-214">However, the sapBinding expects the response action by appending “/response” to the request action, for example `http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`.</span></span>  
  
### <a name="adding-ports"></a><span data-ttu-id="8b0ae-215">添加端口</span><span class="sxs-lookup"><span data-stu-id="8b0ae-215">Adding Ports</span></span>  
 <span data-ttu-id="8b0ae-216">请确保指定的逻辑端口的以下属性。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-216">Make sure you specify the following properties for the logical port.</span></span> <span data-ttu-id="8b0ae-217">中列出的名称*端口*列是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-217">The name listed in the *Port* column is the name of the port as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="8b0ae-218">端口</span><span class="sxs-lookup"><span data-stu-id="8b0ae-218">Port</span></span>|<span data-ttu-id="8b0ae-219">属性</span><span class="sxs-lookup"><span data-stu-id="8b0ae-219">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="8b0ae-220">RFCServerPort</span><span class="sxs-lookup"><span data-stu-id="8b0ae-220">RFCServerPort</span></span>|<span data-ttu-id="8b0ae-221">-设置**标识符**到*RFCServerPort*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-221">-   Set **Identifier** to *RFCServerPort*</span></span><br /><span data-ttu-id="8b0ae-222">-设置**类型**到*RFCServerPortType*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-222">-   Set **Type** to *RFCServerPortType*</span></span><br /><span data-ttu-id="8b0ae-223">-设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-223">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="8b0ae-224">-设置**通信方向**到*接收发送*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-224">-   Set **Communication Direction** to *Receive-Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="8b0ae-225">为操作形状指定消息并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="8b0ae-225">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="8b0ae-226">下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-226">The following table specifies the properties and their values to be set to specify messages for action shapes and linking them to the ports.</span></span> <span data-ttu-id="8b0ae-227">中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-227">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="8b0ae-228">形状</span><span class="sxs-lookup"><span data-stu-id="8b0ae-228">Shape</span></span>|<span data-ttu-id="8b0ae-229">属性</span><span class="sxs-lookup"><span data-stu-id="8b0ae-229">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="8b0ae-230">ListenToSAP</span><span class="sxs-lookup"><span data-stu-id="8b0ae-230">ListenToSAP</span></span>|<span data-ttu-id="8b0ae-231">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-231">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="8b0ae-232">-设置**操作**到*RFCServerPort.Add.Request*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-232">-   Set **Operation** to *RFCServerPort.Add.Request*</span></span>|  
|<span data-ttu-id="8b0ae-233">SendResponse</span><span class="sxs-lookup"><span data-stu-id="8b0ae-233">SendResponse</span></span>|<span data-ttu-id="8b0ae-234">-设置**消息**到*FuncResponse*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-234">-   Set **Message** to *FuncResponse*</span></span><br /><span data-ttu-id="8b0ae-235">-设置**操作**到*RFCServerPort.Add.Response*</span><span class="sxs-lookup"><span data-stu-id="8b0ae-235">-   Set **Operation** to *RFCServerPort.Add.Response*</span></span>|  
  
 <span data-ttu-id="8b0ae-236">指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-236">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="8b0ae-237">你必须现在生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-237">You must now build the BizTalk solution and then deploy it to a BizTalk Server.</span></span> <span data-ttu-id="8b0ae-238">有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-238">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="8b0ae-239">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="8b0ae-239">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="8b0ae-240">部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-240">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="8b0ae-241">必须使用 BizTalk Server 管理控制台来配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-241">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="8b0ae-242">有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-242">For more information about configuring an application, see [How to Configure an Application](../../core/how-to-configure-an-application.md).</span></span>
  
 <span data-ttu-id="8b0ae-243">配置应用程序包括：</span><span class="sxs-lookup"><span data-stu-id="8b0ae-243">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="8b0ae-244">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-244">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="8b0ae-245">映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-245">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="8b0ae-246">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="8b0ae-246">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="8b0ae-247">定义 WCF 自定义或 WCF SAP 接收端口。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-247">Define a WCF-Custom or WCF-SAP receive port.</span></span> <span data-ttu-id="8b0ae-248">此端口将收到来自 SAP 系统的入站的 RFC 调用，将发送到 SAP 系统的响应。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-248">This port will receive inbound RFC calls from the SAP system and will send the response back to the SAP system.</span></span> <span data-ttu-id="8b0ae-249">有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-249">For information about how to create ports, see [Manually configure a physical port binding to the SAP adapter](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8b0ae-250">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-250">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file containing information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="8b0ae-251">从 BizTalk 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-251">You can import this binding file from the BizTalk Administration Console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="8b0ae-252">有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-252">For more information, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
  <span data-ttu-id="8b0ae-253">您还必须将 RFCServerResponseCreator 项目的程序集添加到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-253">You must also add the assembly for the RFCServerResponseCreator project to your BizTalk application.</span></span> <span data-ttu-id="8b0ae-254">创建此项目以处理来自 SAP 系统的 RFC 调用。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-254">You created this project to process the RFC call received from the SAP system.</span></span> <span data-ttu-id="8b0ae-255">为此：</span><span class="sxs-lookup"><span data-stu-id="8b0ae-255">To do so:</span></span>  
  
1.  <span data-ttu-id="8b0ae-256">在下导入绑定，其中的 BizTalk 应用程序的 BizTalk Server 管理控制台左侧的控制台树中右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-256">In the console tree on the left side of the BizTalk Server Administration console, under the BizTalk application where you imported the bindings, right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
2.  <span data-ttu-id="8b0ae-257">在中**添加资源**对话框中，单击**添加**，然后导航到包含 RFCServerResponseCreator.dll 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-257">In the **Add Resources** dialog box, Click **Add**, and then navigate to the folder containing RFCServerResponseCreator.dll.</span></span> <span data-ttu-id="8b0ae-258">选择该文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-258">Select the file and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="8b0ae-259">在中**添加资源**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-259">In the **Add Resources** dialog box, click **OK**.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="8b0ae-260">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="8b0ae-260">Starting the Application</span></span>  
 <span data-ttu-id="8b0ae-261">必须启动用于接收来自 SAP 系统的入站的 RFC 调用的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-261">You must start the BizTalk application for receiving inbound RFC calls from an SAP system.</span></span> <span data-ttu-id="8b0ae-262">在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)，并[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-262">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md), and [How to start an application](../../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>
  
 <span data-ttu-id="8b0ae-263">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="8b0ae-263">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="8b0ae-264">WCF 自定义或 WCF SAP 接收端口以接收 RFC 调用从 SAP 系统正在运行。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-264">The WCF-Custom or WCF-SAP receive port to receive RFC calls from the SAP system is running.</span></span>  
  
-   <span data-ttu-id="8b0ae-265">该操作的 BizTalk 业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-265">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="8b0ae-266">执行该操作</span><span class="sxs-lookup"><span data-stu-id="8b0ae-266">Executing the Operation</span></span>  
 <span data-ttu-id="8b0ae-267">在运行该应用程序后，必须将发送到 RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-267">After you run the application, you must send an RFC to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="8b0ae-268">可以通过 SAP 系统上执行事务 SE37 来执行操作。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-268">You can do so by executing the transaction SE37 on the SAP system.</span></span> <span data-ttu-id="8b0ae-269">此外必须指定的输入的参数的 RFC 调用。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-269">You must also specify the input parameters for the RFC call.</span></span> <span data-ttu-id="8b0ae-270">适配器接收的调用以及参数、 其进行处理，并将发送到 SAP 系统的响应。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-270">The adapter receives the call along with the parameters, processes it, and sends the response back to the SAP system.</span></span> <span data-ttu-id="8b0ae-271">你将能够从发送 RFC 位置在同一事务上看到的响应。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-271">You will be able to see the response on the same transaction from where you sent the RFC.</span></span>  
  
## <a name="possible-exceptions"></a><span data-ttu-id="8b0ae-272">可能的异常</span><span class="sxs-lookup"><span data-stu-id="8b0ae-272">Possible Exceptions</span></span>  
 <span data-ttu-id="8b0ae-273">从 SAP 系统使用 BizTalk Server 接收 RFC 服务器调用时可能会遇到异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-273">For information about the exceptions you might encounter while receiving an RFC server call from an SAP system using BizTalk Server, see [Exceptions and Error Handling with the SAP adapter](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="8b0ae-274">最佳实践</span><span class="sxs-lookup"><span data-stu-id="8b0ae-274">Best Practices</span></span>  
 <span data-ttu-id="8b0ae-275">部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-275">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the bindings file.</span></span> <span data-ttu-id="8b0ae-276">一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-276">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="8b0ae-277">有关绑定文件的详细信息，请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ae-277">For more information about binding files, see [Reuse SAP adapter bindings](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b0ae-278">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b0ae-278">See Also</span></span>  
[<span data-ttu-id="8b0ae-279">开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="8b0ae-279">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)