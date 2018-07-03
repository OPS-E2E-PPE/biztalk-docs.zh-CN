---
title: 运行业务组件使用 BizTalk Server 和 Siebel 适配器的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business components, performing operations by using BizTalk Server
- how to, perform operations on a business component by using BizTalk Server
ms.assetid: 5bd0f4d7-60ec-42ea-84c0-618aeef9688f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49236c834477111ec8b940b4b44585731994fcd3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989294"
---
# <a name="run-operations-on-business-components-using-biztalk-server-and-the-siebel-adapter"></a><span data-ttu-id="ac289-102">运行业务组件使用 BizTalk Server 和 Siebel 适配器的操作</span><span class="sxs-lookup"><span data-stu-id="ac289-102">Run Operations on Business Components Using BizTalk Server and the Siebel adapter</span></span>
<span data-ttu-id="ac289-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]业务组件上的图面可以调用的操作。</span><span class="sxs-lookup"><span data-stu-id="ac289-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces operations that can be invoked on a business component.</span></span> <span data-ttu-id="ac289-104">在业务组件上的操作可以划分为：</span><span class="sxs-lookup"><span data-stu-id="ac289-104">The operations on business components can be categorized as:</span></span>  
  
- <span data-ttu-id="ac289-105">在业务组件上的标准操作。</span><span class="sxs-lookup"><span data-stu-id="ac289-105">Standard operations on business components.</span></span> <span data-ttu-id="ac289-106">其中包括插入、 查询、 更新和删除。</span><span class="sxs-lookup"><span data-stu-id="ac289-106">These include Insert, Query, Update, and Delete.</span></span> <span data-ttu-id="ac289-107">本主题讨论如何使用执行这些操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ac289-107">This topic discusses how to perform these operations using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="ac289-108">对包含多值的组字段的业务组件操作。</span><span class="sxs-lookup"><span data-stu-id="ac289-108">Operations on business components containing multivalued group fields.</span></span> <span data-ttu-id="ac289-109">其中包括标准操作以及相关联，取消关联，Query_ [MVG_Child_Bussiness_Comp]。</span><span class="sxs-lookup"><span data-stu-id="ac289-109">These include the standard operations as well as Associate, Disassociate, Query_[MVG_Child_Bussiness_Comp].</span></span> <span data-ttu-id="ac289-110">有关执行这些操作的详细信息，请参阅[用在包含 MVG 字段使用 BizTalk Server 和 Siebel 适配器的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="ac289-110">For more information about performing these operations, see [Run Operations on Business Components with MVG Fields Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)</span></span>  
  
