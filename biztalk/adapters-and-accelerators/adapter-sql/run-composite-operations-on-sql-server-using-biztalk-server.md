---
title: 运行 SQL Server 使用 BizTalk Server 上的复合操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86fd2aa1-20c7-4b58-9f35-83ba0c959cf1
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62605fef85727311b2a2396463c2b43b690e86e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004326"
---
# <a name="run-composite-operations-on-sql-server-using-biztalk-server"></a><span data-ttu-id="d57f9-102">运行 SQL Server 使用 BizTalk Server 上的复合操作</span><span class="sxs-lookup"><span data-stu-id="d57f9-102">Run composite operations on SQL Server using BizTalk Server</span></span>
<span data-ttu-id="d57f9-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端能够执行复合操作上的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d57f9-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to perform composite operations on the SQL Server database.</span></span> <span data-ttu-id="d57f9-104">复合操作可能包括：</span><span class="sxs-lookup"><span data-stu-id="d57f9-104">A composite operation can include:</span></span>  
  
- <span data-ttu-id="d57f9-105">插入、 更新和删除操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-105">Insert, Update, and Delete operations.</span></span> <span data-ttu-id="d57f9-106">选择操作不支持复合操作的一部分。</span><span class="sxs-lookup"><span data-stu-id="d57f9-106">A Select operation is not supported as part of a composite operation.</span></span>  
  
