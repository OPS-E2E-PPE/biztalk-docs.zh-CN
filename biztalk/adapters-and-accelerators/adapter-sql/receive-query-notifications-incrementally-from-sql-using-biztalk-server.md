---
title: 从使用 BizTalk Server 的 SQL 查询通知以增量方式接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6972e01-80be-47be-986a-c2e4e0fb0cd1
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43616dd0cb8b70d8363c39e897f81e59832ccf8e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368308"
---
# <a name="receive-query-notifications-incrementally-from-sql-using-biztalk-server"></a><span data-ttu-id="1560a-102">从使用 BizTalk Server 的 SQL 查询通知以增量方式接收</span><span class="sxs-lookup"><span data-stu-id="1560a-102">Receive Query Notifications Incrementally from SQL using BizTalk Server</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="1560a-103">为了简洁起见，本主题仅介绍如何以增量方式接收通知。</span><span class="sxs-lookup"><span data-stu-id="1560a-103">For the sake of brevity, this topic only describes how to receive notifications incrementally.</span></span> <span data-ttu-id="1560a-104">在业务方案中，业务流程在理想情况下必须包括用于提取收到通知消息的类型，然后执行任何后续操作的逻辑。</span><span class="sxs-lookup"><span data-stu-id="1560a-104">In business scenarios, the orchestration must ideally include the logic to extract the kind of notification message received and then perform any subsequent operations.</span></span> <span data-ttu-id="1560a-105">换而言之，本主题中所述的业务流程必须基于业务流程中所述[处理通知消息，以完成特定任务中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-105">In other words, the orchestration described in this topic must be built on top of the orchestration described in [Process notification messages to complete specific tasks in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md).</span></span>  
  
 <span data-ttu-id="1560a-106">本主题演示如何配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以从 SQL Server 数据库中接收增量查询通知消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-106">This topic demonstrates how to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive incremental query notification messages from a SQL Server database.</span></span> <span data-ttu-id="1560a-107">若要演示增量通知，请考虑表中的，员工，"状态"列。</span><span class="sxs-lookup"><span data-stu-id="1560a-107">To demonstrate incremental notifications, consider a table, Employee, with a “Status” column.</span></span> <span data-ttu-id="1560a-108">一条新记录插入到此表时，状态列的值设置为 0。</span><span class="sxs-lookup"><span data-stu-id="1560a-108">When a new record is inserted to this table, the value of the Status column is set to 0.</span></span> <span data-ttu-id="1560a-109">可以配置适配器后，通过执行以下接收增量通知：</span><span class="sxs-lookup"><span data-stu-id="1560a-109">You can configure the adapter to receive incremental notifications by doing the following:</span></span>  
  
- <span data-ttu-id="1560a-110">注册通知使用 SQL 语句检索所有记录为 0 的状态列。</span><span class="sxs-lookup"><span data-stu-id="1560a-110">Register for notifications using a SQL statement that retrieves all records that have Status column as 0.</span></span> <span data-ttu-id="1560a-111">您可以通过指定的 SQL 语句来实现**NotificationStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="1560a-111">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span>  
  
- <span data-ttu-id="1560a-112">对于已接收的通知消息的行，更新为 1 的状态列。</span><span class="sxs-lookup"><span data-stu-id="1560a-112">For rows for which notification messages have been received, update the Status column to 1.</span></span>  
  
  <span data-ttu-id="1560a-113">本主题演示如何创建 BizTalk 业务流程和配置 BizTalk 应用程序来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="1560a-113">This topic demonstrates how to create a BizTalk orchestration and configure a BizTalk application to achieve this.</span></span>  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="1560a-114">使用 SQL 适配器的绑定属性中配置通知</span><span class="sxs-lookup"><span data-stu-id="1560a-114">Configuring Notifications with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="1560a-115">下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置 SQL Server 从接收通知的属性。</span><span class="sxs-lookup"><span data-stu-id="1560a-115">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure receiving notifications from SQL Server.</span></span> <span data-ttu-id="1560a-116">配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1560a-116">You must specify these binding properties while configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1560a-117">您可以选择生成的架构时指定这些绑定属性**通知**操作，即使并不总是这样。</span><span class="sxs-lookup"><span data-stu-id="1560a-117">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="1560a-118">如果这样做，端口绑定文件的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含为绑定属性指定的值。</span><span class="sxs-lookup"><span data-stu-id="1560a-118">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="1560a-119">稍后可以导入此绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中创建的 WCF 自定义或 WCF SQL 属性已设置对绑定接收端口。</span><span class="sxs-lookup"><span data-stu-id="1560a-119">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-SQL receive port with the binding properties already set.</span></span> <span data-ttu-id="1560a-120">有关创建使用该绑定文件的端口的详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-120">For more information about creating a port using the binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