- <span data-ttu-id="ac289-111">包含选择列表字段的业务组件上的操作。</span><span class="sxs-lookup"><span data-stu-id="ac289-111">Operations on business components containing picklist fields.</span></span> <span data-ttu-id="ac289-112">有关执行这些操作的详细信息，请参阅[与选择列表字段使用 BizTalk Server 和 Siebel 适配器的业务组件上运行操作](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-112">For more information about performing these operations, see [Run Operations on Business Components with Picklist Fields Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md).</span></span>  
  
  <span data-ttu-id="ac289-113">详细了解如何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持业务组件上的操作，请参阅[上的 Siebel 业务组件操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-113">For more information about how the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] supports operations on business components, see [Operations on Business Components in Siebel](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md).</span></span> <span data-ttu-id="ac289-114">对于执行这些操作的消息的 SOAP 结构有关的详细信息，请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-114">For more information about the structure of SOAP messages for performing these operations, see [Message Schemas for Business Component Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).</span></span>  
  
## <a name="how-to-perform-operations-on-a-business-component"></a><span data-ttu-id="ac289-115">如何在业务组件上执行操作</span><span class="sxs-lookup"><span data-stu-id="ac289-115">How to Perform Operations on a Business Component</span></span>  
 <span data-ttu-id="ac289-116">执行对 Siebel 系统使用的操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-116">Performing an operation on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create BizTalk applications with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md).</span></span> 
 
 <span data-ttu-id="ac289-117">若要完成业务组件上的操作，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="ac289-117">To complete an operation on a business component, these tasks are:</span></span>  
  
1. <span data-ttu-id="ac289-118">创建 BizTalk 项目，并针对你想要在业务组件上调用的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="ac289-118">Create a BizTalk project and generate schema for operation you want to invoke on the business component.</span></span>  
  
2. <span data-ttu-id="ac289-119">用于发送和接收来自 Siebel 系统的消息在 BizTalk 项目中创建消息。</span><span class="sxs-lookup"><span data-stu-id="ac289-119">Create messages in the BizTalk project for sending and receiving messages from the Siebel system.</span></span>  
  
3. <span data-ttu-id="ac289-120">创建一个业务流程在 Siebel 系统调用的操作。</span><span class="sxs-lookup"><span data-stu-id="ac289-120">Create an orchestration to invoke an operation in the Siebel system.</span></span>  
  
4. <span data-ttu-id="ac289-121">生成并部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ac289-121">Build and deploy the BizTalk project.</span></span>  
  
5. <span data-ttu-id="ac289-122">配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="ac289-122">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
6. <span data-ttu-id="ac289-123">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac289-123">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="ac289-124">本主题介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="ac289-124">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="ac289-125">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="ac289-125">Sample Based On This Topic</span></span>  
 <span data-ttu-id="ac289-126">示例中，SiebelAccount，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ac289-126">A sample, SiebelAccount, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ac289-127">有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-127">For more information, see [Samples for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="ac289-128">生成架构</span><span class="sxs-lookup"><span data-stu-id="ac289-128">Generating Schema</span></span>  
 <span data-ttu-id="ac289-129">在本主题中，若要演示如何调用操作的业务组件，架构生成帐户业务组件中的 Insert 操作。</span><span class="sxs-lookup"><span data-stu-id="ac289-129">In this topic, to demonstrate how to invoke operations on a business component, schema are generated for the Insert operation in the Account business component.</span></span> <span data-ttu-id="ac289-130">请参阅[检索 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac289-130">See [Retrieving Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md) for more information about how to generate schema.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="ac289-131">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="ac289-131">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="ac289-132">先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="ac289-132">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="ac289-133">一条消息通常是一个变量，要为其类型定义由相应的架构。</span><span class="sxs-lookup"><span data-stu-id="ac289-133">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="ac289-134">必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="ac289-134">You must link the schema you generated in the first step to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="ac289-135">对于本主题中，您必须创建两条消息，另一个用于将请求发送到 Siebel 系统，另一个用于接收响应。</span><span class="sxs-lookup"><span data-stu-id="ac289-135">For this topic, you must create two messages—one to send a request to the Siebel system and the other to receive a response.</span></span>  
  
 <span data-ttu-id="ac289-136">执行以下步骤以创建消息并将其链接到该架构：</span><span class="sxs-lookup"><span data-stu-id="ac289-136">Perform the following steps to create messages and link them to the schema:</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="ac289-137">若要创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="ac289-137">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="ac289-138">打开业务流程视图 BizTalk 项目中，如果还没有打开。</span><span class="sxs-lookup"><span data-stu-id="ac289-138">Open the orchestration view the BizTalk project, if not already open.</span></span> <span data-ttu-id="ac289-139">单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="ac289-139">Click **View**, point to **Other Windows**, and click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="ac289-140">在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="ac289-140">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="ac289-141">右键单击新创建消息，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="ac289-141">Right-click the newly create message and select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="ac289-142">在中**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ac289-142">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="ac289-143">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ac289-143">Use this</span></span>|<span data-ttu-id="ac289-144">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ac289-144">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ac289-145">Identifier</span><span class="sxs-lookup"><span data-stu-id="ac289-145">Identifier</span></span>|<span data-ttu-id="ac289-146">类型**请求**。</span><span class="sxs-lookup"><span data-stu-id="ac289-146">Type **Request**.</span></span>|  
    |<span data-ttu-id="ac289-147">消息类型</span><span class="sxs-lookup"><span data-stu-id="ac289-147">Message Type</span></span>|<span data-ttu-id="ac289-148">从下拉列表中，展开**架构**，然后选择*SiebelAccount.SiebelBindingSchema.Insert*，其中*SiebelAccount*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="ac289-148">From the drop-down list, expand **Schemas**, and select *SiebelAccount.SiebelBindingSchema.Insert*, where *SiebelAccount* is the name of your BizTalk project.</span></span> <span data-ttu-id="ac289-149">*SiebelBindingSchema*是用于调用生成的架构*插入*上的操作*帐户*业务组件。</span><span class="sxs-lookup"><span data-stu-id="ac289-149">*SiebelBindingSchema* is the schema generated for invoking the *Insert* operation on *Account* business component.</span></span>|  
  
5.  <span data-ttu-id="ac289-150">重复上述步骤以创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="ac289-150">Repeat the previous step to create a new message.</span></span> <span data-ttu-id="ac289-151">在中**属性**窗格中的新消息，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ac289-151">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="ac289-152">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ac289-152">Use this</span></span>|<span data-ttu-id="ac289-153">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ac289-153">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ac289-154">Identifier</span><span class="sxs-lookup"><span data-stu-id="ac289-154">Identifier</span></span>|<span data-ttu-id="ac289-155">类型**响应**。</span><span class="sxs-lookup"><span data-stu-id="ac289-155">Type **Response**.</span></span>|  
    |<span data-ttu-id="ac289-156">消息类型</span><span class="sxs-lookup"><span data-stu-id="ac289-156">Message Type</span></span>|<span data-ttu-id="ac289-157">从下拉列表中，展开**架构**，然后选择*SiebelAccount.SiebelBindingSchema.InsertResponse*。</span><span class="sxs-lookup"><span data-stu-id="ac289-157">From the drop-down list, expand **Schemas**, and select *SiebelAccount.SiebelBindingSchema.InsertResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="ac289-158">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="ac289-158">Setting up the Orchestration</span></span>  
 <span data-ttu-id="ac289-159">必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行上一个 Siebel 业务组件操作。</span><span class="sxs-lookup"><span data-stu-id="ac289-159">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing an operation on a Siebel business component.</span></span> <span data-ttu-id="ac289-160">在将请求消息放在此业务流程，定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="ac289-160">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="ac289-161">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用此消息并将其传递到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="ac289-161">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] consumes this message and passes it on to the Siebel system.</span></span> <span data-ttu-id="ac289-162">来自 Siebel 系统的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="ac289-162">The response from the Siebel system is saved to another location.</span></span> <span data-ttu-id="ac289-163">将包含一个典型的业务流程在 Siebel 业务组件上执行操作：</span><span class="sxs-lookup"><span data-stu-id="ac289-163">A typical orchestration for performing operations on Siebel business components would contain:</span></span>  
  
- <span data-ttu-id="ac289-164">发送和接收形状来将消息发送到 Siebel 和接收响应。</span><span class="sxs-lookup"><span data-stu-id="ac289-164">Send and receive shapes to send messages to Siebel and receive responses.</span></span>  
  
- <span data-ttu-id="ac289-165">一个单向接收端口接收请求消息将发送到 Siebel。</span><span class="sxs-lookup"><span data-stu-id="ac289-165">A one-way receive port to receive request messages to send to Siebel.</span></span>  
  
- <span data-ttu-id="ac289-166">一个双向发送端口以将请求消息发送到 Siebel 和接收响应。</span><span class="sxs-lookup"><span data-stu-id="ac289-166">A two-way send port to send request messages to Siebel and receive responses.</span></span>  
  
- <span data-ttu-id="ac289-167">一个单向发送端口以从 Siebel 将响应发送到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ac289-167">A one-way send port to send the responses from Siebel to a folder.</span></span>  
  
  <span data-ttu-id="ac289-168">有关示例业务流程*插入*上的操作*帐户*业务组件将如下所示：</span><span class="sxs-lookup"><span data-stu-id="ac289-168">A sample orchestration for the *Insert* operation on an *Account* business component resembles the following:</span></span>  
  
  <span data-ttu-id="ac289-169">![用于在 Siebel BC 中插入数据的业务流程](../../adapters-and-accelerators/adapter-siebel/media/f005df04-dfbf-4c75-8f9b-2bc3a357d52b.gif "f005df04-dfbf-4c75-8f9b-2bc3a357d52b")</span><span class="sxs-lookup"><span data-stu-id="ac289-169">![Orchestration to insert data in Siebel BC](../../adapters-and-accelerators/adapter-siebel/media/f005df04-dfbf-4c75-8f9b-2bc3a357d52b.gif "f005df04-dfbf-4c75-8f9b-2bc3a357d52b")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="ac289-170">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="ac289-170">Adding Message Shapes</span></span>  
 <span data-ttu-id="ac289-171">请确保为每个消息形状中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="ac289-171">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="ac289-172">中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="ac289-172">The names listed in the *Shape* column are the names of the message shapes as displayed in the orchestration above.</span></span>  
  
|<span data-ttu-id="ac289-173">形状</span><span class="sxs-lookup"><span data-stu-id="ac289-173">Shape</span></span>|<span data-ttu-id="ac289-174">形状类型</span><span class="sxs-lookup"><span data-stu-id="ac289-174">Shape Type</span></span>|<span data-ttu-id="ac289-175">属性</span><span class="sxs-lookup"><span data-stu-id="ac289-175">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="ac289-176">ReceiveXML</span><span class="sxs-lookup"><span data-stu-id="ac289-176">ReceiveXML</span></span>|<span data-ttu-id="ac289-177">Receive</span><span class="sxs-lookup"><span data-stu-id="ac289-177">Receive</span></span>|<span data-ttu-id="ac289-178">-设置**名称**到*ReceiveXML*</span><span class="sxs-lookup"><span data-stu-id="ac289-178">-   Set **Name** to *ReceiveXML*</span></span><br /><span data-ttu-id="ac289-179">-设置**激活**到 *，则返回 True*</span><span class="sxs-lookup"><span data-stu-id="ac289-179">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="ac289-180">SendToLOB</span><span class="sxs-lookup"><span data-stu-id="ac289-180">SendToLOB</span></span>|<span data-ttu-id="ac289-181">Send</span><span class="sxs-lookup"><span data-stu-id="ac289-181">Send</span></span>|<span data-ttu-id="ac289-182">-设置**名称**到*SendToLOB*</span><span class="sxs-lookup"><span data-stu-id="ac289-182">-   Set **Name** to *SendToLOB*</span></span>|  
|<span data-ttu-id="ac289-183">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="ac289-183">ReceiveResponse</span></span>|<span data-ttu-id="ac289-184">Receive</span><span class="sxs-lookup"><span data-stu-id="ac289-184">Receive</span></span>|<span data-ttu-id="ac289-185">-设置**名称**到*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="ac289-185">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="ac289-186">-设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="ac289-186">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="ac289-187">SendResponse</span><span class="sxs-lookup"><span data-stu-id="ac289-187">SendResponse</span></span>|<span data-ttu-id="ac289-188">Send</span><span class="sxs-lookup"><span data-stu-id="ac289-188">Send</span></span>|<span data-ttu-id="ac289-189">-设置**名称**到*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="ac289-189">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="ac289-190">添加端口</span><span class="sxs-lookup"><span data-stu-id="ac289-190">Adding Ports</span></span>  
 <span data-ttu-id="ac289-191">请确保为每个逻辑端口中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="ac289-191">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="ac289-192">中列出的名称*端口*列是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="ac289-192">The names listed in the *Port* column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="ac289-193">端口</span><span class="sxs-lookup"><span data-stu-id="ac289-193">Port</span></span>|<span data-ttu-id="ac289-194">属性</span><span class="sxs-lookup"><span data-stu-id="ac289-194">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="ac289-195">FileIn</span><span class="sxs-lookup"><span data-stu-id="ac289-195">FileIn</span></span>|<span data-ttu-id="ac289-196">-设置**标识符**到*FileIn*</span><span class="sxs-lookup"><span data-stu-id="ac289-196">-   Set **Identifier** to *FileIn*</span></span><br /><span data-ttu-id="ac289-197">-设置**类型**到*FileInType*</span><span class="sxs-lookup"><span data-stu-id="ac289-197">-   Set **Type** to *FileInType*</span></span><br /><span data-ttu-id="ac289-198">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="ac289-198">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="ac289-199">-设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="ac289-199">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="ac289-200">LOBPort</span><span class="sxs-lookup"><span data-stu-id="ac289-200">LOBPort</span></span>|<span data-ttu-id="ac289-201">-设置**标识符**到*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="ac289-201">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="ac289-202">-设置**类型**到*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="ac289-202">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="ac289-203">-设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="ac289-203">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="ac289-204">-设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="ac289-204">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="ac289-205">SaveResponse</span><span class="sxs-lookup"><span data-stu-id="ac289-205">SaveResponse</span></span>|<span data-ttu-id="ac289-206">-设置**标识符**到*SaveResponse*</span><span class="sxs-lookup"><span data-stu-id="ac289-206">-   Set **Identifier** to *SaveResponse*</span></span><br /><span data-ttu-id="ac289-207">-设置**类型**到*SaveResponseType*</span><span class="sxs-lookup"><span data-stu-id="ac289-207">-   Set **Type** to *SaveResponseType*</span></span><br /><span data-ttu-id="ac289-208">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="ac289-208">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="ac289-209">-设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="ac289-209">-   Set **Communication Direction** to *Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="ac289-210">为操作形状指定消息并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="ac289-210">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="ac289-211">下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。</span><span class="sxs-lookup"><span data-stu-id="ac289-211">The following table specifies the properties and their values to be set to specify messages for action shapes and linking them to the ports.</span></span> <span data-ttu-id="ac289-212">中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="ac289-212">The names listed in the *Shape* column are the names of the message shapes as displayed in the orchestration above.</span></span>  
  
|<span data-ttu-id="ac289-213">形状</span><span class="sxs-lookup"><span data-stu-id="ac289-213">Shape</span></span>|<span data-ttu-id="ac289-214">属性</span><span class="sxs-lookup"><span data-stu-id="ac289-214">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="ac289-215">ReceiveXML</span><span class="sxs-lookup"><span data-stu-id="ac289-215">ReceiveXML</span></span>|<span data-ttu-id="ac289-216">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="ac289-216">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="ac289-217">-设置**操作**到*FileIn.Insert.Request*</span><span class="sxs-lookup"><span data-stu-id="ac289-217">-   Set **Operation** to *FileIn.Insert.Request*</span></span>|  
|<span data-ttu-id="ac289-218">SendToLOB</span><span class="sxs-lookup"><span data-stu-id="ac289-218">SendToLOB</span></span>|<span data-ttu-id="ac289-219">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="ac289-219">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="ac289-220">-设置**操作**到*LOBPort.Insert.Request*</span><span class="sxs-lookup"><span data-stu-id="ac289-220">-   Set **Operation** to *LOBPort.Insert.Request*</span></span>|  
|<span data-ttu-id="ac289-221">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="ac289-221">ReceiveResponse</span></span>|<span data-ttu-id="ac289-222">-设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="ac289-222">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="ac289-223">-设置**操作**到*LOBPort.Insert.Response*</span><span class="sxs-lookup"><span data-stu-id="ac289-223">-   Set **Operation** to *LOBPort.Insert.Response*</span></span>|  
|<span data-ttu-id="ac289-224">SendResponse</span><span class="sxs-lookup"><span data-stu-id="ac289-224">SendResponse</span></span>|<span data-ttu-id="ac289-225">-设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="ac289-225">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="ac289-226">-设置**操作**到*SaveResponse.Insert.Request*</span><span class="sxs-lookup"><span data-stu-id="ac289-226">-   Set **Operation** to *SaveResponse.Insert.Request*</span></span>|  
  
 <span data-ttu-id="ac289-227">指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="ac289-227">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="ac289-228">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ac289-228">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ac289-229">有关详细信息，请参阅[如何生成业务流程](../../core/how-to-build-orchestrations.md)并[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-229">For more information, see [How to Build Orchestrations](../../core/how-to-build-orchestrations.md) and [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="ac289-230">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ac289-230">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="ac289-231">部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="ac289-231">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="ac289-232">必须使用 BizTalk Server 管理控制台来配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac289-232">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="ac289-233">[如何创建应用程序](../../core/how-to-create-an-application.md)列出的步骤。</span><span class="sxs-lookup"><span data-stu-id="ac289-233">[How to Create an Application](../../core/how-to-create-an-application.md) lists the steps.</span></span>
  
 <span data-ttu-id="ac289-234">配置应用程序包括：</span><span class="sxs-lookup"><span data-stu-id="ac289-234">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="ac289-235">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="ac289-235">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="ac289-236">映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="ac289-236">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="ac289-237">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="ac289-237">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="ac289-238">硬盘和相应 file 端口将放置请求消息的位置上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="ac289-238">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="ac289-239">BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="ac289-239">The BizTalk orchestration will consume the request message and send it to the Siebel system.</span></span>  
  
  - <span data-ttu-id="ac289-240">硬盘和相应的 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="ac289-240">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the Siebel system.</span></span>  
  
  - <span data-ttu-id="ac289-241">定义一个物理 WCF 自定义或 Wcf-siebel 发送端口将消息发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="ac289-241">Define a physical WCF-Custom or WCF-Siebel send port to send messages to the Siebel system.</span></span> <span data-ttu-id="ac289-242">您必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="ac289-242">You must also specify the action in the send port.</span></span> <span data-ttu-id="ac289-243">有关如何创建端口的信息，请参阅[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-243">For information about how to create ports, see [Manually configure a physical port binding to the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md).</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="ac289-244">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="ac289-244">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file containing information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="ac289-245">从 BizTalk 管理控制台来创建发送端口 （对于出站调用），可以导入此绑定文件。</span><span class="sxs-lookup"><span data-stu-id="ac289-245">You can import this binding file from the BizTalk Administration Console to create send ports (for outbound calls).</span></span> <span data-ttu-id="ac289-246">有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件到 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-246">For more information, see [Configure a physical port binding using a port binding file to Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span></span>
  
## <a name="starting-the-application"></a><span data-ttu-id="ac289-247">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="ac289-247">Starting the Application</span></span>  
 <span data-ttu-id="ac289-248">必须启动 BizTalk 应用程序用于执行*插入*上的操作*帐户*在 Siebel 业务组件。</span><span class="sxs-lookup"><span data-stu-id="ac289-248">You must start the BizTalk application for performing an *Insert* operation on the *Account* business component in Siebel.</span></span> <span data-ttu-id="ac289-249">在启动 BizTalk 应用程序的说明，请参阅[启动 BizTalk 应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)或[启动业务流程](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-249">For instructions on starting a BizTalk application, see [Start a BizTalk Application](../../core/how-to-start-and-stop-a-biztalk-application.md) or [Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="ac289-250">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="ac289-250">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="ac289-251">文件接收端口接收请求消息的业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="ac289-251">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="ac289-252">运行文件发送端口以接收来自业务流程的响应消息。</span><span class="sxs-lookup"><span data-stu-id="ac289-252">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="ac289-253">WCF 自定义或 Wcf-siebel 发送端口将消息发送到 Siebel 系统正在运行。</span><span class="sxs-lookup"><span data-stu-id="ac289-253">The WCF-Custom or WCF-Siebel send port to send messages to the Siebel system is running.</span></span>  
  
-   <span data-ttu-id="ac289-254">该操作的 BizTalk 业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="ac289-254">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="ac289-255">执行该操作</span><span class="sxs-lookup"><span data-stu-id="ac289-255">Executing the Operation</span></span>  
 <span data-ttu-id="ac289-256">运行应用程序后，你必须请求消息放置到该 FILE 接收位置。</span><span class="sxs-lookup"><span data-stu-id="ac289-256">After you run the application, you must drop the request message to the FILE receive location.</span></span> <span data-ttu-id="ac289-257">请求消息的架构必须符合的架构 （上帐户业务组件） 的插入操作前面生成。</span><span class="sxs-lookup"><span data-stu-id="ac289-257">The schema of the request message must conform to the schema of the Insert operation (on Account business component) you generated earlier.</span></span> <span data-ttu-id="ac289-258">例如，要在帐户业务组件中插入一条记录的请求消息是：</span><span class="sxs-lookup"><span data-stu-id="ac289-258">For example, the request message to insert a record in the Account business component is:</span></span>  
  
```  
<Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
  <ArrayOfAccountInsertRecord>  
    <AccountInsertRecord xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects">  
      <Currency_x0020_Code>usd</Currency_x0020_Code>  
      <Current_x0020_Volume>9</Current_x0020_Volume>  
      <Customer_x0020_Account_x0020_Group>Sold-To Party</Customer_x0020_Account_x0020_Group>  
      <Location>Location_1</Location>  
      <Main_x0020_Phone_x0020_Number>4256543212</Main_x0020_Phone_x0020_Number>  
      <Name>Name_Surname</Name>  
      <Party_x0020_Name>test_party</Party_x0020_Name>  
      <Primary_x0020_Address_x0020_Id>1212 street</Primary_x0020_Address_x0020_Id>  
    </AccountInsertRecord>  
  </ArrayOfAccountInsertRecord>  
</Insert>  
```  
  
 <span data-ttu-id="ac289-259">请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)有关请求消息的架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac289-259">See [Message Schemas for Business Component Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md) for more information about the schema for the request message.</span></span>  
  
 <span data-ttu-id="ac289-260">业务流程将使用请求消息并将其传递到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="ac289-260">The orchestration consumes the request message and passes it to the Siebel system.</span></span> <span data-ttu-id="ac289-261">来自 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置。</span><span class="sxs-lookup"><span data-stu-id="ac289-261">The response from the Siebel system is saved at the other FILE location defined as part of the orchestration.</span></span> <span data-ttu-id="ac289-262">例如，从更高版本的请求消息的 Siebel 系统的响应是：</span><span class="sxs-lookup"><span data-stu-id="ac289-262">For example, the response from Siebel system for the above request message is:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<InsertResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation">  
  <InsertResult>  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">1-8ANYV</string>  
  </InsertResult>  
</InsertResponse>  
```  
  
## <a name="possible-exceptions"></a><span data-ttu-id="ac289-263">可能的异常</span><span class="sxs-lookup"><span data-stu-id="ac289-263">Possible Exceptions</span></span>  
 <span data-ttu-id="ac289-264">对业务组件使用执行操作时可能遇到的有关异常的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理与 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-264">For information about the exceptions you might encounter while performing an operation on business component using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Exceptions and Error Handling with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="ac289-265">最佳实践</span><span class="sxs-lookup"><span data-stu-id="ac289-265">Best Practices</span></span>  
 <span data-ttu-id="ac289-266">部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ac289-266">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="ac289-267">一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。</span><span class="sxs-lookup"><span data-stu-id="ac289-267">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="ac289-268">有关绑定文件的详细信息，请参阅[重用适配器绑定在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac289-268">For more information about binding files, see [Reuse adapter bindings in the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac289-269">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac289-269">See Also</span></span>  
[<span data-ttu-id="ac289-270">开发 BizTalk 应用程序使用 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="ac289-270">Develop BizTalk Applications using the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)