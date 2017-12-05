---
title: "完成对 Oracle E-business Suite 的复合操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 886d066d-2ec8-41b4-bdd5-d8afcb5e3e58
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6e53179e82e7f41f264401b5ebf1c9c022e9727
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="complete-composite-operations-on-oracle-e-business-suite"></a><span data-ttu-id="7f5b2-102">完成对 Oracle E-business Suite 的复合操作</span><span class="sxs-lookup"><span data-stu-id="7f5b2-102">Complete composite operations on Oracle E-Business Suite</span></span>
<span data-ttu-id="7f5b2-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端可以执行对 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to perform composite operations on Oracle database.</span></span> <span data-ttu-id="7f5b2-104">复合操作可以包括：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-104">A composite operation can include:</span></span>  
  
-   <span data-ttu-id="7f5b2-105">插入、 更新、 删除和选择对数据库表的操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-105">Insert, Update, Delete, and Select operations on database tables.</span></span> <span data-ttu-id="7f5b2-106">数据库视图的选择操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-106">Select operation on database views.</span></span>  
  
-   <span data-ttu-id="7f5b2-107">插入、 更新、 删除和选择对接口表的操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-107">Insert, Update, Delete, and Select operations on interface tables.</span></span> <span data-ttu-id="7f5b2-108">界面视图的选择操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-108">Select operation on interface views.</span></span>  
  
-   <span data-ttu-id="7f5b2-109">存储的过程和函数，内部或外部包。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-109">Stored procedures and functions, inside or outside a package.</span></span>  
  
 <span data-ttu-id="7f5b2-110">单个复合操作可以具有任意数量的这些操作，按任何顺序。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-110">A single composite operation can have any number of these operations, in any order.</span></span> <span data-ttu-id="7f5b2-111">例如，你可以通过删除和最后一存储的过程执行后接两个插入。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-111">For example, you can have two inserts followed by a delete, and finally a stored procedure execution.</span></span> <span data-ttu-id="7f5b2-112">此外，你可以以不同的数据库表或视图为目标的不同操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-112">Also, you can have different operations targeting different database tables or views.</span></span> <span data-ttu-id="7f5b2-113">有关如何适配器支持复合操作的详细信息，请参阅[对复合操作的支持](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-113">For more information about how the adapter supports composite operations, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span> <span data-ttu-id="7f5b2-114">有关复合操作的 SOAP 消息结构的信息，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-114">For information about the structure of the SOAP message for composite operations, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md).</span></span>  
  
## <a name="how-to-perform-composite-operations-on-oracle-database"></a><span data-ttu-id="7f5b2-115">如何执行对 Oracle 数据库的复合操作？</span><span class="sxs-lookup"><span data-stu-id="7f5b2-115">How to Perform Composite Operations on Oracle Database?</span></span>  
 <span data-ttu-id="7f5b2-116">使用 Oracle 数据库上执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-116">Performing an operation on Oracle database using [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create Oracle E-Business Suite applications](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md).</span></span> <span data-ttu-id="7f5b2-117">若要执行对 Oracle 数据库的复合操作，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-117">To perform composite operations on Oracle database, these tasks are:</span></span>  
  
1.  <span data-ttu-id="7f5b2-118">创建 BizTalk 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和为你想要调用的所有操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-118">Create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and generate schema for all the operations you want to invoke.</span></span>  
  
2.  <span data-ttu-id="7f5b2-119">手动创建包括对你在上一步中生成的所有架构的引用的架构文件。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-119">Manually create a schema file that includes references to all the schemas you generated in the previous step.</span></span>  
  
3.  <span data-ttu-id="7f5b2-120">在发送和接收消息从 Oracle 数据库的 BizTalk 项目中创建消息。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-120">Create messages in the BizTalk project for sending and receiving messages from Oracle database.</span></span> <span data-ttu-id="7f5b2-121">这些消息必须符合你在上一步中创建的请求和响应架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-121">These messages must conform to the request and response schema you created in the previous step.</span></span>  
  
4.  <span data-ttu-id="7f5b2-122">创建业务流程来调用 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-122">Create an orchestration to invoke the composite operation on Oracle database.</span></span>  
  
5.  <span data-ttu-id="7f5b2-123">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-123">Build and deploy the BizTalk project.</span></span>  
  
6.  <span data-ttu-id="7f5b2-124">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-124">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
7.  <span data-ttu-id="7f5b2-125">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-125">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="7f5b2-126">本主题提供有关如何执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-126">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="7f5b2-127">生成架构</span><span class="sxs-lookup"><span data-stu-id="7f5b2-127">Generating Schema</span></span>  
 <span data-ttu-id="7f5b2-128">在本主题中，来演示如何执行复合操作，我们将执行相同的顺序中的以下任务：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-128">In this topic, to demonstrate how to perform composite operations, we will perform the following tasks in the same order:</span></span>  
  
-   <span data-ttu-id="7f5b2-129">将记录插入 ACCOUNTACTIVITY 表。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-129">Insert record into the ACCOUNTACTIVITY table.</span></span>  
  
-   <span data-ttu-id="7f5b2-130">通过调用 ACCOUNT_PKG 包内的 GET_ALL_ACTIVITY 过程检索 ACCOUNTACTIVITY 表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-130">Retrieve all the records in the ACCOUNTACTIVITY table by invoking the GET_ALL_ACTIVITY procedure within the ACCOUNT_PKG package.</span></span>  
  
