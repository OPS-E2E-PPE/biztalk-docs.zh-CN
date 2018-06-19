---
title: 使用 BizTalk Server 的 Oracle 数据库中运行 SQLEXECUTE 操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLEXECUTE operation, performing by using BizTalk Server
- SQLEXECUTE operation
ms.assetid: 7fdd1ead-0bf0-46cf-86fc-db513f76f6b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02a5da0a5c6ff3560d265759d3c5320e55d7d621
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962259"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-biztalk-server"></a><span data-ttu-id="5edd9-102">使用 BizTalk Server 的 Oracle 数据库中运行 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="5edd9-102">Run SQLEXECUTE operation in Oracle Database using BizTalk Server</span></span>
<span data-ttu-id="5edd9-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使客户端能够在 Oracle 数据库上运行参数化的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="5edd9-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables clients to run parameterized SQL statement on an Oracle database.</span></span> <span data-ttu-id="5edd9-104">若要支持此类操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现 SQLEXECUTE 操作。</span><span class="sxs-lookup"><span data-stu-id="5edd9-104">To support such operations, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces a SQLEXECUTE operation.</span></span> <span data-ttu-id="5edd9-105">SQLEXECUTE 操作支持组成使你可以执行一次为每个集的相同 SQL 语句的参数集的输入的参数块。</span><span class="sxs-lookup"><span data-stu-id="5edd9-105">SQLEXECUTE operation supports an input parameter block comprised of parameter sets that enable you to execute the same SQL statement once for each set.</span></span> <span data-ttu-id="5edd9-106">SQLEXECUTE 操作返回泛型记录集内的 SQL 语句的结果。</span><span class="sxs-lookup"><span data-stu-id="5edd9-106">The SQLEXECUTE operation returns the results of the SQL statement in a generic record set.</span></span> <span data-ttu-id="5edd9-107">有关操作的详细信息，请参阅[Oracle 数据库中的 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-107">For more information about the operation, see [SQLEXECUTE Operation in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md).</span></span> <span data-ttu-id="5edd9-108">有关 SQLEXECUTE 操作的 SOAP 消息结构的信息，请参阅[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-108">For information about the structure of the SOAP message for SQLEXECUTE operation, see [Message Schemas for the SQLEXECUTE Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).</span></span>  
  
## <a name="how-to-perform-a-sqlexecute-operation-on-an-oracle-database"></a><span data-ttu-id="5edd9-109">如何执行对 Oracle 数据库的 SQLEXECUTE 操作？</span><span class="sxs-lookup"><span data-stu-id="5edd9-109">How to Perform a SQLEXECUTE operation on an Oracle Database?</span></span>  
 <span data-ttu-id="5edd9-110">使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-110">Performing an operation on an Oracle database using [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md).</span></span> <span data-ttu-id="5edd9-111">若要执行 SQLEXECUTE 操作，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="5edd9-111">To perform a SQLEXECUTE operation, these tasks are:</span></span>  
  
1.  <span data-ttu-id="5edd9-112">创建 BizTalk 项目和 SQLEXECUTE 操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="5edd9-112">Create a BizTalk project and generate schema for the SQLEXECUTE operation.</span></span> <span data-ttu-id="5edd9-113">在根节点 （/） 下显示 SQLEXECUTE 操作**选择类别**窗格中的[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5edd9-113">The SQLEXECUTE operation is surfaced under the root node (/) in the **Select a category** pane in the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
2.  <span data-ttu-id="5edd9-114">在发送和接收消息从 Oracle 数据库的 BizTalk 项目中创建消息。</span><span class="sxs-lookup"><span data-stu-id="5edd9-114">Create messages in the BizTalk project for sending and receiving messages from the Oracle database.</span></span>  
  
3.  <span data-ttu-id="5edd9-115">创建业务流程以调用在 Oracle 数据库表或视图上的操作。</span><span class="sxs-lookup"><span data-stu-id="5edd9-115">Create an orchestration to invoke the operation on the Oracle database table or view.</span></span>  
  
4.  <span data-ttu-id="5edd9-116">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="5edd9-116">Build and deploy the BizTalk project.</span></span>  
  
5.  <span data-ttu-id="5edd9-117">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="5edd9-117">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
6.  <span data-ttu-id="5edd9-118">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5edd9-118">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="5edd9-119">本主题提供执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="5edd9-119">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="5edd9-120">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="5edd9-120">Sample Based On This Topic</span></span>  
 <span data-ttu-id="5edd9-121">示例中，SqlExec，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5edd9-121">A sample, SqlExec, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="5edd9-122">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-122">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="5edd9-123">生成架构</span><span class="sxs-lookup"><span data-stu-id="5edd9-123">Generating Schema</span></span>  
 <span data-ttu-id="5edd9-124">在本主题中，来演示如何运行参数化的 SQL 查询中，我们将生成 SQLEXECUTE 操作可在根节点 （/） 中的架构**选择类别**窗格中的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5edd9-124">In this topic, to demonstrate how to run a parameterized SQL query, we will generate schema for SQLEXECUTE operation available at the root node (/) in the **Select a category** pane in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="5edd9-125">请参阅[检索元数据的 Visual Studio 中的 Oracle 数据库操作](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5edd9-125">See [Retrieve metadata for Oracle Database operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) for more information about how to generate schema.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="5edd9-126">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="5edd9-126">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="5edd9-127">你先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="5edd9-127">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="5edd9-128">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="5edd9-128">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="5edd9-129">你必须链接您生成第一步中的邮件从 BizTalk 项目的业务流程视图窗口的架构。</span><span class="sxs-lookup"><span data-stu-id="5edd9-129">You must link the schema you generated in the first step to the messages from the Orchestration View window of the BizTalk project.</span></span>  
  
 <span data-ttu-id="5edd9-130">对于本主题中，你必须创建两条消息，另一个用于将请求发送到 Oracle 数据库，另一个用于接收响应。</span><span class="sxs-lookup"><span data-stu-id="5edd9-130">For this topic, you must create two messages—one to send a request to the Oracle database and the other to receive a response.</span></span>  
  
 <span data-ttu-id="5edd9-131">执行以下步骤以创建消息并将它们链接到该架构。</span><span class="sxs-lookup"><span data-stu-id="5edd9-131">Perform the following steps to create messages and link them to the schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="5edd9-132">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="5edd9-132">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="5edd9-133">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="5edd9-133">Open the Orchestration View window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="5edd9-134">若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="5edd9-134">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="5edd9-135">在业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="5edd9-135">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="5edd9-136">右键单击新创建的消息，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="5edd9-136">Right-click the newly created message and then select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="5edd9-137">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5edd9-137">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="5edd9-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5edd9-138">Use this</span></span>|<span data-ttu-id="5edd9-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5edd9-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5edd9-140">Identifier</span><span class="sxs-lookup"><span data-stu-id="5edd9-140">Identifier</span></span>|<span data-ttu-id="5edd9-141">类型**请求**。</span><span class="sxs-lookup"><span data-stu-id="5edd9-141">Type **Request**.</span></span>|  
    |<span data-ttu-id="5edd9-142">消息类型</span><span class="sxs-lookup"><span data-stu-id="5edd9-142">Message Type</span></span>|<span data-ttu-id="5edd9-143">从下拉列表中，展开**架构**，然后选择*SqlExec.OracleDBBindingSchema.SQLEXECUTE*，其中*SqlExec*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="5edd9-143">From the drop-down list, expand **Schemas**, and then select *SqlExec.OracleDBBindingSchema.SQLEXECUTE*, where *SqlExec* is the name of your BizTalk project.</span></span> <span data-ttu-id="5edd9-144">*OracleDBBindingSchema*是为 SQLEXECUTE 操作生成的架构。</span><span class="sxs-lookup"><span data-stu-id="5edd9-144">*OracleDBBindingSchema* is the schema generated for the SQLEXECUTE operation.</span></span>|  
  
5.  <span data-ttu-id="5edd9-145">重复步骤 2 创建一条新消息。</span><span class="sxs-lookup"><span data-stu-id="5edd9-145">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="5edd9-146">在**属性**窗格中，为新的消息中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5edd9-146">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="5edd9-147">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5edd9-147">Use this</span></span>|<span data-ttu-id="5edd9-148">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5edd9-148">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5edd9-149">Identifier</span><span class="sxs-lookup"><span data-stu-id="5edd9-149">Identifier</span></span>|<span data-ttu-id="5edd9-150">类型**响应**。</span><span class="sxs-lookup"><span data-stu-id="5edd9-150">Type **Response**.</span></span>|  
    |<span data-ttu-id="5edd9-151">消息类型</span><span class="sxs-lookup"><span data-stu-id="5edd9-151">Message Type</span></span>|<span data-ttu-id="5edd9-152">从下拉列表中，展开**架构**，然后选择*SqlExec.OracleDBBindingSchema.SQLEXECUTEResponse*。</span><span class="sxs-lookup"><span data-stu-id="5edd9-152">From the drop-down list, expand **Schemas**, and then select *SqlExec.OracleDBBindingSchema.SQLEXECUTEResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="5edd9-153">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="5edd9-153">Setting up the Orchestration</span></span>  
 <span data-ttu-id="5edd9-154">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于运行参数化的 SQL 查询使用 SQLEXECUTE 操作。</span><span class="sxs-lookup"><span data-stu-id="5edd9-154">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for running a parameterized SQL query using the SQLEXECUTE operation.</span></span> <span data-ttu-id="5edd9-155">此业务流程，在你删除时的请求消息的定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="5edd9-155">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="5edd9-156">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此消息，并通过 ODP 将其传递到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="5edd9-156">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumes this message and passes it on to the Oracle database via ODP.</span></span> <span data-ttu-id="5edd9-157">从 Oracle 数据库的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="5edd9-157">The response from the Oracle database is saved to another location.</span></span> <span data-ttu-id="5edd9-158">将包含 SQLEXECUTE 上执行操作 Oracle 数据库典型业务流程：</span><span class="sxs-lookup"><span data-stu-id="5edd9-158">A typical orchestration for performing SQLEXECUTE operation on Oracle database would contain:</span></span>  
  
-   <span data-ttu-id="5edd9-159">发送和接收形状来将消息发送到 Oracle 数据库和接收响应。</span><span class="sxs-lookup"><span data-stu-id="5edd9-159">Send and Receive shapes to send messages to Oracle database and receive responses.</span></span>  
  
-   <span data-ttu-id="5edd9-160">单向接收端口接收请求消息发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="5edd9-160">A one-way receive port to receive request messages to send to the Oracle database.</span></span>  
  
-   <span data-ttu-id="5edd9-161">双向发送端口发送请求消息到 Oracle 数据库和接收响应。</span><span class="sxs-lookup"><span data-stu-id="5edd9-161">A two-way send port to send request messages to Oracle database and receive responses.</span></span>  
  
-   <span data-ttu-id="5edd9-162">单向发送端口将响应从 Oracle 数据库发送到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="5edd9-162">A one-way send port to send the responses from Oracle database to a folder.</span></span>  
  
 <span data-ttu-id="5edd9-163">SQLEXECUTE 操作示例业务流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="5edd9-163">A sample orchestration for the SQLEXECUTE operation resembles the following:</span></span>  
  
 <span data-ttu-id="5edd9-164">![业务流程，以调用 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/media/bdb47660-6013-46f7-aa4b-fe5eb83f3a1e.gif "bdb47660-6013-46f7-aa4b-fe5eb83f3a1e")</span><span class="sxs-lookup"><span data-stu-id="5edd9-164">![Orchestration to invoke the SQLEXECUTE operation](../../adapters-and-accelerators/adapter-oracle-database/media/bdb47660-6013-46f7-aa4b-fe5eb83f3a1e.gif "bdb47660-6013-46f7-aa4b-fe5eb83f3a1e")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="5edd9-165">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="5edd9-165">Adding Message Shapes</span></span>  
 <span data-ttu-id="5edd9-166">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="5edd9-166">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="5edd9-167">刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="5edd9-167">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="5edd9-168">形状</span><span class="sxs-lookup"><span data-stu-id="5edd9-168">Shape</span></span>|<span data-ttu-id="5edd9-169">形状类型</span><span class="sxs-lookup"><span data-stu-id="5edd9-169">Shape Type</span></span>|<span data-ttu-id="5edd9-170">属性</span><span class="sxs-lookup"><span data-stu-id="5edd9-170">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="5edd9-171">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="5edd9-171">ReceiveMessage</span></span>|<span data-ttu-id="5edd9-172">Receive</span><span class="sxs-lookup"><span data-stu-id="5edd9-172">Receive</span></span>|<span data-ttu-id="5edd9-173">-将设置**名称**到*ReceiveMessage*</span><span class="sxs-lookup"><span data-stu-id="5edd9-173">-   Set **Name** to *ReceiveMessage*</span></span><br /><span data-ttu-id="5edd9-174">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="5edd9-174">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="5edd9-175">发送消息</span><span class="sxs-lookup"><span data-stu-id="5edd9-175">SendMessage</span></span>|<span data-ttu-id="5edd9-176">Send</span><span class="sxs-lookup"><span data-stu-id="5edd9-176">Send</span></span>|<span data-ttu-id="5edd9-177">-将设置**名称**到*SendMessage*</span><span class="sxs-lookup"><span data-stu-id="5edd9-177">-   Set **Name** to *SendMessage*</span></span>|  
|<span data-ttu-id="5edd9-178">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="5edd9-178">ReceiveResponse</span></span>|<span data-ttu-id="5edd9-179">Receive</span><span class="sxs-lookup"><span data-stu-id="5edd9-179">Receive</span></span>|<span data-ttu-id="5edd9-180">-将设置**名称**到*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="5edd9-180">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="5edd9-181">-将设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="5edd9-181">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="5edd9-182">SendResponse</span><span class="sxs-lookup"><span data-stu-id="5edd9-182">SendResponse</span></span>|<span data-ttu-id="5edd9-183">Send</span><span class="sxs-lookup"><span data-stu-id="5edd9-183">Send</span></span>|<span data-ttu-id="5edd9-184">-将设置**名称**到*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="5edd9-184">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="5edd9-185">添加端口</span><span class="sxs-lookup"><span data-stu-id="5edd9-185">Adding Ports</span></span>  
 <span data-ttu-id="5edd9-186">请确保为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="5edd9-186">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="5edd9-187">端口列中列出的名称是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="5edd9-187">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="5edd9-188">端口</span><span class="sxs-lookup"><span data-stu-id="5edd9-188">Port</span></span>|<span data-ttu-id="5edd9-189">属性</span><span class="sxs-lookup"><span data-stu-id="5edd9-189">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="5edd9-190">文件</span><span class="sxs-lookup"><span data-stu-id="5edd9-190">FileIn</span></span>|<span data-ttu-id="5edd9-191">-将设置**标识符**到*文件*</span><span class="sxs-lookup"><span data-stu-id="5edd9-191">-   Set **Identifier** to *FileIn*</span></span><br /><span data-ttu-id="5edd9-192">-将设置**类型**到*FileInType*</span><span class="sxs-lookup"><span data-stu-id="5edd9-192">-   Set **Type** to *FileInType*</span></span><br /><span data-ttu-id="5edd9-193">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="5edd9-193">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="5edd9-194">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="5edd9-194">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="5edd9-195">LOBPort</span><span class="sxs-lookup"><span data-stu-id="5edd9-195">LOBPort</span></span>|<span data-ttu-id="5edd9-196">-将设置**标识符**到*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="5edd9-196">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="5edd9-197">-将设置**类型**到*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="5edd9-197">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="5edd9-198">-将设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="5edd9-198">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="5edd9-199">-将设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="5edd9-199">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="5edd9-200">SaveResponse</span><span class="sxs-lookup"><span data-stu-id="5edd9-200">SaveResponse</span></span>|<span data-ttu-id="5edd9-201">-将设置**标识符**到*SaveResponse*</span><span class="sxs-lookup"><span data-stu-id="5edd9-201">-   Set **Identifier** to *SaveResponse*</span></span><br /><span data-ttu-id="5edd9-202">-将设置**类型**到*SaveResponseType*</span><span class="sxs-lookup"><span data-stu-id="5edd9-202">-   Set **Type** to *SaveResponseType*</span></span><br /><span data-ttu-id="5edd9-203">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="5edd9-203">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="5edd9-204">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="5edd9-204">-   Set **Communication Direction** to *Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a><span data-ttu-id="5edd9-205">对于操作形状，指定消息并将其连接到端口</span><span class="sxs-lookup"><span data-stu-id="5edd9-205">Specify Messages for Action Shapes, and Connect Them to Ports</span></span>  
 <span data-ttu-id="5edd9-206">下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。</span><span class="sxs-lookup"><span data-stu-id="5edd9-206">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="5edd9-207">前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="5edd9-207">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="5edd9-208">形状</span><span class="sxs-lookup"><span data-stu-id="5edd9-208">Shape</span></span>|<span data-ttu-id="5edd9-209">属性</span><span class="sxs-lookup"><span data-stu-id="5edd9-209">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="5edd9-210">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="5edd9-210">ReceiveMessage</span></span>|<span data-ttu-id="5edd9-211">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="5edd9-211">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="5edd9-212">-将设置**操作**到*FileIn.SQLEXECUTE.Request*</span><span class="sxs-lookup"><span data-stu-id="5edd9-212">-   Set **Operation** to *FileIn.SQLEXECUTE.Request*</span></span>|  
|<span data-ttu-id="5edd9-213">发送消息</span><span class="sxs-lookup"><span data-stu-id="5edd9-213">SendMessage</span></span>|<span data-ttu-id="5edd9-214">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="5edd9-214">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="5edd9-215">-将设置**操作**到*LOBPort.SQLEXECUTE.Request*</span><span class="sxs-lookup"><span data-stu-id="5edd9-215">-   Set **Operation** to *LOBPort.SQLEXECUTE.Request*</span></span>|  
|<span data-ttu-id="5edd9-216">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="5edd9-216">ReceiveResponse</span></span>|<span data-ttu-id="5edd9-217">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="5edd9-217">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="5edd9-218">-将设置**操作**到*LOBPort.SQLEXECUTE.Response*</span><span class="sxs-lookup"><span data-stu-id="5edd9-218">-   Set **Operation** to *LOBPort.SQLEXECUTE.Response*</span></span>|  
|<span data-ttu-id="5edd9-219">SendResponse</span><span class="sxs-lookup"><span data-stu-id="5edd9-219">SendResponse</span></span>|<span data-ttu-id="5edd9-220">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="5edd9-220">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="5edd9-221">-将设置**操作**到*SaveResponse.SQLEXECUTE.Request*</span><span class="sxs-lookup"><span data-stu-id="5edd9-221">-   Set **Operation** to *SaveResponse.SQLEXECUTE.Request*</span></span>|  
  
 <span data-ttu-id="5edd9-222">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="5edd9-222">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="5edd9-223">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5edd9-223">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5edd9-224">有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-224">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>  
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="5edd9-225">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5edd9-225">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="5edd9-226">部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="5edd9-226">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="5edd9-227">必须使用 BizTalk Server 管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="5edd9-227">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="5edd9-228">有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-228">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="5edd9-229">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="5edd9-229">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="5edd9-230">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="5edd9-230">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="5edd9-231">映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="5edd9-231">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="5edd9-232">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="5edd9-232">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="5edd9-233">硬盘和放置请求消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="5edd9-233">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="5edd9-234">BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="5edd9-234">The BizTalk orchestration will consume the request message and send it to the Oracle database.</span></span>  
  
    -   <span data-ttu-id="5edd9-235">硬盘和 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="5edd9-235">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the Oracle database.</span></span>  
  
    -   <span data-ttu-id="5edd9-236">定义物理 WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="5edd9-236">Define a physical WCF-Custom or WCF-OracleDB send port to send messages to the Oracle database.</span></span> <span data-ttu-id="5edd9-237">你必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="5edd9-237">You must also specify the action in the send port.</span></span> <span data-ttu-id="5edd9-238">有关如何创建 WCF 自定义或 WCF OracleDB 端口的信息，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-238">For information about how to create WCF-Custom or WCF-OracleDB ports, see [Manually configure a physical port binding to Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5edd9-239">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。</span><span class="sxs-lookup"><span data-stu-id="5edd9-239">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file that contains information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="5edd9-240">从 BizTalk Server 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。</span><span class="sxs-lookup"><span data-stu-id="5edd9-240">You can import this binding file from the BizTalk Server Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="5edd9-241">有关详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-241">For more information, see [Configure a physical port binding using a port  binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="5edd9-242">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="5edd9-242">Starting the Application</span></span>  
 <span data-ttu-id="5edd9-243">你必须启动 BizTalk 应用程序执行 SQLEXECUTE 操作。</span><span class="sxs-lookup"><span data-stu-id="5edd9-243">You must start the BizTalk application for performing the SQLEXECUTE operation.</span></span> <span data-ttu-id="5edd9-244">有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-244">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="5edd9-245">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="5edd9-245">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="5edd9-246">FILE 接收端口，以便运行业务流程的是接收请求消息。</span><span class="sxs-lookup"><span data-stu-id="5edd9-246">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="5edd9-247">要从业务流程接收响应消息的文件发送端口正在运行。</span><span class="sxs-lookup"><span data-stu-id="5edd9-247">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="5edd9-248">WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库正在运行。</span><span class="sxs-lookup"><span data-stu-id="5edd9-248">The WCF-Custom or WCF-OracleDB send port to send messages to the Oracle database is running.</span></span>  
  
-   <span data-ttu-id="5edd9-249">BizTalk 业务流程操作正在运行。</span><span class="sxs-lookup"><span data-stu-id="5edd9-249">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="5edd9-250">执行该操作</span><span class="sxs-lookup"><span data-stu-id="5edd9-250">Executing the Operation</span></span>  
 <span data-ttu-id="5edd9-251">运行应用程序后，必须放到该文件的请求消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="5edd9-251">After you run the application, you must drop a request message to the FILE receive location.</span></span> <span data-ttu-id="5edd9-252">请求消息的架构必须符合你先前生成 SQLEXECUTE 操作的架构。</span><span class="sxs-lookup"><span data-stu-id="5edd9-252">The schema for the request message must conform to the schema for the SQLEXECUTE operation you generated earlier.</span></span> <span data-ttu-id="5edd9-253">业务流程使用该消息，并将其发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="5edd9-253">The orchestration consumes the message and sends it to the Oracle database.</span></span> <span data-ttu-id="5edd9-254">从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。</span><span class="sxs-lookup"><span data-stu-id="5edd9-254">The response from the Oracle database is saved at the other FILE location defined as part of the orchestration.</span></span> <span data-ttu-id="5edd9-255">请参阅[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)有关调用 SQLEXECUTE 操作的请求消息架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5edd9-255">See [Message Schemas for the SQLEXECUTE Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md) for more information about the request message schema for invoking a SQLEXECUTE operation.</span></span>  
  
 <span data-ttu-id="5edd9-256">因为 SQLEXECUTE 操作不显示在任何 Oracle 数据库项目下，你可以使用相同的架构在视图上执行参数化的 SQL 查询或者某些其他表执行操作的过程。</span><span class="sxs-lookup"><span data-stu-id="5edd9-256">Because the SQLEXECUTE operation is not surfaced under any Oracle database artifact, you can use the same schema to perform a parameterized SQL query on a view or execute a procedure that operates on some other table.</span></span>  
  
 <span data-ttu-id="5edd9-257">例如，下面的请求消息使用 SQLEXECUTE 操作帐户表上执行参数化的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="5edd9-257">For example, the following request message performs a parameterized SELECT statement on the ACCOUNT table using the SQLEXECUTE operation.</span></span> <span data-ttu-id="5edd9-258">帐户表 SCOTT 架构下创建通过运行这些示例提供的 SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="5edd9-258">The ACCOUNT table is created under the SCOTT schema by running the SQL scripts provided with the samples.</span></span> <span data-ttu-id="5edd9-259">若要了解有关这些示例的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-259">To know more about the samples, see [Schema Samples](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).</span></span>  
  
```  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
  <SQLSTATEMENT>select * from ACCOUNT where ACCTID=:num</SQLSTATEMENT>  
  <PARAMETERSCHEMA>num number</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA xmlns="http://Microsoft.LobServices.OracleDB/2007/03">  
      <PARAMETER>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">100000</string>  
      </PARAMETER>  
    </PARAMETERDATA>  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 <span data-ttu-id="5edd9-260">来自 Oracle 数据库以实现更高版本的请求消息的响应是：</span><span class="sxs-lookup"><span data-stu-id="5edd9-260">The response from Oracle database for the above request message is:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<SQLEXECUTEResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
  <SQLEXECUTEResult>  
    <GenRecordRow xmlns="http://Microsoft.LobServices.OracleDB/2007/03">  
      <GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>ACCTID</ColumnName>   
          <ColumnValue>100000</ColumnValue>   
          <ColumnType>System.Decimal</ColumnType>   
        </GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>NAME</ColumnName>   
          <ColumnValue>Kim Ralls</ColumnValue>   
          <ColumnType>System.String</ColumnType>   
        </GenRecordColumn>  
        <GenRecordColumn>  
          <ColumnName>BALANCE</ColumnName>   
          <ColumnValue>10000</ColumnValue>   
          <ColumnType>System.Decimal</ColumnType>   
        </GenRecordColumn>  
      </GenRecordColumn>  
    </GenRecordRow>  
  </SQLEXECUTEResult>  
</SQLEXECUTEResponse>  
```  
  
## <a name="possible-exceptions"></a><span data-ttu-id="5edd9-261">可能的异常</span><span class="sxs-lookup"><span data-stu-id="5edd9-261">Possible Exceptions</span></span>  
 <span data-ttu-id="5edd9-262">有关异常的信息可能会遇到时执行 DML 操作使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[异常和错误处理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-262">For information about the exceptions you might encounter while performing a DML operation using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Exceptions and error handling](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="5edd9-263">最佳实践</span><span class="sxs-lookup"><span data-stu-id="5edd9-263">Best Practices</span></span>  
 <span data-ttu-id="5edd9-264">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="5edd9-264">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the bindings file.</span></span> <span data-ttu-id="5edd9-265">一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。</span><span class="sxs-lookup"><span data-stu-id="5edd9-265">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="5edd9-266">有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="5edd9-266">For more information about binding files, see [Reuse Oracle Database adapter bindings](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5edd9-267">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5edd9-267">See Also</span></span>  
[<span data-ttu-id="5edd9-268">开发与 Oracle 数据库的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="5edd9-268">Building Blocks to Develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)