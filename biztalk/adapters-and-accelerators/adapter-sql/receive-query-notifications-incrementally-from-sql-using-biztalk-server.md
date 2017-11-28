---
title: "从使用 BizTalk Server 的 SQL 查询通知以增量方式接收 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6972e01-80be-47be-986a-c2e4e0fb0cd1
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62b6137964c493ae8dff3c0ab635a3145f2d9348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-query-notifications-incrementally-from-sql-using-biztalk-server"></a><span data-ttu-id="5bcb2-102">从使用 BizTalk Server 的 SQL 查询通知以增量方式接收</span><span class="sxs-lookup"><span data-stu-id="5bcb2-102">Receive Query Notifications Incrementally from SQL using BizTalk Server</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="5bcb2-103">为了简便起见，本主题仅介绍如何以增量方式接收通知。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-103">For the sake of brevity, this topic only describes how to receive notifications incrementally.</span></span> <span data-ttu-id="5bcb2-104">在业务方案中，业务流程理想情况下必须包含提取的收到的通知消息的种类，然后执行所有后续操作的逻辑。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-104">In business scenarios, the orchestration must ideally include the logic to extract the kind of notification message received and then perform any subsequent operations.</span></span> <span data-ttu-id="5bcb2-105">换而言之，本主题中所述的业务流程必须基于业务流程中所述[处理通知消息，以完成 SQL 使用 BizTalk Server 中的特定任务](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-105">In other words, the orchestration described in this topic must be built on top of the orchestration described in [Process notification messages to complete specific tasks in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md).</span></span>  
  
 <span data-ttu-id="5bcb2-106">本主题演示如何配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以接收从 SQL Server 数据库的增量的查询通知消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-106">This topic demonstrates how to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive incremental query notification messages from a SQL Server database.</span></span> <span data-ttu-id="5bcb2-107">为了演示增量通知，考虑一个表，员工，与"状态"列。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-107">To demonstrate incremental notifications, consider a table, Employee, with a “Status” column.</span></span> <span data-ttu-id="5bcb2-108">一条新记录插入到此表时，状态列的值设置为 0。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-108">When a new record is inserted to this table, the value of the Status column is set to 0.</span></span> <span data-ttu-id="5bcb2-109">你可以配置适配器后，通过执行以下操作中接收增量通知：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-109">You can configure the adapter to receive incremental notifications by doing the following:</span></span>  
  
-   <span data-ttu-id="5bcb2-110">注册使用 SQL 语句，以检索具有为 0 的状态列的所有记录的通知。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-110">Register for notifications using a SQL statement that retrieves all records that have Status column as 0.</span></span> <span data-ttu-id="5bcb2-111">你可以通过指定的 SQL 语句来实现**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-111">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span>  
  
-   <span data-ttu-id="5bcb2-112">对于已接收的通知消息的行，更新为 1 的状态列。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-112">For rows for which notification messages have been received, update the Status column to 1.</span></span>  
  
 <span data-ttu-id="5bcb2-113">本主题演示如何创建 BizTalk 业务流程和配置 BizTalk 应用程序来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-113">This topic demonstrates how to create a BizTalk orchestration and configure a BizTalk application to achieve this.</span></span>  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="5bcb2-114">与 SQL 适配器绑定属性中配置通知</span><span class="sxs-lookup"><span data-stu-id="5bcb2-114">Configuring Notifications with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="5bcb2-115">下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定属性，用于配置从 SQL Server 接收通知。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-115">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure receiving notifications from SQL Server.</span></span> <span data-ttu-id="5bcb2-116">配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-116">You must specify these binding properties while configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bcb2-117">你可以选择在生成的架构时指定这些绑定属性**通知**操作，即使它不是强制性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-117">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="5bcb2-118">如果这样做，端口绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含你指定的绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-118">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="5bcb2-119">你稍后导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义或 WCF SQL 接收属性已设置对绑定的端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-119">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-SQL receive port with the binding properties already set.</span></span> <span data-ttu-id="5bcb2-120">有关创建使用绑定文件的端口的详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-120">For more information about creating a port using the binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