|<span data-ttu-id="1560a-121">绑定属性</span><span class="sxs-lookup"><span data-stu-id="1560a-121">Binding Property</span></span>|<span data-ttu-id="1560a-122">Description</span><span class="sxs-lookup"><span data-stu-id="1560a-122">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="1560a-123">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="1560a-123">**InboundOperationType**</span></span>|<span data-ttu-id="1560a-124">指定你想要执行的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-124">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="1560a-125">若要接收通知消息，请将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="1560a-125">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="1560a-126">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="1560a-126">**NotificationStatement**</span></span>|<span data-ttu-id="1560a-127">指定的 SQL 语句 (SELECT 或 EXEC\<存储过程\>) 用于对查询通知注册。</span><span class="sxs-lookup"><span data-stu-id="1560a-127">Specifies the SQL statement (SELECT or EXEC \<stored procedure\>) used to register for query notifications.</span></span> <span data-ttu-id="1560a-128">仅当指定的 SQL 语句更改的结果集时，适配器从 SQL Server 获取通知消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-128">The adapter gets a notification message from SQL Server only when the result set for the specified SQL statement changes.</span></span>|  
|<span data-ttu-id="1560a-129">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="1560a-129">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="1560a-130">指定适配器是否启动侦听器时在向适配器客户端发送了通知。</span><span class="sxs-lookup"><span data-stu-id="1560a-130">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="1560a-131">有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-131">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="1560a-132">有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要从 SQL Server 中接收通知，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="1560a-132">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive notifications from SQL Server, read further.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="1560a-133">如何本主题演示如何接收通知消息</span><span class="sxs-lookup"><span data-stu-id="1560a-133">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="1560a-134">若要演示如何将[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持从 SQL Server 中接收通知消息，本主题将演示如何将适配器配置为接收到的雇员表更改通知。</span><span class="sxs-lookup"><span data-stu-id="1560a-134">To demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving notification messages from SQL Server, this topic will demonstrate how to configure the adapter to receive notifications for changes to an Employee table.</span></span> <span data-ttu-id="1560a-135">假设 Employee 表包含列 Employee_ID、 名称和状态。</span><span class="sxs-lookup"><span data-stu-id="1560a-135">Assume that the Employee table has columns Employee_ID, Name, and Status.</span></span> <span data-ttu-id="1560a-136">每当添加新员工时，状态列的值设置为 0。</span><span class="sxs-lookup"><span data-stu-id="1560a-136">Whenever a new employee is added, the value of the Status column is set to 0.</span></span>  
  
 <span data-ttu-id="1560a-137">为了演示通知的接收，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1560a-137">To demonstrate receiving notifications, do the following:</span></span>  
  
-   <span data-ttu-id="1560a-138">生成架构**通知**（入站操作），并**选择**（出站操作） 上的 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="1560a-138">Generate schema for the **Notification** (inbound operation), and **Select** (outbound operation) on the Employee table.</span></span>  
  
