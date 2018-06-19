---
title: 使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作 |Microsoft 文档
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
ms.openlocfilehash: 823c2959f10bbd836bd0154b2e59f07fffcc6a96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226829"
---
# <a name="run-operations-on-business-components-with-picklist-fields-using-biztalk-server-and-the-siebel-adapter"></a><span data-ttu-id="a812d-102">使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作</span><span class="sxs-lookup"><span data-stu-id="a812d-102">Run Operations on Business Components with Picklist Fields Using BizTalk Server and the Siebel adapter</span></span>
<span data-ttu-id="a812d-103">Siebel 选择列表字段类型构成的可能的值集合从哪种客户端可以指定要传递到 Siebel 系统的某些值。</span><span class="sxs-lookup"><span data-stu-id="a812d-103">A Siebel picklist field type constitutes a collection of possible values from which client may specify a certain value to be passed onto the Siebel system.</span></span> <span data-ttu-id="a812d-104">换而言之，选择列表字段包含字段接受的值的列表。</span><span class="sxs-lookup"><span data-stu-id="a812d-104">In other words, a picklist field contains a list of accepted values for a field.</span></span> <span data-ttu-id="a812d-105">有关选择列表和它们的类型的详细信息，请参阅 Siebel 文档。</span><span class="sxs-lookup"><span data-stu-id="a812d-105">For more information about picklist and their types, refer to Siebel documentation.</span></span> <span data-ttu-id="a812d-106">有关详细信息，如何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]上与选择列表字段的业务组件支持操作请参阅[Siebel 业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-106">For more information about how the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] supports operations on business components with picklist fields, see [Operations on Business Components in Siebel](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md).</span></span>  
  
 <span data-ttu-id="a812d-107">在生成包含静态绑定的选择列表字段 （一种选择列表） 的业务组件元数据时，还作为元数据的一部分发布的选择列表可接受的值。</span><span class="sxs-lookup"><span data-stu-id="a812d-107">When you generate metadata for a business component containing a static bounded picklist field (a type of picklist), the accepted values for the picklist are also published as part of the metadata.</span></span> <span data-ttu-id="a812d-108">如果你在选择列表字段中插入一个值，你必须指定一个值，在元数据中发布。</span><span class="sxs-lookup"><span data-stu-id="a812d-108">If you are inserting a value into a picklist field, you must specify a value that is published in the metadata.</span></span>  
  
## <a name="how-to-perform-operations-on-business-components-with-picklist-fields"></a><span data-ttu-id="a812d-109">如何执行与选择列表字段的业务组件上的操作？</span><span class="sxs-lookup"><span data-stu-id="a812d-109">How to Perform Operations on Business Components with Picklist Fields?</span></span>  
 <span data-ttu-id="a812d-110">Siebel 系统使用上执行操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[使用 Siebel 适配器创建 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-110">Performing an operation on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create BizTalk applications with Siebel adapter](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md).</span></span> 
 
 <span data-ttu-id="a812d-111">若要完成选择列表字段的业务组件上的操作，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="a812d-111">To complete an operation on a business component with picklist field, these tasks are:</span></span>  
  
1.  <span data-ttu-id="a812d-112">创建 BizTalk 项目，并生成架构，以对在业务组件包含选择列表字段执行操作。</span><span class="sxs-lookup"><span data-stu-id="a812d-112">Create a BizTalk project and generate schema to perform an operation on a business component containing picklist fields.</span></span>  
  
2.  <span data-ttu-id="a812d-113">在发送和接收消息从 Siebel 系统的 BizTalk 项目中创建消息。</span><span class="sxs-lookup"><span data-stu-id="a812d-113">Create messages in the BizTalk project for sending and receiving messages from the Siebel system.</span></span>  
  
3.  <span data-ttu-id="a812d-114">创建要在 Siebel 系统调用操作的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a812d-114">Create orchestration to invoke an operation in the Siebel system.</span></span>  
  
4.  <span data-ttu-id="a812d-115">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="a812d-115">Build and deploy the BizTalk project.</span></span>  
  
5.  <span data-ttu-id="a812d-116">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="a812d-116">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
6.  <span data-ttu-id="a812d-117">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a812d-117">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="a812d-118">本主题提供执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="a812d-118">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="a812d-119">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="a812d-119">Sample Based On This Topic</span></span>  
 <span data-ttu-id="a812d-120">示例中，SiebelPicklist，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a812d-120">A sample, SiebelPicklist, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="a812d-121">有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-121">For more information, see [Samples for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="a812d-122">生成架构</span><span class="sxs-lookup"><span data-stu-id="a812d-122">Generating Schema</span></span>  
 <span data-ttu-id="a812d-123">在本主题中，来演示如何调用操作与选择列表字段的业务组件我们将生成架构**插入**操作**帐户**在业务组件。</span><span class="sxs-lookup"><span data-stu-id="a812d-123">In this topic, to demonstrate how to invoke operations on business components with picklist fields, we will generate schema for the **Insert** operation for the **Account** business component.</span></span> <span data-ttu-id="a812d-124">**帐户**在业务组件具有静态选择列表中，*调查类型*。</span><span class="sxs-lookup"><span data-stu-id="a812d-124">The **Account** business component has a static picklist, *Survey Type*.</span></span>  
  
 <span data-ttu-id="a812d-125">请参阅[检索用于 Siebel 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a812d-125">See [Retrieving Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md) for more information about how to generate schema.</span></span>  
  
 <span data-ttu-id="a812d-126">生成的 Insert 操作的元数据时**帐户**在业务组件，你将获取包含选择列表字段和其可能的值的单独.xsd 文件。</span><span class="sxs-lookup"><span data-stu-id="a812d-126">When you generate the metadata for the Insert operation for the **Account** business component, you get a separate .xsd file containing the picklist fields and their possible values.</span></span> <span data-ttu-id="a812d-127">请注意，.xsd 仅包含值的静态选择列表，包括*调查类型*。</span><span class="sxs-lookup"><span data-stu-id="a812d-127">Note that the .xsd contains only the values for the static picklists, including *Survey Type*.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="a812d-128">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="a812d-128">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="a812d-129">你先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="a812d-129">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="a812d-130">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="a812d-130">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="a812d-131">你必须链接您从生成的架构中的第一步的邮件 BizTalk 项目的业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="a812d-131">You must link the schema you generated in the first step to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="a812d-132">对于本主题中，你必须创建两条消息，另一个用于将请求发送到 Siebel 系统，另一个用于接收响应。</span><span class="sxs-lookup"><span data-stu-id="a812d-132">For this topic, you must create two messages—one to send a request to the Siebel system and the other to receive a response.</span></span>  
  
 <span data-ttu-id="a812d-133">执行以下步骤以创建消息并将它们链接到该架构：</span><span class="sxs-lookup"><span data-stu-id="a812d-133">Perform the following steps to create messages and link them to the schema:</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="a812d-134">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="a812d-134">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="a812d-135">打开业务流程视图 BizTalk 项目中，如果不是已打开。</span><span class="sxs-lookup"><span data-stu-id="a812d-135">Open the orchestration view the BizTalk project, if not already open.</span></span> <span data-ttu-id="a812d-136">单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="a812d-136">Click **View**, point to **Other Windows**, and click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="a812d-137">在**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="a812d-137">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="a812d-138">右键单击新创建消息，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="a812d-138">Right-click the newly create message and select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="a812d-139">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a812d-139">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="a812d-140">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a812d-140">Use this</span></span>|<span data-ttu-id="a812d-141">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a812d-141">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a812d-142">Identifier</span><span class="sxs-lookup"><span data-stu-id="a812d-142">Identifier</span></span>|<span data-ttu-id="a812d-143">类型**请求**。</span><span class="sxs-lookup"><span data-stu-id="a812d-143">Type **Request**.</span></span>|  
    |<span data-ttu-id="a812d-144">消息类型</span><span class="sxs-lookup"><span data-stu-id="a812d-144">Message Type</span></span>|<span data-ttu-id="a812d-145">从下拉列表中，展开**架构**，然后选择*SiebelPicklist.SiebelBindingSchema.Insert*，其中*SiebelPicklist*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="a812d-145">From the drop-down list, expand **Schemas**, and select *SiebelPicklist.SiebelBindingSchema.Insert*, where *SiebelPicklist* is the name of your BizTalk project.</span></span> <span data-ttu-id="a812d-146">*SiebelBindingSchema*是为调用生成的架构*插入*操作*帐户*在业务组件。</span><span class="sxs-lookup"><span data-stu-id="a812d-146">*SiebelBindingSchema* is the schema generated for invoking the *Insert* operation on *Account* business component.</span></span>|  
  
5.  <span data-ttu-id="a812d-147">重复上述步骤以创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="a812d-147">Repeat the previous step to create a new message.</span></span> <span data-ttu-id="a812d-148">在**属性**窗格中，为新的消息中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a812d-148">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="a812d-149">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a812d-149">Use this</span></span>|<span data-ttu-id="a812d-150">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a812d-150">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a812d-151">Identifier</span><span class="sxs-lookup"><span data-stu-id="a812d-151">Identifier</span></span>|<span data-ttu-id="a812d-152">类型**响应**。</span><span class="sxs-lookup"><span data-stu-id="a812d-152">Type **Response**.</span></span>|  
    |<span data-ttu-id="a812d-153">消息类型</span><span class="sxs-lookup"><span data-stu-id="a812d-153">Message Type</span></span>|<span data-ttu-id="a812d-154">从下拉列表中，展开**架构**，然后选择*SiebelPicklist.SiebelBindingSchema.InsertResponse*。</span><span class="sxs-lookup"><span data-stu-id="a812d-154">From the drop-down list, expand **Schemas**, and select *SiebelPicklist.SiebelBindingSchema.InsertResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="a812d-155">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="a812d-155">Setting up the Orchestration</span></span>  
 <span data-ttu-id="a812d-156">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行插入操作在选择列表字段具有 Siebel 业务组件上的。</span><span class="sxs-lookup"><span data-stu-id="a812d-156">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing an Insert operation on a Siebel business component with picklist fields.</span></span> <span data-ttu-id="a812d-157">此业务流程，在你删除时的请求消息的定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="a812d-157">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="a812d-158">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用此消息并将其传递到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a812d-158">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] consumes this message and passes it on to the Siebel system.</span></span> <span data-ttu-id="a812d-159">Siebel 系统的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="a812d-159">The response from the Siebel system is saved to another location.</span></span> <span data-ttu-id="a812d-160">将包含在 Siebel 业务组件上执行操作的典型业务流程：</span><span class="sxs-lookup"><span data-stu-id="a812d-160">A typical orchestration for performing operations on Siebel business components would contain:</span></span>  
  
-   <span data-ttu-id="a812d-161">发送和接收形状来将消息发送到 Siebel 和接收响应。</span><span class="sxs-lookup"><span data-stu-id="a812d-161">Send and receive shapes to send messages to Siebel and receive responses.</span></span>  
  
-   <span data-ttu-id="a812d-162">单向接收端口接收请求消息将发送到 Siebel。</span><span class="sxs-lookup"><span data-stu-id="a812d-162">A one-way receive port to receive request messages to send to Siebel.</span></span>  
  
-   <span data-ttu-id="a812d-163">双向发送端口将请求消息发送到 Siebel 和接收响应。</span><span class="sxs-lookup"><span data-stu-id="a812d-163">A two-way send port to send request messages to Siebel and receive responses.</span></span>  
  
-   <span data-ttu-id="a812d-164">单向发送端口将响应从 Siebel 发送到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a812d-164">A one-way send port to send the responses from Siebel to a folder.</span></span>  
  
 <span data-ttu-id="a812d-165">示例业务流程*插入*操作*帐户*在业务组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="a812d-165">A sample orchestration for the *Insert* operation on an *Account* business component resembles the following:</span></span>  
  
 <span data-ttu-id="a812d-166">![业务流程用于 Siebel 插入选择列表值](../../adapters-and-accelerators/adapter-siebel/media/c981fbf9-9a1f-40a5-9ccb-5e146589f2d3.gif "c981fbf9-9a1f-40a5-9ccb-5e146589f2d3")</span><span class="sxs-lookup"><span data-stu-id="a812d-166">![Orchestration to insert picklist values for Siebel](../../adapters-and-accelerators/adapter-siebel/media/c981fbf9-9a1f-40a5-9ccb-5e146589f2d3.gif "c981fbf9-9a1f-40a5-9ccb-5e146589f2d3")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="a812d-167">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="a812d-167">Adding Message Shapes</span></span>  
 <span data-ttu-id="a812d-168">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="a812d-168">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="a812d-169">中列出的名称*形状*列是上述业务流程中显示的消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="a812d-169">The names listed in the *Shape* column are the names of the message shapes as displayed in the orchestration above.</span></span>  
  
|<span data-ttu-id="a812d-170">形状</span><span class="sxs-lookup"><span data-stu-id="a812d-170">Shape</span></span>|<span data-ttu-id="a812d-171">形状类型</span><span class="sxs-lookup"><span data-stu-id="a812d-171">Shape Type</span></span>|<span data-ttu-id="a812d-172">属性</span><span class="sxs-lookup"><span data-stu-id="a812d-172">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="a812d-173">ReceiveXML</span><span class="sxs-lookup"><span data-stu-id="a812d-173">ReceiveXML</span></span>|<span data-ttu-id="a812d-174">Receive</span><span class="sxs-lookup"><span data-stu-id="a812d-174">Receive</span></span>|<span data-ttu-id="a812d-175">-将设置**名称**到*ReceiveXML*</span><span class="sxs-lookup"><span data-stu-id="a812d-175">-   Set **Name** to *ReceiveXML*</span></span><br /><span data-ttu-id="a812d-176">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="a812d-176">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="a812d-177">SendToLOB</span><span class="sxs-lookup"><span data-stu-id="a812d-177">SendToLOB</span></span>|<span data-ttu-id="a812d-178">Send</span><span class="sxs-lookup"><span data-stu-id="a812d-178">Send</span></span>|<span data-ttu-id="a812d-179">-将设置**名称**到*SendToLOB*</span><span class="sxs-lookup"><span data-stu-id="a812d-179">-   Set **Name** to *SendToLOB*</span></span>|  
|<span data-ttu-id="a812d-180">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="a812d-180">ReceiveResponse</span></span>|<span data-ttu-id="a812d-181">Receive</span><span class="sxs-lookup"><span data-stu-id="a812d-181">Receive</span></span>|<span data-ttu-id="a812d-182">-将设置**名称**到*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="a812d-182">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="a812d-183">-将设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="a812d-183">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="a812d-184">SendResponse</span><span class="sxs-lookup"><span data-stu-id="a812d-184">SendResponse</span></span>|<span data-ttu-id="a812d-185">Send</span><span class="sxs-lookup"><span data-stu-id="a812d-185">Send</span></span>|<span data-ttu-id="a812d-186">-将设置**名称**到*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="a812d-186">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="a812d-187">添加端口</span><span class="sxs-lookup"><span data-stu-id="a812d-187">Adding Ports</span></span>  
 <span data-ttu-id="a812d-188">请确保为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="a812d-188">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="a812d-189">中列出的名称*端口*列是业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="a812d-189">The names listed in the *Port* column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="a812d-190">端口</span><span class="sxs-lookup"><span data-stu-id="a812d-190">Port</span></span>|<span data-ttu-id="a812d-191">属性</span><span class="sxs-lookup"><span data-stu-id="a812d-191">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="a812d-192">文件</span><span class="sxs-lookup"><span data-stu-id="a812d-192">FileIn</span></span>|<span data-ttu-id="a812d-193">-将设置**标识符**到*文件*</span><span class="sxs-lookup"><span data-stu-id="a812d-193">-   Set **Identifier** to *FileIn*</span></span><br /><span data-ttu-id="a812d-194">-将设置**类型**到*FileInType*</span><span class="sxs-lookup"><span data-stu-id="a812d-194">-   Set **Type** to *FileInType*</span></span><br /><span data-ttu-id="a812d-195">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="a812d-195">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="a812d-196">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="a812d-196">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="a812d-197">LOBPort</span><span class="sxs-lookup"><span data-stu-id="a812d-197">LOBPort</span></span>|<span data-ttu-id="a812d-198">-将设置**标识符**到*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="a812d-198">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="a812d-199">-将设置**类型**到*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="a812d-199">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="a812d-200">-将设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="a812d-200">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="a812d-201">-将设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="a812d-201">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="a812d-202">SaveResponse</span><span class="sxs-lookup"><span data-stu-id="a812d-202">SaveResponse</span></span>|<span data-ttu-id="a812d-203">-将设置**标识符**到*SaveResponse*</span><span class="sxs-lookup"><span data-stu-id="a812d-203">-   Set **Identifier** to *SaveResponse*</span></span><br /><span data-ttu-id="a812d-204">-将设置**类型**到*SaveResponseType*</span><span class="sxs-lookup"><span data-stu-id="a812d-204">-   Set **Type** to *SaveResponseType*</span></span><br /><span data-ttu-id="a812d-205">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="a812d-205">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="a812d-206">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="a812d-206">-   Set **Communication Direction** to *Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="a812d-207">指定消息的操作形状并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="a812d-207">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="a812d-208">下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。</span><span class="sxs-lookup"><span data-stu-id="a812d-208">The following table specifies the properties and their values to be set to specify messages for action shapes and linking them to the ports.</span></span> <span data-ttu-id="a812d-209">中列出的名称*形状*列是上述业务流程中显示的消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="a812d-209">The names listed in the *Shape* column are the names of the message shapes as displayed in the orchestration above.</span></span>  
  
|<span data-ttu-id="a812d-210">形状</span><span class="sxs-lookup"><span data-stu-id="a812d-210">Shape</span></span>|<span data-ttu-id="a812d-211">属性</span><span class="sxs-lookup"><span data-stu-id="a812d-211">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="a812d-212">ReceiveXml</span><span class="sxs-lookup"><span data-stu-id="a812d-212">ReceiveXml</span></span>|<span data-ttu-id="a812d-213">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="a812d-213">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="a812d-214">-将设置**操作**到*FileIn.Picklist.Request*</span><span class="sxs-lookup"><span data-stu-id="a812d-214">-   Set **Operation** to *FileIn.Picklist.Request*</span></span>|  
|<span data-ttu-id="a812d-215">SendToLOB</span><span class="sxs-lookup"><span data-stu-id="a812d-215">SendToLOB</span></span>|<span data-ttu-id="a812d-216">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="a812d-216">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="a812d-217">-将设置**操作**到*LOBPort.Picklist.Request*</span><span class="sxs-lookup"><span data-stu-id="a812d-217">-   Set **Operation** to *LOBPort.Picklist.Request*</span></span>|  
|<span data-ttu-id="a812d-218">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="a812d-218">ReceiveResponse</span></span>|<span data-ttu-id="a812d-219">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="a812d-219">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="a812d-220">-将设置**操作**到*LOBPort.Picklist.Response*</span><span class="sxs-lookup"><span data-stu-id="a812d-220">-   Set **Operation** to *LOBPort.Picklist.Response*</span></span>|  
|<span data-ttu-id="a812d-221">SendResponse</span><span class="sxs-lookup"><span data-stu-id="a812d-221">SendResponse</span></span>|<span data-ttu-id="a812d-222">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="a812d-222">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="a812d-223">-将设置**操作**到*SaveResponse.Picklist.Request*</span><span class="sxs-lookup"><span data-stu-id="a812d-223">-   Set **Operation** to *SaveResponse.Picklist.Request*</span></span>|  
  
 <span data-ttu-id="a812d-224">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="a812d-224">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="a812d-225">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a812d-225">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a812d-226">有关详细信息，请参阅[如何构建业务流程](../../core/how-to-build-orchestrations.md)和[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-226">For more information, see [How to Build Orchestrations](../../core/how-to-build-orchestrations.md) and [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span> 
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="a812d-227">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="a812d-227">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="a812d-228">部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="a812d-228">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="a812d-229">必须使用 BizTalk Server 管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a812d-229">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="a812d-230">有关配置应用程序的详细信息，请参阅[如何创建应用程序](../../core/how-to-create-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-230">For more information about configuring an application, see [How to Create an Application](../../core/how-to-create-an-application.md).</span></span>  
  
 <span data-ttu-id="a812d-231">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="a812d-231">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="a812d-232">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="a812d-232">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="a812d-233">映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="a812d-233">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="a812d-234">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="a812d-234">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="a812d-235">硬盘和放置请求消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="a812d-235">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="a812d-236">BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a812d-236">The BizTalk orchestration will consume the request message and send it to the Siebel system.</span></span>  
  
    -   <span data-ttu-id="a812d-237">硬盘和 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="a812d-237">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the Siebel system.</span></span>  
  
    -   <span data-ttu-id="a812d-238">定义物理 WCF 自定义或 WCF Siebel 发送端口将消息发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a812d-238">Define a physical WCF-Custom or WCF-Siebel send port to send messages to the Siebel system.</span></span> <span data-ttu-id="a812d-239">你必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="a812d-239">You must also specify the action in the send port.</span></span> <span data-ttu-id="a812d-240">有关如何创建端口的信息，请参阅[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-240">For information about how to create ports, see [Manually configure a physical port binding to the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md).</span></span>
  
        > [!NOTE]
        >  <span data-ttu-id="a812d-241">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="a812d-241">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file containing information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="a812d-242">从 BizTalk 管理控制台来创建发送端口 （对于出站调用），可以导入此绑定文件。</span><span class="sxs-lookup"><span data-stu-id="a812d-242">You can import this binding file from the BizTalk Administration Console to create send ports (for outbound calls).</span></span> <span data-ttu-id="a812d-243">有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-243">For more information, see [Configure a physical port binding using a port binding file to siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span></span>
  
## <a name="starting-the-application"></a><span data-ttu-id="a812d-244">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="a812d-244">Starting the Application</span></span>  
 <span data-ttu-id="a812d-245">你必须启动 BizTalk 应用程序用于执行*插入*操作*帐户*Siebel 中的业务组件。</span><span class="sxs-lookup"><span data-stu-id="a812d-245">You must start the BizTalk application for performing an *Insert* operation on the *Account* business component in Siebel.</span></span> <span data-ttu-id="a812d-246">有关启动 BizTalk 应用程序的说明，请参阅[启动 BizTalk 应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)或[启动业务流程](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-246">For instructions on starting a BizTalk application, see [Start a BizTalk Application](../../core/how-to-start-and-stop-a-biztalk-application.md) or [Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="a812d-247">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="a812d-247">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="a812d-248">FILE 接收端口，以便运行业务流程的是接收请求消息。</span><span class="sxs-lookup"><span data-stu-id="a812d-248">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="a812d-249">要从业务流程接收响应消息的文件发送端口正在运行。</span><span class="sxs-lookup"><span data-stu-id="a812d-249">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="a812d-250">WCF 自定义或 WCF Siebel 发送端口将消息发送到 Siebel 系统正在运行</span><span class="sxs-lookup"><span data-stu-id="a812d-250">The WCF-Custom or WCF-Siebel send port to send messages to the Siebel system is running</span></span>  
  
-   <span data-ttu-id="a812d-251">运行该操作 BizTalk 业务流程</span><span class="sxs-lookup"><span data-stu-id="a812d-251">The BizTalk orchestration for the operation is running</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="a812d-252">执行该操作</span><span class="sxs-lookup"><span data-stu-id="a812d-252">Executing the Operation</span></span>  
 <span data-ttu-id="a812d-253">你必须放到该文件的请求消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="a812d-253">You must drop the request message to the FILE receive location.</span></span> <span data-ttu-id="a812d-254">本主题前面的生成的架构必须符合的请求消息架构。</span><span class="sxs-lookup"><span data-stu-id="a812d-254">The schema of the request message must conform to the schema you generated earlier in this topic.</span></span> <span data-ttu-id="a812d-255">请参阅[业务组件操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md)有关的请求消息架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a812d-255">See [Message Schemas for Business Component Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md) for more information about the schema for the request messages.</span></span>  
  
 <span data-ttu-id="a812d-256">若要插入到选择列表字段的值，请查看生成的架构，以确定可接受值的列表选择列表。</span><span class="sxs-lookup"><span data-stu-id="a812d-256">To insert a value to the picklist field, look at the generated schema to determine the list of acceptable values for the picklist.</span></span> <span data-ttu-id="a812d-257">请确保请求消息具有要插入到选择列表字段的值的元素。</span><span class="sxs-lookup"><span data-stu-id="a812d-257">Make sure the request message has an element to insert value to the picklist field.</span></span> <span data-ttu-id="a812d-258">例如，请求消息必须包含以下元素插入到值*调查类型*选择列表。</span><span class="sxs-lookup"><span data-stu-id="a812d-258">For example, the request message must contain the following element to insert value to the *Survey Type* picklist.</span></span>  
  
 `<Survey_x0020_Type>1</Survey_x0020_Type>`  
  
 <span data-ttu-id="a812d-259">在这里，"1"是调查类型选取列表的可接受值。</span><span class="sxs-lookup"><span data-stu-id="a812d-259">Here, "1" is an acceptable value for the Survey Type pick list.</span></span>  
  
 <span data-ttu-id="a812d-260">包含的选择列表参数示例请求消息，则：</span><span class="sxs-lookup"><span data-stu-id="a812d-260">An example request message that contains a picklist parameter is:</span></span>  
  
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
  
 <span data-ttu-id="a812d-261">业务流程使用请求消息，并将其传递到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a812d-261">The orchestration consumes the request message and passes it to the Siebel system.</span></span> <span data-ttu-id="a812d-262">Siebel 系统的响应保存在定义为业务流程的一部分的其他文件位置中。</span><span class="sxs-lookup"><span data-stu-id="a812d-262">The response from the Siebel system is saved at the other FILE location defined as part of the orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a812d-263">你还可以选择列表中尝试插入一个无效值。</span><span class="sxs-lookup"><span data-stu-id="a812d-263">You may also try an insert an invalid value for the picklist.</span></span> <span data-ttu-id="a812d-264">在这种情况下，你必须获取`TargetSystemException`。</span><span class="sxs-lookup"><span data-stu-id="a812d-264">In that case, you must get a `TargetSystemException`.</span></span>  
  
## <a name="possible-exceptions"></a><span data-ttu-id="a812d-265">可能的异常</span><span class="sxs-lookup"><span data-stu-id="a812d-265">Possible Exceptions</span></span>  
 <span data-ttu-id="a812d-266">有关异常的信息可能会遇到与使用的选择列表字段执行在业务组件上的操作时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理，并在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-266">For information about the exceptions you might encounter while performing an operation on business component with picklist fields using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Exceptions and Error Handling with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="a812d-267">最佳实践</span><span class="sxs-lookup"><span data-stu-id="a812d-267">Best Practices</span></span>  
 <span data-ttu-id="a812d-268">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="a812d-268">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the bindings file.</span></span> <span data-ttu-id="a812d-269">一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a812d-269">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="a812d-270">有关绑定文件的详细信息，请参阅[重用适配器绑定在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a812d-270">For more information about binding files, see [Reuse adapter bindings in the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a812d-271">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a812d-271">See Also</span></span>  
[<span data-ttu-id="a812d-272">开发使用 Siebel 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="a812d-272">Develop BizTalk Applications using the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)