|<span data-ttu-id="5bcb2-121">绑定属性</span><span class="sxs-lookup"><span data-stu-id="5bcb2-121">Binding Property</span></span>|<span data-ttu-id="5bcb2-122">Description</span><span class="sxs-lookup"><span data-stu-id="5bcb2-122">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="5bcb2-123">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="5bcb2-123">**InboundOperationType**</span></span>|<span data-ttu-id="5bcb2-124">指定你想要执行的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-124">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="5bcb2-125">若要接收通知消息，请将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-125">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="5bcb2-126">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="5bcb2-126">**NotificationStatement**</span></span>|<span data-ttu-id="5bcb2-127">指定的 SQL 语句 (SELECT 或 EXEC\<存储过程 >) 用于注册查询通知。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-127">Specifies the SQL statement (SELECT or EXEC \<stored procedure>) used to register for query notifications.</span></span> <span data-ttu-id="5bcb2-128">仅当指定的 SQL 语句更改的结果集时，适配器从 SQL Server 获取的通知消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-128">The adapter gets a notification message from SQL Server only when the result set for the specified SQL statement changes.</span></span>|  
|<span data-ttu-id="5bcb2-129">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="5bcb2-129">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="5bcb2-130">指定启动侦听器时，适配器是否发送到适配器客户端通知。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-130">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="5bcb2-131">有关这些属性的更完整说明，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-131">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="5bcb2-132">有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要从 SQL Server 接收通知，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-132">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive notifications from SQL Server, read further.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="5bcb2-133">本主题演示接收通知消息的方式</span><span class="sxs-lookup"><span data-stu-id="5bcb2-133">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="5bcb2-134">为了演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持从 SQL Server 接收通知消息，本主题将演示如何配置适配器，以接收对员工表的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-134">To demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving notification messages from SQL Server, this topic will demonstrate how to configure the adapter to receive notifications for changes to an Employee table.</span></span> <span data-ttu-id="5bcb2-135">假定员工表具有 Employee_ID、 名称和状态的列。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-135">Assume that the Employee table has columns Employee_ID, Name, and Status.</span></span> <span data-ttu-id="5bcb2-136">每当添加新员工时，状态列的值设置为 0。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-136">Whenever a new employee is added, the value of the Status column is set to 0.</span></span>  
  
 <span data-ttu-id="5bcb2-137">为了演示接收通知，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-137">To demonstrate receiving notifications, do the following:</span></span>  
  
-   <span data-ttu-id="5bcb2-138">生成架构**通知**（入站操作），和**选择**（出站操作） 上的员工表。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-138">Generate schema for the **Notification** (inbound operation), and **Select** (outbound operation) on the Employee table.</span></span>  
  
