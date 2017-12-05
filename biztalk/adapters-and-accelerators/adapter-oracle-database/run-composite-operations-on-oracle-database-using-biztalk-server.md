---
title: "运行 Oracle 数据库使用 BizTalk Server 上的复合操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf47d95e-cdf1-4c9b-a15a-7cf123d0ea6d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41bb09a2bdece47795eabc91bf5e87ebba7deaa7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="run-composite-operations-on-oracle-database-using-biztalk-server"></a><span data-ttu-id="00d1f-102">运行 Oracle 数据库使用 BizTalk Server 上的复合操作</span><span class="sxs-lookup"><span data-stu-id="00d1f-102">Run Composite Operations on Oracle Database using BizTalk Server</span></span>
<span data-ttu-id="00d1f-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使适配器客户端可以执行对 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to perform composite operations on Oracle database.</span></span> <span data-ttu-id="00d1f-104">复合操作可以包括：</span><span class="sxs-lookup"><span data-stu-id="00d1f-104">A composite operation can include:</span></span>  
  
-   <span data-ttu-id="00d1f-105">插入、 更新、 删除和选择表和视图上的操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-105">Insert, Update, Delete, and Select operations on tables and views.</span></span>  
  
-   <span data-ttu-id="00d1f-106">存储的过程和函数，内部或外部包。</span><span class="sxs-lookup"><span data-stu-id="00d1f-106">Stored procedures and functions, inside or outside a package.</span></span>  
  
 <span data-ttu-id="00d1f-107">单个复合操作可以具有任意数量的这些操作，按任何顺序。</span><span class="sxs-lookup"><span data-stu-id="00d1f-107">A single composite operation can have any number of these operations, in any order.</span></span> <span data-ttu-id="00d1f-108">例如，你可以通过删除和最后一存储的过程执行后接两个插入。</span><span class="sxs-lookup"><span data-stu-id="00d1f-108">For example, you can have two inserts followed by a delete, and finally a stored procedure execution.</span></span> <span data-ttu-id="00d1f-109">此外，你可以以不同的数据库表或视图为目标的不同操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-109">Also, you can have different operations targeting different database tables or views.</span></span> <span data-ttu-id="00d1f-110">有关如何适配器支持复合操作的详细信息，请参阅[Oracle 数据库中执行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-110">For more information about how the adapter supports composite operations, see [Performing Composite Operations in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md).</span></span> <span data-ttu-id="00d1f-111">有关复合操作的 SOAP 消息结构的信息，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-111">For information about the structure of the SOAP message for composite operations, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).</span></span>  
  
## <a name="how-to-perform-composite-operations-on-oracle-database"></a><span data-ttu-id="00d1f-112">如何执行对 Oracle 数据库的复合操作？</span><span class="sxs-lookup"><span data-stu-id="00d1f-112">How to Perform Composite Operations on Oracle Database?</span></span>  
 <span data-ttu-id="00d1f-113">使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-113">Performing an operation on Oracle database using [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md).</span></span> <span data-ttu-id="00d1f-114">若要执行对 Oracle 数据库的复合操作，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="00d1f-114">To perform composite operations on Oracle database, these tasks are:</span></span>  
  
1.  <span data-ttu-id="00d1f-115">创建 BizTalk 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和为你想要调用的所有操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-115">Create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and generate schema for all the operations you want to invoke.</span></span>  
  
2.  <span data-ttu-id="00d1f-116">手动创建包括对你在上一步中生成的所有架构的引用的架构文件。</span><span class="sxs-lookup"><span data-stu-id="00d1f-116">Manually create a schema file that includes references to all the schemas you generated in the previous step.</span></span>  
  
3.  <span data-ttu-id="00d1f-117">在发送和接收消息从 Oracle 数据库的 BizTalk 项目中创建消息。</span><span class="sxs-lookup"><span data-stu-id="00d1f-117">Create messages in the BizTalk project for sending and receiving messages from Oracle database.</span></span> <span data-ttu-id="00d1f-118">这些消息必须符合你在上一步中创建的请求和响应架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-118">These messages must conform to the request and response schema you created in the previous step.</span></span>  
  
4.  <span data-ttu-id="00d1f-119">创建业务流程来调用 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-119">Create an orchestration to invoke the composite operation on Oracle database.</span></span>  
  
5.  <span data-ttu-id="00d1f-120">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="00d1f-120">Build and deploy the BizTalk project.</span></span>  
  
6.  <span data-ttu-id="00d1f-121">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="00d1f-121">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
7.  <span data-ttu-id="00d1f-122">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="00d1f-122">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="00d1f-123">本主题提供有关如何执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="00d1f-123">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="00d1f-124">生成架构</span><span class="sxs-lookup"><span data-stu-id="00d1f-124">Generating Schema</span></span>  
 <span data-ttu-id="00d1f-125">在本主题中，来演示如何执行复合操作，我们将执行相同的顺序中的以下任务：</span><span class="sxs-lookup"><span data-stu-id="00d1f-125">In this topic, to demonstrate how to perform composite operations, we will perform the following tasks in the same order:</span></span>  
  
-   <span data-ttu-id="00d1f-126">将记录插入 ACCOUNTACTIVITY 表。</span><span class="sxs-lookup"><span data-stu-id="00d1f-126">Insert record into the ACCOUNTACTIVITY table.</span></span>  
  
-   <span data-ttu-id="00d1f-127">通过调用 ACCOUNT_PKG 包内的 GET_ALL_ACTIVITY 过程检索 ACCOUNTACTIVITY 表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="00d1f-127">Retrieve all the records in the ACCOUNTACTIVITY table by invoking the GET_ALL_ACTIVITY procedure within the ACCOUNT_PKG package.</span></span>  
  
