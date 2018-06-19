---
title: 接收以增量方式使用 BizTalk Server 的 Oracle 数据库更改通知 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17cef39f-a1aa-4f46-993f-620008f3890d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eebcd37124e0ddde2171f21b233ca8bd8ce23f55
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967323"
---
# <a name="receive-oracle-database-change-notifications-incrementally-using-biztalk-server"></a><span data-ttu-id="36193-102">接收以增量方式使用 BizTalk Server 的 Oracle 数据库更改通知</span><span class="sxs-lookup"><span data-stu-id="36193-102">Receive Oracle Database change notifications incrementally using BizTalk Server</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="36193-103">为了简便起见，本主题仅介绍如何以增量方式接收通知。</span><span class="sxs-lookup"><span data-stu-id="36193-103">For the sake of brevity, this topic only describes how to receive notifications incrementally.</span></span> <span data-ttu-id="36193-104">在业务方案中，业务流程理想情况下必须包含提取的收到的通知消息的种类，然后执行所有后续操作的逻辑。</span><span class="sxs-lookup"><span data-stu-id="36193-104">In business scenarios, the orchestration must ideally include the logic to extract the kind of notification message received and then perform any subsequent operations.</span></span> <span data-ttu-id="36193-105">换而言之，本主题中所述的业务流程必须基于业务流程中所述[过程通知消息来完成特定任务在 Oracle 数据库中使用 BizTalk Sever](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-105">In other words, the orchestration described in this topic must be built on top of the orchestration described in [Process Notification Messages to complete Specific Tasks in Oracle Database using BizTalk Sever](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md).</span></span>  
  
 <span data-ttu-id="36193-106">本主题演示如何配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]要接收来自 Oracle 增量查询通知邮件。</span><span class="sxs-lookup"><span data-stu-id="36193-106">This topic demonstrates how to configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive incremental query notification messages from Oracle.</span></span> <span data-ttu-id="36193-107">为了演示增量通知，我们认为，ACCOUNTACTIVITY，具有列的表"处理"。</span><span class="sxs-lookup"><span data-stu-id="36193-107">To demonstrate incremental notifications, we consider a table, ACCOUNTACTIVITY, with a “Processed” column.</span></span> <span data-ttu-id="36193-108">一条新记录插入到此表时，"处理"列的值设置为 ' n '。</span><span class="sxs-lookup"><span data-stu-id="36193-108">When a new record is inserted to this table, the value of the “Processed” column is set to ‘n’.</span></span> <span data-ttu-id="36193-109">你可以配置适配器后，通过执行以下操作中接收增量通知：</span><span class="sxs-lookup"><span data-stu-id="36193-109">You can configure the adapter to receive incremental notifications by doing the following:</span></span>  
  
-   <span data-ttu-id="36193-110">注册通知使用检索到的具有"处理"列的所有记录的 SELECT 语句 ' n '。</span><span class="sxs-lookup"><span data-stu-id="36193-110">Register for notifications using a SELECT statement that retrieves all records that have “Processed” column as ‘n’.</span></span> <span data-ttu-id="36193-111">你可以通过指定的 SELECT 语句来实现**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="36193-111">You can do so by specifying the SELECT statement for the **NotificationStatement** binding property.</span></span>  
  