-   <span data-ttu-id="5bcb2-139">创建具有以下业务流程：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-139">Create an orchestration that has the following:</span></span>  
  
    -   <span data-ttu-id="5bcb2-140">接收位置接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-140">A receive location to receive notification messages.</span></span> <span data-ttu-id="5bcb2-141">可通过指定为 SELECT 语句来配置通知：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-141">You can configure for notification by specifying the SELECT statement as:</span></span>  
  
        ```  
        SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="5bcb2-142">具体而言，你必须指定在此所示的语句中的列名称 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-142">You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="5bcb2-143">此外，你必须始终指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-143">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="5bcb2-144">例如， `dbo.Employee`。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-144">For example, `dbo.Employee`.</span></span>  
  
    -   <span data-ttu-id="5bcb2-145">若要更新已为其发送通知的行发送端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-145">A send port to update the rows for which notification has already been sent.</span></span> <span data-ttu-id="5bcb2-146">则这样的值设置为 1 的状态列中。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-146">You do so by setting the value in the Status column to 1.</span></span> <span data-ttu-id="5bcb2-147">你可以通过将以下消息发送到适配器执行此选择操作的一部分。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-147">You can do this as part of the Select operation by sending the following message to the adapter.</span></span>  
  
        ```  
        <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
          <Columns>Employee_ID,Name,Status</Columns>  
          <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
        </Select>  
        ```  
  
         <span data-ttu-id="5bcb2-148">在此消息中，作为的一部分`<Query>`元素中，指定 UPDATE 语句，以更新状态列。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-148">In this message, as part of the `<Query>` element, you specify the UPDATE statement to update the Status column.</span></span> <span data-ttu-id="5bcb2-149">请注意后接收通知消息，以便这些已处理的行进行更新，必须执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-149">Note that this operation must be executed after receiving the notification messages so that the processed rows are updated.</span></span> <span data-ttu-id="5bcb2-150">若要使用正在等待获取通知响应，然后手动删除要更新的行的请求消息的开销，执行操作时，将生成更新业务流程本身内的行的请求消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-150">To do away with the overhead of waiting to get the notification response and then manually dropping a request message to update the rows, you will generate the request message for updating the rows within the orchestration itself.</span></span> <span data-ttu-id="5bcb2-151">你可以通过使用来实现**构造消息**形状中业务流程。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-151">You can do so by using the **Construct Message** shape within an orchestration.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a><span data-ttu-id="5bcb2-152">如何从 SQL Server 数据库中接收通知消息</span><span class="sxs-lookup"><span data-stu-id="5bcb2-152">How to Receive Notification Messages from the SQL Server Database</span></span>  
 <span data-ttu-id="5bcb2-153">使用 SQL Server 数据库上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-153">Performing an operation on the SQL Server database using [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md).</span></span> <span data-ttu-id="5bcb2-154">若要配置的适配器以接收通知消息，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-154">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1.  <span data-ttu-id="5bcb2-155">创建 BizTalk 项目，然后生成架构**通知**（入站操作） 和**选择**（出站操作） 上的员工表。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-155">Create a BizTalk project, and then generate schema for the **Notification** (inbound operation) and **Select** (outbound operation) on the Employee table.</span></span> <span data-ttu-id="5bcb2-156">（可选） 你可以为指定值**InboundOperationType**和**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-156">Optionally, you can specify values for the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
2.  <span data-ttu-id="5bcb2-157">在从 SQL Server 数据库接收通知的 BizTalk 项目中创建一条消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-157">Create a message in the BizTalk project for receiving notification from the SQL Server database.</span></span>  
  
3.  <span data-ttu-id="5bcb2-158">创建在 BizTalk 项目中为 SQL Server 数据库上执行选择信息和接收响应消息的消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-158">Create messages in the BizTalk project for performing the Select information on the SQL Server database and receiving response messages.</span></span>  
  
4.  <span data-ttu-id="5bcb2-159">创建业务流程中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-159">Create an orchestration that does the following:</span></span>  
  
    -   <span data-ttu-id="5bcb2-160">从 SQL Server 接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-160">Receives notification message from SQL Server.</span></span>  
  
    -   <span data-ttu-id="5bcb2-161">创建消息，以选择和更新为其接收到通知的行。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-161">Creates a message to select and update the rows for which notification is received.</span></span>  
  
    -   <span data-ttu-id="5bcb2-162">将此邮件发送到 SQL Server 以更新行，并接收响应。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-162">Sends this message to the SQL Server to update the rows and receives a response.</span></span>  
  
5.  <span data-ttu-id="5bcb2-163">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-163">Build and deploy the BizTalk project.</span></span>  
  
6.  <span data-ttu-id="5bcb2-164">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-164">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bcb2-165">对于入站操作，如接收通知消息，你必须仅配置单向的 WCF 自定义或 WCF SQL 接收端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-165">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="5bcb2-166">双向 WCF 自定义或 WCF SQL 接收端口的入站操作不支持。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-166">Two-way WCF-Custom or WCF-SQL receive ports are not supported for inbound operations.</span></span>  
  
7.  <span data-ttu-id="5bcb2-167">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-167">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="5bcb2-168">本主题提供执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-168">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="5bcb2-169">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="5bcb2-169">Sample Based on This Topic</span></span>  
 <span data-ttu-id="5bcb2-170">示例中，IncrementalNotification，基于本主题提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-170">A sample, IncrementalNotification, based on this topic is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="5bcb2-171">有关详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-171">For more information, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="5bcb2-172">生成架构</span><span class="sxs-lookup"><span data-stu-id="5bcb2-172">Generating Schema</span></span>  
 <span data-ttu-id="5bcb2-173">必须生成的架构**通知**操作和**选择**员工表上的操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-173">You must generate the schema for the **Notification** operation and **Select** operation on Employee table.</span></span> <span data-ttu-id="5bcb2-174">请参阅[为使用 SQL 适配器的 Visual Studio 中的 SQL Server 操作获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-174">See [Get metadata for SQL Server operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) for more information about how to generate the schema.</span></span> <span data-ttu-id="5bcb2-175">生成架构时，请执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-175">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="5bcb2-176">如果你不想要在设计时指定的绑定属性，跳过的第一步。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-176">Skip the first step if you do not want to specify the binding properties at design time.</span></span>  
  
1.  <span data-ttu-id="5bcb2-177">为指定值**InboundOperationType**和**NotificationStatement**生成架构时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-177">Specify a value for **InboundOperationType** and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="5bcb2-178">有关此绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-178">For more information about this binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="5bcb2-179">有关如何指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-179">For instructions on how to specify binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
2.  <span data-ttu-id="5bcb2-180">选择与具有协定类型**服务 （入站操作）**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-180">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="5bcb2-181">生成架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-181">Generate schema for the **Notification** operation.</span></span>  
  
4.  <span data-ttu-id="5bcb2-182">选择与具有协定类型**客户端 （出站操作）**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-182">Select the contract type as **Client (Outbound operations)**.</span></span>  
  
5.  <span data-ttu-id="5bcb2-183">生成架构**选择**操作**员工**表。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-183">Generate schema for the **Select** operation on **Employee** table.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="5bcb2-184">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="5bcb2-184">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="5bcb2-185">你先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-185">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="5bcb2-186">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-186">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="5bcb2-187">后生成架构，你必须将其从 BizTalk 项目的业务流程视图链接到消息中。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-187">Once the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="5bcb2-188">对于本主题中，你必须创建三个消息 — 一个用于从 SQL Server 数据库，另一个执行选择操作，以接收选择操作的响应中接收通知。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-188">For this topic, you must create three messages—one to receive notifications from the SQL Server database, one to perform the Select operation, and one to receive the response for Select operation.</span></span>  
  
 <span data-ttu-id="5bcb2-189">执行以下步骤以创建消息并将它们链接到架构。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-189">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="5bcb2-190">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="5bcb2-190">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="5bcb2-191">BizTalk 项目中添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-191">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="5bcb2-192">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-192">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="5bcb2-193">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-193">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="5bcb2-194">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-194">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="5bcb2-195">单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-195">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="5bcb2-196">在**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-196">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="5bcb2-197">右键单击新创建的消息中，，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-197">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="5bcb2-198">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-198">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="5bcb2-199">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5bcb2-199">Use this</span></span>|<span data-ttu-id="5bcb2-200">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5bcb2-200">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5bcb2-201">Identifier</span><span class="sxs-lookup"><span data-stu-id="5bcb2-201">Identifier</span></span>|<span data-ttu-id="5bcb2-202">键入 `NotifyReceive`。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-202">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="5bcb2-203">消息类型</span><span class="sxs-lookup"><span data-stu-id="5bcb2-203">Message Type</span></span>|<span data-ttu-id="5bcb2-204">从下拉列表中，展开**架构**，然后选择*SQLNotify.Notification*，其中*SQLNotify*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-204">From the drop-down list, expand **Schemas**, and select *SQLNotify.Notification*, where *SQLNotify* is the name of your BizTalk project.</span></span> <span data-ttu-id="5bcb2-205">*通知*是为生成的架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-205">*Notification* is the schema generated for the **Notification** operation.</span></span>|  
  
6.  <span data-ttu-id="5bcb2-206">重复步骤 3 以创建两条新消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-206">Repeat step 3 to create two new messages.</span></span> <span data-ttu-id="5bcb2-207">在**属性**窗格中，为新的消息中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-207">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="5bcb2-208">设置为标识符</span><span class="sxs-lookup"><span data-stu-id="5bcb2-208">Set Identifier to</span></span>|<span data-ttu-id="5bcb2-209">将消息类型设置为</span><span class="sxs-lookup"><span data-stu-id="5bcb2-209">Set Message Type to</span></span>|  
    |-----------------------|-------------------------|  
    |<span data-ttu-id="5bcb2-210">选择</span><span class="sxs-lookup"><span data-stu-id="5bcb2-210">Select</span></span>|<span data-ttu-id="5bcb2-211">*SQLNotify.TableOperation_dbo_Employee.Select*，其中*TableOperation_dbo_Employee*是为生成的架构**选择**操作</span><span class="sxs-lookup"><span data-stu-id="5bcb2-211">*SQLNotify.TableOperation_dbo_Employee.Select*, where  *TableOperation_dbo_Employee* is the schema generated for the **Select** operation</span></span>|  
    |<span data-ttu-id="5bcb2-212">SelectResponse</span><span class="sxs-lookup"><span data-stu-id="5bcb2-212">SelectResponse</span></span>|<span data-ttu-id="5bcb2-213">*SQLNotify.TableOperation_dbo_Employee.SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-213">*SQLNotify.TableOperation_dbo_Employee.SelectResponse*</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="5bcb2-214">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="5bcb2-214">Setting up the Orchestration</span></span>  
 <span data-ttu-id="5bcb2-215">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为 SQL Server 数据库从接收通知消息，然后更新为其接收到通知的行。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-215">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from the SQL Server database and then updating the rows for which notification was received.</span></span> <span data-ttu-id="5bcb2-216">在此业务流程，适配器接收基于 SELECT 语句为指定的通知消息**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-216">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="5bcb2-217">在文件位置接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-217">The notification message is received at a FILE location.</span></span> <span data-ttu-id="5bcb2-218">一旦收到响应，业务流程将构造一条消息，将用于更新为其接收到通知的行。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-218">Once the response is received, the orchestration constructs a message that will be used to update the rows for which notification is received.</span></span> <span data-ttu-id="5bcb2-219">在相同的文件位置还收到此消息的响应。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-219">The response for this message is also received at the same FILE location.</span></span>  
  
 <span data-ttu-id="5bcb2-220">因此，您的业务流程必须包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-220">So, your orchestration must contain the following:</span></span>  
  
-   <span data-ttu-id="5bcb2-221">单向接收端口以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-221">A one-way receive port to receive notification messages.</span></span>  
  
-   <span data-ttu-id="5bcb2-222">双向发送要发送消息，以更新行，并接收响应为同一端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-222">A two-way send port to send messages to update rows and receive response for the same.</span></span>  
  
-   <span data-ttu-id="5bcb2-223">A**构造消息**构造消息，以执行更新操作，业务流程中的形状。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-223">A **Construct Message** shape to construct messages, to execute the Update operation, within the orchestration.</span></span>  
  
-   <span data-ttu-id="5bcb2-224">文件发送端口以保存更新操作的响应。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-224">A FILE send port to save the response for the Update operation.</span></span>  
  
-   <span data-ttu-id="5bcb2-225">接收和发送形状。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-225">Receive and send shapes.</span></span>  
  
 <span data-ttu-id="5bcb2-226">示例业务流程如下所示。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-226">A sample orchestration resembles the following.</span></span>  
  
 <span data-ttu-id="5bcb2-227">![业务流程能够接收 SQL Server 通知](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")</span><span class="sxs-lookup"><span data-stu-id="5bcb2-227">![Orchestration to receive SQL Server notifications](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="5bcb2-228">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="5bcb2-228">Adding Message Shapes</span></span>  
 <span data-ttu-id="5bcb2-229">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-229">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="5bcb2-230">刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-230">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="5bcb2-231">形状</span><span class="sxs-lookup"><span data-stu-id="5bcb2-231">Shape</span></span>|<span data-ttu-id="5bcb2-232">形状类型</span><span class="sxs-lookup"><span data-stu-id="5bcb2-232">Shape Type</span></span>|<span data-ttu-id="5bcb2-233">属性</span><span class="sxs-lookup"><span data-stu-id="5bcb2-233">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="5bcb2-234">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="5bcb2-234">ReceiveNotification</span></span>|<span data-ttu-id="5bcb2-235">Receive</span><span class="sxs-lookup"><span data-stu-id="5bcb2-235">Receive</span></span>|<span data-ttu-id="5bcb2-236">-将设置**名称**到*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-236">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="5bcb2-237">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-237">- Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="5bcb2-238">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="5bcb2-238">SaveNotification</span></span>|<span data-ttu-id="5bcb2-239">Send</span><span class="sxs-lookup"><span data-stu-id="5bcb2-239">Send</span></span>|<span data-ttu-id="5bcb2-240">-将设置**名称**到*SaveNotification*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-240">- Set **Name** to *SaveNotification*</span></span>|  
|<span data-ttu-id="5bcb2-241">SendSelectMessage</span><span class="sxs-lookup"><span data-stu-id="5bcb2-241">SendSelectMessage</span></span>|<span data-ttu-id="5bcb2-242">Send</span><span class="sxs-lookup"><span data-stu-id="5bcb2-242">Send</span></span>|<span data-ttu-id="5bcb2-243">-将设置**名称**到*SendSelectMessage*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-243">- Set **Name** to *SendSelectMessage*</span></span>|  
|<span data-ttu-id="5bcb2-244">ReceiveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="5bcb2-244">ReceiveSelectResponse</span></span>|<span data-ttu-id="5bcb2-245">Receive</span><span class="sxs-lookup"><span data-stu-id="5bcb2-245">Receive</span></span>|<span data-ttu-id="5bcb2-246">-将设置**名称**到*ReceiveSelectResponse*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-246">- Set **Name** to *ReceiveSelectResponse*</span></span>|  
|<span data-ttu-id="5bcb2-247">SaveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="5bcb2-247">SaveSelectResponse</span></span>|<span data-ttu-id="5bcb2-248">Send</span><span class="sxs-lookup"><span data-stu-id="5bcb2-248">Send</span></span>|<span data-ttu-id="5bcb2-249">-将设置**名称**到*SaveSelectResponse*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-249">- Set **Name** to *SaveSelectResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="5bcb2-250">添加构造消息形状</span><span class="sxs-lookup"><span data-stu-id="5bcb2-250">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="5bcb2-251">你可以使用**构造消息**形状以生成请求消息在操作内的执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-251">You can use the **Construct Message** shape to generate a request message within the operation to perform the Select operation.</span></span> <span data-ttu-id="5bcb2-252">若要执行此操作，你必须添加**构造消息**形状和在其中**消息分配**形状上与您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-252">To do so, you must add a **Construct Message** shape and within that a **Message Assignment** shape to your orchestration.</span></span> <span data-ttu-id="5bcb2-253">对于此示例，**消息分配**形状调用生成一条消息，发送到 SQL Server 执行选择操作的代码。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-253">For this example, the **Message Assignment** shape invokes code that generates a message that is sent to SQL Server to perform the Select operation.</span></span> <span data-ttu-id="5bcb2-254">**消息分配**形状还设置到 SQL Server 发送的消息的操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-254">The **Message Assignment** shape also sets the action for the message to be sent to SQL Server.</span></span>  
  
 <span data-ttu-id="5bcb2-255">构造消息形状，请设置**构造消息**属性**选择**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-255">For the construct message shape, set the **Message Constructed** property to **Select**.</span></span>  
  
 <span data-ttu-id="5bcb2-256">用于生成响应的代码可能与 BizTalk 项目相同的 Visual Studio 解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-256">The code to generate the response could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="5bcb2-257">示例代码，用于生成响应消息如下所示。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-257">A sample code for generating a response message looks like this.</span></span>  
  
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
  
 <span data-ttu-id="5bcb2-258">对于要能够生成请求消息的前面代码摘要，你必须为指定的位置中具有 XML 请求消息 （对于员工表上的选择操作）`XmlFileLocation`变量。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-258">For the preceding code excerpt to be able to generate a request message, you must have an XML request message (for the Select operation on the Employee table) in the location specified for the `XmlFileLocation` variable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bcb2-259">生成项目后，将在项目目录中创建 SampleMessageCreator.dll。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-259">After you build the project, SampleMessageCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="5bcb2-260">必须将此 DLL 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-260">You must add this DLL to the global assembly cache (GAC).</span></span> <span data-ttu-id="5bcb2-261">此外，你必须添加 SampleMessageCreator.dll 作为 BizTalk 项目中的引用。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-261">Also, you must add the SampleMessageCreator.dll as a reference in the BizTalk project.</span></span>  
  
 <span data-ttu-id="5bcb2-262">添加以下表达式来调用此代码从**消息分配**形状以及设置用于消息的操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-262">Add the following expression to invoke this code from the **Message Assignment** shape and to set the action for message.</span></span> <span data-ttu-id="5bcb2-263">若要添加一个表达式，请双击**消息分配**形状以打开表达式编辑器中。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-263">To add an expression, double-click the **Message Assignment** shape to open the Expression Editor.</span></span>  
  
```  
Select = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Select(WCF.Action) = "TableOp/Select/dbo/Employee";  
```  
  
### <a name="adding-ports"></a><span data-ttu-id="5bcb2-264">添加端口</span><span class="sxs-lookup"><span data-stu-id="5bcb2-264">Adding Ports</span></span>  
 <span data-ttu-id="5bcb2-265">请确保为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-265">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="5bcb2-266">端口列中列出的名称是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-266">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="5bcb2-267">端口</span><span class="sxs-lookup"><span data-stu-id="5bcb2-267">Port</span></span>|<span data-ttu-id="5bcb2-268">属性</span><span class="sxs-lookup"><span data-stu-id="5bcb2-268">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="5bcb2-269">SQLNotifyPort</span><span class="sxs-lookup"><span data-stu-id="5bcb2-269">SQLNotifyPort</span></span>|<span data-ttu-id="5bcb2-270">-将设置**标识符**到*SQLNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-270">- Set **Identifier** to *SQLNotifyPort*</span></span><br /><br /> <span data-ttu-id="5bcb2-271">-将设置**类型**到*SQLNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-271">- Set **Type** to *SQLNotifyPortType*</span></span><br /><br /> <span data-ttu-id="5bcb2-272">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-272">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="5bcb2-273">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-273">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="5bcb2-274">SaveMessagePort</span><span class="sxs-lookup"><span data-stu-id="5bcb2-274">SaveMessagePort</span></span>|<span data-ttu-id="5bcb2-275">-将设置**标识符**到*SaveMessagePort*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-275">- Set **Identifier** to *SaveMessagePort*</span></span><br /><br /> <span data-ttu-id="5bcb2-276">-将设置**类型**到*SaveMessagePortType*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-276">- Set **Type** to *SaveMessagePortType*</span></span><br /><br /> <span data-ttu-id="5bcb2-277">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-277">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="5bcb2-278">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-278">- Set **Communication Direction** to *Send*</span></span><br /><br /> <span data-ttu-id="5bcb2-279">-创建一个操作*通知*。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-279">- Create an operation *Notify*.</span></span> <span data-ttu-id="5bcb2-280">此操作用于通知消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-280">This operation is used for notification messages.</span></span><br /><br /> <span data-ttu-id="5bcb2-281">-创建一个操作*选择*。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-281">- Create an operation *Select*.</span></span> <span data-ttu-id="5bcb2-282">选择响应消息将要使用此操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-282">This operation is used for select response messages.</span></span>|  
|<span data-ttu-id="5bcb2-283">SQLOutboundPort</span><span class="sxs-lookup"><span data-stu-id="5bcb2-283">SQLOutboundPort</span></span>|<span data-ttu-id="5bcb2-284">-将设置**标识符**到*SQLOutboundPort*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-284">- Set **Identifier** to *SQLOutboundPort*</span></span><br /><br /> <span data-ttu-id="5bcb2-285">-将设置**类型**到*SQLOutboundPortType*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-285">- Set **Type** to *SQLOutboundPortType*</span></span><br /><br /> <span data-ttu-id="5bcb2-286">-将设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-286">- Set **Communication Pattern** to *Request-Response*</span></span><br /><br /> <span data-ttu-id="5bcb2-287">-将设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-287">- Set **Communication Direction** to *Send-Receive*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="5bcb2-288">指定消息的操作形状并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="5bcb2-288">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="5bcb2-289">下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-289">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="5bcb2-290">前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-290">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="5bcb2-291">形状</span><span class="sxs-lookup"><span data-stu-id="5bcb2-291">Shape</span></span>|<span data-ttu-id="5bcb2-292">属性</span><span class="sxs-lookup"><span data-stu-id="5bcb2-292">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="5bcb2-293">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="5bcb2-293">ReceiveNotification</span></span>|<span data-ttu-id="5bcb2-294">-将设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-294">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="5bcb2-295">-将设置**操作**到*SQLNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-295">- Set **Operation** to *SQLNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="5bcb2-296">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="5bcb2-296">SaveNotification</span></span>|<span data-ttu-id="5bcb2-297">-将设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-297">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="5bcb2-298">-将设置**操作**到*SaveMessagePort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-298">- Set **Operation** to *SaveMessagePort.Notify.Request*</span></span>|  
|<span data-ttu-id="5bcb2-299">SendSelectMessage</span><span class="sxs-lookup"><span data-stu-id="5bcb2-299">SendSelectMessage</span></span>|<span data-ttu-id="5bcb2-300">-将设置**消息**到*选择*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-300">- Set **Message** to *Select*</span></span><br /><br /> <span data-ttu-id="5bcb2-301">-将设置**操作**到*SQLOutboundPort.Select.Request*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-301">- Set **Operation** to *SQLOutboundPort.Select.Request*</span></span>|  
|<span data-ttu-id="5bcb2-302">ReceiveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="5bcb2-302">ReceiveSelectResponse</span></span>|<span data-ttu-id="5bcb2-303">-将设置**消息**到*SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-303">- Set **Message** to *SelectResponse*</span></span><br /><br /> <span data-ttu-id="5bcb2-304">-将设置**操作**到*SQLOutboundPort.Select.Response*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-304">- Set **Operation** to *SQLOutboundPort.Select.Response*</span></span>|  
|<span data-ttu-id="5bcb2-305">SaveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="5bcb2-305">SaveSelectResponse</span></span>|<span data-ttu-id="5bcb2-306">-将设置**消息**到*SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-306">- Set **Message** to *SelectResponse*</span></span><br /><br /> <span data-ttu-id="5bcb2-307">-将设置**操作**到*SaveMessagePort.Select.Request*</span><span class="sxs-lookup"><span data-stu-id="5bcb2-307">- Set **Operation** to *SaveMessagePort.Select.Request*</span></span>|  
  
 <span data-ttu-id="5bcb2-308">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-308">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="5bcb2-309">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-309">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5bcb2-310">有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-310">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="5bcb2-311">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5bcb2-311">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="5bcb2-312">部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-312">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="5bcb2-313">必须使用 BizTalk Server 管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-313">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="5bcb2-314">有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-314">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="5bcb2-315">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-315">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="5bcb2-316">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-316">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="5bcb2-317">映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-317">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="5bcb2-318">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-318">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="5bcb2-319">定义一个物理 WCF 自定义或 WCF SQL 单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-319">Define a physical WCF-Custom or WCF-SQL one-way receive port.</span></span> <span data-ttu-id="5bcb2-320">此端口侦听来自 SQL Server 数据库的通知。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-320">This port listens for notifications coming from the SQL Server database.</span></span> <span data-ttu-id="5bcb2-321">有关如何创建端口的信息，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-321">For information about how to create ports, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span> <span data-ttu-id="5bcb2-322">请确保指定的接收端口的以下绑定属性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-322">Make sure you specify the following binding properties for the receive port.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="5bcb2-323">不需要执行此步骤中，如果在设计时指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-323">You do not need to perform this step if you specified the binding properties at design time.</span></span> <span data-ttu-id="5bcb2-324">在这种情况下，你可以创建 WCF 自定义或 WCF SQL 接收端口，将设置所需的绑定的属性，通过导入所创建绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-324">In such a case, you can create a WCF-custom or WCF-SQL receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="5bcb2-325">有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-325">For more information see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
        |<span data-ttu-id="5bcb2-326">绑定属性</span><span class="sxs-lookup"><span data-stu-id="5bcb2-326">Binding Property</span></span>|<span data-ttu-id="5bcb2-327">值</span><span class="sxs-lookup"><span data-stu-id="5bcb2-327">Value</span></span>|  
        |----------------------|-----------|  
        |<span data-ttu-id="5bcb2-328">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="5bcb2-328">**InboundOperationType**</span></span>|<span data-ttu-id="5bcb2-329">将其设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-329">Set this to **Notification**.</span></span>|  
        |<span data-ttu-id="5bcb2-330">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="5bcb2-330">**NotificationStatement**</span></span>|<span data-ttu-id="5bcb2-331">将其设置为：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-331">Set this to:</span></span><br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> <span data-ttu-id="5bcb2-332">**注意：**你必须专门的列名称在语句中指定此 SELECT 语句中所示。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-332">**Note:** You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="5bcb2-333">此外，你必须始终指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-333">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="5bcb2-334">例如， `dbo.Employee`。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-334">For example, `dbo.Employee`.</span></span>|  
        |<span data-ttu-id="5bcb2-335">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="5bcb2-335">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="5bcb2-336">将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-336">Set this to **True**.</span></span>|  
  
         <span data-ttu-id="5bcb2-337">有关不同的绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-337">For more information about the different binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5bcb2-338">我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-338">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="5bcb2-339">你可以执行以便通过将服务添加行为配置 WCF 自定义或 WCF SQL 时接收端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-339">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="5bcb2-340">有关如何添加服务行为的说明，请参阅[配置事务隔离级别和与 SQL 的事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-340">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
    -   <span data-ttu-id="5bcb2-341">定义物理 WCF 自定义或 WCF SQL 发送端口将消息发送到的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-341">Define a physical WCF-Custom or WCF-SQL send port to send messages to the SQL Server database.</span></span> <span data-ttu-id="5bcb2-342">你必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-342">You must also specify the action in the send port.</span></span>  
  
    -   <span data-ttu-id="5bcb2-343">硬盘和其中 BizTalk 业务流程将消息从数据库中删除 SQL Server 的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-343">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the messages from the SQL Server database.</span></span> <span data-ttu-id="5bcb2-344">这些将是从 SQL Server 接收的通知消息和消息进行，请选择和更新操作执行通过 WCF 自定义或 WCF SQL 发送端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-344">These will be the notification messages received from SQL Server and messages for the Select and Update operation you perform through the WCF-Custom or WCF-SQL send port.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="5bcb2-345">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="5bcb2-345">Starting the Application</span></span>  
 <span data-ttu-id="5bcb2-346">你必须启动 BizTalk 应用程序从 SQL Server 数据库中接收通知消息并执行后续的选择和更新操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-346">You must start the BizTalk application for receiving notification messages from the SQL Server database and for performing the subsequent Select and Update operations.</span></span> <span data-ttu-id="5bcb2-347">有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-347">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="5bcb2-348">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-348">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="5bcb2-349">WCF 自定义或 WCF SQL 单向接收端口，从而从 SQL Server 数据库运行时接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-349">The WCF-Custom or WCF-SQL one-way receive port, which receives the notification messages from the SQL Server database is running.</span></span>  
  
-   <span data-ttu-id="5bcb2-350">选择要执行的 WCF 自定义或 WCF SQL 发送端口和运行更新操作员工表。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-350">The WCF-Custom or WCF-SQL send port to perform Select and Update operations on the Employee table is running.</span></span>  
  
-   <span data-ttu-id="5bcb2-351">文件发送端口，从而从 SQL Server 接收消息，正在运行。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-351">The FILE send port, which receives messages from SQL Server, is running.</span></span>  
  
-   <span data-ttu-id="5bcb2-352">BizTalk 业务流程操作正在运行。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-352">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="5bcb2-353">执行该操作</span><span class="sxs-lookup"><span data-stu-id="5bcb2-353">Executing the Operation</span></span>  
 <span data-ttu-id="5bcb2-354">若要执行此操作，必须将一个记录插入员工表。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-354">To execute this operation, you must insert a record into the Employee table.</span></span> <span data-ttu-id="5bcb2-355">让我们假定插入一条记录，详细信息如下：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-355">Let us assume you insert a record with following details:</span></span>  
  
```  
Name = John Smith  
Designation = Manager  
Salary = 100000  
```  
  
 <span data-ttu-id="5bcb2-356">此外，请确保要执行的 XML 消息选择和更新操作位于 C:\TestLocation\MessageIn。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-356">Also, make sure the XML message to perform Select and Update operations is available at C:\TestLocation\MessageIn.</span></span> <span data-ttu-id="5bcb2-357">XML 文件应如下所示：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-357">The XML file should resemble the following:</span></span>  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>Employee_ID,Name,Status</Columns>  
  <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
</Select>  
```  
  
 <span data-ttu-id="5bcb2-358">后插入条记录时，下面的一组操作需要置于相同的序列：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-358">Once the record is inserted, the following set of actions take place, in the same sequence:</span></span>  
  