-   <span data-ttu-id="1560a-139">创建具有以下业务流程：</span><span class="sxs-lookup"><span data-stu-id="1560a-139">Create an orchestration that has the following:</span></span>  
  
    -   <span data-ttu-id="1560a-140">接收位置接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-140">A receive location to receive notification messages.</span></span> <span data-ttu-id="1560a-141">可以通过指定 SELECT 语句作为通知进行配置：</span><span class="sxs-lookup"><span data-stu-id="1560a-141">You can configure for notification by specifying the SELECT statement as:</span></span>  
  
        ```  
        SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="1560a-142">具体而言，必须指定在此所示的语句中的列名称的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="1560a-142">You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="1560a-143">此外，您必须始终指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="1560a-143">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="1560a-144">例如，`dbo.Employee`。</span><span class="sxs-lookup"><span data-stu-id="1560a-144">For example, `dbo.Employee`.</span></span>  
  
    -   <span data-ttu-id="1560a-145">要更新的行已为其发送通知的发送端口。</span><span class="sxs-lookup"><span data-stu-id="1560a-145">A send port to update the rows for which notification has already been sent.</span></span> <span data-ttu-id="1560a-146">通过将值设置为 1 的状态列中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-146">You do so by setting the value in the Status column to 1.</span></span> <span data-ttu-id="1560a-147">您可以为此选择操作的一部分，将显示以下消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="1560a-147">You can do this as part of the Select operation by sending the following message to the adapter.</span></span>  
  
        ```  
        <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
          <Columns>Employee_ID,Name,Status</Columns>  
          <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
        </Select>  
        ```  
  
         <span data-ttu-id="1560a-148">在此消息中，作为的一部分`<Query>`元素中，指定要更新状态列的 UPDATE 语句。</span><span class="sxs-lookup"><span data-stu-id="1560a-148">In this message, as part of the `<Query>` element, you specify the UPDATE statement to update the Status column.</span></span> <span data-ttu-id="1560a-149">请注意接收通知消息，以便将更新已处理的行后，必须执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-149">Note that this operation must be executed after receiving the notification messages so that the processed rows are updated.</span></span> <span data-ttu-id="1560a-150">若要使用正在等待获取通知响应，然后手动将请求消息，若要更新的行的开销即可执行操作，将生成为更新的行在业务流程本身内的请求消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-150">To do away with the overhead of waiting to get the notification response and then manually dropping a request message to update the rows, you will generate the request message for updating the rows within the orchestration itself.</span></span> <span data-ttu-id="1560a-151">可以通过使用执行操作**构造消息**形状在业务流程中的。</span><span class="sxs-lookup"><span data-stu-id="1560a-151">You can do so by using the **Construct Message** shape within an orchestration.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a><span data-ttu-id="1560a-152">如何从 SQL Server 数据库中接收通知消息</span><span class="sxs-lookup"><span data-stu-id="1560a-152">How to Receive Notification Messages from the SQL Server Database</span></span>  
 <span data-ttu-id="1560a-153">使用 SQL Server 数据库上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-153">Performing an operation on the SQL Server database using [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md).</span></span> <span data-ttu-id="1560a-154">若要配置要接收通知消息的适配器，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="1560a-154">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1. <span data-ttu-id="1560a-155">创建 BizTalk 项目，然后生成的架构**通知**（入站操作） 和**选择**（出站操作） 上的 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="1560a-155">Create a BizTalk project, and then generate schema for the **Notification** (inbound operation) and **Select** (outbound operation) on the Employee table.</span></span> <span data-ttu-id="1560a-156">或者，您可以指定的值**InboundOperationType**并**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="1560a-156">Optionally, you can specify values for the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
2. <span data-ttu-id="1560a-157">用于从 SQL Server 数据库中接收通知的 BizTalk 项目中创建一条消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-157">Create a message in the BizTalk project for receiving notification from the SQL Server database.</span></span>  
  
3. <span data-ttu-id="1560a-158">在 SQL Server 数据库上执行的选择信息并接收响应消息的 BizTalk 项目中创建消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-158">Create messages in the BizTalk project for performing the Select information on the SQL Server database and receiving response messages.</span></span>  
  
4. <span data-ttu-id="1560a-159">创建业务流程中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="1560a-159">Create an orchestration that does the following:</span></span>  
  
   -   <span data-ttu-id="1560a-160">从 SQL Server 中接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-160">Receives notification message from SQL Server.</span></span>  
  
   -   <span data-ttu-id="1560a-161">创建消息，以选择和更新为其接收通知的行。</span><span class="sxs-lookup"><span data-stu-id="1560a-161">Creates a message to select and update the rows for which notification is received.</span></span>  
  
   -   <span data-ttu-id="1560a-162">将此消息发送到 SQL Server 以更新这些行，并接收响应。</span><span class="sxs-lookup"><span data-stu-id="1560a-162">Sends this message to the SQL Server to update the rows and receives a response.</span></span>  
  
5. <span data-ttu-id="1560a-163">生成并部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="1560a-163">Build and deploy the BizTalk project.</span></span>  
  
6. <span data-ttu-id="1560a-164">配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1560a-164">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="1560a-165">对于入站操作，如接收通知消息，你必须仅配置一个单向 WCF 自定义或 WCF SQL 接收端口。</span><span class="sxs-lookup"><span data-stu-id="1560a-165">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="1560a-166">双向 WCF 自定义或 WCF SQL 接收端口的入站操作不受支持。</span><span class="sxs-lookup"><span data-stu-id="1560a-166">Two-way WCF-Custom or WCF-SQL receive ports are not supported for inbound operations.</span></span>  
  
7. <span data-ttu-id="1560a-167">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1560a-167">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="1560a-168">本主题介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="1560a-168">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="1560a-169">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="1560a-169">Sample Based on This Topic</span></span>  
 <span data-ttu-id="1560a-170">使用提供的示例中，IncrementalNotification，根据本主题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1560a-170">A sample, IncrementalNotification, based on this topic is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="1560a-171">有关详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-171">For more information, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="1560a-172">生成架构</span><span class="sxs-lookup"><span data-stu-id="1560a-172">Generating Schema</span></span>  
 <span data-ttu-id="1560a-173">必须生成的架构**通知**操作并**选择**Employee 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-173">You must generate the schema for the **Notification** operation and **Select** operation on Employee table.</span></span> <span data-ttu-id="1560a-174">请参阅[获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1560a-174">See [Get metadata for SQL Server operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) for more information about how to generate the schema.</span></span> <span data-ttu-id="1560a-175">生成架构时，请执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="1560a-175">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="1560a-176">如果您不想要在设计时指定的绑定属性，跳过的第一步。</span><span class="sxs-lookup"><span data-stu-id="1560a-176">Skip the first step if you do not want to specify the binding properties at design time.</span></span>  
  
1.  <span data-ttu-id="1560a-177">为指定值**InboundOperationType**并**NotificationStatement**生成架构时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="1560a-177">Specify a value for **InboundOperationType** and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="1560a-178">有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-178">For more information about this binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="1560a-179">有关如何指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-179">For instructions on how to specify binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
2.  <span data-ttu-id="1560a-180">选择作为协定类型**服务 （入站操作）**。</span><span class="sxs-lookup"><span data-stu-id="1560a-180">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="1560a-181">生成架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-181">Generate schema for the **Notification** operation.</span></span>  
  
4.  <span data-ttu-id="1560a-182">选择作为协定类型**客户端 （出站操作）**。</span><span class="sxs-lookup"><span data-stu-id="1560a-182">Select the contract type as **Client (Outbound operations)**.</span></span>  
  
5.  <span data-ttu-id="1560a-183">生成架构**选择**上的操作**员工**表。</span><span class="sxs-lookup"><span data-stu-id="1560a-183">Generate schema for the **Select** operation on **Employee** table.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="1560a-184">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="1560a-184">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="1560a-185">先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="1560a-185">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="1560a-186">一条消息通常是一个变量，要为其类型定义由相应的架构。</span><span class="sxs-lookup"><span data-stu-id="1560a-186">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="1560a-187">架构生成后，你必须将其链接到消息从 BizTalk 项目的业务流程视图。</span><span class="sxs-lookup"><span data-stu-id="1560a-187">Once the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="1560a-188">对于本主题中，您必须创建三个消息 — 一个用于从 SQL Server 数据库，另一个执行选择操作，以接收选择操作的响应中接收通知。</span><span class="sxs-lookup"><span data-stu-id="1560a-188">For this topic, you must create three messages—one to receive notifications from the SQL Server database, one to perform the Select operation, and one to receive the response for Select operation.</span></span>  
  
 <span data-ttu-id="1560a-189">执行以下步骤创建消息并将其链接到架构。</span><span class="sxs-lookup"><span data-stu-id="1560a-189">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="1560a-190">若要创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="1560a-190">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="1560a-191">向 BizTalk 项目添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="1560a-191">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="1560a-192">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="1560a-192">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="1560a-193">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="1560a-193">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="1560a-194">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="1560a-194">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="1560a-195">单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="1560a-195">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="1560a-196">在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="1560a-196">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="1560a-197">右键单击新创建的消息，然后依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="1560a-197">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="1560a-198">在中**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1560a-198">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="1560a-199">使用此选项</span><span class="sxs-lookup"><span data-stu-id="1560a-199">Use this</span></span>|<span data-ttu-id="1560a-200">执行的操作</span><span class="sxs-lookup"><span data-stu-id="1560a-200">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1560a-201">Identifier</span><span class="sxs-lookup"><span data-stu-id="1560a-201">Identifier</span></span>|<span data-ttu-id="1560a-202">键入 `NotifyReceive`。</span><span class="sxs-lookup"><span data-stu-id="1560a-202">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="1560a-203">消息类型</span><span class="sxs-lookup"><span data-stu-id="1560a-203">Message Type</span></span>|<span data-ttu-id="1560a-204">从下拉列表中，展开**架构**，然后选择*SQLNotify.Notification*，其中*SQLNotify*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="1560a-204">From the drop-down list, expand **Schemas**, and select *SQLNotify.Notification*, where *SQLNotify* is the name of your BizTalk project.</span></span> <span data-ttu-id="1560a-205">*通知*是为生成的架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-205">*Notification* is the schema generated for the **Notification** operation.</span></span>|  
  
6.  <span data-ttu-id="1560a-206">重复步骤 3 以创建两条新消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-206">Repeat step 3 to create two new messages.</span></span> <span data-ttu-id="1560a-207">在中**属性**窗格中的新消息，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1560a-207">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="1560a-208">将标识符设置为</span><span class="sxs-lookup"><span data-stu-id="1560a-208">Set Identifier to</span></span>|<span data-ttu-id="1560a-209">将消息类型设置为</span><span class="sxs-lookup"><span data-stu-id="1560a-209">Set Message Type to</span></span>|  
    |-----------------------|-------------------------|  
    |<span data-ttu-id="1560a-210">选择</span><span class="sxs-lookup"><span data-stu-id="1560a-210">Select</span></span>|<span data-ttu-id="1560a-211">*SQLNotify.TableOperation_dbo_Employee.Select*，其中*TableOperation_dbo_Employee*是为生成的架构**选择**操作</span><span class="sxs-lookup"><span data-stu-id="1560a-211">*SQLNotify.TableOperation_dbo_Employee.Select*, where  *TableOperation_dbo_Employee* is the schema generated for the **Select** operation</span></span>|  
    |<span data-ttu-id="1560a-212">SelectResponse</span><span class="sxs-lookup"><span data-stu-id="1560a-212">SelectResponse</span></span>|<span data-ttu-id="1560a-213">*SQLNotify.TableOperation_dbo_Employee.SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="1560a-213">*SQLNotify.TableOperation_dbo_Employee.SelectResponse*</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="1560a-214">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="1560a-214">Setting up the Orchestration</span></span>  
 <span data-ttu-id="1560a-215">必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于从 SQL Server 数据库中接收通知消息，然后更新的行已收到通知。</span><span class="sxs-lookup"><span data-stu-id="1560a-215">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from the SQL Server database and then updating the rows for which notification was received.</span></span> <span data-ttu-id="1560a-216">在此业务流程，适配器将接收通知消息根据 SELECT 语句为指定**NotificationStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="1560a-216">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="1560a-217">在文件位置接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-217">The notification message is received at a FILE location.</span></span> <span data-ttu-id="1560a-218">一旦收到响应，该业务流程将构造一条消息，将用于更新为其接收通知的行。</span><span class="sxs-lookup"><span data-stu-id="1560a-218">Once the response is received, the orchestration constructs a message that will be used to update the rows for which notification is received.</span></span> <span data-ttu-id="1560a-219">在相同的文件位置还收到此消息的响应。</span><span class="sxs-lookup"><span data-stu-id="1560a-219">The response for this message is also received at the same FILE location.</span></span>  
  
 <span data-ttu-id="1560a-220">因此，您的业务流程必须包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="1560a-220">So, your orchestration must contain the following:</span></span>  
  
- <span data-ttu-id="1560a-221">一个单向接收端口以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-221">A one-way receive port to receive notification messages.</span></span>  
  
- <span data-ttu-id="1560a-222">一个双向发送端口以发送要更新的行和对同一接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-222">A two-way send port to send messages to update rows and receive response for the same.</span></span>  
  
- <span data-ttu-id="1560a-223">一个**构造消息**形状以构造消息，以执行更新操作，在业务流程内的。</span><span class="sxs-lookup"><span data-stu-id="1560a-223">A **Construct Message** shape to construct messages, to execute the Update operation, within the orchestration.</span></span>  
  
- <span data-ttu-id="1560a-224">FILE 发送端口以保存更新操作的响应。</span><span class="sxs-lookup"><span data-stu-id="1560a-224">A FILE send port to save the response for the Update operation.</span></span>  
  
- <span data-ttu-id="1560a-225">接收和发送形状。</span><span class="sxs-lookup"><span data-stu-id="1560a-225">Receive and send shapes.</span></span>  
  
  <span data-ttu-id="1560a-226">示例业务流程如下所示。</span><span class="sxs-lookup"><span data-stu-id="1560a-226">A sample orchestration resembles the following.</span></span>  
  
  <span data-ttu-id="1560a-227">![用于接收 SQL Server 通知的业务流程](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")</span><span class="sxs-lookup"><span data-stu-id="1560a-227">![Orchestration to receive SQL Server notifications](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="1560a-228">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="1560a-228">Adding Message Shapes</span></span>  
 <span data-ttu-id="1560a-229">请确保为每个消息形状中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="1560a-229">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="1560a-230">形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="1560a-230">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="1560a-231">形状</span><span class="sxs-lookup"><span data-stu-id="1560a-231">Shape</span></span>|<span data-ttu-id="1560a-232">形状类型</span><span class="sxs-lookup"><span data-stu-id="1560a-232">Shape Type</span></span>|<span data-ttu-id="1560a-233">属性</span><span class="sxs-lookup"><span data-stu-id="1560a-233">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="1560a-234">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="1560a-234">ReceiveNotification</span></span>|<span data-ttu-id="1560a-235">Receive</span><span class="sxs-lookup"><span data-stu-id="1560a-235">Receive</span></span>|<span data-ttu-id="1560a-236">-设置**名称**到*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="1560a-236">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="1560a-237">-设置**激活**到 *，则返回 True*</span><span class="sxs-lookup"><span data-stu-id="1560a-237">- Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="1560a-238">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="1560a-238">SaveNotification</span></span>|<span data-ttu-id="1560a-239">Send</span><span class="sxs-lookup"><span data-stu-id="1560a-239">Send</span></span>|<span data-ttu-id="1560a-240">-设置**名称**到*SaveNotification*</span><span class="sxs-lookup"><span data-stu-id="1560a-240">- Set **Name** to *SaveNotification*</span></span>|  
|<span data-ttu-id="1560a-241">SendSelectMessage</span><span class="sxs-lookup"><span data-stu-id="1560a-241">SendSelectMessage</span></span>|<span data-ttu-id="1560a-242">Send</span><span class="sxs-lookup"><span data-stu-id="1560a-242">Send</span></span>|<span data-ttu-id="1560a-243">-设置**名称**到*SendSelectMessage*</span><span class="sxs-lookup"><span data-stu-id="1560a-243">- Set **Name** to *SendSelectMessage*</span></span>|  
|<span data-ttu-id="1560a-244">ReceiveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="1560a-244">ReceiveSelectResponse</span></span>|<span data-ttu-id="1560a-245">Receive</span><span class="sxs-lookup"><span data-stu-id="1560a-245">Receive</span></span>|<span data-ttu-id="1560a-246">-设置**名称**到*ReceiveSelectResponse*</span><span class="sxs-lookup"><span data-stu-id="1560a-246">- Set **Name** to *ReceiveSelectResponse*</span></span>|  
|<span data-ttu-id="1560a-247">SaveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="1560a-247">SaveSelectResponse</span></span>|<span data-ttu-id="1560a-248">Send</span><span class="sxs-lookup"><span data-stu-id="1560a-248">Send</span></span>|<span data-ttu-id="1560a-249">-设置**名称**到*SaveSelectResponse*</span><span class="sxs-lookup"><span data-stu-id="1560a-249">- Set **Name** to *SaveSelectResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="1560a-250">添加构造消息形状</span><span class="sxs-lookup"><span data-stu-id="1560a-250">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="1560a-251">可以使用**构造消息**形状中，以生成操作中的请求消息执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-251">You can use the **Construct Message** shape to generate a request message within the operation to perform the Select operation.</span></span> <span data-ttu-id="1560a-252">若要执行此操作，必须添加**构造消息**形状，并在其中**消息赋值**向业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="1560a-252">To do so, you must add a **Construct Message** shape and within that a **Message Assignment** shape to your orchestration.</span></span> <span data-ttu-id="1560a-253">对于本例，请**消息赋值**形状调用生成一条消息，发送到 SQL Server 执行选择操作的代码。</span><span class="sxs-lookup"><span data-stu-id="1560a-253">For this example, the **Message Assignment** shape invokes code that generates a message that is sent to SQL Server to perform the Select operation.</span></span> <span data-ttu-id="1560a-254">**消息赋值**形状也设置为要发送到 SQL Server 的消息的操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-254">The **Message Assignment** shape also sets the action for the message to be sent to SQL Server.</span></span>  
  
 <span data-ttu-id="1560a-255">对于构造消息形状，请设置**构造的消息**属性设置为**选择**。</span><span class="sxs-lookup"><span data-stu-id="1560a-255">For the construct message shape, set the **Message Constructed** property to **Select**.</span></span>  
  
 <span data-ttu-id="1560a-256">若要生成响应的代码可能与您的 BizTalk 项目相同的 Visual Studio 解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="1560a-256">The code to generate the response could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="1560a-257">用于生成响应消息的示例代码如下所示。</span><span class="sxs-lookup"><span data-stu-id="1560a-257">A sample code for generating a response message looks like this.</span></span>  
  
```  
namespace SampleMessageCreator  
{  
    public class SampleMessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\TestLocation\\CreateMessage";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
 <span data-ttu-id="1560a-258">对于上述摘录的代码可以生成请求消息，您必须具有 XML 请求消息 （适用于员工表上的选择操作），为指定的位置中`XmlFileLocation`变量。</span><span class="sxs-lookup"><span data-stu-id="1560a-258">For the preceding code excerpt to be able to generate a request message, you must have an XML request message (for the Select operation on the Employee table) in the location specified for the `XmlFileLocation` variable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1560a-259">生成项目后，将在项目目录中创建 SampleMessageCreator.dll。</span><span class="sxs-lookup"><span data-stu-id="1560a-259">After you build the project, SampleMessageCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="1560a-260">必须将此 DLL 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="1560a-260">You must add this DLL to the global assembly cache (GAC).</span></span> <span data-ttu-id="1560a-261">此外，必须将 SampleMessageCreator.dll 添加为 BizTalk 项目中的引用。</span><span class="sxs-lookup"><span data-stu-id="1560a-261">Also, you must add the SampleMessageCreator.dll as a reference in the BizTalk project.</span></span>  
  