-   <span data-ttu-id="00d1f-128">从 ACCOUNTACTIVITY 表中删除记录。</span><span class="sxs-lookup"><span data-stu-id="00d1f-128">Delete the record from the ACCOUNTACTIVITY table.</span></span>  
  
 <span data-ttu-id="00d1f-129">运行示例后，若要创建 ACCOUNTACTIVITY 表提供的脚本。</span><span class="sxs-lookup"><span data-stu-id="00d1f-129">Run the scripts provided with the samples to create the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="00d1f-130">有关这些示例的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-130">For more information about the samples, see [Schema Samples](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).</span></span>  
  
 <span data-ttu-id="00d1f-131">您必须创建 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-131">You must create a BizTalk project and use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema.</span></span> <span data-ttu-id="00d1f-132">请参阅[检索元数据的 Visual Studio 中的 Oracle 数据库操作](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="00d1f-132">See [Retrieve metadata for Oracle Database operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) for more information about how to generate schemas.</span></span>  
  
## <a name="creating-a-composite-schema-definition"></a><span data-ttu-id="00d1f-133">创建复合架构定义</span><span class="sxs-lookup"><span data-stu-id="00d1f-133">Creating a Composite Schema Definition</span></span>  
 <span data-ttu-id="00d1f-134">现在，你必须创建中的复合架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk 项目引用的单独操作创建的架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-134">You must now create a composite schema in the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] BizTalk project that references the schemas you created for the individual operations.</span></span> <span data-ttu-id="00d1f-135">执行以下步骤以创建复合架构定义。</span><span class="sxs-lookup"><span data-stu-id="00d1f-135">Perform the following steps to create a composite schema definition.</span></span>  
  
#### <a name="to-add-a-composite-schema-definition"></a><span data-ttu-id="00d1f-136">若要添加的复合架构定义</span><span class="sxs-lookup"><span data-stu-id="00d1f-136">To add a composite schema definition</span></span>  
  
1.  <span data-ttu-id="00d1f-137">将架构文件添加到中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00d1f-137">Add a schema file to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="00d1f-138">右键单击解决方案名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-138">Right-click the solution name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="00d1f-139">在**添加新项**对话框中，从**类别**框中，单击**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-139">In the **Add New Item** dialog box, from the **Categories** box, click **Schema Files**.</span></span> <span data-ttu-id="00d1f-140">从**模板**框中，单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-140">From the **Templates** box, click **Schema**.</span></span> <span data-ttu-id="00d1f-141">指定的架构文件的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-141">Specify a name for the schema file and click **OK**.</span></span>  
  
     <span data-ttu-id="00d1f-142">对于本例，请将架构文件名称指定为`CompositeSchema.xsd`。</span><span class="sxs-lookup"><span data-stu-id="00d1f-142">For this example, specify the schema file name as `CompositeSchema.xsd`.</span></span>  
  