-   <span data-ttu-id="5bcb2-359">适配器将接收通知消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-359">The adapter receives a notification message that resembles the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="5bcb2-360">此消息将通知员工表中已插入一条记录。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-360">This message notifies that a record was inserted in the Employee table.</span></span> <span data-ttu-id="5bcb2-361">请注意，值`<Info>`元素是"插入"。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-361">Note that the value for the `<Info>` element is “Insert”.</span></span>  
  
-   <span data-ttu-id="5bcb2-362">适配器将执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-362">The adapter executes the Select operation.</span></span> <span data-ttu-id="5bcb2-363">因为选择操作 XML 还包括一个 Update 语句，也会执行更新语句。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-363">Because the Select operation XML also includes an Update statement, the Update statement is also executed.</span></span> <span data-ttu-id="5bcb2-364">从 SQL Server 的下一步响应是 Select 语句。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-364">The next response from SQL Server is for the Select statement.</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
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
  
     <span data-ttu-id="5bcb2-365">此响应将显示一条记录插入到员工表，并且该记录的状态为 0。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-365">This response shows that a record was inserted into the Employee table and the Status for that record is 0.</span></span>  
  
-   <span data-ttu-id="5bcb2-366">作为 Select 语句的一部分，也会执行更新语句和新的记录的状态列更改为 1。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-366">As part of the Select statement, the Update statement is also executed and the Status column for the new record is changed to 1.</span></span> <span data-ttu-id="5bcb2-367">这将再次触发从 SQL Server 的另一个通知，而且适配器将收到相应通知消息，类似于以下：</span><span class="sxs-lookup"><span data-stu-id="5bcb2-367">This again triggers another notification from SQL Server and the adapter receives a corresponding notification message, that resembles the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="5bcb2-368">此消息将通知员工表中已更新某个记录。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-368">This message notifies that a record was updated in the Employee table.</span></span> <span data-ttu-id="5bcb2-369">请注意，值`<Info>`元素是"更新"。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-369">Note that the value for the `<Info>` element is “Update”.</span></span>  
  