 <span data-ttu-id="1560a-262">添加以下表达式来调用此代码从**消息赋值**形状，以及设置用于消息的操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-262">Add the following expression to invoke this code from the **Message Assignment** shape and to set the action for message.</span></span> <span data-ttu-id="1560a-263">若要添加一个表达式，请双击**消息赋值**形状以打开表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="1560a-263">To add an expression, double-click the **Message Assignment** shape to open the Expression Editor.</span></span>  
  
```  
Select = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Select(WCF.Action) = "TableOp/Select/dbo/Employee";  
```  
  
### <a name="adding-ports"></a><span data-ttu-id="1560a-264">添加端口</span><span class="sxs-lookup"><span data-stu-id="1560a-264">Adding Ports</span></span>  
 <span data-ttu-id="1560a-265">请确保为每个逻辑端口中指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="1560a-265">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="1560a-266">端口列中列出的名称是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1560a-266">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="1560a-267">Port</span><span class="sxs-lookup"><span data-stu-id="1560a-267">Port</span></span>|<span data-ttu-id="1560a-268">属性</span><span class="sxs-lookup"><span data-stu-id="1560a-268">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="1560a-269">SQLNotifyPort</span><span class="sxs-lookup"><span data-stu-id="1560a-269">SQLNotifyPort</span></span>|<span data-ttu-id="1560a-270">-设置**标识符**到*SQLNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="1560a-270">- Set **Identifier** to *SQLNotifyPort*</span></span><br /><br /> <span data-ttu-id="1560a-271">-设置**类型**到*SQLNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="1560a-271">- Set **Type** to *SQLNotifyPortType*</span></span><br /><br /> <span data-ttu-id="1560a-272">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="1560a-272">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="1560a-273">-设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="1560a-273">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="1560a-274">SaveMessagePort</span><span class="sxs-lookup"><span data-stu-id="1560a-274">SaveMessagePort</span></span>|<span data-ttu-id="1560a-275">-设置**标识符**到*SaveMessagePort*</span><span class="sxs-lookup"><span data-stu-id="1560a-275">- Set **Identifier** to *SaveMessagePort*</span></span><br /><br /> <span data-ttu-id="1560a-276">-设置**类型**到*SaveMessagePortType*</span><span class="sxs-lookup"><span data-stu-id="1560a-276">- Set **Type** to *SaveMessagePortType*</span></span><br /><br /> <span data-ttu-id="1560a-277">-设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="1560a-277">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="1560a-278">-设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="1560a-278">- Set **Communication Direction** to *Send*</span></span><br /><br /> <span data-ttu-id="1560a-279">-创建一个操作*通知*。</span><span class="sxs-lookup"><span data-stu-id="1560a-279">- Create an operation *Notify*.</span></span> <span data-ttu-id="1560a-280">此操作用于通知消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-280">This operation is used for notification messages.</span></span><br /><br /> <span data-ttu-id="1560a-281">-创建一个操作*选择*。</span><span class="sxs-lookup"><span data-stu-id="1560a-281">- Create an operation *Select*.</span></span> <span data-ttu-id="1560a-282">此操作用于选择响应消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-282">This operation is used for select response messages.</span></span>|  
|<span data-ttu-id="1560a-283">SQLOutboundPort</span><span class="sxs-lookup"><span data-stu-id="1560a-283">SQLOutboundPort</span></span>|<span data-ttu-id="1560a-284">-设置**标识符**到*SQLOutboundPort*</span><span class="sxs-lookup"><span data-stu-id="1560a-284">- Set **Identifier** to *SQLOutboundPort*</span></span><br /><br /> <span data-ttu-id="1560a-285">-设置**类型**到*SQLOutboundPortType*</span><span class="sxs-lookup"><span data-stu-id="1560a-285">- Set **Type** to *SQLOutboundPortType*</span></span><br /><br /> <span data-ttu-id="1560a-286">-设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="1560a-286">- Set **Communication Pattern** to *Request-Response*</span></span><br /><br /> <span data-ttu-id="1560a-287">-设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="1560a-287">- Set **Communication Direction** to *Send-Receive*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="1560a-288">为操作形状指定消息并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="1560a-288">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="1560a-289">下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。</span><span class="sxs-lookup"><span data-stu-id="1560a-289">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="1560a-290">形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。</span><span class="sxs-lookup"><span data-stu-id="1560a-290">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="1560a-291">形状</span><span class="sxs-lookup"><span data-stu-id="1560a-291">Shape</span></span>|<span data-ttu-id="1560a-292">属性</span><span class="sxs-lookup"><span data-stu-id="1560a-292">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="1560a-293">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="1560a-293">ReceiveNotification</span></span>|<span data-ttu-id="1560a-294">-设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="1560a-294">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="1560a-295">-设置**操作**到*SQLNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="1560a-295">- Set **Operation** to *SQLNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="1560a-296">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="1560a-296">SaveNotification</span></span>|<span data-ttu-id="1560a-297">-设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="1560a-297">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="1560a-298">-设置**操作**到*SaveMessagePort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="1560a-298">- Set **Operation** to *SaveMessagePort.Notify.Request*</span></span>|  
|<span data-ttu-id="1560a-299">SendSelectMessage</span><span class="sxs-lookup"><span data-stu-id="1560a-299">SendSelectMessage</span></span>|<span data-ttu-id="1560a-300">-设置**消息**到*选择*</span><span class="sxs-lookup"><span data-stu-id="1560a-300">- Set **Message** to *Select*</span></span><br /><br /> <span data-ttu-id="1560a-301">-设置**操作**到*SQLOutboundPort.Select.Request*</span><span class="sxs-lookup"><span data-stu-id="1560a-301">- Set **Operation** to *SQLOutboundPort.Select.Request*</span></span>|  
|<span data-ttu-id="1560a-302">ReceiveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="1560a-302">ReceiveSelectResponse</span></span>|<span data-ttu-id="1560a-303">-设置**消息**到*SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="1560a-303">- Set **Message** to *SelectResponse*</span></span><br /><br /> <span data-ttu-id="1560a-304">-设置**操作**到*SQLOutboundPort.Select.Response*</span><span class="sxs-lookup"><span data-stu-id="1560a-304">- Set **Operation** to *SQLOutboundPort.Select.Response*</span></span>|  
|<span data-ttu-id="1560a-305">SaveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="1560a-305">SaveSelectResponse</span></span>|<span data-ttu-id="1560a-306">-设置**消息**到*SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="1560a-306">- Set **Message** to *SelectResponse*</span></span><br /><br /> <span data-ttu-id="1560a-307">-设置**操作**到*SaveMessagePort.Select.Request*</span><span class="sxs-lookup"><span data-stu-id="1560a-307">- Set **Operation** to *SaveMessagePort.Select.Request*</span></span>|  
  