2.  <span data-ttu-id="00d1f-143">添加对生成的不同你想要执行的操作的架构的引用。</span><span class="sxs-lookup"><span data-stu-id="00d1f-143">Add references to the schema generated for the different operations that you want to perform.</span></span> <span data-ttu-id="00d1f-144">在此示例中，为操作生成的不同架构是：</span><span class="sxs-lookup"><span data-stu-id="00d1f-144">In this example, the different schemas generated for operations are:</span></span>  
  
    -   <span data-ttu-id="00d1f-145">OracleDBBinding.xsd，ACCOUNTACTIVITY 表的 Insert 和 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-145">OracleDBBinding.xsd, for Insert and Delete operations on ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="00d1f-146">OracleDBBinding2.xsd，GET_ALL_ACTIVITY 过程。</span><span class="sxs-lookup"><span data-stu-id="00d1f-146">OracleDBBinding2.xsd, for the GET_ALL_ACTIVITY procedure.</span></span>  
  
     <span data-ttu-id="00d1f-147">若要添加的引用：</span><span class="sxs-lookup"><span data-stu-id="00d1f-147">To add references:</span></span>  
  
    1.  <span data-ttu-id="00d1f-148">右键单击根**\<架构\>** CompositeSchema.xsd，然后单击的节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-148">Right-click the root **\<Schema\>** node in the CompositeSchema.xsd, and click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="00d1f-149">在**属性**框中，单击省略号按钮**（...）**针对**导入**属性。</span><span class="sxs-lookup"><span data-stu-id="00d1f-149">In the **Property** box, click the ellipsis button **(…)** against the **Imports** property.</span></span>  
  
         <span data-ttu-id="00d1f-150">![导入架构定义](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span><span class="sxs-lookup"><span data-stu-id="00d1f-150">![Import schema definitions](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span></span>  
  
    3.  <span data-ttu-id="00d1f-151">在**导入**对话框中，从**导入的新架构**列表中，选择**XSD 导入**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-151">In the **Imports** dialog box, from the **Import new schema as** list, select **XSD Import**, and then click **Add**.</span></span>  
  
    4.  <span data-ttu-id="00d1f-152">在**BizTalk 类型选取器**对话框框中，展开 BizTalk 项目名称节点，展开**架构**，然后选择你想要导入的架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-152">In the **BizTalk Type Picker** dialog box, expand the BizTalk project name node, expand **Schemas**, and then select the schema you want to import.</span></span> <span data-ttu-id="00d1f-153">对于此示例中，选择 < BizTalk_project_name >。OracleDBBinding.xsd。</span><span class="sxs-lookup"><span data-stu-id="00d1f-153">For this example, select <BizTalk_project_name>.OracleDBBinding.xsd.</span></span> <span data-ttu-id="00d1f-154">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-154">Click **OK**.</span></span>  
  
         <span data-ttu-id="00d1f-155">重复此步骤以导入 < BizTalk_project_name >。OracleDBBinding2.xsd 过。</span><span class="sxs-lookup"><span data-stu-id="00d1f-155">Repeat this step to import <BizTalk_project_name>.OracleDBBinding2.xsd too.</span></span>  
  
    5.  <span data-ttu-id="00d1f-156">在**导入**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-156">In the **Imports** dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="00d1f-157">将两个子节点添加到根架构节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-157">Add two child nodes to the root schema node.</span></span> <span data-ttu-id="00d1f-158">一个子节点对应于执行复合操作的请求架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-158">One child node corresponds to the request schema for performing the composite operation.</span></span> <span data-ttu-id="00d1f-159">另一个子节点对应于响应架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-159">The other child node corresponds to the response schema.</span></span> <span data-ttu-id="00d1f-160">对应于请求架构的节点可以具有任何名称。</span><span class="sxs-lookup"><span data-stu-id="00d1f-160">The node that corresponds to the request schema can have any name.</span></span> <span data-ttu-id="00d1f-161">< Request_schema_node > 响应，必须调用到响应架构相对应的节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-161">The node that corresponds to the response schema must be called <request_schema_node>Response.</span></span> <span data-ttu-id="00d1f-162">对于此示例，我们将调用该请求架构节点作为**请求**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-162">For this example, we will call the request schema node as **Request**.</span></span> <span data-ttu-id="00d1f-163">因此，响应架构节点称为**请求响应**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-163">So, the response schema node is called **RequestResponse**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00d1f-164">默认情况下，**根**还将节点添加到新的架构文件。</span><span class="sxs-lookup"><span data-stu-id="00d1f-164">By default, a **Root** node is also added to a new schema file.</span></span> <span data-ttu-id="00d1f-165">你可以重命名**根**节点**请求**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-165">You can rename the **Root** node to **Request**.</span></span> <span data-ttu-id="00d1f-166">若要重命名节点，右键单击节点名称，然后单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-166">To rename a node, right-click the node name and click **Rename**.</span></span>  
  
     <span data-ttu-id="00d1f-167">若要添加一个节点下的**\<架构\>**节点：</span><span class="sxs-lookup"><span data-stu-id="00d1f-167">To add a node under the **\<Schema\>** node:</span></span>  
  
    1.  <span data-ttu-id="00d1f-168">右键单击**\<架构\>**节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-168">Right-click the **\<Schema\>** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
    2.  <span data-ttu-id="00d1f-169">重命名为新节点**请求响应**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-169">Rename the new node to **RequestResponse**.</span></span>  
  
4.  <span data-ttu-id="00d1f-170">添加下的子节点**请求**对应于每个将作为复合操作的一部分执行的操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-170">Add child nodes under the **Request** node that correspond to the request schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="00d1f-171">对于此示例中，你必须添加对应于以下的子节点：</span><span class="sxs-lookup"><span data-stu-id="00d1f-171">For this example, you must add child nodes corresponding to the following:</span></span>  
  
    -   <span data-ttu-id="00d1f-172">插入和删除 ACCOUNTACTIVITY 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-172">Insert and Delete operations on the ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="00d1f-173">GET_ALL_ACTIVITY 过程。</span><span class="sxs-lookup"><span data-stu-id="00d1f-173">GET_ALL_ACTIVITY procedure.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="00d1f-174">必须将节点添加与要在其中执行操作的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="00d1f-174">You must add the nodes in the same order in which you want to perform the operations.</span></span> <span data-ttu-id="00d1f-175">例如，如果你想要插入一条记录，然后执行存储的过程，然后删除你必须首先添加的节点插入操作的记录，跟的节点的存储过程，以及最后的删除操作的节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-175">For example, if you want to insert a record, then execute a stored procedure, and then delete a record you must first add a node for the Insert operation, followed by a node for the stored procedure, and finally a node for the Delete operation.</span></span>  
  
     <span data-ttu-id="00d1f-176">若要添加到的子节点**请求**节点：</span><span class="sxs-lookup"><span data-stu-id="00d1f-176">To add child nodes to the **Request** node:</span></span>  
  
    1.  <span data-ttu-id="00d1f-177">右键单击**请求**节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-177">Right-click the **Request** node, point to **Insert Schema Node**, and then click  **Child Record**.</span></span>  
  
         <span data-ttu-id="00d1f-178">![插入架构的子节点](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span><span class="sxs-lookup"><span data-stu-id="00d1f-178">![Insert child nodes for a schema](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span></span>  
  
    2.  <span data-ttu-id="00d1f-179">重命名以作为复合操作的一部分执行的操作的请求架构与相对应的记录。</span><span class="sxs-lookup"><span data-stu-id="00d1f-179">Rename the record to correspond to a request schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="00d1f-180">例如，重命名为"Insert"节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-180">For example, rename the node to “Insert”.</span></span>  
  
    3.  <span data-ttu-id="00d1f-181">映射**插入**ACCOUNTACTIVITY 表上的插入操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-181">Map the **Insert** node to the request schema for the Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="00d1f-182">为此，请右键单击**插入**节点，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-182">To do so, right-click the **Insert** node, and click **Properties**.</span></span> <span data-ttu-id="00d1f-183">在**属性**框中，从**数据结构类型**列表中，选择**插入 （引用）**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-183">In the **Properties** box, from the **Data Structure Type** list, select **Insert (Reference)**.</span></span>  
  
         <span data-ttu-id="00d1f-184">![将子节点映射到请求架构](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")</span><span class="sxs-lookup"><span data-stu-id="00d1f-184">![Map child nodes to request schema](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")</span></span>  
  
    4.  <span data-ttu-id="00d1f-185">重复上述步骤以添加 GET_ALL_ACTIVITY 存储过程和删除操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-185">Repeat these steps to add nodes for the request schemas for GET_ALL_ACTIVITY stored procedure and the Delete operation.</span></span> <span data-ttu-id="00d1f-186">指定节点名称，并将它们映射到相应的架构下, 表中所述。</span><span class="sxs-lookup"><span data-stu-id="00d1f-186">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
        |<span data-ttu-id="00d1f-187">节点名称</span><span class="sxs-lookup"><span data-stu-id="00d1f-187">Node name</span></span>|<span data-ttu-id="00d1f-188">映射到架构</span><span class="sxs-lookup"><span data-stu-id="00d1f-188">Mapped to schema</span></span>|  
        |---------------|----------------------|  
        |<span data-ttu-id="00d1f-189">GET_ALL_ACTIVITY</span><span class="sxs-lookup"><span data-stu-id="00d1f-189">GET_ALL_ACTIVITY</span></span>|<span data-ttu-id="00d1f-190">GET_ALL_ACTIVITY （参考）</span><span class="sxs-lookup"><span data-stu-id="00d1f-190">GET_ALL_ACTIVITY (Reference)</span></span>|  
        |<span data-ttu-id="00d1f-191">DELETE</span><span class="sxs-lookup"><span data-stu-id="00d1f-191">Delete</span></span>|<span data-ttu-id="00d1f-192">删除 （参考）</span><span class="sxs-lookup"><span data-stu-id="00d1f-192">Delete (Reference)</span></span>|  
  
5.  <span data-ttu-id="00d1f-193">添加下的子节点**请求响应**对应于每个将作为复合操作的一部分执行的操作的响应架构的节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-193">Add child nodes under the **RequestResponse** node that correspond to the response schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="00d1f-194">对于此示例中，你必须添加对应于以下的子节点：</span><span class="sxs-lookup"><span data-stu-id="00d1f-194">For this example, you must add child nodes corresponding to the following:</span></span>  
  
    -   <span data-ttu-id="00d1f-195">插入和删除 ACCOUNTACTIVITY 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-195">Insert and Delete operations on the ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="00d1f-196">GET_ALL_ACTIVITY 存储过程。</span><span class="sxs-lookup"><span data-stu-id="00d1f-196">GET_ALL_ACTIVITY stored procedure.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="00d1f-197">你必须添加的子节点下的子节点的顺序相同**请求**节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-197">You must add the child nodes in the same order as the child nodes under the **Request** node.</span></span>  
  
     <span data-ttu-id="00d1f-198">若要添加到的子节点**请求响应**节点：</span><span class="sxs-lookup"><span data-stu-id="00d1f-198">To add child nodes to the **RequestResponse** node:</span></span>  
  
    1.  <span data-ttu-id="00d1f-199">右键单击**请求响应**节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-199">Right-click the **RequestResponse** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
    2.  <span data-ttu-id="00d1f-200">重命名以作为复合操作的一部分执行的操作的响应架构与相对应的记录。</span><span class="sxs-lookup"><span data-stu-id="00d1f-200">Rename the record to correspond to a response schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="00d1f-201">例如，重命名为"InsertResponse"节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-201">For example, rename the node to “InsertResponse”.</span></span>  
  
    3.  <span data-ttu-id="00d1f-202">映射**InsertResponse** ACCOUNTACTIVITY 表上的插入操作的响应架构的节点。</span><span class="sxs-lookup"><span data-stu-id="00d1f-202">Map the **InsertResponse** node to the response schema for the Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="00d1f-203">为此，请右键单击**InsertResponse**节点，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-203">To do so, right-click the **InsertResponse** node, and click **Properties**.</span></span> <span data-ttu-id="00d1f-204">在**属性**框中，从**数据结构类型**列表中，选择**InsertResponse （引用）**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-204">In the **Properties** box, from the **Data Structure Type** list, select **InsertResponse (Reference)**.</span></span>  
  
    4.  <span data-ttu-id="00d1f-205">重复上述步骤以添加节点 GET_ALL_ACTIVITY 存储过程和删除操作的响应架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-205">Repeat these steps to add nodes for the response schemas for the GET_ALL_ACTIVITY stored procedure and the Delete operation.</span></span> <span data-ttu-id="00d1f-206">指定节点名称，并将它们映射到相应的架构下, 表中所述。</span><span class="sxs-lookup"><span data-stu-id="00d1f-206">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
        |<span data-ttu-id="00d1f-207">节点名称</span><span class="sxs-lookup"><span data-stu-id="00d1f-207">Node name</span></span>|<span data-ttu-id="00d1f-208">映射到架构</span><span class="sxs-lookup"><span data-stu-id="00d1f-208">Mapped to schema</span></span>|  
        |---------------|----------------------|  
        |<span data-ttu-id="00d1f-209">GET_ALL_ACTIVITYResponse</span><span class="sxs-lookup"><span data-stu-id="00d1f-209">GET_ALL_ACTIVITYResponse</span></span>|<span data-ttu-id="00d1f-210">GET_ALL_ACTIVITYResponse （参考）</span><span class="sxs-lookup"><span data-stu-id="00d1f-210">GET_ALL_ACTIVITYResponse (Reference)</span></span>|  
        |<span data-ttu-id="00d1f-211">DeleteResponse</span><span class="sxs-lookup"><span data-stu-id="00d1f-211">DeleteResponse</span></span>|<span data-ttu-id="00d1f-212">DeleteResponse （参考）</span><span class="sxs-lookup"><span data-stu-id="00d1f-212">DeleteResponse (Reference)</span></span>|  
  
6.  <span data-ttu-id="00d1f-213">保存**CompositeSchema.xsd**文件。</span><span class="sxs-lookup"><span data-stu-id="00d1f-213">Save the **CompositeSchema.xsd** file.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="00d1f-214">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="00d1f-214">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="00d1f-215">在最后一步中创建复合架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="00d1f-215">The composite schema that you created in the last step describes the “types” required for the messages in an orchestration.</span></span> <span data-ttu-id="00d1f-216">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="00d1f-216">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="00d1f-217">现在，你必须创建业务流程的消息，并将它们链接到你在上一步中创建的架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-217">You must now create messages for the orchestration and link them to schema you created in the previous step.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="00d1f-218">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="00d1f-218">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="00d1f-219">中的 BizTalk 项目中添加业务流程[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00d1f-219">Add an orchestration to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="00d1f-220">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-220">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="00d1f-221">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-221">Type a name for the BizTalk orchestration, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="00d1f-222">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="00d1f-222">Open the Orchestration View window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="00d1f-223">若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-223">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="00d1f-224">在业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-224">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="00d1f-225">右键单击新创建的消息中，，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-225">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="00d1f-226">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00d1f-226">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="00d1f-227">使用此选项</span><span class="sxs-lookup"><span data-stu-id="00d1f-227">Use this</span></span>|<span data-ttu-id="00d1f-228">执行的操作</span><span class="sxs-lookup"><span data-stu-id="00d1f-228">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="00d1f-229">Identifier</span><span class="sxs-lookup"><span data-stu-id="00d1f-229">Identifier</span></span>|<span data-ttu-id="00d1f-230">类型`Request`</span><span class="sxs-lookup"><span data-stu-id="00d1f-230">Type `Request`</span></span>|  
    |<span data-ttu-id="00d1f-231">消息类型</span><span class="sxs-lookup"><span data-stu-id="00d1f-231">Message Type</span></span>|<span data-ttu-id="00d1f-232">从下拉列表中，展开**架构**，然后选择*Composite_Op.CompositeSchema.Request*，其中 Composite_Op 是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="00d1f-232">From the drop-down list, expand **Schemas**, and then select *Composite_Op.CompositeSchema.Request*, where Composite_Op is the name of your BizTalk project.</span></span> <span data-ttu-id="00d1f-233">CompositeSchema 是手动创建的复合操作的架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-233">CompositeSchema is the schema you created manually for the composite operations.</span></span>|  
  
6.  <span data-ttu-id="00d1f-234">重复步骤 2 创建一条新消息。</span><span class="sxs-lookup"><span data-stu-id="00d1f-234">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="00d1f-235">在**属性**窗格中，为新的消息中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00d1f-235">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="00d1f-236">使用此选项</span><span class="sxs-lookup"><span data-stu-id="00d1f-236">Use this</span></span>|<span data-ttu-id="00d1f-237">执行的操作</span><span class="sxs-lookup"><span data-stu-id="00d1f-237">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="00d1f-238">Identifier</span><span class="sxs-lookup"><span data-stu-id="00d1f-238">Identifier</span></span>|<span data-ttu-id="00d1f-239">类型`Response`</span><span class="sxs-lookup"><span data-stu-id="00d1f-239">Type `Response`</span></span>|  
    |<span data-ttu-id="00d1f-240">消息类型</span><span class="sxs-lookup"><span data-stu-id="00d1f-240">Message Type</span></span>|<span data-ttu-id="00d1f-241">从下拉列表中，展开**架构**，然后选择*Composite_Op.CompositeSchema.RequestResponse*。</span><span class="sxs-lookup"><span data-stu-id="00d1f-241">From the drop-down list, expand **Schemas**, and then select *Composite_Op.CompositeSchema.RequestResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="00d1f-242">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="00d1f-242">Setting up the Orchestration</span></span>  
 <span data-ttu-id="00d1f-243">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行对 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-243">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing composite operations on Oracle database.</span></span> <span data-ttu-id="00d1f-244">此业务流程，在你删除时的请求消息的定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="00d1f-244">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="00d1f-245">请求消息必须符合前面创建的复合架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-245">The request message must conform to the composite schema you created earlier.</span></span> <span data-ttu-id="00d1f-246">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此消息并将其传递到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="00d1f-246">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumes this message and passes it on to Oracle database.</span></span> <span data-ttu-id="00d1f-247">从 Oracle 数据库的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="00d1f-247">The response from Oracle database is saved to another location.</span></span> <span data-ttu-id="00d1f-248">你必须包括发送和接收形状来将消息发送到 Oracle 数据库和接收响应，分别。</span><span class="sxs-lookup"><span data-stu-id="00d1f-248">You must include Send and Receive shapes to send messages to Oracle database and receive responses, respectively.</span></span> <span data-ttu-id="00d1f-249">业务执行复合操作的基本流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="00d1f-249">A basic orchestration for performing composite operations resembles the following:</span></span>  
  
 <span data-ttu-id="00d1f-250">![执行复合操作的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span><span class="sxs-lookup"><span data-stu-id="00d1f-250">![Orchestration to peform composite operations](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="00d1f-251">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="00d1f-251">Adding Message Shapes</span></span>  
 <span data-ttu-id="00d1f-252">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="00d1f-252">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="00d1f-253">刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="00d1f-253">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="00d1f-254">形状</span><span class="sxs-lookup"><span data-stu-id="00d1f-254">Shape</span></span>|<span data-ttu-id="00d1f-255">形状类型</span><span class="sxs-lookup"><span data-stu-id="00d1f-255">Shape Type</span></span>|<span data-ttu-id="00d1f-256">属性</span><span class="sxs-lookup"><span data-stu-id="00d1f-256">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="00d1f-257">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="00d1f-257">ReceiveMessage</span></span>|<span data-ttu-id="00d1f-258">Receive</span><span class="sxs-lookup"><span data-stu-id="00d1f-258">Receive</span></span>|<span data-ttu-id="00d1f-259">-将设置**名称**到*ReceiveMessage*</span><span class="sxs-lookup"><span data-stu-id="00d1f-259">-   Set **Name** to *ReceiveMessage*</span></span><br /><span data-ttu-id="00d1f-260">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="00d1f-260">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="00d1f-261">发送消息</span><span class="sxs-lookup"><span data-stu-id="00d1f-261">SendMessage</span></span>|<span data-ttu-id="00d1f-262">Send</span><span class="sxs-lookup"><span data-stu-id="00d1f-262">Send</span></span>|<span data-ttu-id="00d1f-263">-将设置**名称**到*SendMessage*</span><span class="sxs-lookup"><span data-stu-id="00d1f-263">-   Set **Name** to *SendMessage*</span></span>|  
|<span data-ttu-id="00d1f-264">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="00d1f-264">ReceiveResponse</span></span>|<span data-ttu-id="00d1f-265">Receive</span><span class="sxs-lookup"><span data-stu-id="00d1f-265">Receive</span></span>|<span data-ttu-id="00d1f-266">-将设置**名称**到*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="00d1f-266">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="00d1f-267">-将设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="00d1f-267">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="00d1f-268">SendResponse</span><span class="sxs-lookup"><span data-stu-id="00d1f-268">SendResponse</span></span>|<span data-ttu-id="00d1f-269">Send</span><span class="sxs-lookup"><span data-stu-id="00d1f-269">Send</span></span>|<span data-ttu-id="00d1f-270">-将设置**名称**到*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="00d1f-270">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="00d1f-271">添加端口</span><span class="sxs-lookup"><span data-stu-id="00d1f-271">Adding Ports</span></span>  
 <span data-ttu-id="00d1f-272">请确保为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="00d1f-272">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="00d1f-273">端口列中列出的名称是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="00d1f-273">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="00d1f-274">端口</span><span class="sxs-lookup"><span data-stu-id="00d1f-274">Port</span></span>|<span data-ttu-id="00d1f-275">属性</span><span class="sxs-lookup"><span data-stu-id="00d1f-275">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="00d1f-276">MessageIn</span><span class="sxs-lookup"><span data-stu-id="00d1f-276">MessageIn</span></span>|<span data-ttu-id="00d1f-277">-将设置**标识符**到*MessageIn*</span><span class="sxs-lookup"><span data-stu-id="00d1f-277">-   Set **Identifier** to *MessageIn*</span></span><br /><span data-ttu-id="00d1f-278">-将设置**类型**到*MessageInType*</span><span class="sxs-lookup"><span data-stu-id="00d1f-278">-   Set **Type** to *MessageInType*</span></span><br /><span data-ttu-id="00d1f-279">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="00d1f-279">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="00d1f-280">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="00d1f-280">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="00d1f-281">LOBPort</span><span class="sxs-lookup"><span data-stu-id="00d1f-281">LOBPort</span></span>|<span data-ttu-id="00d1f-282">-将设置**标识符**到*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="00d1f-282">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="00d1f-283">-将设置**类型**到*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="00d1f-283">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="00d1f-284">-将设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="00d1f-284">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="00d1f-285">-将设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="00d1f-285">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="00d1f-286">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="00d1f-286">ResponseOut</span></span>|<span data-ttu-id="00d1f-287">-将设置**标识符**到*ResponseOut*</span><span class="sxs-lookup"><span data-stu-id="00d1f-287">-   Set **Identifier** to *ResponseOut*</span></span><br /><span data-ttu-id="00d1f-288">-将设置**类型**到*ResponseOutType*</span><span class="sxs-lookup"><span data-stu-id="00d1f-288">-   Set **Type** to *ResponseOutType*</span></span><br /><span data-ttu-id="00d1f-289">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="00d1f-289">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="00d1f-290">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="00d1f-290">-   Set **Communication Direction** to *Send*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a><span data-ttu-id="00d1f-291">对于操作形状，指定消息并将其连接到端口</span><span class="sxs-lookup"><span data-stu-id="00d1f-291">Specify Messages for Action Shapes, and Connect Them to Ports</span></span>  
 <span data-ttu-id="00d1f-292">下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。</span><span class="sxs-lookup"><span data-stu-id="00d1f-292">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="00d1f-293">前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="00d1f-293">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="00d1f-294">形状</span><span class="sxs-lookup"><span data-stu-id="00d1f-294">Shape</span></span>|<span data-ttu-id="00d1f-295">属性</span><span class="sxs-lookup"><span data-stu-id="00d1f-295">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="00d1f-296">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="00d1f-296">ReceiveMessage</span></span>|<span data-ttu-id="00d1f-297">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="00d1f-297">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="00d1f-298">-将设置**操作**到*MessageIn.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="00d1f-298">-   Set **Operation** to *MessageIn.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="00d1f-299">发送消息</span><span class="sxs-lookup"><span data-stu-id="00d1f-299">SendMessage</span></span>|<span data-ttu-id="00d1f-300">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="00d1f-300">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="00d1f-301">-将设置**操作**到*LOBPort.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="00d1f-301">-   Set **Operation** to *LOBPort.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="00d1f-302">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="00d1f-302">ReceiveResponse</span></span>|<span data-ttu-id="00d1f-303">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="00d1f-303">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="00d1f-304">-将设置**操作**到*LOBPort.CompositeOp.Response*</span><span class="sxs-lookup"><span data-stu-id="00d1f-304">-   Set **Operation** to *LOBPort.CompositeOp.Response*</span></span>|  
|<span data-ttu-id="00d1f-305">SendResponse</span><span class="sxs-lookup"><span data-stu-id="00d1f-305">SendResponse</span></span>|<span data-ttu-id="00d1f-306">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="00d1f-306">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="00d1f-307">-将设置**操作**到*ResponseOut.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="00d1f-307">-   Set **Operation** to *ResponseOut.CompositeOp.Request*</span></span>|  
  
 <span data-ttu-id="00d1f-308">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="00d1f-308">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="00d1f-309">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00d1f-309">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="00d1f-310">有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-310">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>  
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="00d1f-311">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="00d1f-311">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="00d1f-312">部署 BizTalk 项目后，将先前创建的业务流程下列出的业务流程窗格中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="00d1f-312">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the Orchestrations pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="00d1f-313">必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="00d1f-313">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="00d1f-314">有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-314">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="00d1f-315">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="00d1f-315">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="00d1f-316">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="00d1f-316">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="00d1f-317">映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="00d1f-317">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="00d1f-318">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="00d1f-318">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="00d1f-319">硬盘和放置请求消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="00d1f-319">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="00d1f-320">BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="00d1f-320">The BizTalk orchestration will consume the request message and send it to Oracle database.</span></span>  
  
    -   <span data-ttu-id="00d1f-321">硬盘和 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="00d1f-321">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from Oracle database.</span></span>  
  
    -   <span data-ttu-id="00d1f-322">定义物理 WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="00d1f-322">Define a physical WCF-Custom or WCF-OracleDB send port to send messages to Oracle database.</span></span> <span data-ttu-id="00d1f-323">因为操作都是由于复合操作的一部分执行在单个事务中，请确保**UseAmbientTransaction**绑定属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="00d1f-323">Because the operations that are being as part of the composite operation are executed in a single transaction, make sure the **UseAmbientTransaction** binding property is set to **True**.</span></span>  
  
         <span data-ttu-id="00d1f-324">你必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-324">You must also specify the action in the send port.</span></span> <span data-ttu-id="00d1f-325">复合操作的操作是"http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation"。</span><span class="sxs-lookup"><span data-stu-id="00d1f-325">The action for a composite operation is “http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”.</span></span> <span data-ttu-id="00d1f-326">有关如何创建端口的信息，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-326">For information about how to create ports, see [Manually configure a physical port binding to the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).</span></span> <span data-ttu-id="00d1f-327">有关如何指定端口的操作的详细信息，请参阅[配置 Oracle 数据库的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-327">For more information about how to specify actions for ports, see [Configure the SOAP action for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="00d1f-328">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。</span><span class="sxs-lookup"><span data-stu-id="00d1f-328">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file that contains information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="00d1f-329">你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。</span><span class="sxs-lookup"><span data-stu-id="00d1f-329">You can import this binding file from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="00d1f-330">有关详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-330">For more information, see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span> <span data-ttu-id="00d1f-331">如果你导入此绑定文件，将发送端口上的操作设置为涉及在中选择的所有操作的动态操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构时。</span><span class="sxs-lookup"><span data-stu-id="00d1f-331">If you import this binding file, the action on the send port is set to a dynamic action involving all the operations you selected in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] while generating the schema.</span></span> <span data-ttu-id="00d1f-332">对于复合操作，必须将"http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation"的动态操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-332">For a composite operation, you must replace the dynamic action with “http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation”.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="00d1f-333">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="00d1f-333">Starting the Application</span></span>  
 <span data-ttu-id="00d1f-334">你必须启动 BizTalk 应用程序用于执行对 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-334">You must start the BizTalk application for performing composite operations on Oracle database.</span></span> <span data-ttu-id="00d1f-335">有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-335">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="00d1f-336">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="00d1f-336">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="00d1f-337">FILE 接收端口，以便运行业务流程的是接收请求消息。</span><span class="sxs-lookup"><span data-stu-id="00d1f-337">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="00d1f-338">要从业务流程接收响应消息的文件发送端口正在运行。</span><span class="sxs-lookup"><span data-stu-id="00d1f-338">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="00d1f-339">WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库正在运行。</span><span class="sxs-lookup"><span data-stu-id="00d1f-339">The WCF-Custom or WCF-OracleDB send port to send messages to Oracle database is running.</span></span>  
  
-   <span data-ttu-id="00d1f-340">BizTalk 业务流程操作正在运行。</span><span class="sxs-lookup"><span data-stu-id="00d1f-340">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="00d1f-341">执行该操作</span><span class="sxs-lookup"><span data-stu-id="00d1f-341">Executing the Operation</span></span>  
 <span data-ttu-id="00d1f-342">运行应用程序后，必须放到该文件的请求消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="00d1f-342">After you run the application, you must drop a request message to the FILE receive location.</span></span> <span data-ttu-id="00d1f-343">请求消息的架构必须符合前面创建的复合操作的架构。</span><span class="sxs-lookup"><span data-stu-id="00d1f-343">The schema for the request message must conform to the schema for the composite operations you created earlier.</span></span> <span data-ttu-id="00d1f-344">例如，将记录插入 ACCOUNTACTIVITY 表中，调用 GET_ALL_ACTIVITY 存储过程中，并从 ACCOUNTACTIVITY 表中删除的记录的请求消息是：</span><span class="sxs-lookup"><span data-stu-id="00d1f-344">For example, a request message that inserts a record in the ACCOUNTACTIVITY table, invokes the GET_ALL_ACTIVITY stored procedure, and deletes a record from the ACCOUNTACTIVITY table is:</span></span>  
  
```  
<Request xmlns="http://Composite_Op.CompositeSchema">  
  <Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <RECORDSET>  
      <ACCOUNTACTIVITYRECORDINSERT>  
        <TID>1</TID>  
        <ACCOUNT>100001</ACCOUNT>  
        <AMOUNT>1500</AMOUNT>  
        <DESCRIPTION></DESCRIPTION>  
        <TRANSDATE>2008-06-21T15:52:19</TRANSDATE>  
        <PROCESSED>n</PROCESSED>  
      </ACCOUNTACTIVITYRECORDINSERT >  
    </RECORDSET>  
  </Insert>  
  <GET_ALL_ACTIVITY xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"/>  
  <Delete xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <FILTER>WHERE AMOUNT = 1500</FILTER>  
  </Delete>  
</Request>  
```  
  
 <span data-ttu-id="00d1f-345">前面的请求消息第一次插入一条记录，并调用 GET_ALL_ACTIVITY 过程，以获取 ACCOUNTACTIVITY 表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="00d1f-345">The preceding request message first inserts a record and then invokes the GET_ALL_ACTIVITY procedure to get all the records in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="00d1f-346">然后，通过指定筛选器子句删除插入的记录。</span><span class="sxs-lookup"><span data-stu-id="00d1f-346">Then, the inserted record is deleted by specifying a FILTER clause.</span></span> <span data-ttu-id="00d1f-347">请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)有关执行对 Oracle 的复合操作的请求消息架构的详细信息数据库使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00d1f-347">See [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md) for more information about the request message schema for performing composite operations on Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="00d1f-348">业务流程使用该消息，并将其发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="00d1f-348">The orchestration consumes the message and sends it to Oracle database.</span></span> <span data-ttu-id="00d1f-349">从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。</span><span class="sxs-lookup"><span data-stu-id="00d1f-349">The response from Oracle database is saved at the other FILE location defined as part of the orchestration.</span></span> <span data-ttu-id="00d1f-350">例如，从前面的请求消息的 Oracle 数据库响应如下所示：</span><span class="sxs-lookup"><span data-stu-id="00d1f-350">For example, the response from Oracle database for the preceding request message resembles the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://Composite_Op.CompositeSchema">  
  <InsertResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOOT/Table/ACCOUNTACTIVITY">  
    <InsertResult>1</InsertResult>   
  </InsertResponse>  
  <GET_ALL_ACTIVITYResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
    <ALLRECS>  
      <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
        <xs:element msdata:IsDataSet="true" name="NewDataSet">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="AMOUNT" type="xs:decimal" />   
                    <xs:element minOccurs="0" name="DESCRIPTION" type="xs:string" />   
                    <xs:element minOccurs="0" name="TRANSDATE" type="xs:dateTime" />   
                    <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                  </xs:sequence>  
                </xs:complexType>  
              </xs:element>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:schema>  
      <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
        <NewDataSet xmlns="">  
          <NewTable>  
            ......   
            ......   
          </NewTable>  
          ......  
          ......  
          <NewTable>  
            <TID>10</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <AMOUNT>1000</AMOUNT>   
            <TRANSDATE>2008-07-28T21:39:57</TRANSDATE>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
        </NewDataSet>  
      </diffgr:diffgram>  
    </ALLRECS>  
  </GET_ALL_ACTIVITYResponse>  
  <DeleteResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 <span data-ttu-id="00d1f-351">前面的响应中包含相应作为复合操作的一部分执行的不同操作的多个结果集。</span><span class="sxs-lookup"><span data-stu-id="00d1f-351">The preceding response contains multiple result sets corresponding the different operations performed as part of the composite operation.</span></span> <span data-ttu-id="00d1f-352">例如，`InsertResult`元素包含"1"，该值指示由插入操作插入的行数。</span><span class="sxs-lookup"><span data-stu-id="00d1f-352">For example, the `InsertResult` element contains ‘1’, indicating the number of rows inserted by the Insert operation.</span></span> <span data-ttu-id="00d1f-353">同样，`DeleteResult`元素包含"1"，以指示删除操作已删除的行数。</span><span class="sxs-lookup"><span data-stu-id="00d1f-353">Similarly, the `DeleteResult` element contains ‘1’, indicating the number of rows deleted by the Delete operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="00d1f-354">如果您在执行复合操作时遇到超时问题，则可能是因为连接数低于在复合操作涉及的操作的数目：</span><span class="sxs-lookup"><span data-stu-id="00d1f-354">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
>   
>  -   <span data-ttu-id="00d1f-355">缩小为包含 BFILE、 BLOB、 CLOB、 NCLOB、 和 REF CURSOR 的存储的过程或 IN OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="00d1f-355">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
> -   <span data-ttu-id="00d1f-356">选择操作。</span><span class="sxs-lookup"><span data-stu-id="00d1f-356">Select operation.</span></span>  
>   
>  <span data-ttu-id="00d1f-357">若要解决此问题，你必须确保，如果没有此类操作复合操作中的"n"数目，指定的值**MinPoolSize**绑定属性为"n + 1"或更高版本。</span><span class="sxs-lookup"><span data-stu-id="00d1f-357">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="00d1f-358">有关详细信息**MinPoolSize**绑定属性，请参阅[使用绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-358">For more information about the **MinPoolSize** binding property, see [Working with binding properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="00d1f-359">最佳实践</span><span class="sxs-lookup"><span data-stu-id="00d1f-359">Best Practices</span></span>  
 <span data-ttu-id="00d1f-360">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="00d1f-360">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="00d1f-361">后生成绑定文件，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。</span><span class="sxs-lookup"><span data-stu-id="00d1f-361">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create items such as send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="00d1f-362">有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="00d1f-362">For more information about binding files, see [Reuse Oracle Database adapter bindings](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d1f-363">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00d1f-363">See Also</span></span>  
[<span data-ttu-id="00d1f-364">开发与 Oracle 数据库的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="00d1f-364">Building Blocks to Develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)