-   <span data-ttu-id="7f5b2-131">从 ACCOUNTACTIVITY 表中删除记录。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-131">Delete the record from the ACCOUNTACTIVITY table.</span></span>  
  
 <span data-ttu-id="7f5b2-132">运行示例后，若要创建 ACCOUNTACTIVITY 表提供的脚本。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-132">Run the scripts provided with the samples to create the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7f5b2-133">有关这些示例的详细信息，请参阅[示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-133">For more information about the samples, see [Samples](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span>  
  
 <span data-ttu-id="7f5b2-134">您必须创建 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-134">You must create a BizTalk project and use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema.</span></span> <span data-ttu-id="7f5b2-135">请参阅[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-135">See [Retrieving Metadata for Oracle E-Business Suite Operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) for more information about how to generate schemas.</span></span>  
  
## <a name="creating-a-composite-schema-definition"></a><span data-ttu-id="7f5b2-136">创建复合架构定义</span><span class="sxs-lookup"><span data-stu-id="7f5b2-136">Creating a Composite Schema Definition</span></span>  
 <span data-ttu-id="7f5b2-137">现在，你必须创建中的复合架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk 项目引用的单独操作创建的架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-137">You must now create a composite schema in the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] BizTalk project that references the schemas you created for the individual operations.</span></span> <span data-ttu-id="7f5b2-138">执行以下步骤以创建复合架构定义。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-138">Perform the following steps to create a composite schema definition.</span></span>  
  
#### <a name="to-add-a-composite-schema-definition"></a><span data-ttu-id="7f5b2-139">若要添加的复合架构定义</span><span class="sxs-lookup"><span data-stu-id="7f5b2-139">To add a composite schema definition</span></span>  
  
1.  <span data-ttu-id="7f5b2-140">将架构文件添加到中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-140">Add a schema file to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="7f5b2-141">右键单击解决方案名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-141">Right-click the solution name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="7f5b2-142">在**添加新项**对话框中，从**类别**框中，单击**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-142">In the **Add New Item** dialog box, from the **Categories** box, click **Schema Files**.</span></span> <span data-ttu-id="7f5b2-143">从**模板**框中，单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-143">From the **Templates** box, click **Schema**.</span></span> <span data-ttu-id="7f5b2-144">指定的架构文件的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-144">Specify a name for the schema file and click **OK**.</span></span>  
  
     <span data-ttu-id="7f5b2-145">对于本例，请将架构文件名称指定为`CompositeSchema.xsd`。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-145">For this example, specify the schema file name as `CompositeSchema.xsd`.</span></span>  
  
2.  <span data-ttu-id="7f5b2-146">添加对生成的不同你想要执行的操作的架构的引用。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-146">Add references to the schema generated for the different operations that you want to perform.</span></span> <span data-ttu-id="7f5b2-147">在此示例中，为操作生成的不同架构是：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-147">In this example, the different schemas generated for operations are:</span></span>  
  
    -   <span data-ttu-id="7f5b2-148">OracleEBSBinding.xsd，ACCOUNTACTIVITY 表的 Insert 和 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-148">OracleEBSBinding.xsd, for Insert and Delete operations on ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="7f5b2-149">OracleEBSBinding2.xsd，GET_ALL_ACTIVITY 过程。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-149">OracleEBSBinding2.xsd, for the GET_ALL_ACTIVITY procedure.</span></span>  
  
     <span data-ttu-id="7f5b2-150">若要添加的引用：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-150">To add references:</span></span>  
  
    1.  <span data-ttu-id="7f5b2-151">右键单击根**\<架构\>** CompositeSchema.xsd，然后单击的节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-151">Right-click the root **\<Schema\>** node in the CompositeSchema.xsd, and click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="7f5b2-152">在**属性**框中，单击省略号按钮**（...）**针对**导入**属性。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-152">In the **Property** box, click the ellipsis button **(…)** against the **Imports** property.</span></span>  
  
         <span data-ttu-id="7f5b2-153">![导入架构定义](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span><span class="sxs-lookup"><span data-stu-id="7f5b2-153">![Import schema definitions](../../adapters-and-accelerators/adapter-oracle-database/media/d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca.gif "d084d0f0-60b5-4ae8-9e80-7ed2c9e3ecca")</span></span>  
  
    3.  <span data-ttu-id="7f5b2-154">在**导入**对话框中，从**导入的新架构**列表中，选择**XSD 导入**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-154">In the **Imports** dialog box, from the **Import new schema as** list, select **XSD Import**, and then click **Add**.</span></span>  
  
    4.  <span data-ttu-id="7f5b2-155">在**BizTalk 类型选取器**对话框框中，展开 BizTalk 项目名称节点，展开**架构**，然后选择你想要导入的架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-155">In the **BizTalk Type Picker** dialog box, expand the BizTalk project name node, expand **Schemas**, and then select the schema you want to import.</span></span> <span data-ttu-id="7f5b2-156">对于此示例中，选择 < BizTalk_project_name >。OracleEBSBinding.xsd。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-156">For this example, select <BizTalk_project_name>.OracleEBSBinding.xsd.</span></span> <span data-ttu-id="7f5b2-157">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-157">Click **OK**.</span></span>  
  
         <span data-ttu-id="7f5b2-158">重复此步骤以导入 < BizTalk_project_name >。OracleEBSBinding2.xsd 过。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-158">Repeat this step to import <BizTalk_project_name>.OracleEBSBinding2.xsd too.</span></span>  
  
    5.  <span data-ttu-id="7f5b2-159">在**导入**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-159">In the **Imports** dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="7f5b2-160">将两个子节点添加到根架构节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-160">Add two child nodes to the root schema node.</span></span> <span data-ttu-id="7f5b2-161">一个子节点对应于执行复合操作的请求架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-161">One child node corresponds to the request schema for performing the composite operation.</span></span> <span data-ttu-id="7f5b2-162">另一个子节点对应于响应架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-162">The other child node corresponds to the response schema.</span></span> <span data-ttu-id="7f5b2-163">对应于请求架构的节点可以具有任何名称。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-163">The node that corresponds to the request schema can have any name.</span></span> <span data-ttu-id="7f5b2-164">< Request_schema_node > 响应，必须调用到响应架构相对应的节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-164">The node that corresponds to the response schema must be called <request_schema_node>Response.</span></span> <span data-ttu-id="7f5b2-165">对于此示例，我们将调用该请求架构节点作为**请求**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-165">For this example, we will call the request schema node as **Request**.</span></span> <span data-ttu-id="7f5b2-166">因此，响应架构节点称为**请求响应**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-166">So, the response schema node is called **RequestResponse**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f5b2-167">默认情况下，**根**还将节点添加到新的架构文件。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-167">By default, a **Root** node is also added to a new schema file.</span></span> <span data-ttu-id="7f5b2-168">你可以重命名**根**节点**请求**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-168">You can rename the **Root** node to **Request**.</span></span> <span data-ttu-id="7f5b2-169">若要重命名节点，右键单击节点名称，然后单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-169">To rename a node, right-click the node name and click **Rename**.</span></span>  
  
     <span data-ttu-id="7f5b2-170">若要添加一个节点下的**\<架构\>**节点：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-170">To add a node under the **\<Schema\>** node:</span></span>  
  
    1.  <span data-ttu-id="7f5b2-171">右键单击**\<架构\>**节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-171">Right-click the **\<Schema\>** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
    2.  <span data-ttu-id="7f5b2-172">重命名为新节点**请求响应**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-172">Rename the new node to **RequestResponse**.</span></span>  
  
4.  <span data-ttu-id="7f5b2-173">添加下的子节点**请求**对应于每个将作为复合操作的一部分执行的操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-173">Add child nodes under the **Request** node that correspond to the request schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="7f5b2-174">对于此示例中，你必须添加对应于以下的子节点：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-174">For this example, you must add child nodes corresponding to the following:</span></span>  
  
    -   <span data-ttu-id="7f5b2-175">插入和删除 ACCOUNTACTIVITY 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-175">Insert and Delete operations on the ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="7f5b2-176">GET_ALL_ACTIVITY 过程。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-176">GET_ALL_ACTIVITY procedure.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7f5b2-177">必须将节点添加与要在其中执行操作的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-177">You must add the nodes in the same order in which you want to perform the operations.</span></span> <span data-ttu-id="7f5b2-178">例如，如果你想要插入一条记录，然后执行存储的过程，然后删除你必须首先添加的节点插入操作的记录，跟的节点的存储过程，以及最后的删除操作的节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-178">For example, if you want to insert a record, then execute a stored procedure, and then delete a record you must first add a node for the Insert operation, followed by a node for the stored procedure, and finally a node for the Delete operation.</span></span>  
  
     <span data-ttu-id="7f5b2-179">若要添加到的子节点**请求**节点：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-179">To add child nodes to the **Request** node:</span></span>  
  
    1.  <span data-ttu-id="7f5b2-180">右键单击**请求**节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-180">Right-click the **Request** node, point to **Insert Schema Node**, and then click  **Child Record**.</span></span>  
  
         <span data-ttu-id="7f5b2-181">![插入架构的子节点](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span><span class="sxs-lookup"><span data-stu-id="7f5b2-181">![Insert child nodes for a schema](../../adapters-and-accelerators/adapter-oracle-database/media/58992131-13a6-45c3-9513-5c0995091fae.gif "58992131-13a6-45c3-9513-5c0995091fae")</span></span>  
  
    2.  <span data-ttu-id="7f5b2-182">重命名以作为复合操作的一部分执行的操作的请求架构与相对应的记录。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-182">Rename the record to correspond to a request schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="7f5b2-183">例如，重命名为"Insert"节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-183">For example, rename the node to “Insert”.</span></span>  
  
    3.  <span data-ttu-id="7f5b2-184">映射**插入**ACCOUNTACTIVITY 表上的插入操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-184">Map the **Insert** node to the request schema for the Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7f5b2-185">为此，请右键单击**插入**节点，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-185">To do so, right-click the **Insert** node, and click **Properties**.</span></span> <span data-ttu-id="7f5b2-186">在**属性**框中，从**数据结构类型**列表中，选择**插入 （引用）**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-186">In the **Properties** box, from the **Data Structure Type** list, select **Insert (Reference)**.</span></span>  
  
         <span data-ttu-id="7f5b2-187">![将子节点映射到请求架构](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")</span><span class="sxs-lookup"><span data-stu-id="7f5b2-187">![Map child nodes to request schema](../../adapters-and-accelerators/adapter-oracle-database/media/b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e.gif "b4ebd3c7-14e5-4c37-abd7-83f0b4db4c9e")</span></span>  
  
    4.  <span data-ttu-id="7f5b2-188">重复上述步骤以添加 GET_ALL_ACTIVITY 存储过程和删除操作的请求架构的节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-188">Repeat these steps to add nodes for the request schemas for GET_ALL_ACTIVITY stored procedure and the Delete operation.</span></span> <span data-ttu-id="7f5b2-189">指定节点名称，并将它们映射到相应的架构下, 表中所述。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-189">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
        |<span data-ttu-id="7f5b2-190">节点名称</span><span class="sxs-lookup"><span data-stu-id="7f5b2-190">Node name</span></span>|<span data-ttu-id="7f5b2-191">映射到架构</span><span class="sxs-lookup"><span data-stu-id="7f5b2-191">Mapped to schema</span></span>|  
        |---------------|----------------------|  
        |<span data-ttu-id="7f5b2-192">GET_ALL_ACTIVITY</span><span class="sxs-lookup"><span data-stu-id="7f5b2-192">GET_ALL_ACTIVITY</span></span>|<span data-ttu-id="7f5b2-193">GET_ALL_ACTIVITY （参考）</span><span class="sxs-lookup"><span data-stu-id="7f5b2-193">GET_ALL_ACTIVITY (Reference)</span></span>|  
        |<span data-ttu-id="7f5b2-194">DELETE</span><span class="sxs-lookup"><span data-stu-id="7f5b2-194">Delete</span></span>|<span data-ttu-id="7f5b2-195">删除 （参考）</span><span class="sxs-lookup"><span data-stu-id="7f5b2-195">Delete (Reference)</span></span>|  
  
5.  <span data-ttu-id="7f5b2-196">添加下的子节点**请求响应**对应于每个将作为复合操作的一部分执行的操作的响应架构的节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-196">Add child nodes under the **RequestResponse** node that correspond to the response schema for each operation that you will perform as part of the composite operation.</span></span> <span data-ttu-id="7f5b2-197">对于此示例中，你必须添加对应于以下的子节点：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-197">For this example, you must add child nodes corresponding to the following:</span></span>  
  
    -   <span data-ttu-id="7f5b2-198">插入和删除 ACCOUNTACTIVITY 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-198">Insert and Delete operations on the ACCOUNTACTIVITY table.</span></span>  
  
    -   <span data-ttu-id="7f5b2-199">GET_ALL_ACTIVITY 存储过程。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-199">GET_ALL_ACTIVITY stored procedure.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7f5b2-200">你必须添加的子节点下的子节点的顺序相同**请求**节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-200">You must add the child nodes in the same order as the child nodes under the **Request** node.</span></span>  
  
     <span data-ttu-id="7f5b2-201">若要添加到的子节点**请求响应**节点：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-201">To add child nodes to the **RequestResponse** node:</span></span>  
  
    1.  <span data-ttu-id="7f5b2-202">右键单击**请求响应**节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-202">Right-click the **RequestResponse** node, point to **Insert Schema Node**, and click **Child Record**.</span></span>  
  
    2.  <span data-ttu-id="7f5b2-203">重命名以作为复合操作的一部分执行的操作的响应架构与相对应的记录。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-203">Rename the record to correspond to a response schema for an operation that you perform as part of the composite operation.</span></span> <span data-ttu-id="7f5b2-204">例如，重命名为"InsertResponse"节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-204">For example, rename the node to “InsertResponse”.</span></span>  
  
    3.  <span data-ttu-id="7f5b2-205">映射**InsertResponse** ACCOUNTACTIVITY 表上的插入操作的响应架构的节点。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-205">Map the **InsertResponse** node to the response schema for the Insert operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7f5b2-206">为此，请右键单击**InsertResponse**节点，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-206">To do so, right-click the **InsertResponse** node, and click **Properties**.</span></span> <span data-ttu-id="7f5b2-207">在**属性**框中，从**数据结构类型**列表中，选择**InsertResponse （引用）**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-207">In the **Properties** box, from the **Data Structure Type** list, select **InsertResponse (Reference)**.</span></span>  
  
    4.  <span data-ttu-id="7f5b2-208">重复上述步骤以添加节点 GET_ALL_ACTIVITY 存储过程和删除操作的响应架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-208">Repeat these steps to add nodes for the response schemas for the GET_ALL_ACTIVITY stored procedure and the Delete operation.</span></span> <span data-ttu-id="7f5b2-209">指定节点名称，并将它们映射到相应的架构下, 表中所述。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-209">Specify the node names and map them to the corresponding schema as mentioned in the following table.</span></span>  
  
        |<span data-ttu-id="7f5b2-210">节点名称</span><span class="sxs-lookup"><span data-stu-id="7f5b2-210">Node name</span></span>|<span data-ttu-id="7f5b2-211">映射到架构</span><span class="sxs-lookup"><span data-stu-id="7f5b2-211">Mapped to schema</span></span>|  
        |---------------|----------------------|  
        |<span data-ttu-id="7f5b2-212">GET_ALL_ACTIVITYResponse</span><span class="sxs-lookup"><span data-stu-id="7f5b2-212">GET_ALL_ACTIVITYResponse</span></span>|<span data-ttu-id="7f5b2-213">GET_ALL_ACTIVITYResponse （参考）</span><span class="sxs-lookup"><span data-stu-id="7f5b2-213">GET_ALL_ACTIVITYResponse (Reference)</span></span>|  
        |<span data-ttu-id="7f5b2-214">DeleteResponse</span><span class="sxs-lookup"><span data-stu-id="7f5b2-214">DeleteResponse</span></span>|<span data-ttu-id="7f5b2-215">DeleteResponse （参考）</span><span class="sxs-lookup"><span data-stu-id="7f5b2-215">DeleteResponse (Reference)</span></span>|  
  
6.  <span data-ttu-id="7f5b2-216">保存**CompositeSchema.xsd**文件。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-216">Save the **CompositeSchema.xsd** file.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="7f5b2-217">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="7f5b2-217">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="7f5b2-218">在最后一步中创建复合架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-218">The composite schema that you created in the last step describes the “types” required for the messages in an orchestration.</span></span> <span data-ttu-id="7f5b2-219">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-219">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="7f5b2-220">现在，你必须创建业务流程的消息，并将它们链接到你在上一步中创建的架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-220">You must now create messages for the orchestration and link them to schema you created in the previous step.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="7f5b2-221">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="7f5b2-221">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="7f5b2-222">中的 BizTalk 项目中添加业务流程[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-222">Add an orchestration to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="7f5b2-223">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-223">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="7f5b2-224">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-224">Type a name for the BizTalk orchestration, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="7f5b2-225">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-225">Open the Orchestration View window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="7f5b2-226">若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-226">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="7f5b2-227">在业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-227">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="7f5b2-228">右键单击新创建的消息中，，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-228">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="7f5b2-229">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-229">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="7f5b2-230">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7f5b2-230">Use this</span></span>|<span data-ttu-id="7f5b2-231">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7f5b2-231">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f5b2-232">Identifier</span><span class="sxs-lookup"><span data-stu-id="7f5b2-232">Identifier</span></span>|<span data-ttu-id="7f5b2-233">类型`Request`</span><span class="sxs-lookup"><span data-stu-id="7f5b2-233">Type `Request`</span></span>|  
    |<span data-ttu-id="7f5b2-234">消息类型</span><span class="sxs-lookup"><span data-stu-id="7f5b2-234">Message Type</span></span>|<span data-ttu-id="7f5b2-235">从下拉列表中，展开**架构**，然后选择*Composite_Op.CompositeSchema.Request*，其中 Composite_Op 是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-235">From the drop-down list, expand **Schemas**, and then select *Composite_Op.CompositeSchema.Request*, where Composite_Op is the name of your BizTalk project.</span></span> <span data-ttu-id="7f5b2-236">CompositeSchema 是手动创建的复合操作的架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-236">CompositeSchema is the schema you created manually for the composite operations.</span></span>|  
  
6.  <span data-ttu-id="7f5b2-237">重复步骤 2 创建一条新消息。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-237">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="7f5b2-238">在**属性**窗格中，为新的消息中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-238">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="7f5b2-239">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7f5b2-239">Use this</span></span>|<span data-ttu-id="7f5b2-240">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7f5b2-240">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7f5b2-241">Identifier</span><span class="sxs-lookup"><span data-stu-id="7f5b2-241">Identifier</span></span>|<span data-ttu-id="7f5b2-242">类型`Response`</span><span class="sxs-lookup"><span data-stu-id="7f5b2-242">Type `Response`</span></span>|  
    |<span data-ttu-id="7f5b2-243">消息类型</span><span class="sxs-lookup"><span data-stu-id="7f5b2-243">Message Type</span></span>|<span data-ttu-id="7f5b2-244">从下拉列表中，展开**架构**，然后选择*Composite_Op.CompositeSchema.RequestResponse*。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-244">From the drop-down list, expand **Schemas**, and then select *Composite_Op.CompositeSchema.RequestResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="7f5b2-245">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="7f5b2-245">Setting up the Orchestration</span></span>  
 <span data-ttu-id="7f5b2-246">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]执行对 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-246">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for performing composite operations on Oracle database.</span></span> <span data-ttu-id="7f5b2-247">此业务流程，在你删除时的请求消息的定义接收位置。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-247">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="7f5b2-248">请求消息必须符合前面创建的复合架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-248">The request message must conform to the composite schema you created earlier.</span></span> <span data-ttu-id="7f5b2-249">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用此消息并将其传递到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-249">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consumes this message and passes it on to Oracle database.</span></span> <span data-ttu-id="7f5b2-250">从 Oracle 数据库的响应保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-250">The response from Oracle database is saved to another location.</span></span> <span data-ttu-id="7f5b2-251">你必须包括发送和接收形状来将消息发送到 Oracle 数据库和接收响应，分别。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-251">You must include Send and Receive shapes to send messages to Oracle database and receive responses, respectively.</span></span> <span data-ttu-id="7f5b2-252">业务执行复合操作的基本流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-252">A basic orchestration for performing composite operations resembles the following:</span></span>  
  
 <span data-ttu-id="7f5b2-253">![执行复合操作的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span><span class="sxs-lookup"><span data-stu-id="7f5b2-253">![Orchestration to peform composite operations](../../adapters-and-accelerators/adapter-oracle-database/media/4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb.gif "4a1ecae7-8bf2-4c8a-a413-34d6a402cbfb")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="7f5b2-254">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="7f5b2-254">Adding Message Shapes</span></span>  
 <span data-ttu-id="7f5b2-255">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-255">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="7f5b2-256">刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-256">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="7f5b2-257">形状</span><span class="sxs-lookup"><span data-stu-id="7f5b2-257">Shape</span></span>|<span data-ttu-id="7f5b2-258">形状类型</span><span class="sxs-lookup"><span data-stu-id="7f5b2-258">Shape Type</span></span>|<span data-ttu-id="7f5b2-259">属性</span><span class="sxs-lookup"><span data-stu-id="7f5b2-259">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="7f5b2-260">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="7f5b2-260">ReceiveMessage</span></span>|<span data-ttu-id="7f5b2-261">Receive</span><span class="sxs-lookup"><span data-stu-id="7f5b2-261">Receive</span></span>|<span data-ttu-id="7f5b2-262">-将设置**名称**到*ReceiveMessage*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-262">-   Set **Name** to *ReceiveMessage*</span></span><br /><span data-ttu-id="7f5b2-263">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-263">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="7f5b2-264">发送消息</span><span class="sxs-lookup"><span data-stu-id="7f5b2-264">SendMessage</span></span>|<span data-ttu-id="7f5b2-265">Send</span><span class="sxs-lookup"><span data-stu-id="7f5b2-265">Send</span></span>|<span data-ttu-id="7f5b2-266">-将设置**名称**到*SendMessage*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-266">-   Set **Name** to *SendMessage*</span></span>|  
|<span data-ttu-id="7f5b2-267">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="7f5b2-267">ReceiveResponse</span></span>|<span data-ttu-id="7f5b2-268">Receive</span><span class="sxs-lookup"><span data-stu-id="7f5b2-268">Receive</span></span>|<span data-ttu-id="7f5b2-269">-将设置**名称**到*ReceiveResponse*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-269">-   Set **Name** to *ReceiveResponse*</span></span><br /><span data-ttu-id="7f5b2-270">-将设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-270">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="7f5b2-271">SendResponse</span><span class="sxs-lookup"><span data-stu-id="7f5b2-271">SendResponse</span></span>|<span data-ttu-id="7f5b2-272">Send</span><span class="sxs-lookup"><span data-stu-id="7f5b2-272">Send</span></span>|<span data-ttu-id="7f5b2-273">-将设置**名称**到*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-273">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="7f5b2-274">添加端口</span><span class="sxs-lookup"><span data-stu-id="7f5b2-274">Adding Ports</span></span>  
 <span data-ttu-id="7f5b2-275">请确保为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-275">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="7f5b2-276">端口列中列出的名称是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-276">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="7f5b2-277">端口</span><span class="sxs-lookup"><span data-stu-id="7f5b2-277">Port</span></span>|<span data-ttu-id="7f5b2-278">属性</span><span class="sxs-lookup"><span data-stu-id="7f5b2-278">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="7f5b2-279">MessageIn</span><span class="sxs-lookup"><span data-stu-id="7f5b2-279">MessageIn</span></span>|<span data-ttu-id="7f5b2-280">-将设置**标识符**到*MessageIn*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-280">-   Set **Identifier** to *MessageIn*</span></span><br /><span data-ttu-id="7f5b2-281">-将设置**类型**到*MessageInType*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-281">-   Set **Type** to *MessageInType*</span></span><br /><span data-ttu-id="7f5b2-282">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-282">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="7f5b2-283">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-283">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="7f5b2-284">LOBPort</span><span class="sxs-lookup"><span data-stu-id="7f5b2-284">LOBPort</span></span>|<span data-ttu-id="7f5b2-285">-将设置**标识符**到*LOBPort*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-285">-   Set **Identifier** to *LOBPort*</span></span><br /><span data-ttu-id="7f5b2-286">-将设置**类型**到*LOBPortType*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-286">-   Set **Type** to *LOBPortType*</span></span><br /><span data-ttu-id="7f5b2-287">-将设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-287">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="7f5b2-288">-将设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-288">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="7f5b2-289">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="7f5b2-289">ResponseOut</span></span>|<span data-ttu-id="7f5b2-290">-将设置**标识符**到*ResponseOut*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-290">-   Set **Identifier** to *ResponseOut*</span></span><br /><span data-ttu-id="7f5b2-291">-将设置**类型**到*ResponseOutType*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-291">-   Set **Type** to *ResponseOutType*</span></span><br /><span data-ttu-id="7f5b2-292">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-292">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="7f5b2-293">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-293">-   Set **Communication Direction** to *Send*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a><span data-ttu-id="7f5b2-294">对于操作形状，指定消息并将其连接到端口</span><span class="sxs-lookup"><span data-stu-id="7f5b2-294">Specify Messages for Action Shapes, and Connect Them to Ports</span></span>  
 <span data-ttu-id="7f5b2-295">下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-295">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="7f5b2-296">前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-296">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="7f5b2-297">形状</span><span class="sxs-lookup"><span data-stu-id="7f5b2-297">Shape</span></span>|<span data-ttu-id="7f5b2-298">属性</span><span class="sxs-lookup"><span data-stu-id="7f5b2-298">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="7f5b2-299">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="7f5b2-299">ReceiveMessage</span></span>|<span data-ttu-id="7f5b2-300">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-300">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="7f5b2-301">-将设置**操作**到*MessageIn.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-301">-   Set **Operation** to *MessageIn.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="7f5b2-302">发送消息</span><span class="sxs-lookup"><span data-stu-id="7f5b2-302">SendMessage</span></span>|<span data-ttu-id="7f5b2-303">-将设置**消息**到*请求*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-303">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="7f5b2-304">-将设置**操作**到*LOBPort.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-304">-   Set **Operation** to *LOBPort.CompositeOp.Request*</span></span>|  
|<span data-ttu-id="7f5b2-305">ReceiveResponse</span><span class="sxs-lookup"><span data-stu-id="7f5b2-305">ReceiveResponse</span></span>|<span data-ttu-id="7f5b2-306">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-306">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="7f5b2-307">-将设置**操作**到*LOBPort.CompositeOp.Response*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-307">-   Set **Operation** to *LOBPort.CompositeOp.Response*</span></span>|  
|<span data-ttu-id="7f5b2-308">SendResponse</span><span class="sxs-lookup"><span data-stu-id="7f5b2-308">SendResponse</span></span>|<span data-ttu-id="7f5b2-309">-将设置**消息**到*响应*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-309">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="7f5b2-310">-将设置**操作**到*ResponseOut.CompositeOp.Request*</span><span class="sxs-lookup"><span data-stu-id="7f5b2-310">-   Set **Operation** to *ResponseOut.CompositeOp.Request*</span></span>|  
  
 <span data-ttu-id="7f5b2-311">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-311">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="7f5b2-312">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-312">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7f5b2-313">有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-313">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>  
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="7f5b2-314">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="7f5b2-314">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="7f5b2-315">部署 BizTalk 项目后，将先前创建的业务流程下列出的业务流程窗格中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-315">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the Orchestrations pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7f5b2-316">必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-316">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="7f5b2-317">有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-317">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>  
  
 <span data-ttu-id="7f5b2-318">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-318">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="7f5b2-319">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-319">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="7f5b2-320">映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-320">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7f5b2-321">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-321">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="7f5b2-322">硬盘和放置请求消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-322">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="7f5b2-323">BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-323">The BizTalk orchestration will consume the request message and send it to Oracle database.</span></span>  
  
    -   <span data-ttu-id="7f5b2-324">硬盘和 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-324">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from Oracle database.</span></span>  
  
    -   <span data-ttu-id="7f5b2-325">定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-325">Define a physical WCF-Custom or WCF-OracleEBS send port to send messages to Oracle database.</span></span> <span data-ttu-id="7f5b2-326">因为操作都是由于复合操作的一部分执行在单个事务中，请确保**UseAmbientTransaction**绑定属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-326">Because the operations that are being as part of the composite operation are executed in a single transaction, make sure the **UseAmbientTransaction** binding property is set to **True**.</span></span>  
  
         <span data-ttu-id="7f5b2-327">你必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-327">You must also specify the action in the send port.</span></span> <span data-ttu-id="7f5b2-328">复合操作的操作是"CompositeOperation"。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-328">The action for a composite operation is “CompositeOperation”.</span></span> <span data-ttu-id="7f5b2-329">有关如何创建端口的信息，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-329">For information about how to create ports, see [Manually Configuring a Physical Port Binding to the Oracle E-Business Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md).</span></span> <span data-ttu-id="7f5b2-330">有关如何指定端口的操作的详细信息，请参阅[为 Oracle E-business Suite 配置 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-330">For more information about how to specify actions for ports, see [Configure the SOAP Action for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="7f5b2-331">复合操作的一部分如果执行操作的对象，例如存储过程、 函数、 接口表或界面视图，属于 Oracle E-business Suite 应用程序，你必须设置应用程序上下文指定所需的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-331">As part of composite operations, if you are executing operations on objects, for example stored procedures, functions, interface tables, or interface views, which belong to an Oracle E-Business Suite application, you must set the application context by specifying the requisite binding properties.</span></span> <span data-ttu-id="7f5b2-332">有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-332">For more information about setting the application context, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
        >   
        >  <span data-ttu-id="7f5b2-333">你可以通过指定的绑定属性或设置消息上下文属性公开的设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-333">You can set the application context either by specifying the binding properties or by setting the message context properties exposed by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="7f5b2-334">有关如何设置绑定属性的说明，请参阅[配置的 Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-334">For instructions on how to set the binding properties, see [Configure the Binding Properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span> <span data-ttu-id="7f5b2-335">有关如何设置应用程序上下文使用消息上下文属性的说明，请参阅[在 Oracle E-business Suite 中配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-335">For instructions on how to set the application context using message context properties, see [Configure the Application Context Using Message Context Properties in Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="7f5b2-336">生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-336">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file that contains information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="7f5b2-337">你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-337">You can import this binding file from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="7f5b2-338">有关详细信息，请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-338">For more information, see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span> <span data-ttu-id="7f5b2-339">如果你导入此绑定文件，将发送端口上的操作设置为涉及在中选择的所有操作的动态操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构时。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-339">If you import this binding file, the action on the send port is set to a dynamic action involving all the operations you selected in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] while generating the schema.</span></span> <span data-ttu-id="7f5b2-340">对于复合操作，必须将"CompositeOperation"的动态操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-340">For a composite operation, you must replace the dynamic action with “CompositeOperation”.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="7f5b2-341">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="7f5b2-341">Starting the Application</span></span>  
 <span data-ttu-id="7f5b2-342">你必须启动 BizTalk 应用程序用于执行对 Oracle 数据库的复合操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-342">You must start the BizTalk application for performing composite operations on Oracle database.</span></span> <span data-ttu-id="7f5b2-343">有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-343">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="7f5b2-344">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-344">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="7f5b2-345">FILE 接收端口，以便运行业务流程的是接收请求消息。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-345">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="7f5b2-346">要从业务流程接收响应消息的文件发送端口正在运行。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-346">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="7f5b2-347">WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle 数据库正在运行。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-347">The WCF-Custom or WCF-OracleEBS send port to send messages to Oracle database is running.</span></span>  
  
-   <span data-ttu-id="7f5b2-348">BizTalk 业务流程操作正在运行。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-348">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="7f5b2-349">执行该操作</span><span class="sxs-lookup"><span data-stu-id="7f5b2-349">Executing the Operation</span></span>  
 <span data-ttu-id="7f5b2-350">运行应用程序后，必须放到该文件的请求消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-350">After you run the application, you must drop a request message to the FILE receive location.</span></span> <span data-ttu-id="7f5b2-351">请求消息的架构必须符合前面创建的复合操作的架构。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-351">The schema for the request message must conform to the schema for the composite operations you created earlier.</span></span> <span data-ttu-id="7f5b2-352">例如，将记录插入 ACCOUNTACTIVITY 表中，调用 GET_ALL_ACTIVITY 存储过程中，并从 ACCOUNTACTIVITY 表中删除的记录的请求消息是：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-352">For example, a request message that inserts a record in the ACCOUNTACTIVITY table, invokes the GET_ALL_ACTIVITY stored procedure, and deletes a record from the ACCOUNTACTIVITY table is:</span></span>  
  
```  
<Request xmlns="http://Composite_Op.CompositeSchema">  
  <Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/ACCOUNTACTIVITY">  
    <RECORDSET>  
      <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/SCOTT/ACCOUNTACTIVITY">  
        <TID InlineValue="tid_seq.nextval"></TID>  
        <ACCOUNT>100001</ACCOUNT>  
        <AMOUNT>1500</AMOUNT>  
        <DESCRIPTION></DESCRIPTION>  
        <TRANSDATE InlineValue="sysdate">1999-05-31T13:20:00</TRANSDATE>  
        <PROCESSED>n</PROCESSED>  
      </InsertRecord>  
    </RECORDSET>  
  </Insert>  
  <GET_ALL_ACTIVITY xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG" />  
  <Delete xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/ACCOUNTACTIVITY">  
    <FILTER>WHERE AMOUNT = 1500</FILTER>  
  </Delete>  
</Request>  
```  
  
 <span data-ttu-id="7f5b2-353">前面的请求消息第一次插入一条记录，并调用 GET_ALL_ACTIVITY 过程，以获取 ACCOUNTACTIVITY 表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-353">The preceding request message first inserts a record and then invokes the GET_ALL_ACTIVITY procedure to get all the records in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7f5b2-354">然后，通过指定筛选器子句删除插入的记录。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-354">Then, the inserted record is deleted by specifying a FILTER clause.</span></span> <span data-ttu-id="7f5b2-355">有关复合操作有关的请求消息架构执行对 Oracle 数据库使用的复合操作的详细信息，请参阅消息架构[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-355">See Message Schemas for the composite operations for more information about the request message schema for performing composite operations on Oracle database using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f5b2-356">在前面的消息中，插入操作的摘录内容使用"InlineValue"属性。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-356">In the preceding message, the excerpt for the Insert operation uses the “InlineValue” attribute.</span></span> <span data-ttu-id="7f5b2-357">有关"InlineValue"属性的详细信息请参阅中的插入操作的架构描述[插入、 更新、 删除和选择操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-357">For more information about the “InlineValue” attribute see the schema description for Insert operation in [Message Schemas for Insert, Update, Delete, and Select Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md).</span></span>  
  
 <span data-ttu-id="7f5b2-358">业务流程使用该消息，并将其发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-358">The orchestration consumes the message and sends it to Oracle database.</span></span> <span data-ttu-id="7f5b2-359">从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-359">The response from Oracle database is saved at the other FILE location defined as part of the orchestration.</span></span> <span data-ttu-id="7f5b2-360">例如，从前面的请求消息的 Oracle 数据库响应如下所示：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-360">For example, the response from Oracle database for the preceding request message resembles the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RequestResponse xmlns="http://Composite_Op.CompositeSchema">  
  <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/ACCOUNTACTIVITY">  
    <InsertResult>1</InsertResult>   
  </InsertResponse>  
  <GET_ALL_ACTIVITYResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
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
  <DeleteResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/ACCOUNTACTIVITY">  
    <DeleteResult>1</DeleteResult>   
  </DeleteResponse>  
</RequestResponse>  
```  
  
 <span data-ttu-id="7f5b2-361">前面的响应中包含相应作为复合操作的一部分执行的不同操作的多个结果集。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-361">The preceding response contains multiple result sets corresponding the different operations performed as part of the composite operation.</span></span> <span data-ttu-id="7f5b2-362">例如，`InsertResult`元素包含"1"，该值指示由插入操作插入的行数。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-362">For example, the `InsertResult` element contains ‘1’, indicating the number of rows inserted by the Insert operation.</span></span> <span data-ttu-id="7f5b2-363">同样，`DeleteResult`元素包含"1"，以指示删除操作已删除的行数。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-363">Similarly, the `DeleteResult` element contains ‘1’, indicating the number of rows deleted by the Delete operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7f5b2-364">如果您在执行复合操作时遇到超时问题，则可能是因为连接数低于在复合操作涉及的操作的数目：</span><span class="sxs-lookup"><span data-stu-id="7f5b2-364">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
>   
>  -   <span data-ttu-id="7f5b2-365">缩小为包含 BFILE、 BLOB、 CLOB、 NCLOB、 和 REF CURSOR 的存储的过程或 IN OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-365">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
> -   <span data-ttu-id="7f5b2-366">选择操作。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-366">Select operation.</span></span>  
>   
>  <span data-ttu-id="7f5b2-367">若要解决此问题，你必须确保，如果没有此类操作复合操作中的"n"数目，指定的值**MinPoolSize**绑定属性为"n + 1"或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-367">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="7f5b2-368">有关详细信息**MinPoolSize**绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-368">For more information about the **MinPoolSize** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="7f5b2-369">最佳实践</span><span class="sxs-lookup"><span data-stu-id="7f5b2-369">Best Practices</span></span>  
 <span data-ttu-id="7f5b2-370">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-370">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="7f5b2-371">后生成绑定文件，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-371">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create items such as send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="7f5b2-372">有关绑定文件的详细信息，请参阅[重用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="7f5b2-372">For more information about binding files, see [Reuse Adapter Bindings with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f5b2-373">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f5b2-373">See Also</span></span>  
[<span data-ttu-id="7f5b2-374">开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="7f5b2-374">Develop BizTalk applications using the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)