 <span data-ttu-id="1560a-308">指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="1560a-308">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="1560a-309">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1560a-309">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1560a-310">有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-310">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="1560a-311">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="1560a-311">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="1560a-312">部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="1560a-312">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="1560a-313">必须使用 BizTalk Server 管理控制台来配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="1560a-313">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="1560a-314">有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-314">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="1560a-315">配置应用程序包括：</span><span class="sxs-lookup"><span data-stu-id="1560a-315">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="1560a-316">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="1560a-316">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="1560a-317">映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="1560a-317">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="1560a-318">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="1560a-318">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="1560a-319">定义一个物理 WCF 自定义或 WCF-SQL 单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="1560a-319">Define a physical WCF-Custom or WCF-SQL one-way receive port.</span></span> <span data-ttu-id="1560a-320">此端口侦听来自 SQL Server 数据库的通知。</span><span class="sxs-lookup"><span data-stu-id="1560a-320">This port listens for notifications coming from the SQL Server database.</span></span> <span data-ttu-id="1560a-321">有关如何创建端口的信息，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-321">For information about how to create ports, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span> <span data-ttu-id="1560a-322">请确保指定的接收端口的以下绑定属性。</span><span class="sxs-lookup"><span data-stu-id="1560a-322">Make sure you specify the following binding properties for the receive port.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1560a-323">不需要执行此步骤中，如果在设计时指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="1560a-323">You do not need to perform this step if you specified the binding properties at design time.</span></span> <span data-ttu-id="1560a-324">在这种情况下，您可以创建 WCF 自定义或 WCF SQL 通过导入绑定文件创建的接收端口，设置了所需的绑定属性[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1560a-324">In such a case, you can create a WCF-custom or WCF-SQL receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="1560a-325">有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-325">For more information see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="1560a-326">绑定属性</span><span class="sxs-lookup"><span data-stu-id="1560a-326">Binding Property</span></span>|<span data-ttu-id="1560a-327">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="1560a-327">Value</span></span>|  
    |----------------------|-----------|  
    |<span data-ttu-id="1560a-328">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="1560a-328">**InboundOperationType**</span></span>|<span data-ttu-id="1560a-329">将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="1560a-329">Set this to **Notification**.</span></span>|  
    |<span data-ttu-id="1560a-330">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="1560a-330">**NotificationStatement**</span></span>|<span data-ttu-id="1560a-331">将此设置为：</span><span class="sxs-lookup"><span data-stu-id="1560a-331">Set this to:</span></span><br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> <span data-ttu-id="1560a-332">**注意：** 具体而言，必须指定在此所示的语句中的列名称的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="1560a-332">**Note:** You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="1560a-333">此外，您必须始终指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="1560a-333">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="1560a-334">例如，`dbo.Employee`。</span><span class="sxs-lookup"><span data-stu-id="1560a-334">For example, `dbo.Employee`.</span></span>|  
    |<span data-ttu-id="1560a-335">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="1560a-335">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="1560a-336">将此设置为 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="1560a-336">Set this to **True**.</span></span>|  
  
     <span data-ttu-id="1560a-337">有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-337">For more information about the different binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1560a-338">我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1560a-338">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="1560a-339">你可以执行以便通过将服务添加行为时配置 WCF 自定义或 WCF SQL 接收端口。</span><span class="sxs-lookup"><span data-stu-id="1560a-339">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="1560a-340">有关如何添加服务行为的说明，请参阅[配置事务隔离级别和使用 SQL 事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-340">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
  - <span data-ttu-id="1560a-341">定义一个物理 WCF 自定义或 WCF-SQL 发送端口将消息发送到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="1560a-341">Define a physical WCF-Custom or WCF-SQL send port to send messages to the SQL Server database.</span></span> <span data-ttu-id="1560a-342">您必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-342">You must also specify the action in the send port.</span></span>  
  
  - <span data-ttu-id="1560a-343">硬盘和相应的 BizTalk 业务流程将消息从数据库中删除 SQL Server 的文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="1560a-343">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the messages from the SQL Server database.</span></span> <span data-ttu-id="1560a-344">这些将是从 SQL Server 收到的通知消息和消息进行，请选择和更新操作执行通过 WCF 自定义或 WCF-SQL 发送端口。</span><span class="sxs-lookup"><span data-stu-id="1560a-344">These will be the notification messages received from SQL Server and messages for the Select and Update operation you perform through the WCF-Custom or WCF-SQL send port.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="1560a-345">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="1560a-345">Starting the Application</span></span>  
 <span data-ttu-id="1560a-346">必须启动 BizTalk 应用程序从 SQL Server 数据库中接收通知消息并执行后续的 Select 和 Update 操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-346">You must start the BizTalk application for receiving notification messages from the SQL Server database and for performing the subsequent Select and Update operations.</span></span> <span data-ttu-id="1560a-347">在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-347">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="1560a-348">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="1560a-348">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="1560a-349">WCF 自定义或 WCF-SQL 单向接收端口，从 SQL Server 数据库运行时接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="1560a-349">The WCF-Custom or WCF-SQL one-way receive port, which receives the notification messages from the SQL Server database is running.</span></span>  
  
-   <span data-ttu-id="1560a-350">要执行的 WCF 自定义或 WCF-SQL 发送端口选择并运行 Employee 表更新操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-350">The WCF-Custom or WCF-SQL send port to perform Select and Update operations on the Employee table is running.</span></span>  
  
-   <span data-ttu-id="1560a-351">FILE 发送端口，从 SQL Server 接收消息，正在运行。</span><span class="sxs-lookup"><span data-stu-id="1560a-351">The FILE send port, which receives messages from SQL Server, is running.</span></span>  
  
-   <span data-ttu-id="1560a-352">该操作的 BizTalk 业务流程正在运行。</span><span class="sxs-lookup"><span data-stu-id="1560a-352">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="1560a-353">执行该操作</span><span class="sxs-lookup"><span data-stu-id="1560a-353">Executing the Operation</span></span>  
 <span data-ttu-id="1560a-354">若要执行此操作，必须将一条记录插入到 Employee 表中。</span><span class="sxs-lookup"><span data-stu-id="1560a-354">To execute this operation, you must insert a record into the Employee table.</span></span> <span data-ttu-id="1560a-355">让我们假设插入具有以下详细信息的记录：</span><span class="sxs-lookup"><span data-stu-id="1560a-355">Let us assume you insert a record with following details:</span></span>  
  
```  
Name = John Smith  
Designation = Manager  
Salary = 100000  
```  
  
 <span data-ttu-id="1560a-356">此外，请确保要执行的 XML 消息选择和更新操作，请参阅 C:\TestLocation\MessageIn。</span><span class="sxs-lookup"><span data-stu-id="1560a-356">Also, make sure the XML message to perform Select and Update operations is available at C:\TestLocation\MessageIn.</span></span> <span data-ttu-id="1560a-357">XML 文件应如下所示：</span><span class="sxs-lookup"><span data-stu-id="1560a-357">The XML file should resemble the following:</span></span>  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>Employee_ID,Name,Status</Columns>  
  <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
</Select>  
```  
  
 <span data-ttu-id="1560a-358">后插入记录时，以下组操作需要置于相同的序列：</span><span class="sxs-lookup"><span data-stu-id="1560a-358">Once the record is inserted, the following set of actions take place, in the same sequence:</span></span>  
  
-   <span data-ttu-id="1560a-359">适配器接收一条通知消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1560a-359">The adapter receives a notification message that resembles the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="1560a-360">此消息会通知员工表中已插入一条记录。</span><span class="sxs-lookup"><span data-stu-id="1560a-360">This message notifies that a record was inserted in the Employee table.</span></span> <span data-ttu-id="1560a-361">请注意，对于值`<Info>`元素为"Insert"。</span><span class="sxs-lookup"><span data-stu-id="1560a-361">Note that the value for the `<Info>` element is “Insert”.</span></span>  
  
-   <span data-ttu-id="1560a-362">适配器将执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="1560a-362">The adapter executes the Select operation.</span></span> <span data-ttu-id="1560a-363">因为选择操作 XML 还包括了 Update 语句，也会执行更新语句。</span><span class="sxs-lookup"><span data-stu-id="1560a-363">Because the Select operation XML also includes an Update statement, the Update statement is also executed.</span></span> <span data-ttu-id="1560a-364">SQL Server 的下一步响应是 Select 语句。</span><span class="sxs-lookup"><span data-stu-id="1560a-364">The next response from SQL Server is for the Select statement.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult>  
        <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10006</Employee_ID>   
          <Name>John</Name>   
          <Status>0</Status>  
        </Employee>  
      </SelectResult>  
    </SelectResponse>  
    ```  
  
     <span data-ttu-id="1560a-365">此响应将显示一条记录插入到 Employee 表，并且该记录的状态为 0。</span><span class="sxs-lookup"><span data-stu-id="1560a-365">This response shows that a record was inserted into the Employee table and the Status for that record is 0.</span></span>  
  
-   <span data-ttu-id="1560a-366">作为 Select 语句的一部分，也会执行更新语句和新的记录的状态列更改为 1。</span><span class="sxs-lookup"><span data-stu-id="1560a-366">As part of the Select statement, the Update statement is also executed and the Status column for the new record is changed to 1.</span></span> <span data-ttu-id="1560a-367">这会再次触发从 SQL Server 的另一条通知和适配器接收相应的通知消息，类似于下面：</span><span class="sxs-lookup"><span data-stu-id="1560a-367">This again triggers another notification from SQL Server and the adapter receives a corresponding notification message, that resembles the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="1560a-368">此消息会通知员工表中已更新记录。</span><span class="sxs-lookup"><span data-stu-id="1560a-368">This message notifies that a record was updated in the Employee table.</span></span> <span data-ttu-id="1560a-369">请注意，对于值`<Info>`元素是"更新"。</span><span class="sxs-lookup"><span data-stu-id="1560a-369">Note that the value for the `<Info>` element is “Update”.</span></span>  
  
-   <span data-ttu-id="1560a-370">第二个通知之后, 适配器执行 Select 语句。</span><span class="sxs-lookup"><span data-stu-id="1560a-370">After the second notification, the adapter executes the Select statement.</span></span> <span data-ttu-id="1560a-371">但是，因为没有记录现在的有状态为 0，适配器将获取类似于以下的响应为空。</span><span class="sxs-lookup"><span data-stu-id="1560a-371">However, because there are no records now that have Status as 0, the adapter gets an empty response resembling the following.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult />   
    </SelectResponse>  
    ```  
  
## <a name="best-practices"></a><span data-ttu-id="1560a-372">最佳实践</span><span class="sxs-lookup"><span data-stu-id="1560a-372">Best Practices</span></span>  
 <span data-ttu-id="1560a-373">部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="1560a-373">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="1560a-374">后生成的绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程，从文件导的配置设置。</span><span class="sxs-lookup"><span data-stu-id="1560a-374">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="1560a-375">有关绑定文件的详细信息，请参阅[重复使用 SQL 适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="1560a-375">For more information about binding files, see [Reuse SQL adapter bindings](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1560a-376">请参阅</span><span class="sxs-lookup"><span data-stu-id="1560a-376">See Also</span></span>  
 [<span data-ttu-id="1560a-377">接收使用 BizTalk Server 的 SQL 查询通知</span><span class="sxs-lookup"><span data-stu-id="1560a-377">Receive SQL Query Notifications using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)