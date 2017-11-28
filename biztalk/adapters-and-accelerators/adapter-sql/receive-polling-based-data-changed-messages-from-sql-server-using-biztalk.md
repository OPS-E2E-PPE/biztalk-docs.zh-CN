---
title: "使用 BizTalk Server 从 SQL Server 接收基于轮询的数据更改消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ecaf6f7-974b-4487-8c65-d1ab628cbfeb
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b86a58a092f5f38c4a09c014feb0b4fe85d1fc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a><span data-ttu-id="cc698-102">使用 BizTalk Server 从 SQL Server 接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="cc698-102">Receive Polling-based Data-changed Messages from SQL Server using BizTalk Server</span></span>
<span data-ttu-id="cc698-103">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来接收 SQL Server 表或视图的定期的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="cc698-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="cc698-104">你可以指定适配器执行轮询数据库轮询语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="cc698-105">轮询语句可以是 SELECT 语句或存储的过程返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="cc698-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  

  
 <span data-ttu-id="cc698-106">有关如何的适配器支持轮询的详细信息，请参阅[进行轮询的支持](https://msdn.microsoft.com/library/dd788416.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cc698-106">For more information on how the adapter supports polling, see [Support for Polling](https://msdn.microsoft.com/library/dd788416.aspx).</span></span> <span data-ttu-id="cc698-107">有关轮询操作的 SOAP 消息结构的信息，请参阅[轮询和 TypedPolling 操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-107">For information about the structure of the SOAP message for polling operations, see [Message Schemas for the Polling and TypedPolling Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc698-108">本主题演示如何使用**轮询**入站操作人员使用轮询消息。</span><span class="sxs-lookup"><span data-stu-id="cc698-108">This topic demonstrates how to use the **Polling** inbound operation to use polling messages.</span></span> <span data-ttu-id="cc698-109">轮询操作的消息不是强类型，以及在运行时消息检索轮询的对象的架构。</span><span class="sxs-lookup"><span data-stu-id="cc698-109">The message for the Polling operation is not strongly-typed and schema of the object being polled is retrieved along with the message at run-time.</span></span> <span data-ttu-id="cc698-110">如果你想要获取强类型的轮询消息，则必须使用**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="cc698-110">If you want to get strongly-typed polling message, you must use the **TypedPolling** operation.</span></span> <span data-ttu-id="cc698-111">你还必须使用**TypedPolling**操作以单个的 BizTalk 应用程序中有多个轮询操作。</span><span class="sxs-lookup"><span data-stu-id="cc698-111">You must also use the **TypedPolling** operation to have multiple polling operations in a single BizTalk application.</span></span> <span data-ttu-id="cc698-112">有关说明如何执行**TypedPolling**操作，请参阅[接收强类型轮询基于的数据更改消息从 SQL Server 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-112">For instructions on how to perform **TypedPolling** operation, see [Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc698-113">如果你想要单个的 BizTalk 应用程序中有多个轮询操作，你必须指定**InboundID**作为连接以使其唯一的 URI 的一部分的连接属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-113">If you want to have more than one polling operation in a single BizTalk application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="cc698-114">使用唯一连接 URI，你可以创建多个接收轮询同一数据库中或甚至同一个表在数据库中的端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-114">With a unique connection URI, you can create multiple receive ports that poll the same database, or even the same table in a database.</span></span> <span data-ttu-id="cc698-115">有关详细信息，请参阅[接收轮询消息跨多个接收端口从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-115">For more information, see [Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="cc698-116">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="cc698-116">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="cc698-117">在此主题中，以演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收数据的支持更改消息、 创建 BizTalk 项目和生成架构**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="cc698-117">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a BizTalk project and generate schema for the **Polling** operation.</span></span> <span data-ttu-id="cc698-118">如果你想要指定轮询相关在设计时绑定属性，指定**PolledDataAvailableStatement**作为：</span><span class="sxs-lookup"><span data-stu-id="cc698-118">If you want to specify the polling related binding properties at design time, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="cc698-119">**PolledDataAvailableStatement**必须返回具有包含正值的第一个单元格的结果集。</span><span class="sxs-lookup"><span data-stu-id="cc698-119">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="cc698-120">如果第一个单元格不包含是正数值，该适配器将不会执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-120">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="cc698-121">作为轮询语句的一部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc698-121">As part of the polling statement, perform the following operations:</span></span>  
  
-   <span data-ttu-id="cc698-122">从员工表中选择所有行。</span><span class="sxs-lookup"><span data-stu-id="cc698-122">Select all the rows from the Employee table.</span></span>  
  
-   <span data-ttu-id="cc698-123">执行存储的过程 (MOVE_EMP_DATA) 将从员工表到 EmployeeHistory 表的所有记录。</span><span class="sxs-lookup"><span data-stu-id="cc698-123">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
-   <span data-ttu-id="cc698-124">执行存储的过程 (ADD_EMP_DETAILS) 将一条新记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="cc698-124">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="cc698-125">此过程使用雇员姓名、 名称以及薪金作为参数。</span><span class="sxs-lookup"><span data-stu-id="cc698-125">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="cc698-126">若要执行这些操作，必须指定以下项作为**PollingStatement**绑定属性：</span><span class="sxs-lookup"><span data-stu-id="cc698-126">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="cc698-127">执行轮询语句后，选择从 Employee 表的所有记录，并从 SQL Server 消息拖放到接收位置。</span><span class="sxs-lookup"><span data-stu-id="cc698-127">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is dropped to a receive location.</span></span> <span data-ttu-id="cc698-128">一旦 MOVE_EMP_DATA 存储过程执行适配器，所有记录都移动到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="cc698-128">Once the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="cc698-129">然后，执行 ADD_EMP_DETAILS 存储过程将一条新记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="cc698-129">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="cc698-130">下一次轮询执行将只返回单个记录。</span><span class="sxs-lookup"><span data-stu-id="cc698-130">The next polling execution will only return a single record.</span></span> <span data-ttu-id="cc698-131">此循环将持续，直到您禁用接收轮询 SQL Server 的端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-131">This cycle continues until you disable the receive port that polls SQL Server.</span></span>  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="cc698-132">配置与 SQL 适配器绑定属性的轮询查询</span><span class="sxs-lookup"><span data-stu-id="cc698-132">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="cc698-133">下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-133">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="cc698-134">配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="cc698-134">You must specify these binding properties while configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc698-135">你可以选择在生成的架构时指定这些绑定属性**轮询**操作，即使它不是强制性。</span><span class="sxs-lookup"><span data-stu-id="cc698-135">You may choose to specify these binding properties when generating the schema for the **Polling** operation, even though it is not mandatory.</span></span> <span data-ttu-id="cc698-136">如果这样做，端口绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含你指定的绑定属性的值。</span><span class="sxs-lookup"><span data-stu-id="cc698-136">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="cc698-137">你稍后导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义或 WCF SQL 接收属性已设置对绑定的端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-137">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-SQL receive port with the binding properties already set.</span></span> <span data-ttu-id="cc698-138">有关创建使用绑定文件的端口的详细信息，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-138">For more information about creating a port using the binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
|<span data-ttu-id="cc698-139">绑定属性</span><span class="sxs-lookup"><span data-stu-id="cc698-139">Binding Property</span></span>|<span data-ttu-id="cc698-140">Description</span><span class="sxs-lookup"><span data-stu-id="cc698-140">Description</span></span>|  
|---|---|  
|<span data-ttu-id="cc698-141">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="cc698-141">**InboundOperationType**</span></span>|<span data-ttu-id="cc698-142">指定是否想要执行**轮询**， **TypedPolling**，或**通知**入站操作。</span><span class="sxs-lookup"><span data-stu-id="cc698-142">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="cc698-143">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="cc698-143">Default is **Polling**.</span></span>|  
|<span data-ttu-id="cc698-144">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="cc698-144">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="cc698-145">指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-145">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="cc698-146">SQL 语句必须返回的结果集行和列组成。</span><span class="sxs-lookup"><span data-stu-id="cc698-146">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="cc698-147">仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-147">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="cc698-148">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="cc698-148">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="cc698-149">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-149">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="cc698-150">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="cc698-150">The default is 30 seconds.</span></span> <span data-ttu-id="cc698-151">轮询间隔确定连续两次轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="cc698-151">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="cc698-152">如果在指定间隔内执行该语句，该适配器将等待的间隔中的剩余时间。</span><span class="sxs-lookup"><span data-stu-id="cc698-152">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="cc698-153">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="cc698-153">**PollingStatement**</span></span>|<span data-ttu-id="cc698-154">指定要轮询的 SQL Server 数据库表的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-154">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="cc698-155">你可以指定简单的 SELECT 语句或存储的过程轮询语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-155">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="cc698-156">默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="cc698-156">The default is null.</span></span> <span data-ttu-id="cc698-157">必须指定的值**PollingStatement**来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="cc698-157">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="cc698-158">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-158">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="cc698-159">你可以指定任意数量的以分号分隔的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-159">You can specify any number of SQL statements separated by a semi-colon.</span></span>|  
|<span data-ttu-id="cc698-160">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="cc698-160">**PollWhileDataFound**</span></span>|<span data-ttu-id="cc698-161">指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略轮询间隔和连续执行为指定的 SQL 语句**PolledDataAvailableStatement**绑定属性，如果数据中轮询的表。</span><span class="sxs-lookup"><span data-stu-id="cc698-161">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="cc698-162">如果表中可用的任何数据不，该适配器将恢复执行 SQL 语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="cc698-162">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="cc698-163">默认值是**false**。</span><span class="sxs-lookup"><span data-stu-id="cc698-163">Default is **false**.</span></span>|  
  
 <span data-ttu-id="cc698-164">有关这些属性的更完整说明，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-164">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="cc698-165">有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，进一步阅读。</span><span class="sxs-lookup"><span data-stu-id="cc698-165">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  
  
## <a name="how-to-receive-data-change-messages-from-the-sql-server-database"></a><span data-ttu-id="cc698-166">如何从 SQL Server 数据库中接收数据更改消息</span><span class="sxs-lookup"><span data-stu-id="cc698-166">How to Receive Data-change Messages from the SQL Server Database</span></span>  
 <span data-ttu-id="cc698-167">使用 SQL Server 数据库上执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[开发与 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-167">Performing an operation on the SQL Server database using [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md).</span></span> <span data-ttu-id="cc698-168">若要配置接收数据更改消息的适配器，这些任务包括：</span><span class="sxs-lookup"><span data-stu-id="cc698-168">To configure the adapter to receive data-change messages, these tasks are:</span></span>  
  
1.  <span data-ttu-id="cc698-169">创建 BizTalk 项目，然后生成架构**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="cc698-169">Create a BizTalk project, and then generate schema for the **Polling** operation.</span></span> <span data-ttu-id="cc698-170">（可选） 你可以为指定值**PolledDataAvailableStatement**和**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-170">Optionally, you can specify values for the **PolledDataAvailableStatement** and **PollingStatement** binding properties.</span></span>  
  
2.  <span data-ttu-id="cc698-171">在从 SQL Server 数据库中接收消息的 BizTalk 项目中创建一条消息。</span><span class="sxs-lookup"><span data-stu-id="cc698-171">Create a message in the BizTalk project for receiving messages from the SQL Server database.</span></span>  
  
3.  <span data-ttu-id="cc698-172">创建业务流程的 SQL Server 数据库从接收消息，并将它们保存到一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc698-172">Create an orchestration to receive messages from the SQL Server database and to save them to a folder.</span></span>  
  
4.  <span data-ttu-id="cc698-173">生成和部署 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="cc698-173">Build and deploy the BizTalk project.</span></span>  
  
5.  <span data-ttu-id="cc698-174">配置的 BizTalk 应用程序创建的物理发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-174">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cc698-175">对于入站的轮询方案，你始终必须配置单向的 WCF 自定义或 WCF SQL 接收端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-175">For inbound polling scenarios you must always configure a one-way WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="cc698-176">双向 WCF 自定义或 WCF SQL 接收端口的入站操作不支持。</span><span class="sxs-lookup"><span data-stu-id="cc698-176">Two-way WCF-Custom or WCF-SQL receive ports are not supported for inbound operations.</span></span>  
  
6.  <span data-ttu-id="cc698-177">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="cc698-177">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="cc698-178">本主题提供执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="cc698-178">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="cc698-179">生成架构</span><span class="sxs-lookup"><span data-stu-id="cc698-179">Generating Schema</span></span>  
 <span data-ttu-id="cc698-180">必须生成的架构**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="cc698-180">You must generate the schema for the **Polling** operation.</span></span> <span data-ttu-id="cc698-181">请参阅[检索元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)有关如何生成架构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc698-181">See [Retrieving Metadata for SQL Server Operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) for more information about how to generate the schema.</span></span> <span data-ttu-id="cc698-182">生成架构时，请执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="cc698-182">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="cc698-183">如果你不想要指定的绑定属性在设计时，跳过的第一步。</span><span class="sxs-lookup"><span data-stu-id="cc698-183">Skip the first step if you do not want to specify the binding properties at design-time.</span></span>  
  
1.  <span data-ttu-id="cc698-184">为指定值**PolledDataAvailableStatement**和**PollingStatement**生成架构时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-184">Specify a value for **PolledDataAvailableStatement** and **PollingStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="cc698-185">有关此绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-185">For more information about this binding property, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
     <span data-ttu-id="cc698-186">有关如何指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-186">For instructions on how to specify binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
2.  <span data-ttu-id="cc698-187">选择与具有协定类型**服务 （入站操作）**。</span><span class="sxs-lookup"><span data-stu-id="cc698-187">Select the contract type as **Service (Inbound operation)**.</span></span>  
  
3.  <span data-ttu-id="cc698-188">生成架构**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="cc698-188">Generate schema for the **Polling** operation.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="cc698-189">定义消息和消息类型</span><span class="sxs-lookup"><span data-stu-id="cc698-189">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="cc698-190">你先前生成的架构描述业务流程中的消息所需的"类型"。</span><span class="sxs-lookup"><span data-stu-id="cc698-190">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="cc698-191">一条消息通常是一个变量，为其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="cc698-191">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="cc698-192">后生成架构，你必须将其从 BizTalk 项目的业务流程视图链接到消息中。</span><span class="sxs-lookup"><span data-stu-id="cc698-192">Once the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="cc698-193">对于本主题中，你必须创建一条消息的 SQL Server 数据库从接收消息。</span><span class="sxs-lookup"><span data-stu-id="cc698-193">For this topic, you must create one message to receive messages from the SQL Server database.</span></span>  
  
 <span data-ttu-id="cc698-194">执行以下步骤以创建消息并将它们链接到架构。</span><span class="sxs-lookup"><span data-stu-id="cc698-194">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="cc698-195">创建消息并将链接到架构</span><span class="sxs-lookup"><span data-stu-id="cc698-195">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="cc698-196">BizTalk 项目中添加业务流程。</span><span class="sxs-lookup"><span data-stu-id="cc698-196">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="cc698-197">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="cc698-197">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="cc698-198">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="cc698-198">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="cc698-199">如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。</span><span class="sxs-lookup"><span data-stu-id="cc698-199">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="cc698-200">单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="cc698-200">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="cc698-201">在**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="cc698-201">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="cc698-202">右键单击新创建的消息中，，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="cc698-202">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="cc698-203">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc698-203">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="cc698-204">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cc698-204">Use this</span></span>|<span data-ttu-id="cc698-205">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cc698-205">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cc698-206">Identifier</span><span class="sxs-lookup"><span data-stu-id="cc698-206">Identifier</span></span>|<span data-ttu-id="cc698-207">类型**接收**。</span><span class="sxs-lookup"><span data-stu-id="cc698-207">Type **Receive**.</span></span>|  
    |<span data-ttu-id="cc698-208">消息类型</span><span class="sxs-lookup"><span data-stu-id="cc698-208">Message Type</span></span>|<span data-ttu-id="cc698-209">从下拉列表中，展开**架构**，然后选择*PollingQuery.Polling*，其中*PollingQuery*是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="cc698-209">From the drop-down list, expand **Schemas**, and select *PollingQuery.Polling*, where *PollingQuery* is the name of your BizTalk project.</span></span> <span data-ttu-id="cc698-210">*轮询*是为生成的架构**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="cc698-210">*Polling* is the schema generated for the **Polling** operation.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="cc698-211">设置业务流程</span><span class="sxs-lookup"><span data-stu-id="cc698-211">Setting up the Orchestration</span></span>  
 <span data-ttu-id="cc698-212">你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于接收基于轮询的数据更改消息从 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="cc698-212">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving polling-based data-change messages from the SQL Server database.</span></span> <span data-ttu-id="cc698-213">在此业务流程，适配器接收到为指定的 select 语句的响应**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-213">In this orchestration, the adapter receives the response of the select statement specified for the **PollingStatement** binding property.</span></span> <span data-ttu-id="cc698-214">SELECT 语句的响应保存到文件位置。</span><span class="sxs-lookup"><span data-stu-id="cc698-214">The response for the SELECT statement is saved to a FILE location.</span></span> <span data-ttu-id="cc698-215">将包含轮询 SQL Server 数据库典型业务流程：</span><span class="sxs-lookup"><span data-stu-id="cc698-215">A typical orchestration for polling a SQL Server database would contain:</span></span>  
  
-   <span data-ttu-id="cc698-216">接收和发送形状来从 SQL Server 接收消息并分别将发送到文件端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-216">Receive and Send shapes to receive messages from SQL Server and send to a FILE port, respectively.</span></span>  
  
-   <span data-ttu-id="cc698-217">单向接收端口从 SQL Server 接收消息。</span><span class="sxs-lookup"><span data-stu-id="cc698-217">A one-way receive port to receive messages from SQL Server.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cc698-218">你始终必须配置的入站的轮询方案单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-218">For inbound polling scenarios you must always configure a one-way receive port.</span></span> <span data-ttu-id="cc698-219">双向接收入站操作不支持端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-219">Two-way receive ports are not supported for inbound operations.</span></span>  
  
-   <span data-ttu-id="cc698-220">单向发送端口将从 SQL Server 数据库的轮询响应发送到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc698-220">A one-way send port to send polling responses from a SQL Server database to a folder.</span></span>  
  
 <span data-ttu-id="cc698-221">示例业务流程如下所示。</span><span class="sxs-lookup"><span data-stu-id="cc698-221">A sample orchestration resembles the following.</span></span>  
  
 <span data-ttu-id="cc698-222">![轮询 SQL Server 数据库的业务流程](../../adapters-and-accelerators/adapter-sql/media/5cf65d53-d70d-444d-82f7-2561efcd9ee4.gif "5cf65d53-d70d-444d-82f7-2561efcd9ee4")</span><span class="sxs-lookup"><span data-stu-id="cc698-222">![Orchestration for polling a SQL Server database](../../adapters-and-accelerators/adapter-sql/media/5cf65d53-d70d-444d-82f7-2561efcd9ee4.gif "5cf65d53-d70d-444d-82f7-2561efcd9ee4")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="cc698-223">添加消息形状</span><span class="sxs-lookup"><span data-stu-id="cc698-223">Adding Message Shapes</span></span>  
 <span data-ttu-id="cc698-224">请确保为每个消息形状指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-224">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="cc698-225">刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="cc698-225">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="cc698-226">形状</span><span class="sxs-lookup"><span data-stu-id="cc698-226">Shape</span></span>|<span data-ttu-id="cc698-227">形状类型</span><span class="sxs-lookup"><span data-stu-id="cc698-227">Shape Type</span></span>|<span data-ttu-id="cc698-228">属性</span><span class="sxs-lookup"><span data-stu-id="cc698-228">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="cc698-229">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="cc698-229">ReceiveMessage</span></span>|<span data-ttu-id="cc698-230">Receive</span><span class="sxs-lookup"><span data-stu-id="cc698-230">Receive</span></span>|<span data-ttu-id="cc698-231">-将设置**名称**到*ReceiveMessage*</span><span class="sxs-lookup"><span data-stu-id="cc698-231">- Set **Name** to *ReceiveMessage*</span></span><br /><br /> <span data-ttu-id="cc698-232">-将设置**激活**到*True*</span><span class="sxs-lookup"><span data-stu-id="cc698-232">- Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="cc698-233">SaveMessage</span><span class="sxs-lookup"><span data-stu-id="cc698-233">SaveMessage</span></span>|<span data-ttu-id="cc698-234">Send</span><span class="sxs-lookup"><span data-stu-id="cc698-234">Send</span></span>|<span data-ttu-id="cc698-235">-将设置**名称**到*SaveMessage*</span><span class="sxs-lookup"><span data-stu-id="cc698-235">- Set **Name** to *SaveMessage*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="cc698-236">添加端口</span><span class="sxs-lookup"><span data-stu-id="cc698-236">Adding Ports</span></span>  
 <span data-ttu-id="cc698-237">请确保为每个逻辑端口指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-237">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="cc698-238">端口列中列出的名称是在业务流程中显示的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="cc698-238">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="cc698-239">端口</span><span class="sxs-lookup"><span data-stu-id="cc698-239">Port</span></span>|<span data-ttu-id="cc698-240">属性</span><span class="sxs-lookup"><span data-stu-id="cc698-240">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="cc698-241">SQLReceivePort</span><span class="sxs-lookup"><span data-stu-id="cc698-241">SQLReceivePort</span></span>|<span data-ttu-id="cc698-242">-将设置**标识符**到*SQLReceivePort*</span><span class="sxs-lookup"><span data-stu-id="cc698-242">- Set **Identifier** to *SQLReceivePort*</span></span><br /><br /> <span data-ttu-id="cc698-243">-将设置**类型**到*SQLReceivePortType*</span><span class="sxs-lookup"><span data-stu-id="cc698-243">- Set **Type** to *SQLReceivePortType*</span></span><br /><br /> <span data-ttu-id="cc698-244">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="cc698-244">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="cc698-245">-将设置**通信方向**到*接收*</span><span class="sxs-lookup"><span data-stu-id="cc698-245">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="cc698-246">SaveMessagePort</span><span class="sxs-lookup"><span data-stu-id="cc698-246">SaveMessagePort</span></span>|<span data-ttu-id="cc698-247">-将设置**标识符**到*SaveMessagePort*</span><span class="sxs-lookup"><span data-stu-id="cc698-247">- Set **Identifier** to *SaveMessagePort*</span></span><br /><br /> <span data-ttu-id="cc698-248">-将设置**类型**到*SaveMessagePortType*</span><span class="sxs-lookup"><span data-stu-id="cc698-248">- Set **Type** to *SaveMessagePortType*</span></span><br /><br /> <span data-ttu-id="cc698-249">-将设置**通信模式**到*单向*</span><span class="sxs-lookup"><span data-stu-id="cc698-249">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="cc698-250">-将设置**通信方向**到*发送*</span><span class="sxs-lookup"><span data-stu-id="cc698-250">- Set **Communication Direction** to *Send*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="cc698-251">指定消息的操作形状并将连接到端口</span><span class="sxs-lookup"><span data-stu-id="cc698-251">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="cc698-252">下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。</span><span class="sxs-lookup"><span data-stu-id="cc698-252">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="cc698-253">前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。</span><span class="sxs-lookup"><span data-stu-id="cc698-253">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="cc698-254">形状</span><span class="sxs-lookup"><span data-stu-id="cc698-254">Shape</span></span>|<span data-ttu-id="cc698-255">属性</span><span class="sxs-lookup"><span data-stu-id="cc698-255">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="cc698-256">ReceiveMessage</span><span class="sxs-lookup"><span data-stu-id="cc698-256">ReceiveMessage</span></span>|<span data-ttu-id="cc698-257">-将设置**消息**到*接收*</span><span class="sxs-lookup"><span data-stu-id="cc698-257">- Set **Message** to *Receive*</span></span><br /><br /> <span data-ttu-id="cc698-258">-将设置**操作**到*SQLReceivePort.Polling.Request*</span><span class="sxs-lookup"><span data-stu-id="cc698-258">- Set **Operation** to *SQLReceivePort.Polling.Request*</span></span>|  
|<span data-ttu-id="cc698-259">SaveMessage</span><span class="sxs-lookup"><span data-stu-id="cc698-259">SaveMessage</span></span>|<span data-ttu-id="cc698-260">-将设置**消息**到*接收*</span><span class="sxs-lookup"><span data-stu-id="cc698-260">- Set **Message** to *Receive*</span></span><br /><br /> <span data-ttu-id="cc698-261">-将设置**操作**到*SaveMessagePort.Polling.Request*</span><span class="sxs-lookup"><span data-stu-id="cc698-261">- Set **Operation** to *SaveMessagePort.Polling.Request*</span></span>|  
  
 <span data-ttu-id="cc698-262">指定这些属性后，连接的消息形状和端口，您的业务流程已完成。</span><span class="sxs-lookup"><span data-stu-id="cc698-262">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="cc698-263">现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cc698-263">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="cc698-264">有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-264">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span> 
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="cc698-265">配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="cc698-265">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="cc698-266">部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="cc698-266">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="cc698-267">必须使用 BizTalk Server 管理控制台配置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cc698-267">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="cc698-268">有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-268">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>  
  
 <span data-ttu-id="cc698-269">配置应用程序涉及：</span><span class="sxs-lookup"><span data-stu-id="cc698-269">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="cc698-270">选择应用程序的主机。</span><span class="sxs-lookup"><span data-stu-id="cc698-270">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="cc698-271">映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-271">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="cc698-272">对于此业务流程，您必须：</span><span class="sxs-lookup"><span data-stu-id="cc698-272">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="cc698-273">硬盘和其中 BizTalk 业务流程将消息从数据库中删除 SQL Server 的相应文件端口上定义的位置。</span><span class="sxs-lookup"><span data-stu-id="cc698-273">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the messages from the SQL Server database.</span></span> <span data-ttu-id="cc698-274">这些消息将以响应接收端口指定轮询语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-274">These messages will be in response to the polling statement that you specify for the receive port.</span></span>  
  
    -   <span data-ttu-id="cc698-275">定义一个物理 WCF 自定义或 WCF SQL 单向接收端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-275">Define a physical WCF-Custom or WCF-SQL one-way receive port.</span></span> <span data-ttu-id="cc698-276">此端口轮询作为端口号指定的轮询语句的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="cc698-276">This port polls the SQL Server database with the polling statement you specify for the port.</span></span> <span data-ttu-id="cc698-277">有关如何创建端口的信息，请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-277">For information about how to create ports, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span> <span data-ttu-id="cc698-278">请确保指定的接收端口的以下绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-278">Make sure you specify the following binding properties for the receive port.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="cc698-279">不需要执行此步骤中，如果指定在设计时绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-279">You do not need to perform this step if you specified the binding properties at design-time.</span></span> <span data-ttu-id="cc698-280">在这种情况下，你可以创建 WCF 自定义或 WCF SQL 接收端口，将设置所需的绑定的属性，通过导入所创建绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cc698-280">In such a case, you can create a WCF-custom or WCF-SQL receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="cc698-281">有关详细信息请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-281">For more information see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
        |<span data-ttu-id="cc698-282">绑定属性</span><span class="sxs-lookup"><span data-stu-id="cc698-282">Binding Property</span></span>|<span data-ttu-id="cc698-283">值</span><span class="sxs-lookup"><span data-stu-id="cc698-283">Value</span></span>|  
        |----------------------|-----------|  
        |<span data-ttu-id="cc698-284">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="cc698-284">**InboundOperationType**</span></span>|<span data-ttu-id="cc698-285">请确保将此设置为**轮询**。</span><span class="sxs-lookup"><span data-stu-id="cc698-285">Make sure you set this to **Polling**.</span></span>|  
        |<span data-ttu-id="cc698-286">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="cc698-286">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="cc698-287">请确保指定的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-287">Make sure you specify a SQL statement.</span></span> <span data-ttu-id="cc698-288">对于本主题中，指定：</span><span class="sxs-lookup"><span data-stu-id="cc698-288">For this topic, specify:</span></span><br /><br /> `SELECT COUNT(*) FROM Employee`|  
        |<span data-ttu-id="cc698-289">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="cc698-289">**PollingStatement**</span></span>|<span data-ttu-id="cc698-290">请确保指定轮询语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-290">Make sure you specify the polling statement.</span></span> <span data-ttu-id="cc698-291">对于本主题中，指定：</span><span class="sxs-lookup"><span data-stu-id="cc698-291">For this topic, specify:</span></span><br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
         <span data-ttu-id="cc698-292">有关不同的绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-292">For more information about the different binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="cc698-293">我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cc698-293">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="cc698-294">你可以执行以便通过将服务添加行为配置 WCF 自定义或 WCF SQL 时接收端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-294">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="cc698-295">有关如何添加服务行为的说明，请参阅[配置事务隔离级别和与 SQL 的事务超时](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-295">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="cc698-296">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="cc698-296">Starting the Application</span></span>  
 <span data-ttu-id="cc698-297">你必须启动 SQL Server 数据库从接收消息的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="cc698-297">You must start the BizTalk application for receiving messages from the SQL Server database.</span></span> <span data-ttu-id="cc698-298">有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-298">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="cc698-299">在此阶段，请确保：</span><span class="sxs-lookup"><span data-stu-id="cc698-299">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="cc698-300">WCF 自定义或 WCF SQL 单向接收端口，从而轮询使用为指定的语句的 SQL Server 数据库**PollingStatement**绑定属性，正在运行。</span><span class="sxs-lookup"><span data-stu-id="cc698-300">The WCF-Custom or WCF-SQL one-way receive port, which polls the SQL Server database using the statements specified for the **PollingStatement** binding property, is running.</span></span>  
  
-   <span data-ttu-id="cc698-301">文件发送端口，从而从 SQL Server 接收消息，正在运行。</span><span class="sxs-lookup"><span data-stu-id="cc698-301">The FILE send port, which receives messages from SQL Server, is running.</span></span>  
  
-   <span data-ttu-id="cc698-302">BizTalk 业务流程操作正在运行。</span><span class="sxs-lookup"><span data-stu-id="cc698-302">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="cc698-303">执行该操作</span><span class="sxs-lookup"><span data-stu-id="cc698-303">Executing the Operation</span></span>  
 <span data-ttu-id="cc698-304">运行应用程序后，下面的一组操作需要置于相同的序列：</span><span class="sxs-lookup"><span data-stu-id="cc698-304">After you run the application, the following set of actions take place, in the same sequence:</span></span>  
  
-   <span data-ttu-id="cc698-305">适配器执行**PolledDataAvailableStatement**对员工表并确定表具有进行轮询的记录。</span><span class="sxs-lookup"><span data-stu-id="cc698-305">The adapter executes the **PolledDataAvailableStatement** on the Employee table and determines that the table has records for polling.</span></span>  
  
-   <span data-ttu-id="cc698-306">适配器执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="cc698-306">The adapter executes the polling statement.</span></span> <span data-ttu-id="cc698-307">轮询语句包含 SELECT 语句和存储的过程，因为该适配器后将不执行所有语句一个其他。</span><span class="sxs-lookup"><span data-stu-id="cc698-307">Because the polling statement consists of a SELECT statement and stored procedures, the adapter will execute all the statements one after the other.</span></span>  
  
    -   <span data-ttu-id="cc698-308">适配器首先执行 SELECT 语句返回员工表中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="cc698-308">The adapter first executes the SELECT statement that returns all the records in the Employee table.</span></span>  
  
    -   <span data-ttu-id="cc698-309">然后，适配器执行将从员工表的所有数据都移动到 EmployeeHistory 表 MOVE_EMP_DATA 存储过程。</span><span class="sxs-lookup"><span data-stu-id="cc698-309">The adapter then executes the MOVE_EMP_DATA stored procedure that moves all data from the Employee table to the EmployeeHistory table.</span></span> <span data-ttu-id="cc698-310">此存储的过程不返回任何值。</span><span class="sxs-lookup"><span data-stu-id="cc698-310">This stored procedure does not return any value.</span></span>  
  
    -   <span data-ttu-id="cc698-311">适配器然后执行 ADD_EMP_DETAILS 存储过程，将一条记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="cc698-311">The adapter then executes the ADD_EMP_DETAILS stored procedure that adds one record to the Employee table.</span></span> <span data-ttu-id="cc698-312">此存储的过程返回插入的记录的员工 ID。</span><span class="sxs-lookup"><span data-stu-id="cc698-312">This stored procedure returns the Employee ID for the inserted record.</span></span>  
  
     <span data-ttu-id="cc698-313">因此，从 SQL Server 接收的消息将包含多个结果集 （SELECT 语句和 ADD_EMP_DETAILS 存储过程），并将如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc698-313">So, the message received from SQL Server will contain multiple result sets (for SELECT statement and for ADD_EMP_DETAILS stored procedure), and will resemble the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling/">  
      <PolledData>  
        <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
          \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
            \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
              \<xs:complexType>  
                \<xs:sequence>  
                  \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                    \<xs:complexType>  
                      \<xs:sequence>  
                        \<xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                        \<xs:element minOccurs="0" name="Name" type="xs:string" />   
                        \<xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                        \<xs:element minOccurs="0" name="Designation" type="xs:string" />   
                        \<xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                        \<xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                        \<xs:element minOccurs="0" name="Rating" type="xs:string" />   
                        \<xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                        \<xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
                      \</xs:sequence>  
                    \</xs:complexType>  
                  \</xs:element>  
                \</xs:sequence>  
              \</xs:complexType>  
            \</xs:element>  
          \</xs:schema>  
          \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
            <NewDataSet xmlns="">  
              <NewTable>  
                <Employee_ID>10001</Employee_ID>   
                <Name>John</Name>   
                <Designation>Tester</Designation>   
                <Salary>100000.00</Salary>   
                <Last_Modified>AAAAAAAAF34=</Last_Modified>   
              </NewTable>  
              ........  
              ........  
              <NewTable>  
                <Employee_ID>10005</Employee_ID>   
                <Name>Wilson</Name>   
                <Designation>Tester3</Designation>   
                <Salary>100000.00</Salary>   
                <Last_Modified>AAAAAAAAF4E=</Last_Modified>   
              </NewTable>  
            </NewDataSet>  
          \</diffgr:diffgram>  
        </DataSet>  
        <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
          \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
            \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
              \<xs:complexType>  
                \<xs:sequence>  
                  \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                    \<xs:complexType>  
                      \<xs:sequence>  
                        \<xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      \</xs:sequence>  
                    \</xs:complexType>  
                  \</xs:element>  
                \</xs:sequence>  
              \</xs:complexType>  
            \</xs:element>  
          \</xs:schema>  
          \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
            <NewDataSet xmlns="">  
              <NewTable>  
                <Employee_ID>10006</Employee_ID>  
              </NewTable>  
            </NewDataSet>  
          \</diffgr:diffgram>  
        </DataSet>  
      </PolledData>  
    </Polling>  
    ```  
  
     <span data-ttu-id="cc698-314">前面的响应包含两个数据集。</span><span class="sxs-lookup"><span data-stu-id="cc698-314">The preceding response contains two data sets.</span></span> <span data-ttu-id="cc698-315">第一个数据集包含 SELECT 语句的响应。</span><span class="sxs-lookup"><span data-stu-id="cc698-315">The first data set contains the response for the SELECT statement.</span></span> <span data-ttu-id="cc698-316">SELECT 语句员工表中选择的所有记录。</span><span class="sxs-lookup"><span data-stu-id="cc698-316">The SELECT statement selects all the records in the Employee table.</span></span> <span data-ttu-id="cc698-317">第二个数据集是 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="cc698-317">The second data set is for the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="cc698-318">此存储的过程将记录添加到员工表，并返回新的记录的员工 ID。</span><span class="sxs-lookup"><span data-stu-id="cc698-318">This stored procedure adds a record to the Employee table and returns the employee ID for the new record.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc698-319">MOVE_EMP_DATA 存储过程不返回结果集。</span><span class="sxs-lookup"><span data-stu-id="cc698-319">The MOVE_EMP_DATA stored procedure does not return a result set.</span></span> <span data-ttu-id="cc698-320">因此，在响应消息中，如果没有相应的数据集。</span><span class="sxs-lookup"><span data-stu-id="cc698-320">So, there is no corresponding data set in the response message.</span></span>  
  
-   <span data-ttu-id="cc698-321">当适配器执行**PollDataAvailableStatement**再次，它找到一个记录所插入的 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="cc698-321">When the adapter executes the **PollDataAvailableStatement** again, it finds one record that was inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="cc698-322">适配器然后执行为指定的所有三个语句**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cc698-322">The adapter then executes all three statements that are specified for the **PollingStatement** binding property.</span></span> <span data-ttu-id="cc698-323">此时，来自 SQL Server 的响应包含 SELECT 语句只是一条记录，并且一条记录 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="cc698-323">This time, the response from SQL Server contains just one record for the SELECT statement and one record for the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="cc698-324">所有后续轮询将返回类似的响应。</span><span class="sxs-lookup"><span data-stu-id="cc698-324">All subsequent polls will return similar responses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc698-325">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将继续轮询除非你显式禁用接收端口从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="cc698-325">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] will continue to poll until you explicitly disable the receive port from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="cc698-326">最佳实践</span><span class="sxs-lookup"><span data-stu-id="cc698-326">Best Practices</span></span>  
 <span data-ttu-id="cc698-327">已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。</span><span class="sxs-lookup"><span data-stu-id="cc698-327">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="cc698-328">后生成绑定文件，你可以导入的配置设置文件，以便不需要创建发送端口和接收相同的业务流程的端口。</span><span class="sxs-lookup"><span data-stu-id="cc698-328">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="cc698-329">有关绑定文件的详细信息，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="cc698-329">For more information about binding files, see [Reuse adapter bindings](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc698-330">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc698-330">See Also</span></span>  
 [<span data-ttu-id="cc698-331">与 BizTalk Server 中使用 SQL 适配器的轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="cc698-331">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)