-   <span data-ttu-id="36193-112">对于已接到通知有关的行，更新为 y 的"处理"列。</span><span class="sxs-lookup"><span data-stu-id="36193-112">For rows which have been notified for, update the “Processed” column to ‘y’.</span></span>  
  
 <span data-ttu-id="36193-113">本主题演示如何创建 BizTalk 业务流程和配置 BizTalk 应用程序来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="36193-113">This topic demonstrates how to create a BizTalk orchestration and configure a BizTalk application to achieve this.</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-database-adapter-binding-properties"></a><span data-ttu-id="36193-114">与 Oracle 数据库适配器绑定属性中配置通知</span><span class="sxs-lookup"><span data-stu-id="36193-114">Configuring Notifications with the Oracle Database Adapter Binding Properties</span></span>  
 <span data-ttu-id="36193-115">下表总结了[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，用于配置从 Oracle 数据库接收通知。</span><span class="sxs-lookup"><span data-stu-id="36193-115">The following table summarizes the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties that you use to configure receiving notifications from the Oracle database.</span></span> <span data-ttu-id="36193-116">配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="36193-116">You must specify these binding properties while configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36193-117">你可以选择在生成的架构时指定这些绑定属性**通知**操作，即使它不是强制性。</span><span class="sxs-lookup"><span data-stu-id="36193-117">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="36193-118">如果这样做，端口绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含你指定的绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="36193-118">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="36193-119">你稍后导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义或 WCF OracleDB 接收属性已设置对绑定的端口。</span><span class="sxs-lookup"><span data-stu-id="36193-119">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-OracleDB receive port with the binding properties already set.</span></span> <span data-ttu-id="36193-120">有关创建接收端口使用绑定文件的详细信息，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-120">For more information about creating a receive port using the binding file, see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span>  
  
|<span data-ttu-id="36193-121">绑定属性</span><span class="sxs-lookup"><span data-stu-id="36193-121">Binding Property</span></span>|<span data-ttu-id="36193-122">Description</span><span class="sxs-lookup"><span data-stu-id="36193-122">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="36193-123">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="36193-123">**InboundOperationType**</span></span>|<span data-ttu-id="36193-124">指定你想要执行的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="36193-124">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="36193-125">若要接收通知消息，请将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="36193-125">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="36193-126">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="36193-126">**NotificationPort**</span></span>|<span data-ttu-id="36193-127">指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。</span><span class="sxs-lookup"><span data-stu-id="36193-127">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="36193-128">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="36193-128">**NotificationStatement**</span></span>|<span data-ttu-id="36193-129">指定用来注册查询通知的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="36193-129">Specifies the SELECT statement used to register for query notifications.</span></span> <span data-ttu-id="36193-130">仅当指定的 SELECT 语句更改的结果集时，适配器获取一条通知消息。</span><span class="sxs-lookup"><span data-stu-id="36193-130">The adapter gets a notification message only when the result set for the specified SELECT statement changes.</span></span>|  
|<span data-ttu-id="36193-131">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="36193-131">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="36193-132">指定启动侦听器时，适配器是否发送到适配器客户端通知。</span><span class="sxs-lookup"><span data-stu-id="36193-132">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="36193-133">有关这些属性的更完整说明，请参阅[Oracle 数据库绑定属性的使用 BizTalk Adapter](https://msdn.microsoft.com/library/dd788467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="36193-133">For a more complete description of these properties, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span> <span data-ttu-id="36193-134">有关如何使用的完整说明[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]若要从 Oracle 数据库接收通知，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="36193-134">For a complete description of how to use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive notifications from the Oracle database, read further.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="36193-135">本主题演示接收通知消息的方式</span><span class="sxs-lookup"><span data-stu-id="36193-135">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="36193-136">在此主题中，以演示如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持从 Oracle 数据库中接收增量数据库更改通知消息的功能，我们将配置的适配器接收到 ACCOUNTACTIVTY 表的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="36193-136">In this topic, to demonstrate how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports receiving incremental database change notification messages from the Oracle database, we will configure the adapter to receive notifications for changes to the ACCOUNTACTIVTY table.</span></span> <span data-ttu-id="36193-137">让我们假定 ACCOUNTACTIVITY 表具有"TID"、"帐户"和"处理"的列。</span><span class="sxs-lookup"><span data-stu-id="36193-137">Let us assume that the ACCOUNTACTIVITY table has columns “TID”, “Account”, and “Processed”.</span></span> <span data-ttu-id="36193-138">每当添加一条新记录，"处理"列的值设置为 ' n '。</span><span class="sxs-lookup"><span data-stu-id="36193-138">Whenever a new record is added, the value of the “Processed” column is set to ‘n’.</span></span> <span data-ttu-id="36193-139">因此，若要获取增量通知并将需要作为 BizTalk 业务流程的一部分执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="36193-139">So, to get incremental notifications you will have to do the following tasks as part of the BizTalk orchestration:</span></span>  
  
-   <span data-ttu-id="36193-140">获取"处理"所在的所有记录的通知 ' n '。</span><span class="sxs-lookup"><span data-stu-id="36193-140">Get notification for all records where “Processed” is ‘n’.</span></span> <span data-ttu-id="36193-141">你可以指定为通知语句的 SELECT 语句来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="36193-141">You can do this by specifying a SELECT statement as a notification statement.</span></span>  
  
-   <span data-ttu-id="36193-142">对于某些记录收到通知后，设置为 y 的"处理"。</span><span class="sxs-lookup"><span data-stu-id="36193-142">After the notification is received for a certain record, set “Processed” to ‘y’.</span></span> <span data-ttu-id="36193-143">可以通过执行存储的过程，PROCESS_RECORDS，这将更新的"处理"列来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="36193-143">You can do this by executing a stored procedure, PROCESS_RECORDS, which updates the “Processed” column.</span></span>  
  
 <span data-ttu-id="36193-144">为了演示接收增量通知，我们执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="36193-144">To demonstrate receiving incremental notifications, we do the following:</span></span>  
  
-   <span data-ttu-id="36193-145">生成架构**通知**（入站操作），和**PROCESS_RECORDS** （出站操作） ACCOUNTACTIVITY 表。</span><span class="sxs-lookup"><span data-stu-id="36193-145">Generate schema for the **Notification** (inbound operation), and **PROCESS_RECORDS** (outbound operation) on the ACCOUNTACTIVITY table.</span></span>  
  
-   <span data-ttu-id="36193-146">创建具有以下业务流程：</span><span class="sxs-lookup"><span data-stu-id="36193-146">Create an orchestration that has the following:</span></span>  
  
    -   <span data-ttu-id="36193-147">接收位置接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="36193-147">A receive location to receive notification messages.</span></span> <span data-ttu-id="36193-148">可通过指定为 SELECT 语句来配置通知：</span><span class="sxs-lookup"><span data-stu-id="36193-148">You can configure for notification by specifying the SELECT statement as:</span></span>  
  
        ```  
        SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="36193-149">您必须指定架构名称以及表名称。</span><span class="sxs-lookup"><span data-stu-id="36193-149">You must specify the table name along with the schema name.</span></span> <span data-ttu-id="36193-150">例如， `SCOTT.ACCOUNTACTIVITY`。</span><span class="sxs-lookup"><span data-stu-id="36193-150">For example, `SCOTT.ACCOUNTACTIVITY`.</span></span>  
  
    -   <span data-ttu-id="36193-151">若要更新已为其发送通知的行发送端口。</span><span class="sxs-lookup"><span data-stu-id="36193-151">A send port to update the rows for which notification has already been sent.</span></span> <span data-ttu-id="36193-152">在此端口设置为 y 收到通知时的记录的"处理"列的值，则将执行 PROCESS_RECORDS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="36193-152">You will execute the PROCESS_RECORDS stored procedure on this port to set the value of “Processed” column to ‘y’ for the records for which notification is received.</span></span>  
  
         <span data-ttu-id="36193-153">请注意后接收通知消息，以便这些已处理的行进行更新，必须执行此操作。</span><span class="sxs-lookup"><span data-stu-id="36193-153">Note that this operation must be executed after receiving the notification messages so that the processed rows are updated.</span></span> <span data-ttu-id="36193-154">若要使用正在等待获取通知响应，然后手动删除要执行 PROCESS_RECORDS 过程的请求消息的开销，执行操作时，将生成 PROCESS_RECORDS 过程中业务流程本身的请求消息。</span><span class="sxs-lookup"><span data-stu-id="36193-154">To do away with the overhead of waiting to get the notification response and then manually dropping a request message to execute the PROCESS_RECORDS procedure, you will generate the request message for PROCESS_RECORDS procedure within the orchestration itself.</span></span> <span data-ttu-id="36193-155">你可以通过使用来实现**构造消息**形状中业务流程。</span><span class="sxs-lookup"><span data-stu-id="36193-155">You can do so by using the **Construct Message** shape within an orchestration.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-the-oracle-database"></a><span data-ttu-id="36193-156">如何从 Oracle 数据库接收通知消息</span><span class="sxs-lookup"><span data-stu-id="36193-156">How to Receive Notification Messages from the Oracle database</span></span>  
 <span data-ttu-id="36193-157">使用 Oracle 数据库上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-157">Performing an operation on the Oracle database using [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md).</span></span> <span data-ttu-id="36193-158">若要配置的适配器以接收通知消息，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="36193-158">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1.  <span data-ttu-id="36193-159">创建 BizTalk 项目，然后生成架构**通知**（入站操作） 和**PROCESS_RECORDS** ACCOUNTACTIVITY 表上的过程 （出站操作）。</span><span class="sxs-lookup"><span data-stu-id="36193-159">Create a BizTalk project, and then generate schema for the **Notification** (inbound operation) and **PROCESS_RECORDS** procedure (outbound operation) on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="36193-160">（可选） 你可以为指定值**InboundOperationType**， **NotificationPort**，和**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="36193-160">Optionally, you can specify values for the **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties.</span></span>  
  
2.  <span data-ttu-id="36193-161">在从 Oracle 数据库接收通知的 BizTalk 项目中创建一条消息。</span><span class="sxs-lookup"><span data-stu-id="36193-161">Create a message in the BizTalk project for receiving notification from the Oracle database.</span></span>  
  
3.  <span data-ttu-id="36193-162">创建 BizTalk 项目用于执行 PROCESS_RECORDS 存储过程和接收响应消息中的消息。</span><span class="sxs-lookup"><span data-stu-id="36193-162">Create messages in the BizTalk project for executing the PROCESS_RECORDS stored procedure and receiving response messages.</span></span>  
  
4.  <span data-ttu-id="36193-163">创建业务流程中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="36193-163">Create an orchestration that does the following:</span></span>  
  
    -   <span data-ttu-id="36193-164">从 Oracle 数据库接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="36193-164">Receives notification message from the Oracle database.</span></span>  
  
    -   <span data-ttu-id="36193-165">创建消息，以执行 PROCESS_RECORDS 过程。</span><span class="sxs-lookup"><span data-stu-id="36193-165">Creates a message to execute the PROCESS_RECORDS procedure.</span></span>  
  
    -   <span data-ttu-id="36193-166">将此邮件发送到 Oracle 数据库选择和更新的记录，收到的响应。</span><span class="sxs-lookup"><span data-stu-id="36193-166">Sends this message to the Oracle database to select and update the records and receive a response.</span></span>  
  
5.  <span data-ttu-id="36193-167">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="36193-167">Build and deploy the BizTalk project.</span></span>  
  
6.  <span data-ttu-id="36193-168">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="36193-168">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="36193-169">对于入站操作，如接收通知消息，你必须仅配置单向的 WCF 自定义或 WCF OracleDB 接收端口。</span><span class="sxs-lookup"><span data-stu-id="36193-169">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-OracleDB receive port.</span></span> <span data-ttu-id="36193-170">双向接收入站操作不支持端口。</span><span class="sxs-lookup"><span data-stu-id="36193-170">Two-way receive ports are not supported for inbound operations.</span></span>  
  
7.  <span data-ttu-id="36193-171">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="36193-171">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="36193-172">本主题提供执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="36193-172">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="36193-173">生成架构</span><span class="sxs-lookup"><span data-stu-id="36193-173">Generating Schema</span></span>  
 <span data-ttu-id="36193-174">必须生成的架构**通知**操作和**PROCESS_RECORDS**过程。</span><span class="sxs-lookup"><span data-stu-id="36193-174">You must generate the schema for the **Notification** operation and **PROCESS_RECORDS** procedure.</span></span> <span data-ttu-id="36193-175">请参阅[检索用于 Oracle 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="36193-175">See [Retrieve metadata for Oracle operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) for more information about how to generate the schema.</span></span> <span data-ttu-id="36193-176">生成架构时，请执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="36193-176">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="36193-177">如果你不想要指定的绑定属性在设计时，跳过的第一步。</span><span class="sxs-lookup"><span data-stu-id="36193-177">Skip the first step if you do not want to specify the binding properties at design-time.</span></span>  
  
1.  <span data-ttu-id="36193-178">为指定值**InboundOperationType**， **NotificationPort**，和**NotificationStatement**生成架构时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="36193-178">Specify a value for **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="36193-179">有关此绑定属性的详细信息，请参阅[Oracle 数据库绑定属性的使用 BizTalk Adapter](https://msdn.microsoft.com/library/dd788467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="36193-179">For more information about this binding property, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span> <span data-ttu-id="36193-180">有关如何指定绑定属性的说明，请参阅[指定绑定属性](https://msdn.microsoft.com/library/dd788420.aspx)。</span><span class="sxs-lookup"><span data-stu-id="36193-180">For instructions on how to specify binding properties, see [Specifying Binding Properties](https://msdn.microsoft.com/library/dd788420.aspx).</span></span>  
  
2.  <span data-ttu-id="36193-181">选择与具有协定类型**服务 （入站操作）**。</span><span class="sxs-lookup"><span data-stu-id="36193-181">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="36193-182">生成架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="36193-182">Generate schema for the **Notification** operation.</span></span>  
  
4.  <span data-ttu-id="36193-183">选择与具有协定类型**客户端 （出站操作）**。</span><span class="sxs-lookup"><span data-stu-id="36193-183">Select the contract type as **Client (Outbound operations)**.</span></span>  
  
5.  <span data-ttu-id="36193-184">生成架构**PROCESS_RECORDS**过程。</span><span class="sxs-lookup"><span data-stu-id="36193-184">Generate schema for the **PROCESS_RECORDS** procedure.</span></span> <span data-ttu-id="36193-185">此过程位于下**ACCOUNT_PKG**包。</span><span class="sxs-lookup"><span data-stu-id="36193-185">This procedure is available under the **ACCOUNT_PKG** package.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="36193-186">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="36193-186">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="36193-187">你先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="36193-187">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="36193-188">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="36193-188">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="36193-189">后生成架构，你必须将其从 BizTalk 项目的业务流程视图链接到消息中。</span><span class="sxs-lookup"><span data-stu-id="36193-189">Once the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="36193-190">对于本主题中，你必须创建三个消息 — 一个用于从 Oracle 数据库、 一个用于执行 PROCESS_RECORDS 过程中，和一个用于接收过程的响应中接收通知。</span><span class="sxs-lookup"><span data-stu-id="36193-190">For this topic, you must create three messages—one to receive notifications from the Oracle database, one to execute the PROCESS_RECORDS procedure, and one to receive the response for the procedure.</span></span>  
  
 <span data-ttu-id="36193-191">执行以下步骤以创建消息并将它们链接到架构。</span><span class="sxs-lookup"><span data-stu-id="36193-191">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="36193-192">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="36193-192">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="36193-193">BizTalk 项目中添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="36193-193">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="36193-194">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="36193-194">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="36193-195">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="36193-195">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="36193-196">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="36193-196">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="36193-197">单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="36193-197">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="36193-198">在**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="36193-198">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="36193-199">右键单击新创建的消息中，，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="36193-199">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="36193-200">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="36193-200">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="36193-201">使用此选项</span><span class="sxs-lookup"><span data-stu-id="36193-201">Use this</span></span>|<span data-ttu-id="36193-202">执行的操作</span><span class="sxs-lookup"><span data-stu-id="36193-202">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="36193-203">Identifier</span><span class="sxs-lookup"><span data-stu-id="36193-203">Identifier</span></span>|<span data-ttu-id="36193-204">键入 `NotifyReceive`。</span><span class="sxs-lookup"><span data-stu-id="36193-204">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="36193-205">消息类型</span><span class="sxs-lookup"><span data-stu-id="36193-205">Message Type</span></span>|<span data-ttu-id="36193-206">从下拉列表中，展开**架构**，然后选择*OracleNotifyIncremental.OracleDBBinding.Notification*，其中*OracleNotifyIncremental*是的名称你的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="36193-206">From the drop-down list, expand **Schemas**, and select *OracleNotifyIncremental.OracleDBBinding.Notification*, where *OracleNotifyIncremental* is the name of your BizTalk project.</span></span> <span data-ttu-id="36193-207">*OracleDBBinding*是为生成的架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="36193-207">*OracleDBBinding* is the schema generated for the **Notification** operation.</span></span>|  
  
6.  <span data-ttu-id="36193-208">重复步骤 3 以创建两条新消息。</span><span class="sxs-lookup"><span data-stu-id="36193-208">Repeat step 3 to create two new messages.</span></span> <span data-ttu-id="36193-209">在**属性**窗格中，为新的消息中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="36193-209">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="36193-210">设置为标识符</span><span class="sxs-lookup"><span data-stu-id="36193-210">Set Identifier to</span></span>|<span data-ttu-id="36193-211">将消息类型设置为</span><span class="sxs-lookup"><span data-stu-id="36193-211">Set Message Type to</span></span>|  
    |-----------------------|-------------------------|  
    |<span data-ttu-id="36193-212">过程</span><span class="sxs-lookup"><span data-stu-id="36193-212">Procedure</span></span>|<span data-ttu-id="36193-213">*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDS*，其中*OracleDBBinding1*是为生成的架构**PROCESS_RECORDS**过程。</span><span class="sxs-lookup"><span data-stu-id="36193-213">*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDS*, where  *OracleDBBinding1* is the schema generated for the **PROCESS_RECORDS** procedure.</span></span>|  
    |<span data-ttu-id="36193-214">ProcedureResponse</span><span class="sxs-lookup"><span data-stu-id="36193-214">ProcedureResponse</span></span>|<span data-ttu-id="36193-215">*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDSResponse*</span><span class="sxs-lookup"><span data-stu-id="36193-215">*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDSResponse*</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="36193-216">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="36193-216">Setting up the Orchestration</span></span>  
 <span data-ttu-id="36193-217">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为从 Oracle 数据库接收通知消息，然后更新为其接收到通知的行。</span><span class="sxs-lookup"><span data-stu-id="36193-217">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from the Oracle database and then updating the rows for which notification was received.</span></span> <span data-ttu-id="36193-218">在此业务流程，适配器接收基于 SELECT 语句为指定的通知消息**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="36193-218">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="36193-219">在文件位置接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="36193-219">The notification message is received at a FILE location.</span></span> <span data-ttu-id="36193-220">一旦收到响应，业务流程将构造一条消息，调用 PROCESS_RECORDS 过程中，将更新为其接收通知的行。</span><span class="sxs-lookup"><span data-stu-id="36193-220">Once the response is received, the orchestration constructs a message to invoke the PROCESS_RECORDS procedure, which updates the rows for which notification is received.</span></span> <span data-ttu-id="36193-221">在相同的文件位置还收到此消息的响应。</span><span class="sxs-lookup"><span data-stu-id="36193-221">The response for this message is also received at the same FILE location.</span></span>  
  
 <span data-ttu-id="36193-222">因此，您的业务流程必须包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="36193-222">So, your orchestration must contain the following:</span></span>  
  
-   <span data-ttu-id="36193-223">单向的 WCF 自定义或 WCF OracleDB 接收端口以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="36193-223">A one-way WCF-Custom or WCF-OracleDB receive port to receive notification messages.</span></span>  
  
-   <span data-ttu-id="36193-224">双向的 WCF 自定义或 WCF OracleDB 发送端口发送消息，以执行 PROCESS_RECORDS 过程。</span><span class="sxs-lookup"><span data-stu-id="36193-224">A two-way WCF-Custom or WCF-OracleDB send port to send messages to execute the PROCESS_RECORDS procedure.</span></span>  
  
-   <span data-ttu-id="36193-225">A**构造消息**构造消息，以执行 PROCESS_RECORDS 过程，业务流程中的形状。</span><span class="sxs-lookup"><span data-stu-id="36193-225">A **Construct Message** shape to construct messages, to execute PROCESS_RECORDS procedure, within the orchestration.</span></span>  
  
-   <span data-ttu-id="36193-226">文件发送端口以保存通知消息并 PROCESS_RECORDS 过程的响应。</span><span class="sxs-lookup"><span data-stu-id="36193-226">A FILE send port to save the notification message and the response for the PROCESS_RECORDS procedure.</span></span>  
  
-   <span data-ttu-id="36193-227">接收和发送形状。</span><span class="sxs-lookup"><span data-stu-id="36193-227">Receive and send shapes.</span></span>  
  
 <span data-ttu-id="36193-228">示例业务流程如下所示。</span><span class="sxs-lookup"><span data-stu-id="36193-228">A sample orchestration resembles the following.</span></span>  
  
 <span data-ttu-id="36193-229">![要从 Oracle 接收通知的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")</span><span class="sxs-lookup"><span data-stu-id="36193-229">![Orchestration to receive notifications from Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="36193-230">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="36193-230">Adding Message Shapes</span></span>  
 <span data-ttu-id="36193-231">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="36193-231">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="36193-232">刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="36193-232">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="36193-233">形状</span><span class="sxs-lookup"><span data-stu-id="36193-233">Shape</span></span>|<span data-ttu-id="36193-234">形状类型</span><span class="sxs-lookup"><span data-stu-id="36193-234">Shape Type</span></span>|<span data-ttu-id="36193-235">属性</span><span class="sxs-lookup"><span data-stu-id="36193-235">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="36193-236">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="36193-236">ReceiveNotification</span></span>|<span data-ttu-id="36193-237">Receive</span><span class="sxs-lookup"><span data-stu-id="36193-237">Receive</span></span>|<span data-ttu-id="36193-238">-将设置**名称**到*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="36193-238">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="36193-239">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="36193-239">- Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="36193-240">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="36193-240">SaveNotification</span></span>|<span data-ttu-id="36193-241">Send</span><span class="sxs-lookup"><span data-stu-id="36193-241">Send</span></span>|<span data-ttu-id="36193-242">-将设置**名称**到*SaveNotification*</span><span class="sxs-lookup"><span data-stu-id="36193-242">- Set **Name** to *SaveNotification*</span></span>|  
|<span data-ttu-id="36193-243">SendProcMessage</span><span class="sxs-lookup"><span data-stu-id="36193-243">SendProcMessage</span></span>|<span data-ttu-id="36193-244">Send</span><span class="sxs-lookup"><span data-stu-id="36193-244">Send</span></span>|<span data-ttu-id="36193-245">-将设置**名称**到*SendProcMessage*</span><span class="sxs-lookup"><span data-stu-id="36193-245">- Set **Name** to *SendProcMessage*</span></span>|  
|<span data-ttu-id="36193-246">ReceiveProcResponse</span><span class="sxs-lookup"><span data-stu-id="36193-246">ReceiveProcResponse</span></span>|<span data-ttu-id="36193-247">Receive</span><span class="sxs-lookup"><span data-stu-id="36193-247">Receive</span></span>|<span data-ttu-id="36193-248">-将设置**名称**到*ReceiveProcResponse*</span><span class="sxs-lookup"><span data-stu-id="36193-248">- Set **Name** to *ReceiveProcResponse*</span></span>|  
|<span data-ttu-id="36193-249">SaveProcResponse</span><span class="sxs-lookup"><span data-stu-id="36193-249">SaveProcResponse</span></span>|<span data-ttu-id="36193-250">Send</span><span class="sxs-lookup"><span data-stu-id="36193-250">Send</span></span>|<span data-ttu-id="36193-251">-将设置**名称**到*SaveProcResponse*</span><span class="sxs-lookup"><span data-stu-id="36193-251">- Set **Name** to *SaveProcResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="36193-252">添加构造消息形状</span><span class="sxs-lookup"><span data-stu-id="36193-252">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="36193-253">你可以使用**构造消息**形状以生成请求消息中业务流程执行 PROCESS_RECORDS 过程。</span><span class="sxs-lookup"><span data-stu-id="36193-253">You can use the **Construct Message** shape to generate a request message within the orchestration to execute the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="36193-254">若要执行此操作，你必须添加**构造消息**形状和在其中**消息分配**形状上与您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="36193-254">To do so, you must add a **Construct Message** shape and within that a **Message Assignment** shape to your orchestration.</span></span> <span data-ttu-id="36193-255">对于此示例，**消息分配**形状调用生成一条消息，发送到 Oracle 数据库执行该过程的代码。</span><span class="sxs-lookup"><span data-stu-id="36193-255">For this example, the **Message Assignment** shape invokes code that generates a message that is sent to the Oracle database to execute the procedure.</span></span> <span data-ttu-id="36193-256">**消息分配**形状还设置用于消息发送到 Oracle 数据库的操作。</span><span class="sxs-lookup"><span data-stu-id="36193-256">The **Message Assignment** shape also sets the action for the message to be sent to the Oracle database.</span></span>  
  
 <span data-ttu-id="36193-257">构造消息形状，请设置**构造消息**属性**过程**。</span><span class="sxs-lookup"><span data-stu-id="36193-257">For the construct message shape, set the **Message Constructed** property to **Procedure**.</span></span>  
  
 <span data-ttu-id="36193-258">用于生成响应的代码可能与 BizTalk 项目相同的 Visual Studio 解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="36193-258">The code to generate the response could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="36193-259">示例代码，用于生成响应消息如下所示。</span><span class="sxs-lookup"><span data-stu-id="36193-259">A sample code for generating a response message looks like this.</span></span>  
  
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
            XmlFileLocation = "C:\\TestLocation\\MessageIn";  
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
  
 <span data-ttu-id="36193-260">对于上述代码摘录中能够生成请求消息，你必须为指定的位置中具有 XML 请求消息 （针对 PROCESS_RECORDS 过程中）`XmlFileLocation`变量。</span><span class="sxs-lookup"><span data-stu-id="36193-260">For the above code excerpt to be able to generate a request message, you must have an XML request message (for the PROCESS_RECORDS procedure) in the location specified for the `XmlFileLocation` variable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36193-261">生成项目后，将在项目目录中创建 MessageCreator.dll。</span><span class="sxs-lookup"><span data-stu-id="36193-261">After you build the project, MessageCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="36193-262">必须将此 DLL 添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="36193-262">You must add this DLL to the global assembly cache (GAC).</span></span> <span data-ttu-id="36193-263">此外，你必须添加 MessageCreator.dll 作为 BizTalk 项目中的引用。</span><span class="sxs-lookup"><span data-stu-id="36193-263">Also, you must add the MessageCreator.dll as a reference in the BizTalk project.</span></span>  
  
 <span data-ttu-id="36193-264">添加以下表达式来调用此代码从**消息分配**形状以及设置用于消息的操作。</span><span class="sxs-lookup"><span data-stu-id="36193-264">Add the following expression to invoke this code from the **Message Assignment** shape and to set the action for message.</span></span> <span data-ttu-id="36193-265">若要添加一个表达式，请双击**消息分配**形状以打开表达式编辑器中。</span><span class="sxs-lookup"><span data-stu-id="36193-265">To add an expression, double-click the **Message Assignment** shape to open the Expression Editor.</span></span>  
  
```  
Procedure = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Procedure(WCF.Action) = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/PROCESS_RECORDS";  
```  
  
### <a name="adding-ports"></a><span data-ttu-id="36193-266">添加端口</span><span class="sxs-lookup"><span data-stu-id="36193-266">Adding Ports</span></span>  
 <span data-ttu-id="36193-267">请确保为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="36193-267">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="36193-268">端口列中列出的名称是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="36193-268">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="36193-269">端口</span><span class="sxs-lookup"><span data-stu-id="36193-269">Port</span></span>|<span data-ttu-id="36193-270">属性</span><span class="sxs-lookup"><span data-stu-id="36193-270">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="36193-271">OracleNotifyPort</span><span class="sxs-lookup"><span data-stu-id="36193-271">OracleNotifyPort</span></span>|<span data-ttu-id="36193-272">-将设置**标识符**到*OracleNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="36193-272">- Set **Identifier** to *OracleNotifyPort*</span></span><br /><br /> <span data-ttu-id="36193-273">-将设置**类型**到*OracleNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="36193-273">- Set **Type** to *OracleNotifyPortType*</span></span><br /><br /> <span data-ttu-id="36193-274">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="36193-274">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="36193-275">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="36193-275">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="36193-276">SaveMessagePort</span><span class="sxs-lookup"><span data-stu-id="36193-276">SaveMessagePort</span></span>|<span data-ttu-id="36193-277">-将设置**标识符**到*SaveMessagePort*</span><span class="sxs-lookup"><span data-stu-id="36193-277">- Set **Identifier** to *SaveMessagePort*</span></span><br /><br /> <span data-ttu-id="36193-278">-将设置**类型**到*SaveMessagePortType*</span><span class="sxs-lookup"><span data-stu-id="36193-278">- Set **Type** to *SaveMessagePortType*</span></span><br /><br /> <span data-ttu-id="36193-279">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="36193-279">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="36193-280">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="36193-280">- Set **Communication Direction** to *Send*</span></span><br /><br /> <span data-ttu-id="36193-281">-创建一个操作*通知*。</span><span class="sxs-lookup"><span data-stu-id="36193-281">- Create an operation *Notify*.</span></span> <span data-ttu-id="36193-282">此操作用于通知消息。</span><span class="sxs-lookup"><span data-stu-id="36193-282">This operation is used for notification messages.</span></span><br /><br /> <span data-ttu-id="36193-283">-创建一个操作*过程*。</span><span class="sxs-lookup"><span data-stu-id="36193-283">- Create an operation *Procedure*.</span></span> <span data-ttu-id="36193-284">选择响应消息将要使用此操作。</span><span class="sxs-lookup"><span data-stu-id="36193-284">This operation is used for select response messages.</span></span>|  
|<span data-ttu-id="36193-285">OracleOutboundPort</span><span class="sxs-lookup"><span data-stu-id="36193-285">OracleOutboundPort</span></span>|<span data-ttu-id="36193-286">-将设置**标识符**到*OracleOutboundPort*</span><span class="sxs-lookup"><span data-stu-id="36193-286">- Set **Identifier** to *OracleOutboundPort*</span></span><br /><br /> <span data-ttu-id="36193-287">-将设置**类型**到*OracleOutboundPortType*</span><span class="sxs-lookup"><span data-stu-id="36193-287">- Set **Type** to *OracleOutboundPortType*</span></span><br /><br /> <span data-ttu-id="36193-288">-将设置**通信模式**到*请求-响应*</span><span class="sxs-lookup"><span data-stu-id="36193-288">- Set **Communication Pattern** to *Request-Response*</span></span><br /><br /> <span data-ttu-id="36193-289">-将设置**通信方向**到*发送接收*</span><span class="sxs-lookup"><span data-stu-id="36193-289">- Set **Communication Direction** to *Send-Receive*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="36193-290">指定消息的操作形状并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="36193-290">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="36193-291">下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。</span><span class="sxs-lookup"><span data-stu-id="36193-291">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="36193-292">前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="36193-292">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="36193-293">形状</span><span class="sxs-lookup"><span data-stu-id="36193-293">Shape</span></span>|<span data-ttu-id="36193-294">属性</span><span class="sxs-lookup"><span data-stu-id="36193-294">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="36193-295">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="36193-295">ReceiveNotification</span></span>|<span data-ttu-id="36193-296">-将设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="36193-296">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="36193-297">-将设置**操作**到*OracleNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="36193-297">- Set **Operation** to *OracleNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="36193-298">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="36193-298">SaveNotification</span></span>|<span data-ttu-id="36193-299">-将设置**消息**到*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="36193-299">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="36193-300">-将设置**操作**到*SaveMessagePort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="36193-300">- Set **Operation** to *SaveMessagePort.Notify.Request*</span></span>|  
|<span data-ttu-id="36193-301">SendProcMessage</span><span class="sxs-lookup"><span data-stu-id="36193-301">SendProcMessage</span></span>|<span data-ttu-id="36193-302">-将设置**消息**到*过程*</span><span class="sxs-lookup"><span data-stu-id="36193-302">- Set **Message** to *Procedure*</span></span><br /><br /> <span data-ttu-id="36193-303">-将设置**操作**到*OracleOutboundPort.Procedure.Request*</span><span class="sxs-lookup"><span data-stu-id="36193-303">- Set **Operation** to *OracleOutboundPort.Procedure.Request*</span></span>|  
|<span data-ttu-id="36193-304">ReceiveProcResponse</span><span class="sxs-lookup"><span data-stu-id="36193-304">ReceiveProcResponse</span></span>|<span data-ttu-id="36193-305">-将设置**消息**到*ProcedureResponse*</span><span class="sxs-lookup"><span data-stu-id="36193-305">- Set **Message** to *ProcedureResponse*</span></span><br /><br /> <span data-ttu-id="36193-306">-将设置**操作**到*OracleOutboundPort.Procedure.Response*</span><span class="sxs-lookup"><span data-stu-id="36193-306">- Set **Operation** to *OracleOutboundPort.Procedure.Response*</span></span>|  
|<span data-ttu-id="36193-307">SaveProcResponse</span><span class="sxs-lookup"><span data-stu-id="36193-307">SaveProcResponse</span></span>|<span data-ttu-id="36193-308">-将设置**消息**到*ProedureResponse*</span><span class="sxs-lookup"><span data-stu-id="36193-308">- Set **Message** to *ProedureResponse*</span></span><br /><br /> <span data-ttu-id="36193-309">-将设置**操作**到*SaveMessagePort.Procedure.Request*</span><span class="sxs-lookup"><span data-stu-id="36193-309">- Set **Operation** to *SaveMessagePort.Procedure.Request*</span></span>|  
  
 <span data-ttu-id="36193-310">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="36193-310">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="36193-311">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="36193-311">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="36193-312">有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-312">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>  
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="36193-313">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="36193-313">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="36193-314">部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="36193-314">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="36193-315">必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="36193-315">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="36193-316">有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-316">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="36193-317">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="36193-317">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="36193-318">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="36193-318">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="36193-319">映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="36193-319">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="36193-320">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="36193-320">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="36193-321">定义一个物理 WCF 自定义或 WCF OracleDB 单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="36193-321">Define a physical WCF-Custom or WCF-OracleDB one-way receive port.</span></span> <span data-ttu-id="36193-322">此端口侦听来自 Oracle 数据库的通知。</span><span class="sxs-lookup"><span data-stu-id="36193-322">This port listens for notifications coming from the Oracle database.</span></span> <span data-ttu-id="36193-323">有关如何创建接收端口，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-323">For information about how to create receive ports, see [Manually configure a physical port binding to the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).</span></span> <span data-ttu-id="36193-324">请确保指定的接收端口的以下绑定属性。</span><span class="sxs-lookup"><span data-stu-id="36193-324">Make sure you specify the following binding properties for the receive port.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="36193-325">不需要执行此步骤中，如果指定在设计时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="36193-325">You do not need to perform this step if you specified the binding properties at design-time.</span></span> <span data-ttu-id="36193-326">在这种情况下，你可以创建接收端口，将设置所需的绑定的属性，通过导入所创建绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="36193-326">In such a case, you can create a receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="36193-327">有关详细信息请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-327">For more information see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span>  
  
        |<span data-ttu-id="36193-328">绑定属性</span><span class="sxs-lookup"><span data-stu-id="36193-328">Binding Property</span></span>|<span data-ttu-id="36193-329">值</span><span class="sxs-lookup"><span data-stu-id="36193-329">Value</span></span>|  
        |----------------------|-----------|  
        |<span data-ttu-id="36193-330">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="36193-330">**InboundOperationType**</span></span>|<span data-ttu-id="36193-331">将其设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="36193-331">Set this to **Notification**.</span></span>|  
        |<span data-ttu-id="36193-332">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="36193-332">**NotificationPort**</span></span>|<span data-ttu-id="36193-333">指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。</span><span class="sxs-lookup"><span data-stu-id="36193-333">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span> <span data-ttu-id="36193-334">将其设置为相同的端口号必须已添加到 Windows 防火墙例外列表。</span><span class="sxs-lookup"><span data-stu-id="36193-334">Set this to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="36193-335">有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。</span><span class="sxs-lookup"><span data-stu-id="36193-335">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span><br /><br /> <span data-ttu-id="36193-336">**重要说明：** 如果设置为默认值为-1，则你将需要完全禁用 Windows 防火墙，以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="36193-336">**Important:** If you set this to the default value of -1, you will have to completely disable Windows Firewall to receive notification messages.</span></span>|  
        |<span data-ttu-id="36193-337">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="36193-337">**NotificationStatement**</span></span>|<span data-ttu-id="36193-338">将其设置为：</span><span class="sxs-lookup"><span data-stu-id="36193-338">Set this to:</span></span><br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> <span data-ttu-id="36193-339">**注意：** 必须指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="36193-339">**Note:** You must specify the table name along with the schema name.</span></span> <span data-ttu-id="36193-340">例如， `SCOTT.ACCOUNTACTIVITY`。</span><span class="sxs-lookup"><span data-stu-id="36193-340">For example, `SCOTT.ACCOUNTACTIVITY`.</span></span>|  
        |<span data-ttu-id="36193-341">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="36193-341">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="36193-342">将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="36193-342">Set this to **True**.</span></span>|  
  
         <span data-ttu-id="36193-343">有关不同的绑定属性的详细信息，请参阅[Oracle 数据库绑定属性的使用 BizTalk Adapter](https://msdn.microsoft.com/library/dd788467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="36193-343">For more information about the different binding properties, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="36193-344">我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="36193-344">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="36193-345">你可以执行以便通过将服务添加行为配置 WCF 自定义或 WCF OracleDB 时接收端口。</span><span class="sxs-lookup"><span data-stu-id="36193-345">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-OracleDB receive port.</span></span> <span data-ttu-id="36193-346">有关如何添加服务行为的说明，请参阅[配置事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-346">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).</span></span>  
  
    -   <span data-ttu-id="36193-347">定义物理 WCF 自定义或 WCF OracleDB 发送端口将消息发送到 Oracle 数据库执行 PROCESS_REOCRDS 过程。</span><span class="sxs-lookup"><span data-stu-id="36193-347">Define a physical WCF-Custom or WCF-OracleDB send port to send messages to the Oracle database to execute the PROCESS_REOCRDS procedure.</span></span> <span data-ttu-id="36193-348">你必须在发送端口中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="36193-348">You must also specify the action in the send port.</span></span>  
  
    -   <span data-ttu-id="36193-349">硬盘和 BizTalk 业务流程将在此放置消息从 Oracle 数据库的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="36193-349">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the messages from the Oracle database.</span></span> <span data-ttu-id="36193-350">这些将是从 Oracle 数据库接收的通知消息和 PROCESS_RECORDS 过程通过 WCF 自定义执行的消息或 WCF OracleDB 发送端口。</span><span class="sxs-lookup"><span data-stu-id="36193-350">These will be the notification messages received from the Oracle database and messages for the PROCESS_RECORDS procedure you execute through the WCF-Custom or WCF-OracleDB send port.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="36193-351">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="36193-351">Starting the Application</span></span>  
 <span data-ttu-id="36193-352">你必须启动 BizTalk 应用程序用于接收从 Oracle 数据库的通知消息以及用于执行 PROCESS_RECORDS 过程。</span><span class="sxs-lookup"><span data-stu-id="36193-352">You must start the BizTalk application for receiving notification messages from the Oracle database and for executing the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="36193-353">有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-353">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="36193-354">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="36193-354">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="36193-355">WCF 自定义或 WCF OracleDB 单向接收端口，从而从 Oracle 数据库运行时接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="36193-355">The WCF-Custom or WCF-OracleDB one-way receive port, which receives the notification messages from the Oracle database is running.</span></span>  
  
-   <span data-ttu-id="36193-356">WCF 自定义或 WCF OracleDB 发送端口，以执行 PROCESS_RECORDS 过程正在运行。</span><span class="sxs-lookup"><span data-stu-id="36193-356">The WCF-Custom or WCF-OracleDB send port to execute the PROCESS_RECORDS procedure is running.</span></span>  
  
-   <span data-ttu-id="36193-357">文件发送端口，从而从 Oracle 数据库中接收消息，正在运行。</span><span class="sxs-lookup"><span data-stu-id="36193-357">The FILE send port, which receives messages from the Oracle database, is running.</span></span>  
  
-   <span data-ttu-id="36193-358">BizTalk 业务流程操作正在运行。</span><span class="sxs-lookup"><span data-stu-id="36193-358">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="36193-359">执行该操作</span><span class="sxs-lookup"><span data-stu-id="36193-359">Executing the Operation</span></span>  
 <span data-ttu-id="36193-360">假定 ACCOUNTACTIVITY 表已经有一些记录。</span><span class="sxs-lookup"><span data-stu-id="36193-360">Assume that the ACCOUNTACTIVITY table already has some records.</span></span> <span data-ttu-id="36193-361">此外，请确保要执行 PROCESS_RECORDS 过程的 XML 消息位于 C:\TestLocation\MessageIn。</span><span class="sxs-lookup"><span data-stu-id="36193-361">Also, make sure the XML message to execute PROCESS_RECORDS procedure is available at C:\TestLocation\MessageIn.</span></span> <span data-ttu-id="36193-362">XML 文件应如下所示：</span><span class="sxs-lookup"><span data-stu-id="36193-362">The XML file should resemble the following:</span></span>  
  
```  
<PROCESS_RECORDS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"/>  
```  
  
 <span data-ttu-id="36193-363">BizTalk 业务流程启动后，以下一组操作将会发生，在相同的序列：</span><span class="sxs-lookup"><span data-stu-id="36193-363">Once the BizTalk orchestration is started, the following set of actions take place, in the same sequence:</span></span>  
  
-   <span data-ttu-id="36193-364">适配器将接收通知消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="36193-364">The adapter receives a notification message that resembles the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?\>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleDBBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="36193-365">此消息将通知以接收通知消息的接收端口已启动。</span><span class="sxs-lookup"><span data-stu-id="36193-365">This message notifies that the receive port for receiving the notification messages is started.</span></span> <span data-ttu-id="36193-366">请注意，值`<Info>`元素是"ListnerStarted"。</span><span class="sxs-lookup"><span data-stu-id="36193-366">Note that the value for the `<Info>` element is “ListnerStarted”.</span></span>  
  
-   <span data-ttu-id="36193-367">适配器执行 PROCESS_RECORDS 过程。</span><span class="sxs-lookup"><span data-stu-id="36193-367">The adapter executes the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="36193-368">从 Oracle 数据库的下一步响应适用于该过程。</span><span class="sxs-lookup"><span data-stu-id="36193-368">The next response from the Oracle database is for the procedure.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
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
            <TID>1</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
          <NewTable>  
            ......  
            ......  
          </NewTable>  
          ......  
          ......  
        </NewDataSet>  
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
     <span data-ttu-id="36193-369">这是 SELECT 语句执行 PROCESS_RECORDS 过程中响应。</span><span class="sxs-lookup"><span data-stu-id="36193-369">This is the response for the SELECT statement execute as part of the PROCESS_RECORDS procedure.</span></span>  
  
-   <span data-ttu-id="36193-370">PROCESS_RECORDS 过程还会更新要设置为 y 的处理的行。</span><span class="sxs-lookup"><span data-stu-id="36193-370">The PROCESS_RECORDS procedure also updates the rows to set PROCESSED to ‘y’.</span></span> <span data-ttu-id="36193-371">因此，该适配器接收更新操作的另一个通知。</span><span class="sxs-lookup"><span data-stu-id="36193-371">Hence, the adapter receives another notification for the Update operation.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="36193-372">请注意，`Info`元素包含"更新"。</span><span class="sxs-lookup"><span data-stu-id="36193-372">Note that the `Info` element contains “Update”.</span></span>  
  
-   <span data-ttu-id="36193-373">第二个通知之后, 该适配器再次执行 PROCESS_RECORDS 过程。</span><span class="sxs-lookup"><span data-stu-id="36193-373">After the second notification, the adapter again executes the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="36193-374">但是，现在其中处理列设置为任何记录，因为 ' n '，该过程返回与下面类似的一个空响应。</span><span class="sxs-lookup"><span data-stu-id="36193-374">However, now because there are no records where PROCESSED column is set to ‘n’, the procedure returns an empty response resembling the following.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="" />   
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
## <a name="best-practices"></a><span data-ttu-id="36193-375">最佳实践</span><span class="sxs-lookup"><span data-stu-id="36193-375">Best Practices</span></span>  
 <span data-ttu-id="36193-376">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="36193-376">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="36193-377">后生成绑定文件，你可以导入的配置设置文件，以便不需要创建发送端口和接收相同的业务流程的端口。</span><span class="sxs-lookup"><span data-stu-id="36193-377">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="36193-378">有关绑定文件的详细信息，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="36193-378">For more information about binding files, see [Reuse Oracle Database Adapter bindings](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36193-379">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36193-379">See Also</span></span>  
 [<span data-ttu-id="36193-380">使用 BizTalk Server 的接收 Oracle 数据库更改通知</span><span class="sxs-lookup"><span data-stu-id="36193-380">Receiving Oracle Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)