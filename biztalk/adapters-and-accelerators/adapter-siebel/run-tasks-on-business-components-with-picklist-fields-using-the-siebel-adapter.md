---
title: 使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, perform operations with picklist fields by using BizTalk Server
- business components, performing operations with picklist fields by using BizTalk Server
ms.assetid: b62d32fa-903a-442b-951b-2343ef719bd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c722caaad6e1474ac80a14843171550aa53b9d77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986078"
---
# <a name="run-operations-on-business-components-with-picklist-fields-using-biztalk-server-and-the-siebel-adapter"></a><span data-ttu-id="1cc12-102">使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作</span><span class="sxs-lookup"><span data-stu-id="1cc12-102">Run Operations on Business Components with Picklist Fields Using BizTalk Server and the Siebel adapter</span></span>
<span data-ttu-id="1cc12-103">Siebel 选择列表字段类型构成一系列可能的值从哪种客户端可以指定传递到 Siebel 系统的某些值。</span><span class="sxs-lookup"><span data-stu-id="1cc12-103">A Siebel picklist field type constitutes a collection of possible values from which client may specify a certain value to be passed onto the Siebel system.</span></span> <span data-ttu-id="1cc12-104">换而言之，选择列表字段包含一系列字段接受的值。</span><span class="sxs-lookup"><span data-stu-id="1cc12-104">In other words, a picklist field contains a list of accepted values for a field.</span></span> <span data-ttu-id="1cc12-105">有关选择列表及其类型的详细信息，请参阅 Siebel 文档。</span><span class="sxs-lookup"><span data-stu-id="1cc12-105">For more information about picklist and their types, refer to Siebel documentation.</span></span> <span data-ttu-id="1cc12-106">详细了解如何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持与选择列表字段的业务组件上的操作，请参阅[上的 Siebel 业务组件操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-106">For more information about how the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] supports operations on business components with picklist fields, see [Operations on Business Components in Siebel](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md).</span></span>  
  
 <span data-ttu-id="1cc12-107">生成包含静态绑定选择列表字段 （一种选择列表） 的业务组件元数据时，接受的值的选择列表还作为元数据的一部分发布。</span><span class="sxs-lookup"><span data-stu-id="1cc12-107">When you generate metadata for a business component containing a static bounded picklist field (a type of picklist), the accepted values for the picklist are also published as part of the metadata.</span></span> <span data-ttu-id="1cc12-108">如果选择列表字段中插入一个值，则必须指定一个值，元数据中发布。</span><span class="sxs-lookup"><span data-stu-id="1cc12-108">If you are inserting a value into a picklist field, you must specify a value that is published in the metadata.</span></span>  
  
## <a name="how-to-perform-operations-on-business-components-with-picklist-fields"></a><span data-ttu-id="1cc12-109">如何执行与选择列表字段的业务组件上的操作？</span><span class="sxs-lookup"><span data-stu-id="1cc12-109">How to Perform Operations on Business Components with Picklist Fields?</span></span>  
 <span data-ttu-id="1cc12-110">执行对 Siebel 系统使用的操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-110">Performing an operation on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create BizTalk applications with Siebel adapter](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md).</span></span> 
 
 <span data-ttu-id="1cc12-111">若要完成选择列表字段具有的业务组件上的操作，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="1cc12-111">To complete an operation on a business component with picklist field, these tasks are:</span></span>  
  
1. <span data-ttu-id="1cc12-112">创建 BizTalk 项目并生成架构以包含选择列表字段的业务组件上执行操作。</span><span class="sxs-lookup"><span data-stu-id="1cc12-112">Create a BizTalk project and generate schema to perform an operation on a business component containing picklist fields.</span></span>  
  
2. <span data-ttu-id="1cc12-113">用于发送和接收来自 Siebel 系统的消息在 BizTalk 项目中创建消息。</span><span class="sxs-lookup"><span data-stu-id="1cc12-113">Create messages in the BizTalk project for sending and receiving messages from the Siebel system.</span></span>  
  
3. <span data-ttu-id="1cc12-114">创建用于 Siebel 系统中调用的操作的业务流程。</span><span class="sxs-lookup"><span data-stu-id="1cc12-114">Create orchestration to invoke an operation in the Siebel system.</span></span>  
  
4. <span data-ttu-id="1cc12-115">生成并部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="1cc12-115">Build and deploy the BizTalk project.</span></span>  
  
5. <span data-ttu-id="1cc12-116">配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1cc12-116">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
6. <span data-ttu-id="1cc12-117">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1cc12-117">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="1cc12-118">本主题介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="1cc12-118">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="1cc12-119">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="1cc12-119">Sample Based On This Topic</span></span>  
 <span data-ttu-id="1cc12-120">示例中，SiebelPicklist，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1cc12-120">A sample, SiebelPicklist, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="1cc12-121">有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-121">For more information, see [Samples for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="1cc12-122">生成架构</span><span class="sxs-lookup"><span data-stu-id="1cc12-122">Generating Schema</span></span>  
 <span data-ttu-id="1cc12-123">在本主题中，用于演示如何调用操作与选择列表字段的业务组件上我们将生成的架构**插入**操作**帐户**业务组件。</span><span class="sxs-lookup"><span data-stu-id="1cc12-123">In this topic, to demonstrate how to invoke operations on business components with picklist fields, we will generate schema for the **Insert** operation for the **Account** business component.</span></span> <span data-ttu-id="1cc12-124">**帐户**业务组件具有静态选择列表中，*调查类型*。</span><span class="sxs-lookup"><span data-stu-id="1cc12-124">The **Account** business component has a static picklist, *Survey Type*.</span></span>  
  
 <span data-ttu-id="1cc12-125">请参阅[检索 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1cc12-125">See [Retrieving Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md) for more information about how to generate schema.</span></span>  
  
 <span data-ttu-id="1cc12-126">生成的插入操作的元数据时**帐户**业务组件，你将获得单独的.xsd 文件包含选择列表字段和其可能的值。</span><span class="sxs-lookup"><span data-stu-id="1cc12-126">When you generate the metadata for the Insert operation for the **Account** business component, you get a separate .xsd file containing the picklist fields and their possible values.</span></span> <span data-ttu-id="1cc12-127">请注意，.xsd 仅包含值的静态选择列表，包括*调查类型*。</span><span class="sxs-lookup"><span data-stu-id="1cc12-127">Note that the .xsd contains only the values for the static picklists, including *Survey Type*.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="1cc12-128">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="1cc12-128">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="1cc12-129">先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="1cc12-129">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="1cc12-130">一条消息通常是一个变量，要为其类型定义由相应的架构。</span><span class="sxs-lookup"><span data-stu-id="1cc12-130">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="1cc12-131">必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="1cc12-131">You must link the schema you generated in the first step to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="1cc12-132">对于本主题中，您必须创建两条消息，另一个用于将请求发送到 Siebel 系统，另一个用于接收响应。</span><span class="sxs-lookup"><span data-stu-id="1cc12-132">For this topic, you must create two messages—one to send a request to the Siebel system and the other to receive a response.</span></span>  
  
 <span data-ttu-id="1cc12-133">执行以下步骤以创建消息并将其链接到该架构：</span><span class="sxs-lookup"><span data-stu-id="1cc12-133">Perform the following steps to create messages and link them to the schema:</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="1cc12-134">若要创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="1cc12-134">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="1cc12-135">打开业务流程视图 BizTalk 项目中，如果还没有打开。</span><span class="sxs-lookup"><span data-stu-id="1cc12-135">Open the orchestration view the BizTalk project, if not already open.</span></span> <span data-ttu-id="1cc12-136">单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="1cc12-136">Click **View**, point to **Other Windows**, and click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="1cc12-137">在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="1cc12-137">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="1cc12-138">右键单击新创建消息，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="1cc12-138">Right-click the newly create message and select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="1cc12-139">在中**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1cc12-139">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="1cc12-140">使用此选项</span><span class="sxs-lookup"><span data-stu-id="1cc12-140">Use this</span></span>|<span data-ttu-id="1cc12-141">执行的操作</span><span class="sxs-lookup"><span data-stu-id="1cc12-141">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1cc12-142">Identifier</span><span class="sxs-lookup"><span data-stu-id="1cc12-142">Identifier</span></span>|<span data-ttu-id="1cc12-143">类型**请求**。</span><span class="sxs-lookup"><span data-stu-id="1cc12-143">Type **Request**.</span></span>|  
    |<span data-ttu-id="1cc12-144">消息类型</span><span class="sxs-lookup"><span data-stu-id="1cc12-144">Message Type</span></span>|<span data-ttu-id="1cc12-145">从下拉列表中，展开**架构**，然后选择*SiebelPicklist.SiebelBindingSchema.Insert*，其中*SiebelPicklist*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="1cc12-145">From the drop-down list, expand **Schemas**, and select *SiebelPicklist.SiebelBindingSchema.Insert*, where *SiebelPicklist* is the name of your BizTalk project.</span></span> <span data-ttu-id="1cc12-146">*SiebelBindingSchema*是用于调用生成的架构*插入*上的操作*帐户*业务组件。</span><span class="sxs-lookup"><span data-stu-id="1cc12-146">*SiebelBindingSchema* is the schema generated for invoking the *Insert* operation on *Account* business component.</span></span>|  
  
5.  <span data-ttu-id="1cc12-147">重复上述步骤以创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="1cc12-147">Repeat the previous step to create a new message.</span></span> <span data-ttu-id="1cc12-148">在中**属性**窗格中的新消息，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1cc12-148">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="1cc12-149">使用此选项</span><span class="sxs-lookup"><span data-stu-id="1cc12-149">Use this</span></span>|<span data-ttu-id="1cc12-150">执行的操作</span><span class="sxs-lookup"><span data-stu-id="1cc12-150">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1cc12-151">Identifier</span><span class="sxs-lookup"><span data-stu-id="1cc12-151">Identifier</span></span>|<span data-ttu-id="1cc12-152">类型**响应**。</span><span class="sxs-lookup"><span data-stu-id="1cc12-152">Type **Response**.</span></span>|  
    |<span data-ttu-id="1cc12-153">消息类型</span><span class="sxs-lookup"><span data-stu-id="1cc12-153">Message Type</span></span>|<span data-ttu-id="1cc12-154">从下拉列表中，展开**架构**，然后选择*SiebelPicklist.SiebelBindingSchema.InsertResponse*。</span><span class="sxs-lookup"><span data-stu-id="1cc12-154">From the drop-down list, expand **Schemas**, and select *SiebelPicklist.SiebelBindingSchema.InsertResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="1cc12-155">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="1cc12-155">Setting up the Orchestration</span></span>  
 <span data-ttu-id="1cc12-156">必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行插入操作与选择列表字段在 Siebel 业务组件上的。</span><span class="sxs-lookup"><span data-stu-id="1cc12-156">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing an Insert operation on a Siebel business component with picklist fields.</span></span> <span data-ttu-id="1cc12-157">在将请求消息放在此业务流程，定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="1cc12-157">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="1cc12-158">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用此消息并将其传递到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="1cc12-158">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] consumes this message and passes it on to the Siebel system.</span></span> <span data-ttu-id="1cc12-159">来自 Siebel 系统的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="1cc12-159">The response from the Siebel system is saved to another location.</span></span> <span data-ttu-id="1cc12-160">将包含一个典型的业务流程在 Siebel 业务组件上执行操作：</span><span class="sxs-lookup"><span data-stu-id="1cc12-160">A typical orchestration for performing operations on Siebel business components would contain:</span></span>  
  
- <span data-ttu-id="1cc12-161">发送和接收形状来将消息发送到 Siebel 和接收响应。</span><span class="sxs-lookup"><span data-stu-id="1cc12-161">Send and receive shapes to send messages to Siebel and receive responses.</span></span>  
  
- <span data-ttu-id="1cc12-162">一个单向接收端口接收请求消息将发送到 Siebel。</span><span class="sxs-lookup"><span data-stu-id="1cc12-162">A one-way receive port to receive request messages to send to Siebel.</span></span>  
  
- <span data-ttu-id="1cc12-163">一个双向发送端口以将请求消息发送到 Siebel 和接收响应。</span><span class="sxs-lookup"><span data-stu-id="1cc12-163">A two-way send port to send request messages to Siebel and receive responses.</span></span>  
  
- <span data-ttu-id="1cc12-164">一个单向发送端口以从 Siebel 将响应发送到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1cc12-164">A one-way send port to send the responses from Siebel to a folder.</span></span>  
  
  <span data-ttu-id="1cc12-165">有关示例业务流程*插入*上的操作*帐户*业务组件将如下所示：</span><span class="sxs-lookup"><span data-stu-id="1cc12-165">A sample orchestration for the *Insert* operation on an *Account* business component resembles the following:</span></span>  
  
  <span data-ttu-id="1cc12-166">![用于插入 siebel 选择列表值的业务流程](../../adapters-and-accelerators/adapter-siebel/media/c981fbf9-9a1f-40a5-9ccb-5e146589f2d3.gif "c981fbf9-9a1f-40a5-9ccb-5e146589f2d3")</span><span class="sxs-lookup"><span data-stu-id="1cc12-166">![Orchestration to insert picklist values for Siebel](../../adapters-and-accelerators/adapter-siebel/media/c981fbf9-9a1f-40a5-9ccb-5e146589f2d3.gif "c981fbf9-9a1f-40a5-9ccb-5e146589f2d3")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="1cc12-167">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="1cc12-167">Adding Message Shapes</span></span>  
 <span data-ttu-id="1cc12-168">请确保为每个消息形状中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="1cc12-168">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="1cc12-169">中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="1cc12-169">The names listed in the *Shape* column are the names of the message shapes as displayed in the orchestration above.</span></span>  
  
|<span data-ttu-id="1cc12-170">形状</span><span class="sxs-lookup"><span data-stu-id="1cc12-170">Shape</span></span>|<span data-ttu-id="1cc12-171">形状类型</span><span class="sxs-lookup"><span data-stu-id="1cc12-171">Shape Type</span></span>|<span data-ttu-id="1cc12-172">属性</span><span class="sxs-lookup"><span data-stu-id="1cc12-172">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="1cc12-173">ReceiveXML</span><span class="sxs-lookup"><span data-stu-id="1cc12-173">ReceiveXML</span></span>|<span data-ttu-id="1cc12-174">Receive</span><span class="sxs-lookup"><span data-stu-id="1cc12-174">Receive</span></span>|<span data-ttu-id="1cc12-175">-设置**名称**到*ReceiveXML*</span><span class="sxs-lookup"><span data-stu-id="1cc12-175">-   Set **Name** to *ReceiveXML*</span></span><br /><span data-ttu-id="1cc12-176">-设置**激活**到 *，则返回 True*</span><span class="sxs-lookup"><span data-stu-id="1cc12-176">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="1cc12-177">SendToLOB</span><span class="sxs-lookup"><span data-stu-id="1cc12-177">SendToLOB</span></span>|<span data-ttu-id="1cc12-178">Send</span><span class="sxs-lookup"><span data-stu-id="1cc12-178">Send</span></span>|<span data-ttu-id="1cc12-179">-设置**名称**到*SendToLOB*</span><span class="sxs-lookup"><span data-stu-id="1cc12-179">-   Set **Name** to *SendToLOB*</span></span>|  
|<span data-ttu-id="1cc12-180">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="1cc12-180">ReceiveResponse</span></span>|<span data-ttu-id="1cc12-181">Receive</span><span class="sxs-lookup"><span data-stu-id="1cc12-181">Receive</span></span>|<span data-ttu-id="1cc12-182">-设置**名称**到*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="1cc12-182">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="1cc12-183">-设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="1cc12-183">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="1cc12-184">SendResponse</span><span class="sxs-lookup"><span data-stu-id="1cc12-184">SendResponse</span></span>|<span data-ttu-id="1cc12-185">Send</span><span class="sxs-lookup"><span data-stu-id="1cc12-185">Send</span></span>|<span data-ttu-id="1cc12-186">-设置**名称**到*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="1cc12-186">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="1cc12-187">添加端口</span><span class="sxs-lookup"><span data-stu-id="1cc12-187">Adding Ports</span></span>  
 <span data-ttu-id="1cc12-188">请确保为每个逻辑端口中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="1cc12-188">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="1cc12-189">中列出的名称*端口*列是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1cc12-189">The names listed in the *Port* column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="1cc12-190">端口</span><span class="sxs-lookup"><span data-stu-id="1cc12-190">Port</span></span>|<span data-ttu-id="1cc12-191">属性</span><span class="sxs-lookup"><span data-stu-id="1cc12-191">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="1cc12-192">FileIn</span><span class="sxs-lookup"><span data-stu-id="1cc12-192">FileIn</span></span>|<span data-ttu-id="1cc12-193">-设置**标识符**到*FileIn*</span><span class="sxs-lookup"><span data-stu-id="1cc12-193">-   Set **Identifier** to *FileIn*</span></span><br /><span data-ttu-id="1cc12-194">-设置**类型**到*FileInType*</span><span class="sxs-lookup"><span data-stu-id="1cc12-194">-   Set **Type** to *FileInType*</span></span><br /><span data-ttu-id="1cc12-195">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="1cc12-195">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="1cc12-196">-设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="1cc12-196">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="1cc12-197">LOBPort</span><span class="sxs-lookup"><span data-stu-id="1cc12-197">LOBPort</span></span>|<span data-ttu-id="1cc12-198">-设置**标识符**到*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="1cc12-198">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="1cc12-199">-设置**类型**到*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="1cc12-199">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="1cc12-200">-设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="1cc12-200">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="1cc12-201">-设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="1cc12-201">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="1cc12-202">SaveResponse</span><span class="sxs-lookup"><span data-stu-id="1cc12-202">SaveResponse</span></span>|<span data-ttu-id="1cc12-203">-设置**标识符**到*SaveResponse*</span><span class="sxs-lookup"><span data-stu-id="1cc12-203">-   Set **Identifier** to *SaveResponse*</span></span><br /><span data-ttu-id="1cc12-204">-设置**类型**到*SaveResponseType*</span><span class="sxs-lookup"><span data-stu-id="1cc12-204">-   Set **Type** to *SaveResponseType*</span></span><br /><span data-ttu-id="1cc12-205">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="1cc12-205">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="1cc12-206">-设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="1cc12-206">-   Set **Communication Direction** to *Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="1cc12-207">为操作形状指定消息并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="1cc12-207">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="1cc12-208">下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。</span><span class="sxs-lookup"><span data-stu-id="1cc12-208">The following table specifies the properties and their values to be set to specify messages for action shapes and linking them to the ports.</span></span> <span data-ttu-id="1cc12-209">中列出的名称*形状*列是消息形状的名称，上述业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="1cc12-209">The names listed in the *Shape* column are the names of the message shapes as displayed in the orchestration above.</span></span>  
  
|<span data-ttu-id="1cc12-210">形状</span><span class="sxs-lookup"><span data-stu-id="1cc12-210">Shape</span></span>|<span data-ttu-id="1cc12-211">属性</span><span class="sxs-lookup"><span data-stu-id="1cc12-211">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="1cc12-212">ReceiveXml</span><span class="sxs-lookup"><span data-stu-id="1cc12-212">ReceiveXml</span></span>|<span data-ttu-id="1cc12-213">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="1cc12-213">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="1cc12-214">-设置**操作**到*FileIn.Picklist.Request*</span><span class="sxs-lookup"><span data-stu-id="1cc12-214">-   Set **Operation** to *FileIn.Picklist.Request*</span></span>|  
|<span data-ttu-id="1cc12-215">SendToLOB</span><span class="sxs-lookup"><span data-stu-id="1cc12-215">SendToLOB</span></span>|<span data-ttu-id="1cc12-216">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="1cc12-216">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="1cc12-217">-设置**操作**到*LOBPort.Picklist.Request*</span><span class="sxs-lookup"><span data-stu-id="1cc12-217">-   Set **Operation** to *LOBPort.Picklist.Request*</span></span>|  
|<span data-ttu-id="1cc12-218">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="1cc12-218">ReceiveResponse</span></span>|<span data-ttu-id="1cc12-219">-设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="1cc12-219">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="1cc12-220">-设置**操作**到*LOBPort.Picklist.Response*</span><span class="sxs-lookup"><span data-stu-id="1cc12-220">-   Set **Operation** to *LOBPort.Picklist.Response*</span></span>|  
|<span data-ttu-id="1cc12-221">SendResponse</span><span class="sxs-lookup"><span data-stu-id="1cc12-221">SendResponse</span></span>|<span data-ttu-id="1cc12-222">-设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="1cc12-222">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="1cc12-223">-设置**操作**到*SaveResponse.Picklist.Request*</span><span class="sxs-lookup"><span data-stu-id="1cc12-223">-   Set **Operation** to *SaveResponse.Picklist.Request*</span></span>|  
  
 <span data-ttu-id="1cc12-224">指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="1cc12-224">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="1cc12-225">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1cc12-225">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1cc12-226">有关详细信息，请参阅[如何生成业务流程](../../core/how-to-build-orchestrations.md)并[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-226">For more information, see [How to Build Orchestrations](../../core/how-to-build-orchestrations.md) and [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span> 
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="1cc12-227">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="1cc12-227">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="1cc12-228">部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="1cc12-228">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="1cc12-229">必须使用 BizTalk Server 管理控制台来配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="1cc12-229">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="1cc12-230">有关配置应用程序的详细信息，请参阅[如何创建应用程序](../../core/how-to-create-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-230">For more information about configuring an application, see [How to Create an Application](../../core/how-to-create-an-application.md).</span></span>  
  
 <span data-ttu-id="1cc12-231">配置应用程序包括：</span><span class="sxs-lookup"><span data-stu-id="1cc12-231">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="1cc12-232">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="1cc12-232">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="1cc12-233">映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="1cc12-233">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="1cc12-234">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="1cc12-234">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="1cc12-235">硬盘和相应 file 端口将放置请求消息的位置上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="1cc12-235">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="1cc12-236">BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="1cc12-236">The BizTalk orchestration will consume the request message and send it to the Siebel system.</span></span>  
  
  - <span data-ttu-id="1cc12-237">硬盘和相应的 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="1cc12-237">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the Siebel system.</span></span>  
  
  - <span data-ttu-id="1cc12-238">定义一个物理 WCF 自定义或 Wcf-siebel 发送端口将消息发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="1cc12-238">Define a physical WCF-Custom or WCF-Siebel send port to send messages to the Siebel system.</span></span> <span data-ttu-id="1cc12-239">您必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="1cc12-239">You must also specify the action in the send port.</span></span> <span data-ttu-id="1cc12-240">有关如何创建端口的信息，请参阅[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-240">For information about how to create ports, see [Manually configure a physical port binding to the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md).</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="1cc12-241">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="1cc12-241">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file containing information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="1cc12-242">从 BizTalk 管理控制台来创建发送端口 （对于出站调用），可以导入此绑定文件。</span><span class="sxs-lookup"><span data-stu-id="1cc12-242">You can import this binding file from the BizTalk Administration Console to create send ports (for outbound calls).</span></span> <span data-ttu-id="1cc12-243">有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件到 siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-243">For more information, see [Configure a physical port binding using a port binding file to siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span></span>
  
## <a name="starting-the-application"></a><span data-ttu-id="1cc12-244">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="1cc12-244">Starting the Application</span></span>  
 <span data-ttu-id="1cc12-245">必须启动 BizTalk 应用程序用于执行*插入*上的操作*帐户*在 Siebel 业务组件。</span><span class="sxs-lookup"><span data-stu-id="1cc12-245">You must start the BizTalk application for performing an *Insert* operation on the *Account* business component in Siebel.</span></span> <span data-ttu-id="1cc12-246">在启动 BizTalk 应用程序的说明，请参阅[启动 BizTalk 应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)或[启动业务流程](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-246">For instructions on starting a BizTalk application, see [Start a BizTalk Application](../../core/how-to-start-and-stop-a-biztalk-application.md) or [Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="1cc12-247">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="1cc12-247">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="1cc12-248">文件接收端口接收请求消息的业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="1cc12-248">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="1cc12-249">运行文件发送端口以接收来自业务流程的响应消息。</span><span class="sxs-lookup"><span data-stu-id="1cc12-249">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="1cc12-250">WCF 自定义或 Wcf-siebel 发送端口将消息发送到 Siebel 系统正在运行</span><span class="sxs-lookup"><span data-stu-id="1cc12-250">The WCF-Custom or WCF-Siebel send port to send messages to the Siebel system is running</span></span>  
  
-   <span data-ttu-id="1cc12-251">运行该操作的 BizTalk 业务流程</span><span class="sxs-lookup"><span data-stu-id="1cc12-251">The BizTalk orchestration for the operation is running</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="1cc12-252">执行该操作</span><span class="sxs-lookup"><span data-stu-id="1cc12-252">Executing the Operation</span></span>  
 <span data-ttu-id="1cc12-253">必须将请求消息放置到的文件接收位置。</span><span class="sxs-lookup"><span data-stu-id="1cc12-253">You must drop the request message to the FILE receive location.</span></span> <span data-ttu-id="1cc12-254">本主题中前面生成的架构必须符合请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="1cc12-254">The schema of the request message must conform to the schema you generated earlier in this topic.</span></span> <span data-ttu-id="1cc12-255">请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)有关请求消息的架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1cc12-255">See [Message Schemas for Business Component Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md) for more information about the schema for the request messages.</span></span>  
  
 <span data-ttu-id="1cc12-256">若要插入到选择列表字段的值，请查看生成的架构，以确定可接受值的列表的选择列表。</span><span class="sxs-lookup"><span data-stu-id="1cc12-256">To insert a value to the picklist field, look at the generated schema to determine the list of acceptable values for the picklist.</span></span> <span data-ttu-id="1cc12-257">请确保请求消息具有的元素插入到选择列表字段的值。</span><span class="sxs-lookup"><span data-stu-id="1cc12-257">Make sure the request message has an element to insert value to the picklist field.</span></span> <span data-ttu-id="1cc12-258">例如，请求消息必须包含以下元素插入到值*调查类型*选择列表。</span><span class="sxs-lookup"><span data-stu-id="1cc12-258">For example, the request message must contain the following element to insert value to the *Survey Type* picklist.</span></span>  
  
 `<Survey_x0020_Type>1</Survey_x0020_Type>`  
  
 <span data-ttu-id="1cc12-259">在这里，"1"是调查类型选取列表的可接受值。</span><span class="sxs-lookup"><span data-stu-id="1cc12-259">Here, "1" is an acceptable value for the Survey Type pick list.</span></span>  
  
 <span data-ttu-id="1cc12-260">包含选择列表参数的示例请求消息是：</span><span class="sxs-lookup"><span data-stu-id="1cc12-260">An example request message that contains a picklist parameter is:</span></span>  
  
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
      <Survey_x0020_Type>1</Survey_x0020_Type>  
    </AccountInsertRecord>  
  </ArrayOfAccountInsertRecord>  
</Insert>  
```  
  
 <span data-ttu-id="1cc12-261">业务流程将使用请求消息并将其传递到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="1cc12-261">The orchestration consumes the request message and passes it to the Siebel system.</span></span> <span data-ttu-id="1cc12-262">来自 Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置。</span><span class="sxs-lookup"><span data-stu-id="1cc12-262">The response from the Siebel system is saved at the other FILE location defined as part of the orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1cc12-263">你还可以选择列表中尝试插入值无效。</span><span class="sxs-lookup"><span data-stu-id="1cc12-263">You may also try an insert an invalid value for the picklist.</span></span> <span data-ttu-id="1cc12-264">在这种情况下，必须获取`TargetSystemException`。</span><span class="sxs-lookup"><span data-stu-id="1cc12-264">In that case, you must get a `TargetSystemException`.</span></span>  
  
## <a name="possible-exceptions"></a><span data-ttu-id="1cc12-265">可能的异常</span><span class="sxs-lookup"><span data-stu-id="1cc12-265">Possible Exceptions</span></span>  
 <span data-ttu-id="1cc12-266">使用选择列表字段使用执行业务组件上的操作时可能遇到的有关异常的信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理与 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-266">For information about the exceptions you might encounter while performing an operation on business component with picklist fields using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Exceptions and Error Handling with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="1cc12-267">最佳实践</span><span class="sxs-lookup"><span data-stu-id="1cc12-267">Best Practices</span></span>  
 <span data-ttu-id="1cc12-268">部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="1cc12-268">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the bindings file.</span></span> <span data-ttu-id="1cc12-269">一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。</span><span class="sxs-lookup"><span data-stu-id="1cc12-269">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="1cc12-270">有关绑定文件的详细信息，请参阅[重用适配器绑定在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1cc12-270">For more information about binding files, see [Reuse adapter bindings in the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1cc12-271">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cc12-271">See Also</span></span>  
[<span data-ttu-id="1cc12-272">开发 BizTalk 应用程序使用 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="1cc12-272">Develop BizTalk Applications using the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)