-   <span data-ttu-id="5bcb2-370">第二个通知之后, 该适配器执行 Select 语句。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-370">After the second notification, the adapter executes the Select statement.</span></span> <span data-ttu-id="5bcb2-371">但是，因为没有记录现在具有状态为 0，适配器获取类似于以下一个空响应。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-371">However, because there are no records now that have Status as 0, the adapter gets an empty response resembling the following.</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult />   
    </SelectResponse>  
    ```  
  
## <a name="best-practices"></a><span data-ttu-id="5bcb2-372">最佳实践</span><span class="sxs-lookup"><span data-stu-id="5bcb2-372">Best Practices</span></span>  
 <span data-ttu-id="5bcb2-373">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-373">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="5bcb2-374">后生成绑定文件，你可以导入的配置设置文件，以便不需要创建发送端口和接收相同的业务流程的端口。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-374">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="5bcb2-375">有关绑定文件的详细信息，请参阅[重用 SQL 适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcb2-375">For more information about binding files, see [Reuse SQL adapter bindings](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5bcb2-376">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bcb2-376">See Also</span></span>  
 [<span data-ttu-id="5bcb2-377">接收使用 BizTalk Server 的 SQL 查询通知</span><span class="sxs-lookup"><span data-stu-id="5bcb2-377">Receive SQL Query Notifications using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)