- <span data-ttu-id="d57f9-107">作为操作执行的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="d57f9-107">Stored procedures executed as operations.</span></span>  
  
  <span data-ttu-id="d57f9-108">单个复合操作可能具有任意数量的这些操作，按任何顺序。</span><span class="sxs-lookup"><span data-stu-id="d57f9-108">A single composite operation can have any number of these operations, in any order.</span></span> <span data-ttu-id="d57f9-109">例如，您可以跟一个删除操作，以及存储的过程执行最后两个插入操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-109">For example, you can have two Insert operations followed by a Delete operation, and finally a stored procedure execution.</span></span> <span data-ttu-id="d57f9-110">此外，您可以以不同的数据库表或视图为目标的不同操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-110">Also, you can have different operations targeting different database tables or views.</span></span> <span data-ttu-id="d57f9-111">有关如何在适配器支持复合操作的详细信息，请参阅[在使用 SQL 适配器的 SQL Server 中运行复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-111">For more information about how the adapter supports composite operations, see [Run composite operations in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).</span></span> <span data-ttu-id="d57f9-112">复合操作的 SOAP 消息结构的信息，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-112">For information about the structure of the SOAP message for composite operations, see [Message Schemas for Composite Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d57f9-113">如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图使用 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。</span><span class="sxs-lookup"><span data-stu-id="d57f9-113">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="how-to-perform-composite-operations-on-sql-server"></a><span data-ttu-id="d57f9-114">如何执行 SQL Server 上的复合操作</span><span class="sxs-lookup"><span data-stu-id="d57f9-114">How to Perform Composite Operations on SQL Server</span></span>  
 <span data-ttu-id="d57f9-115">使用 SQL Server 上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-115">Performing an operation on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md).</span></span> <span data-ttu-id="d57f9-116">若要执行复合操作上的 SQL Server 数据库，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="d57f9-116">To perform composite operations on the SQL Server database, these tasks are:</span></span>  
  
1. <span data-ttu-id="d57f9-117">创建 BizTalk 项目，并为你想要调用的所有操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-117">Create a BizTalk project, and generate schema for all the operations you want to invoke.</span></span>  
  
2. <span data-ttu-id="d57f9-118">手动创建一个包含对你在上一步中生成的所有架构的引用的架构文件。</span><span class="sxs-lookup"><span data-stu-id="d57f9-118">Manually create a schema file that includes references to all the schemas you generated in the previous step.</span></span>  
  
3. <span data-ttu-id="d57f9-119">在发送和接收消息，从 SQL Server 数据库的 BizTalk 项目中创建的消息。</span><span class="sxs-lookup"><span data-stu-id="d57f9-119">Create messages in the BizTalk project for sending and receiving messages from the SQL Server database.</span></span> <span data-ttu-id="d57f9-120">这些消息必须符合在上一步中创建的请求和响应架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-120">These messages must conform to the request and response schema you created in the previous step.</span></span>  
  
4. <span data-ttu-id="d57f9-121">创建一个业务流程调用上的 SQL Server 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-121">Create an orchestration to invoke the composite operation on the SQL Server database.</span></span>  
  
5. <span data-ttu-id="d57f9-122">生成并部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d57f9-122">Build and deploy the BizTalk project.</span></span>  
  
6. <span data-ttu-id="d57f9-123">配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d57f9-123">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
7. <span data-ttu-id="d57f9-124">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d57f9-124">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="d57f9-125">本主题提供有关如何执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="d57f9-125">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="d57f9-126">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="d57f9-126">Sample Based on This Topic</span></span>  
 <span data-ttu-id="d57f9-127">使用提供的示例中，CompositeOperations，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d57f9-127">A sample, CompositeOperations, based on this topic is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d57f9-128">有关详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-128">For more information, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="d57f9-129">生成架构</span><span class="sxs-lookup"><span data-stu-id="d57f9-129">Generating Schema</span></span>  
 <span data-ttu-id="d57f9-130">在本主题中，若要演示如何执行复合操作，执行以下任务将指定的顺序：</span><span class="sxs-lookup"><span data-stu-id="d57f9-130">In this topic, to demonstrate how to perform composite operations, the following tasks will be performed in the order specified:</span></span>  
  
- <span data-ttu-id="d57f9-131">EMPLOYEE 表中插入记录。</span><span class="sxs-lookup"><span data-stu-id="d57f9-131">Insert record into the EMPLOYEE table.</span></span>  
  
- <span data-ttu-id="d57f9-132">通过调用 GET_LAST_EMP_DATA 存储过程检索最后一个插入记录的所有列。</span><span class="sxs-lookup"><span data-stu-id="d57f9-132">Retrieve all the columns for the last inserted record by invoking the GET_LAST_EMP_DATA stored procedure.</span></span>  
  
- <span data-ttu-id="d57f9-133">从 EMPLOYEE 表中删除的记录。</span><span class="sxs-lookup"><span data-stu-id="d57f9-133">Delete the record from the EMPLOYEE table.</span></span>  
  
  <span data-ttu-id="d57f9-134">运行提供的示例创建员工表的脚本。</span><span class="sxs-lookup"><span data-stu-id="d57f9-134">Run the scripts provided with the samples to create the EMPLOYEE table.</span></span> <span data-ttu-id="d57f9-135">有关示例的详细信息，请参阅[架构示例](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-135">For more information about the samples, see [Schema Samples](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md).</span></span>  
  
  <span data-ttu-id="d57f9-136">必须创建一个 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成这些操作的架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-136">You must create a BizTalk project and use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema for these operations.</span></span> <span data-ttu-id="d57f9-137">请参阅[检索用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d57f9-137">See [Retrieving Metadata for SQL Server Operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) for more information about how to generate schemas.</span></span>  
  
## <a name="creating-a-composite-schema-definition"></a><span data-ttu-id="d57f9-138">创建复合架构定义</span><span class="sxs-lookup"><span data-stu-id="d57f9-138">Creating a Composite Schema Definition</span></span>  
 <span data-ttu-id="d57f9-139">现在必须创建一个复合架构引用为单个操作创建的架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-139">You must now create a composite schema that references the schemas you created for the individual operations.</span></span> <span data-ttu-id="d57f9-140">执行以下步骤来创建复合架构定义。</span><span class="sxs-lookup"><span data-stu-id="d57f9-140">Perform the following steps to create a composite schema definition.</span></span>  
  
#### <a name="to-add-a-composite-schema-definition"></a><span data-ttu-id="d57f9-141">若要添加的复合架构定义</span><span class="sxs-lookup"><span data-stu-id="d57f9-141">To add a composite schema definition</span></span>  
  
1. <span data-ttu-id="d57f9-142">将架构文件添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d57f9-142">Add a schema file to the BizTalk project.</span></span> <span data-ttu-id="d57f9-143">右键单击项目名称，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-143">Right-click the project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="d57f9-144">在中**添加新项**对话框中，从**类别**框中，单击**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-144">In the **Add New Item** dialog box, from the **Categories** box, click **Schema Files**.</span></span> <span data-ttu-id="d57f9-145">从**模板**框中，单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-145">From the **Templates** box, click **Schema**.</span></span> <span data-ttu-id="d57f9-146">指定的架构文件的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-146">Specify a name for the schema file, and then click **OK**.</span></span>  
  
    <span data-ttu-id="d57f9-147">对于此示例中，指定的架构文件名称作为`CompositeSchema.xsd`。</span><span class="sxs-lookup"><span data-stu-id="d57f9-147">For this example, specify the schema file name as `CompositeSchema.xsd`.</span></span>  
  
2. <span data-ttu-id="d57f9-148">添加对生成适用于你想要执行的不同操作的架构的引用。</span><span class="sxs-lookup"><span data-stu-id="d57f9-148">Add references to the schema generated for the different operations that you want to perform.</span></span> <span data-ttu-id="d57f9-149">在此示例中，为操作生成的不同架构是：</span><span class="sxs-lookup"><span data-stu-id="d57f9-149">In this example, the different schemas generated for operations are:</span></span>  
  
   - <span data-ttu-id="d57f9-150">TableOperation.dbo.Employee.xsd，对于 Insert 和 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-150">TableOperation.dbo.Employee.xsd, for Insert and Delete operations.</span></span>  
  
   - <span data-ttu-id="d57f9-151">有关 GET_LAST_EMP_DATA Procedure.dbo.xsd，存储过程。</span><span class="sxs-lookup"><span data-stu-id="d57f9-151">Procedure.dbo.xsd, for the GET_LAST_EMP_DATA stored procedure.</span></span>  
  
     <span data-ttu-id="d57f9-152">若要添加的引用：</span><span class="sxs-lookup"><span data-stu-id="d57f9-152">To add references:</span></span>  
  
   1.  <span data-ttu-id="d57f9-153">右键单击根**\<架构\>** 节点，CompositeSchema.xsd，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-153">Right-click the root **\<Schema\>** node in the CompositeSchema.xsd, and click **Properties**.</span></span>  
  
   2.  <span data-ttu-id="d57f9-154">在中**属性**框中，单击省略号按钮 **（...）** 针对**导入**属性。</span><span class="sxs-lookup"><span data-stu-id="d57f9-154">In the **Property** box, click the ellipsis button **(…)** against the **Imports** property.</span></span>  
  
        <span data-ttu-id="d57f9-155">![导入架构定义](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span><span class="sxs-lookup"><span data-stu-id="d57f9-155">![Import schema definitions](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span></span>  
  
   3.  <span data-ttu-id="d57f9-156">在中**导入**对话框中，从**作为导入新架构**列表中，选择**XSD 导入**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-156">In the **Imports** dialog box, from the **Import new schema as** list, select **XSD Import**, and then click **Add**.</span></span>  
  
   4.  <span data-ttu-id="d57f9-157">在中**BizTalk 类型选取器**对话框框中，展开 BizTalk 项目名称节点，展开**架构**，然后选择你想要导入的架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-157">In the **BizTalk Type Picker** dialog box, expand the BizTalk project name node, expand **Schemas**, and then select the schema you want to import.</span></span> <span data-ttu-id="d57f9-158">对于此示例中，选择 < BizTalk_project_name >。TableOperation_dbo_Employee。</span><span class="sxs-lookup"><span data-stu-id="d57f9-158">For this example, select <BizTalk_project_name>.TableOperation_dbo_Employee.</span></span> <span data-ttu-id="d57f9-159">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d57f9-159">Click **OK**.</span></span>  
  
        <span data-ttu-id="d57f9-160">重复此步骤以导入 < BizTalk_project_name >。Procedure_dbo 过。</span><span class="sxs-lookup"><span data-stu-id="d57f9-160">Repeat this step to import <BizTalk_project_name>.Procedure_dbo too.</span></span>  
  
   5.  <span data-ttu-id="d57f9-161">在中**导入**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-161">In the **Imports** dialog box, click **OK**.</span></span>  
  
3. <span data-ttu-id="d57f9-162">将两个子节点添加到的根架构节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-162">Add two child nodes to the root schema node.</span></span> <span data-ttu-id="d57f9-163">一个子节点对应于执行复合操作的请求架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-163">One child node corresponds to the request schema for performing the composite operation.</span></span> <span data-ttu-id="d57f9-164">另一个子节点对应的响应架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-164">The other child node corresponds to the response schema.</span></span> <span data-ttu-id="d57f9-165">对应于请求架构的节点可以具有任何名称。</span><span class="sxs-lookup"><span data-stu-id="d57f9-165">The node that corresponds to the request schema can have any name.</span></span> <span data-ttu-id="d57f9-166">< Request_schema_node > 响应，必须调用到响应架构相对应的节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-166">The node that corresponds to the response schema must be called <request_schema_node>Response.</span></span> <span data-ttu-id="d57f9-167">对于此示例中，我们将调用请求架构节点作为**请求**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-167">For this example, we will call the request schema node as **Request**.</span></span> <span data-ttu-id="d57f9-168">因此，响应架构节点称为**RequestResponse**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-168">So, the response schema node is called **RequestResponse**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d57f9-169">默认情况下**根**节点也会添加到新的架构文件。</span><span class="sxs-lookup"><span data-stu-id="d57f9-169">By default, a **Root** node is also added to a new schema file.</span></span> <span data-ttu-id="d57f9-170">您可以重命名**根**节点到节点**请求**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-170">You can rename the **Root** node to **Request**.</span></span> <span data-ttu-id="d57f9-171">若要重命名节点，右键单击节点名称，然后单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-171">To rename a node, right-click the node name and click **Rename**.</span></span>  
  
    <span data-ttu-id="d57f9-172">若要添加的节点下**\<架构\>** 节点：</span><span class="sxs-lookup"><span data-stu-id="d57f9-172">To add a node under the **\<Schema\>** node:</span></span>  
  
   1.  <span data-ttu-id="d57f9-173">右键单击**\<架构\>** 节点，指向**插入 Schema 节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-173">Right-click the **\<Schema\>** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
   2.  <span data-ttu-id="d57f9-174">重命名的新节点**RequestResponse**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-174">Rename the new node to **RequestResponse**.</span></span>  
  
4. <span data-ttu-id="d57f9-175">添加下的子节点**请求**对应于将执行复合操作的一部分的每个操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-175">Add child nodes under the **Request** node that correspond to the request schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="d57f9-176">对于此示例中，必须添加对应于以下的子节点：</span><span class="sxs-lookup"><span data-stu-id="d57f9-176">For this example, you must add child nodes corresponding to the following:</span></span>  
  
   -   <span data-ttu-id="d57f9-177">插入和删除 EMPLOYEE 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-177">Insert and Delete operations on the EMPLOYEE table.</span></span>  
  
   -   <span data-ttu-id="d57f9-178">GET_LAST_EMP_DATA 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d57f9-178">GET_LAST_EMP_DATA stored procedure.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="d57f9-179">必须在想要执行的操作的顺序来添加节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-179">You must add the nodes in the same order in which you want to perform the operations.</span></span> <span data-ttu-id="d57f9-180">例如，如果你想要插入的记录，然后执行存储的过程，然后删除必须首先添加的节点插入操作的记录后, 接存储过程，一个节点，最后删除操作的节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-180">For example, if you want to insert a record, then execute a stored procedure, and then delete a record you must first add a node for the Insert operation, followed by a node for the stored procedure, and finally a node for the Delete operation.</span></span>  
  
    <span data-ttu-id="d57f9-181">若要添加到的子节点**请求**节点：</span><span class="sxs-lookup"><span data-stu-id="d57f9-181">To add child nodes to the **Request** node:</span></span>  
  
   1.  <span data-ttu-id="d57f9-182">右键单击**请求**节点，指向**插入 Schema 节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-182">Right-click the **Request** node, point to **Insert Schema Node**, and then click  **Child Record**.</span></span>  
  
        <span data-ttu-id="d57f9-183">![插入架构的子节点](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span><span class="sxs-lookup"><span data-stu-id="d57f9-183">![Insert child nodes for a schema](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span></span>  
  
   2.  <span data-ttu-id="d57f9-184">重命名要与复合操作的一部分执行的操作请求架构相对应的记录。</span><span class="sxs-lookup"><span data-stu-id="d57f9-184">Rename the record to correspond to a request schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="d57f9-185">例如，重命名为"Insert"节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-185">For example, rename the node to “Insert”.</span></span>  
  
   3.  <span data-ttu-id="d57f9-186">地图**插入**为 EMPLOYEE 表上的插入操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-186">Map the **Insert** node to the request schema for the Insert operation on the EMPLOYEE table.</span></span> <span data-ttu-id="d57f9-187">为此，请右键单击**插入**节点，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-187">To do so, right-click the **Insert** node, and click **Properties**.</span></span> <span data-ttu-id="d57f9-188">在中**属性**框中，从**Data Structure Type**列表中，选择**插入 （参考）**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-188">In the **Properties** box, from the **Data Structure Type** list, select **Insert (Reference)**.</span></span>  
  
        <span data-ttu-id="d57f9-189">![将子节点映射到请求架构](../../adapters-and-accelerators/adapter-sql/media/5ace18be-0fe8-44c6-bd2f-cb19035494b5.gif "5ace18be-0fe8-44c6-bd2f-cb19035494b5")</span><span class="sxs-lookup"><span data-stu-id="d57f9-189">![Map child nodes to the request schema](../../adapters-and-accelerators/adapter-sql/media/5ace18be-0fe8-44c6-bd2f-cb19035494b5.gif "5ace18be-0fe8-44c6-bd2f-cb19035494b5")</span></span>  
  
   4.  <span data-ttu-id="d57f9-190">重复这些步骤以添加 GET_LAST_EMP_DATA 存储过程和删除操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-190">Repeat these steps to add nodes for the request schemas for GET_LAST_EMP_DATA stored procedure and the Delete operation.</span></span> <span data-ttu-id="d57f9-191">指定节点名称，并将它们映射到相应的架构，如下表中所述。</span><span class="sxs-lookup"><span data-stu-id="d57f9-191">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
       |<span data-ttu-id="d57f9-192">节点名称</span><span class="sxs-lookup"><span data-stu-id="d57f9-192">Node name</span></span>|<span data-ttu-id="d57f9-193">映射到架构</span><span class="sxs-lookup"><span data-stu-id="d57f9-193">Mapped to schema</span></span>|  
       |---------------|----------------------|  
       |<span data-ttu-id="d57f9-194">GET_LAST_EMP_DATA</span><span class="sxs-lookup"><span data-stu-id="d57f9-194">GET_LAST_EMP_DATA</span></span>|<span data-ttu-id="d57f9-195">GET_LAST_EMP_DATA （参考）</span><span class="sxs-lookup"><span data-stu-id="d57f9-195">GET_LAST_EMP_DATA (Reference)</span></span>|  
       |<span data-ttu-id="d57f9-196">DELETE</span><span class="sxs-lookup"><span data-stu-id="d57f9-196">Delete</span></span>|<span data-ttu-id="d57f9-197">删除 （参考）</span><span class="sxs-lookup"><span data-stu-id="d57f9-197">Delete (Reference)</span></span>|  
  
5. <span data-ttu-id="d57f9-198">添加下的子节点**RequestResponse**对应于将执行复合操作的一部分的每个操作的响应架构的节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-198">Add child nodes under the **RequestResponse** node that correspond to the response schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="d57f9-199">对于此示例中，必须添加对应于以下的子节点：</span><span class="sxs-lookup"><span data-stu-id="d57f9-199">For this example, you must add child nodes corresponding to the following:</span></span>  
  
   -   <span data-ttu-id="d57f9-200">插入和删除 EMPLOYEE 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-200">Insert and Delete operations on the EMPLOYEE table.</span></span>  
  
   -   <span data-ttu-id="d57f9-201">GET_LAST_EMP_DATA 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d57f9-201">GET_LAST_EMP_DATA stored procedure.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="d57f9-202">必须添加子节点下的子节点的顺序相同**请求**节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-202">You must add the child nodes in the same order as the child nodes under the **Request** node.</span></span>  
  
    <span data-ttu-id="d57f9-203">若要添加到的子节点**RequestResponse**节点：</span><span class="sxs-lookup"><span data-stu-id="d57f9-203">To add child nodes to the **RequestResponse** node:</span></span>  
  
   1.  <span data-ttu-id="d57f9-204">右键单击**RequestResponse**节点，指向**插入 Schema 节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-204">Right-click the **RequestResponse** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
   2.  <span data-ttu-id="d57f9-205">重命名要与复合操作的一部分执行的操作的响应架构相对应的记录。</span><span class="sxs-lookup"><span data-stu-id="d57f9-205">Rename the record to correspond to a response schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="d57f9-206">例如，重命名为"InsertResponse"节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-206">For example, rename the node to “InsertResponse”.</span></span>  
  
   3.  <span data-ttu-id="d57f9-207">地图**InsertResponse**为 EMPLOYEE 表上的插入操作的响应架构的节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-207">Map the **InsertResponse** node to the response schema for the Insert operation on the EMPLOYEE table.</span></span> <span data-ttu-id="d57f9-208">为此，请右键单击**InsertResponse**节点，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-208">To do so, right-click the **InsertResponse** node, and click **Properties**.</span></span> <span data-ttu-id="d57f9-209">在中**属性**框中，从**Data Structure Type**列表中，选择**InsertResponse （参考）**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-209">In the **Properties** box, from the **Data Structure Type** list, select **InsertResponse (Reference)**.</span></span>  
  
   4.  <span data-ttu-id="d57f9-210">重复这些步骤以添加 GET_LAST_EMP_DATA 存储过程和删除操作的响应架构的节点。</span><span class="sxs-lookup"><span data-stu-id="d57f9-210">Repeat these steps to add nodes for the response schemas for the GET_LAST_EMP_DATA stored procedure and the Delete operation.</span></span> <span data-ttu-id="d57f9-211">指定节点名称，并将它们映射到相应的架构，如下表中所述。</span><span class="sxs-lookup"><span data-stu-id="d57f9-211">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
       |<span data-ttu-id="d57f9-212">节点名称</span><span class="sxs-lookup"><span data-stu-id="d57f9-212">Node name</span></span>|<span data-ttu-id="d57f9-213">映射到架构</span><span class="sxs-lookup"><span data-stu-id="d57f9-213">Mapped to schema</span></span>|  
       |---------------|----------------------|  
       |<span data-ttu-id="d57f9-214">GET_LAST_EMP_DATAResponse</span><span class="sxs-lookup"><span data-stu-id="d57f9-214">GET_LAST_EMP_DATAResponse</span></span>|<span data-ttu-id="d57f9-215">GET_LAST_EMP_DATAResponse （参考）</span><span class="sxs-lookup"><span data-stu-id="d57f9-215">GET_LAST_EMP_DATAResponse (Reference)</span></span>|  
       |<span data-ttu-id="d57f9-216">DeleteResponse</span><span class="sxs-lookup"><span data-stu-id="d57f9-216">DeleteResponse</span></span>|<span data-ttu-id="d57f9-217">DeleteResponse （参考）</span><span class="sxs-lookup"><span data-stu-id="d57f9-217">DeleteResponse (Reference)</span></span>|  
  
6. <span data-ttu-id="d57f9-218">保存**CompositeSchema.xsd**文件。</span><span class="sxs-lookup"><span data-stu-id="d57f9-218">Save the **CompositeSchema.xsd** file.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="d57f9-219">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="d57f9-219">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="d57f9-220">在最后一步中创建复合架构描述了在业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="d57f9-220">The composite schema that you created in the last step describes the “types” required for the messages in an orchestration.</span></span> <span data-ttu-id="d57f9-221">一条消息通常是一个变量，要为其类型定义由相应的架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-221">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="d57f9-222">现在必须为该业务流程创建消息并将其链接到上一步中创建的架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-222">You must now create messages for the orchestration and link them to schema you created in the previous step.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="d57f9-223">若要创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="d57f9-223">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="d57f9-224">向 BizTalk 项目添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="d57f9-224">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="d57f9-225">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-225">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="d57f9-226">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-226">Type a name for the BizTalk orchestration, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="d57f9-227">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="d57f9-227">Open the Orchestration View window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="d57f9-228">若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-228">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="d57f9-229">在业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-229">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="d57f9-230">右键单击新创建的消息，然后依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-230">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="d57f9-231">在中**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d57f9-231">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="d57f9-232">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d57f9-232">Use this</span></span>|<span data-ttu-id="d57f9-233">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d57f9-233">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d57f9-234">Identifier</span><span class="sxs-lookup"><span data-stu-id="d57f9-234">Identifier</span></span>|<span data-ttu-id="d57f9-235">类型 `Request`</span><span class="sxs-lookup"><span data-stu-id="d57f9-235">Type `Request`</span></span>|  
    |<span data-ttu-id="d57f9-236">消息类型</span><span class="sxs-lookup"><span data-stu-id="d57f9-236">Message Type</span></span>|<span data-ttu-id="d57f9-237">从下拉列表中，展开**架构**，然后选择*CompositeOp.CompositeSchema.Request*，其中 CompositeOp 是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="d57f9-237">From the drop-down list, expand **Schemas**, and then select *CompositeOp.CompositeSchema.Request*, where CompositeOp is the name of your BizTalk project.</span></span> <span data-ttu-id="d57f9-238">CompositeSchema 是手动创建的复合操作的架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-238">CompositeSchema is the schema you created manually for the composite operations.</span></span>|  
  
6.  <span data-ttu-id="d57f9-239">重复步骤 2，以创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="d57f9-239">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="d57f9-240">在中**属性**窗格中的新消息，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d57f9-240">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="d57f9-241">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d57f9-241">Use this</span></span>|<span data-ttu-id="d57f9-242">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d57f9-242">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d57f9-243">Identifier</span><span class="sxs-lookup"><span data-stu-id="d57f9-243">Identifier</span></span>|<span data-ttu-id="d57f9-244">类型 `Response`</span><span class="sxs-lookup"><span data-stu-id="d57f9-244">Type `Response`</span></span>|  
    |<span data-ttu-id="d57f9-245">消息类型</span><span class="sxs-lookup"><span data-stu-id="d57f9-245">Message Type</span></span>|<span data-ttu-id="d57f9-246">从下拉列表中，展开**架构**，然后选择*CompositeOp.CompositeSchema.RequestResponse*。</span><span class="sxs-lookup"><span data-stu-id="d57f9-246">From the drop-down list, expand **Schemas**, and then select *CompositeOp.CompositeSchema.RequestResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="d57f9-247">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="d57f9-247">Setting up the Orchestration</span></span>  
 <span data-ttu-id="d57f9-248">必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于执行 SQL Server 上的复合操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-248">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing composite operations on SQL Server.</span></span> <span data-ttu-id="d57f9-249">在将请求消息放在此业务流程，定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="d57f9-249">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="d57f9-250">请求消息必须符合前面创建的复合架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-250">The request message must conform to the composite schema you created earlier.</span></span> <span data-ttu-id="d57f9-251">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此消息并将其传递到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d57f9-251">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] consumes this message and passes it on to SQL Server.</span></span> <span data-ttu-id="d57f9-252">从 SQL Server 的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="d57f9-252">The response from SQL Server is saved to another location.</span></span> <span data-ttu-id="d57f9-253">必须包括发送和接收形状将消息发送到 SQL Server 和接收响应，分别。</span><span class="sxs-lookup"><span data-stu-id="d57f9-253">You must include Send and Receive shapes to send messages to SQL Server and receive responses, respectively.</span></span> <span data-ttu-id="d57f9-254">用于执行复合操作的基本业务流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="d57f9-254">A basic orchestration for performing composite operations resembles the following:</span></span>  
  
 <span data-ttu-id="d57f9-255">![用于执行复合操作的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span><span class="sxs-lookup"><span data-stu-id="d57f9-255">![Orchestration to peform composite operations](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="d57f9-256">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="d57f9-256">Adding Message Shapes</span></span>  
 <span data-ttu-id="d57f9-257">请确保为每个消息形状中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="d57f9-257">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="d57f9-258">形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="d57f9-258">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="d57f9-259">形状</span><span class="sxs-lookup"><span data-stu-id="d57f9-259">Shape</span></span>|<span data-ttu-id="d57f9-260">形状类型</span><span class="sxs-lookup"><span data-stu-id="d57f9-260">Shape Type</span></span>|<span data-ttu-id="d57f9-261">属性</span><span class="sxs-lookup"><span data-stu-id="d57f9-261">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="d57f9-262">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="d57f9-262">ReceiveMessage</span></span>|<span data-ttu-id="d57f9-263">Receive</span><span class="sxs-lookup"><span data-stu-id="d57f9-263">Receive</span></span>|<span data-ttu-id="d57f9-264">-设置**名称**到*ReceiveMessage*</span><span class="sxs-lookup"><span data-stu-id="d57f9-264">-   Set **Name** to *ReceiveMessage*</span></span><br /><span data-ttu-id="d57f9-265">-设置**激活**到 *，则返回 True*</span><span class="sxs-lookup"><span data-stu-id="d57f9-265">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="d57f9-266">SendMessage</span><span class="sxs-lookup"><span data-stu-id="d57f9-266">SendMessage</span></span>|<span data-ttu-id="d57f9-267">Send</span><span class="sxs-lookup"><span data-stu-id="d57f9-267">Send</span></span>|<span data-ttu-id="d57f9-268">-设置**名称**到*SendMessage*</span><span class="sxs-lookup"><span data-stu-id="d57f9-268">-   Set **Name** to *SendMessage*</span></span>|  
|<span data-ttu-id="d57f9-269">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="d57f9-269">ReceiveResponse</span></span>|<span data-ttu-id="d57f9-270">Receive</span><span class="sxs-lookup"><span data-stu-id="d57f9-270">Receive</span></span>|<span data-ttu-id="d57f9-271">-设置**名称**到*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="d57f9-271">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="d57f9-272">-设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="d57f9-272">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="d57f9-273">SendResponse</span><span class="sxs-lookup"><span data-stu-id="d57f9-273">SendResponse</span></span>|<span data-ttu-id="d57f9-274">Send</span><span class="sxs-lookup"><span data-stu-id="d57f9-274">Send</span></span>|<span data-ttu-id="d57f9-275">-设置**名称**到*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="d57f9-275">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="d57f9-276">添加端口</span><span class="sxs-lookup"><span data-stu-id="d57f9-276">Adding Ports</span></span>  
 <span data-ttu-id="d57f9-277">请确保为每个逻辑端口中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="d57f9-277">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="d57f9-278">端口列中列出的名称是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="d57f9-278">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="d57f9-279">端口</span><span class="sxs-lookup"><span data-stu-id="d57f9-279">Port</span></span>|<span data-ttu-id="d57f9-280">属性</span><span class="sxs-lookup"><span data-stu-id="d57f9-280">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="d57f9-281">MessageIn</span><span class="sxs-lookup"><span data-stu-id="d57f9-281">MessageIn</span></span>|<span data-ttu-id="d57f9-282">-设置**标识符**到*MessageIn*</span><span class="sxs-lookup"><span data-stu-id="d57f9-282">-   Set **Identifier** to *MessageIn*</span></span><br /><span data-ttu-id="d57f9-283">-设置**类型**到*MessageInType*</span><span class="sxs-lookup"><span data-stu-id="d57f9-283">-   Set **Type** to *MessageInType*</span></span><br /><span data-ttu-id="d57f9-284">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="d57f9-284">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="d57f9-285">-设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="d57f9-285">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="d57f9-286">LOBPort</span><span class="sxs-lookup"><span data-stu-id="d57f9-286">LOBPort</span></span>|<span data-ttu-id="d57f9-287">-设置**标识符**到*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="d57f9-287">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="d57f9-288">-设置**类型**到*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="d57f9-288">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="d57f9-289">-设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="d57f9-289">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="d57f9-290">-设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="d57f9-290">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="d57f9-291">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="d57f9-291">ResponseOut</span></span>|<span data-ttu-id="d57f9-292">-设置**标识符**到*ResponseOut*</span><span class="sxs-lookup"><span data-stu-id="d57f9-292">-   Set **Identifier** to *ResponseOut*</span></span><br /><span data-ttu-id="d57f9-293">-设置**类型**到*ResponseOutType*</span><span class="sxs-lookup"><span data-stu-id="d57f9-293">-   Set **Type** to *ResponseOutType*</span></span><br /><span data-ttu-id="d57f9-294">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="d57f9-294">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="d57f9-295">-设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="d57f9-295">-   Set **Communication Direction** to *Send*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a><span data-ttu-id="d57f9-296">为操作形状指定消息并将它们连接到端口</span><span class="sxs-lookup"><span data-stu-id="d57f9-296">Specify Messages for Action Shapes, and Connect Them to Ports</span></span>  
 <span data-ttu-id="d57f9-297">下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。</span><span class="sxs-lookup"><span data-stu-id="d57f9-297">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="d57f9-298">形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="d57f9-298">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="d57f9-299">形状</span><span class="sxs-lookup"><span data-stu-id="d57f9-299">Shape</span></span>|<span data-ttu-id="d57f9-300">属性</span><span class="sxs-lookup"><span data-stu-id="d57f9-300">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="d57f9-301">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="d57f9-301">ReceiveMessage</span></span>|<span data-ttu-id="d57f9-302">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="d57f9-302">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="d57f9-303">-设置**操作**到*MessageIn.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="d57f9-303">-   Set **Operation** to *MessageIn.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="d57f9-304">SendMessage</span><span class="sxs-lookup"><span data-stu-id="d57f9-304">SendMessage</span></span>|<span data-ttu-id="d57f9-305">-设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="d57f9-305">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="d57f9-306">-设置**操作**到*LOBPort.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="d57f9-306">-   Set **Operation** to *LOBPort.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="d57f9-307">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="d57f9-307">ReceiveResponse</span></span>|<span data-ttu-id="d57f9-308">-设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="d57f9-308">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="d57f9-309">-设置**操作**到*LOBPort.CompositeOp.Response*</span><span class="sxs-lookup"><span data-stu-id="d57f9-309">-   Set **Operation** to *LOBPort.CompositeOp.Response*</span></span>|  
|<span data-ttu-id="d57f9-310">SendResponse</span><span class="sxs-lookup"><span data-stu-id="d57f9-310">SendResponse</span></span>|<span data-ttu-id="d57f9-311">-设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="d57f9-311">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="d57f9-312">-设置**操作**到*ResponseOut.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="d57f9-312">-   Set **Operation** to *ResponseOut.CompositeOp.Request*</span></span>|  
  
 <span data-ttu-id="d57f9-313">指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="d57f9-313">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="d57f9-314">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d57f9-314">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d57f9-315">有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-315">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="d57f9-316">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d57f9-316">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="d57f9-317">部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d57f9-317">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the Orchestrations pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d57f9-318">必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="d57f9-318">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="d57f9-319">有关演练，请参阅[演练： 部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-319">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="d57f9-320">配置应用程序包括：</span><span class="sxs-lookup"><span data-stu-id="d57f9-320">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="d57f9-321">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="d57f9-321">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="d57f9-322">映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d57f9-322">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d57f9-323">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="d57f9-323">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="d57f9-324">硬盘和相应 file 端口将放置请求消息的位置上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="d57f9-324">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="d57f9-325">BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d57f9-325">The BizTalk orchestration will consume the request message and send it to the SQL Server database.</span></span>  
  
  - <span data-ttu-id="d57f9-326">硬盘和相应的 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="d57f9-326">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the SQL Server database.</span></span>  
  
  - <span data-ttu-id="d57f9-327">定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d57f9-327">Define a physical WCF-Custom or WCF-SQL send port to send messages to the SQL Server database.</span></span> <span data-ttu-id="d57f9-328">因为操作是与复合操作的一部分执行在单个事务中，请确保**UseAmbientTransaction**绑定属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="d57f9-328">Because the operations that are being as part of the composite operation are executed in a single transaction, make sure the **UseAmbientTransaction** binding property is set to **True**.</span></span>  
  
     <span data-ttu-id="d57f9-329">您必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-329">You must also specify the action in the send port.</span></span> <span data-ttu-id="d57f9-330">复合操作的操作是"**CompositeOperation**"。</span><span class="sxs-lookup"><span data-stu-id="d57f9-330">The action for a composite operation is “**CompositeOperation**”.</span></span> <span data-ttu-id="d57f9-331">有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-331">For information about how to create ports, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span> <span data-ttu-id="d57f9-332">有关如何指定端口的操作的详细信息，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-332">For more information about how to specify actions for ports, see [Configure the SOAP action for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="d57f9-333">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。</span><span class="sxs-lookup"><span data-stu-id="d57f9-333">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file that contains information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="d57f9-334">可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。</span><span class="sxs-lookup"><span data-stu-id="d57f9-334">You can import this binding file from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="d57f9-335">有关详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-335">For more information, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span> <span data-ttu-id="d57f9-336">如果此绑定文件导入，WCF 自定义或 WCF-SQL 发送端口上的操作设置为涉及中选择的所有操作的动态操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构时。</span><span class="sxs-lookup"><span data-stu-id="d57f9-336">If you import this binding file, the action on the WCF-Custom or WCF-SQL send port is set to a dynamic action involving all the operations you selected in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] while generating the schema.</span></span> <span data-ttu-id="d57f9-337">对于复合操作，必须将为"CompositeOperation"包含的动态操作。</span><span class="sxs-lookup"><span data-stu-id="d57f9-337">For a composite operation, you must replace the dynamic action with “CompositeOperation”.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="d57f9-338">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="d57f9-338">Starting the Application</span></span>  
 <span data-ttu-id="d57f9-339">必须启动执行复合操作的 SQL Server 数据库上的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d57f9-339">You must start the BizTalk application for performing composite operations on the SQL Server database.</span></span> <span data-ttu-id="d57f9-340">在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-340">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="d57f9-341">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="d57f9-341">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="d57f9-342">文件接收端口接收请求消息的业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="d57f9-342">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="d57f9-343">运行文件发送端口以接收来自业务流程的响应消息。</span><span class="sxs-lookup"><span data-stu-id="d57f9-343">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="d57f9-344">正在运行的 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d57f9-344">The WCF-Custom or WCF-SQL send port to send messages to the SQL Server database is running.</span></span>  
  
-   <span data-ttu-id="d57f9-345">该操作的 BizTalk 业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="d57f9-345">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="d57f9-346">执行该操作</span><span class="sxs-lookup"><span data-stu-id="d57f9-346">Executing the Operation</span></span>  
 <span data-ttu-id="d57f9-347">在运行该应用程序后，必须放置到的文件的请求消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="d57f9-347">After you run the application, you must drop a request message to the FILE receive location.</span></span> <span data-ttu-id="d57f9-348">请求消息的架构必须符合前面创建的复合操作的架构。</span><span class="sxs-lookup"><span data-stu-id="d57f9-348">The schema for the request message must conform to the schema for the composite operations you created earlier.</span></span> <span data-ttu-id="d57f9-349">例如，员工表中插入一条记录，调用 GET_LAST_EMP_DATA 存储过程，并从 EMPLOYEE 表中删除记录的请求消息是：</span><span class="sxs-lookup"><span data-stu-id="d57f9-349">For example, a request message that inserts a record in the EMPLOYEE table, invokes the GET_LAST_EMP_DATA stored procedure, and deletes a record from the EMPLOYEE table is:</span></span>  
  
```  
<Request xmlns="http://CompositeTest.CompositeSchema">  
  <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
        <Designation>Manager</Designation>  
        <Salary>100000</Salary>  
      </Employee>  
    </Rows>  
  </Insert>  
  <GET_LAST_EMP_DATA xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo" />  
  <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <Rows>  
      <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
        <Name>John</Name>  
      </Employee>  
    </Rows>  
  </Delete>  
</Request>  
```  
  
 <span data-ttu-id="d57f9-350">请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)详细了解请求消息架构执行复合操作的 SQL Server 上的数据库使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d57f9-350">See [Message Schemas for Composite Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md) for more information about the request message schema for performing composite operations on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="d57f9-351">业务流程使用该消息并将其发送到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d57f9-351">The orchestration consumes the message and sends it to the SQL Server database.</span></span> <span data-ttu-id="d57f9-352">从 SQL Server 数据库响应保存在定义为业务流程的一部分的其他文件位置。</span><span class="sxs-lookup"><span data-stu-id="d57f9-352">The response from the SQL Server database is saved at the other FILE location defined as part of the orchestration.</span></span> <span data-ttu-id="d57f9-353">例如，从前面的请求消息的 SQL Server 数据库响应是：</span><span class="sxs-lookup"><span data-stu-id="d57f9-353">For example, the response from the SQL Server database for the preceding request message is:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://CompositeTest.CompositeSchema">  
  <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <InsertResult>  
      <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10080</long>   
    </InsertResult>  
  </InsertResponse>  
  <GET_LAST_EMP_DATAResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
    <GET_LAST_EMP_DATAResult>  
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      <xs:element minOccurs="0" name="Name" type="xs:string" />   
                      <xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                      <xs:element minOccurs="0" name="Designation" type="xs:string" />   
                      <xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                      <xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                      <xs:element minOccurs="0" name="Rating" type="xs:string" />   
                      <xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
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
              <Employee_ID>10080</Employee_ID>   
              <Name>John</Name>   
              <Designation>Manager</Designation>   
              <Salary>100000.00</Salary>   
              <Last_Modified>AAAAAAAAF40=</Last_Modified>   
            </NewTable>  
          </NewDataSet>  
        </diffgr:diffgram>  
      </DataSet>  
    </GET_LAST_EMP_DATAResult>  
    <ReturnValue>0</ReturnValue>   
  </GET_LAST_EMP_DATAResponse>  
  <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 <span data-ttu-id="d57f9-354">上面的响应包含多个对应复合操作的一部分执行的不同操作的结果集。</span><span class="sxs-lookup"><span data-stu-id="d57f9-354">The preceding response contains multiple result sets corresponding the different operations performed as part of the composite operation.</span></span> <span data-ttu-id="d57f9-355">例如，`InsertResult`元素包含 10080，这是新添加的记录的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d57f9-355">For example, the `InsertResult` element contains 10080, which is the unique identifier for the newly added record.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="d57f9-356">最佳实践</span><span class="sxs-lookup"><span data-stu-id="d57f9-356">Best Practices</span></span>  
 <span data-ttu-id="d57f9-357">部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d57f9-357">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="d57f9-358">后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。</span><span class="sxs-lookup"><span data-stu-id="d57f9-358">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create items such as send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="d57f9-359">有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="d57f9-359">For more information about binding files, see [Reuse adapter bindings](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d57f9-360">请参阅</span><span class="sxs-lookup"><span data-stu-id="d57f9-360">See Also</span></span>  
[<span data-ttu-id="d57f9-361">使用 SQL 适配器开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d57f9-361">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)