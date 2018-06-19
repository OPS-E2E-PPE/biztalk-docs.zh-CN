---
title: 通过使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0f4af71-fb0c-433d-ba74-48ee6487eb1a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb785631d6fe00ea68f57f943dca11ebd1a84b1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226389"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-by-using-the-wcf-channel-model"></a><span data-ttu-id="6367a-102">通过使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="6367a-102">Receive Polling-based Data-changed Messages from SQL Server by Using the WCF Channel Model</span></span>
<span data-ttu-id="6367a-103">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来接收 SQL Server 表或视图的定期的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="6367a-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="6367a-104">你可以指定适配器执行轮询数据库轮询语句。</span><span class="sxs-lookup"><span data-stu-id="6367a-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="6367a-105">轮询语句可以是 SELECT 语句或存储的过程返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="6367a-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  
  
 <span data-ttu-id="6367a-106">有关如何的适配器支持轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="6367a-106">For more information on how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6367a-107">如果你想要在单个应用程序中具有多个轮询操作，你必须指定**InboundID**作为连接以使其唯一的 URI 的一部分的连接属性。</span><span class="sxs-lookup"><span data-stu-id="6367a-107">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="6367a-108">你指定的入站的 ID 添加到要使之唯一的操作命名空间。</span><span class="sxs-lookup"><span data-stu-id="6367a-108">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="6367a-109">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="6367a-109">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="6367a-110">在此主题中，以演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收数据的支持更改消息，请创建.NET 应用程序来**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="6367a-110">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a .NET application for the **Polling** operation.</span></span> <span data-ttu-id="6367a-111">对于本主题中，指定**PolledDataAvailableStatement**作为：</span><span class="sxs-lookup"><span data-stu-id="6367a-111">For this topic, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="6367a-112">**PolledDataAvailableStatement**必须返回具有包含正值的第一个单元格的结果集。</span><span class="sxs-lookup"><span data-stu-id="6367a-112">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="6367a-113">如果第一个单元格不包含是正数值，该适配器将不会执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="6367a-113">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="6367a-114">作为轮询语句的一部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6367a-114">As part of the polling statement, perform the following operations:</span></span>  
  
1.  <span data-ttu-id="6367a-115">从员工表中选择所有行。</span><span class="sxs-lookup"><span data-stu-id="6367a-115">Select all the rows from the Employee table.</span></span>  
  
2.  <span data-ttu-id="6367a-116">执行存储的过程 (MOVE_EMP_DATA) 将从员工表到 EmployeeHistory 表的所有记录。</span><span class="sxs-lookup"><span data-stu-id="6367a-116">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="6367a-117">执行存储的过程 (ADD_EMP_DETAILS) 将一条新记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="6367a-117">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="6367a-118">此过程使用雇员姓名、 名称以及薪金作为参数。</span><span class="sxs-lookup"><span data-stu-id="6367a-118">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="6367a-119">若要执行这些操作，必须指定以下项作为**PollingStatement**绑定属性：</span><span class="sxs-lookup"><span data-stu-id="6367a-119">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="6367a-120">执行轮询语句后，选择从 Employee 表的所有记录，并接收来自 SQL Server 的消息。</span><span class="sxs-lookup"><span data-stu-id="6367a-120">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="6367a-121">一旦 MOVE_EMP_DATA 存储过程执行适配器，所有记录都移动到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="6367a-121">Once the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="6367a-122">然后，执行 ADD_EMP_DETAILS 存储过程将一条新记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="6367a-122">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="6367a-123">下一次轮询执行将只返回单个记录。</span><span class="sxs-lookup"><span data-stu-id="6367a-123">The next polling execution will only return a single record.</span></span> <span data-ttu-id="6367a-124">此循环会持续关闭通道侦听器。</span><span class="sxs-lookup"><span data-stu-id="6367a-124">This cycle continues until you close the channel listener.</span></span>  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="6367a-125">配置与 SQL 适配器绑定属性的轮询查询</span><span class="sxs-lookup"><span data-stu-id="6367a-125">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="6367a-126">下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="6367a-126">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="6367a-127">轮询.NET 应用程序的一部分，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6367a-127">You must specify these binding properties as part of the .NET application for polling.</span></span>  
  
|<span data-ttu-id="6367a-128">绑定属性</span><span class="sxs-lookup"><span data-stu-id="6367a-128">Binding Property</span></span>|<span data-ttu-id="6367a-129">Description</span><span class="sxs-lookup"><span data-stu-id="6367a-129">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="6367a-130">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="6367a-130">**InboundOperationType**</span></span>|<span data-ttu-id="6367a-131">指定是否想要执行**轮询**， **TypedPolling**，或**通知**入站操作。</span><span class="sxs-lookup"><span data-stu-id="6367a-131">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="6367a-132">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="6367a-132">Default is **Polling**.</span></span>|  
|<span data-ttu-id="6367a-133">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="6367a-133">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="6367a-134">指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="6367a-134">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="6367a-135">SQL 语句必须返回的结果集行和列组成。</span><span class="sxs-lookup"><span data-stu-id="6367a-135">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="6367a-136">仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6367a-136">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="6367a-137">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="6367a-137">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="6367a-138">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6367a-138">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="6367a-139">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="6367a-139">The default is 30 seconds.</span></span> <span data-ttu-id="6367a-140">轮询间隔确定连续两次轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="6367a-140">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="6367a-141">如果在指定间隔内执行该语句，该适配器将等待的间隔中的剩余时间。</span><span class="sxs-lookup"><span data-stu-id="6367a-141">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="6367a-142">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="6367a-142">**PollingStatement**</span></span>|<span data-ttu-id="6367a-143">指定要轮询的 SQL Server 数据库表的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="6367a-143">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="6367a-144">你可以指定简单的 SELECT 语句或存储的过程轮询语句。</span><span class="sxs-lookup"><span data-stu-id="6367a-144">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="6367a-145">默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="6367a-145">The default is null.</span></span> <span data-ttu-id="6367a-146">必须指定的值**PollingStatement**来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="6367a-146">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="6367a-147">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6367a-147">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="6367a-148">你可以指定任意数量的以分号分隔的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="6367a-148">You can specify any number of SQL statements separated by a semi-colon.</span></span>|  
|<span data-ttu-id="6367a-149">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="6367a-149">**PollWhileDataFound**</span></span>|<span data-ttu-id="6367a-150">指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略轮询间隔和连续执行为指定的 SQL 语句**PolledDataAvailableStatement**绑定属性，如果数据中轮询的表。</span><span class="sxs-lookup"><span data-stu-id="6367a-150">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="6367a-151">如果表中可用的任何数据不，该适配器将恢复执行 SQL 语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="6367a-151">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="6367a-152">默认值是**false**。</span><span class="sxs-lookup"><span data-stu-id="6367a-152">Default is **false**.</span></span>|  
  
 <span data-ttu-id="6367a-153">有关这些属性的更完整说明，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="6367a-153">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="6367a-154">有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，请阅读此主题的其余部分。</span><span class="sxs-lookup"><span data-stu-id="6367a-154">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read the remainder of this topic.</span></span>  
  
## <a name="consuming-the-polling-request-message"></a><span data-ttu-id="6367a-155">使用轮询请求消息</span><span class="sxs-lookup"><span data-stu-id="6367a-155">Consuming the Polling Request Message</span></span>  
 <span data-ttu-id="6367a-156">适配器时，将调用**轮询**于你的代码来轮询 SQL Server 数据库的操作。</span><span class="sxs-lookup"><span data-stu-id="6367a-156">The adapter invokes the **Polling** operation on your code to poll the SQL Server database.</span></span> <span data-ttu-id="6367a-157">也就是说，该适配器通过 IInputChannel 通道形状发送轮询请求消息，你将收到。</span><span class="sxs-lookup"><span data-stu-id="6367a-157">That is, the adapter sends a Polling request message that you receive over an IInputChannel channel shape.</span></span> <span data-ttu-id="6367a-158">轮询请求消息包含由 PollingStatement 绑定属性指定的查询的结果集。</span><span class="sxs-lookup"><span data-stu-id="6367a-158">The Polling request message contains the result set of the query specified by the PollingStatement binding property.</span></span> <span data-ttu-id="6367a-159">你可以使用两种方式之一中的轮询消息：</span><span class="sxs-lookup"><span data-stu-id="6367a-159">You can consume the Polling message in one of two ways:</span></span>  
  
-   <span data-ttu-id="6367a-160">若要使用使用流式处理你的节点的值的消息必须调用**WriteBodyContents**方法则会在响应消息并将其传递**XmlDictionaryWriter**实现节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="6367a-160">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="6367a-161">若要使用的消息使用节点流可以调用**GetReaderAtBodyContents**若要获取的响应消息**XmlReader**。</span><span class="sxs-lookup"><span data-stu-id="6367a-161">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="6367a-162">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="6367a-162">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="6367a-163">本主题中的示例轮询员工表。</span><span class="sxs-lookup"><span data-stu-id="6367a-163">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="6367a-164">此示例还使用 MOVE_EMP_DATA 和 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="6367a-164">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="6367a-165">在示例提供了一个脚本以生成这些项目。</span><span class="sxs-lookup"><span data-stu-id="6367a-165">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="6367a-166">有关这些示例的详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6367a-166">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="6367a-167">示例中， **Polling_ChannelModel**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="6367a-167">A sample, **Polling_ChannelModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a><span data-ttu-id="6367a-168">使用 WCF 通道模型的轮询操作接收入站的消息</span><span class="sxs-lookup"><span data-stu-id="6367a-168">Receiving Inbound Messages for Polling Operation Using the WCF Channel Model</span></span>  
 <span data-ttu-id="6367a-169">此部分提供有关如何编写一个.NET 应用程序 （通道模型） 来接收使用的入站的轮询消息说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6367a-169">This section provides instructions on how to write a .NET application (channel model) to receive inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="6367a-170">从 SQL 适配器接收轮询消息</span><span class="sxs-lookup"><span data-stu-id="6367a-170">To receive polling messages from the SQL adapter</span></span>  
  
1.  <span data-ttu-id="6367a-171">创建 Microsoft Visual C# 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6367a-171">Create a Microsoft Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="6367a-172">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="6367a-172">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="6367a-173">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。</span><span class="sxs-lookup"><span data-stu-id="6367a-173">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="6367a-174">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="6367a-174">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="6367a-175">指定连接 URI。</span><span class="sxs-lookup"><span data-stu-id="6367a-175">Specify a connection URI.</span></span> <span data-ttu-id="6367a-176">有关 URI 的适配器连接的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="6367a-176">For more information about the adapter connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    ```  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    ```  
  
5.  <span data-ttu-id="6367a-177">创建的实例**SqlAdapterBinding**并设置配置轮询所需的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6367a-177">Create an instance of **SqlAdapterBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="6367a-178">至少必须设置**InboundOperationType**， **PolledDataAvailableStatement**，和**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6367a-178">At a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement** binding properties.</span></span> <span data-ttu-id="6367a-179">有关绑定属性用于配置轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="6367a-179">For more information about binding properties used to configure polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
6.  <span data-ttu-id="6367a-180">创建一个绑定参数集合，并设置凭据。</span><span class="sxs-lookup"><span data-stu-id="6367a-180">Create a binding parameter collection and set the credentials.</span></span>  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
7.  <span data-ttu-id="6367a-181">创建一个通道侦听器，并将其打开。</span><span class="sxs-lookup"><span data-stu-id="6367a-181">Create a channel listener and open it.</span></span> <span data-ttu-id="6367a-182">通过调用创建侦听器**BuildChannelListener < IInputChannel\>** 方法**SqlAdapterBinding**。</span><span class="sxs-lookup"><span data-stu-id="6367a-182">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **SqlAdapterBinding**.</span></span>  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
8.  <span data-ttu-id="6367a-183">获取**IInputChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。</span><span class="sxs-lookup"><span data-stu-id="6367a-183">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
9. <span data-ttu-id="6367a-184">调用**接收**从适配器获取下一步的 POLLINGSTMT 消息在通道上。</span><span class="sxs-lookup"><span data-stu-id="6367a-184">Invoke **Receive** on the channel to get the next POLLINGSTMT message from the adapter.</span></span>  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
10. <span data-ttu-id="6367a-185">使用 POLLINGSTMT 操作返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="6367a-185">Consume the result set returned by the POLLINGSTMT operation.</span></span> <span data-ttu-id="6367a-186">你可以使用使用消息**XmlReader**或**XmlDictionaryWriter**。</span><span class="sxs-lookup"><span data-stu-id="6367a-186">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
11. <span data-ttu-id="6367a-187">已完成处理请求时，请关闭通道。</span><span class="sxs-lookup"><span data-stu-id="6367a-187">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6367a-188">处理 POLLINGSTMT 操作之后，您必须关闭通道。</span><span class="sxs-lookup"><span data-stu-id="6367a-188">You must close the channel after you have finished processing the POLLINGSTMT operation.</span></span> <span data-ttu-id="6367a-189">未能关闭通道可能会影响你代码的行为。</span><span class="sxs-lookup"><span data-stu-id="6367a-189">Failure to close the channel may affect the behavior of your code.</span></span>  
  
12. <span data-ttu-id="6367a-190">在完成接收数据更改消息时，请关闭该侦听器。</span><span class="sxs-lookup"><span data-stu-id="6367a-190">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6367a-191">关闭侦听器不会关闭使用侦听器创建的通道。</span><span class="sxs-lookup"><span data-stu-id="6367a-191">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="6367a-192">您必须显式关闭使用侦听器创建每个通道。</span><span class="sxs-lookup"><span data-stu-id="6367a-192">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="6367a-193">示例</span><span class="sxs-lookup"><span data-stu-id="6367a-193">Example</span></span>  
 <span data-ttu-id="6367a-194">下面的示例演示执行员工表的轮询查询。</span><span class="sxs-lookup"><span data-stu-id="6367a-194">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="6367a-195">轮询语句将执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="6367a-195">The polling statement performs the following tasks:</span></span>  
  
-   <span data-ttu-id="6367a-196">从员工表中选择的所有记录。</span><span class="sxs-lookup"><span data-stu-id="6367a-196">Selects all the records from the Employee table.</span></span>  
  
-   <span data-ttu-id="6367a-197">执行上述 MOVE_EMP_DATA 存储过程以从员工表的所有记录都移到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="6367a-197">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  
  
-   <span data-ttu-id="6367a-198">执行上述 ADD_EMP_DETAILS 存储过程以将单个记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="6367a-198">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  
  
 <span data-ttu-id="6367a-199">轮询消息会保存在`C:\PollingOutput.xml`。</span><span class="sxs-lookup"><span data-stu-id="6367a-199">The polling messages are saved at `C:\PollingOutput.xml`.</span></span>  
  
```  
using System;  
using Microsoft.Adapters.Sql;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
  
using System.Xml;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Console.WriteLine("Sample started. This sample will poll 5 times and will perform the following tasks:");  
            Console.WriteLine("Press any key to start polling...");  
            Console.ReadLine();  
            IChannelListener<IInputChannel> listener = null;  
  
            IInputChannel channel = null;  
  
            try  
            {  
                TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  
  
                listener = binding.BuildChannelListener<IInputChannel>(ConnectionUri, bindingParams);  
                listener.Open();  
  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel and Listener opened...");  
                Console.WriteLine("\nWaiting for polled data...");  
                Console.WriteLine("Receive request timeout is {0}", messageTimeout);  
  
                // Poll five times with the specified message timeout   
                // If a timeout occurs polling will be aborted  
                for (int i = 0; i < 5; i++)  
                {  
                    Console.WriteLine("Polling: " + i);  
                    Message message = null;  
                    XmlReader reader = null;  
                    try  
                    {  
                        //Message is received so process the results  
                        message = channel.Receive(messageTimeout);  
                    }  
                    catch (System.TimeoutException toEx)  
                    {  
                        Console.WriteLine("\nNo data for request number {0}: {1}", i + 1, toEx.Message);  
                        continue;  
                    }  
  
                    // Get the query results using an XML reader  
                    try  
                    {  
                        reader = message.GetReaderAtBodyContents();  
                    }  
                    catch (Exception ex)  
                    {  
                        Console.WriteLine("Exception :" + ex);  
                        throw;  
                    }  
  
                    XmlDocument doc = new XmlDocument();  
                    doc.Load(reader);  
                    using (XmlWriter writer = XmlWriter.Create("C:\\PollingOutput.xml"))  
                    {  
                        doc.WriteTo(writer);  
                        Console.WriteLine("The polling response is saved at 'C:\\PollingOutput.xml'");  
                    }  
  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    message.Close();  
                }  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // IMPORTANT: close the channel and listener to stop polling  
                if (channel != null)  
                {  
                    if (channel.State == CommunicationState.Opened)  
                        channel.Close();  
                    else  
                        channel.Abort();  
                }  
  
                if (listener != null)  
                {  
                    if (listener.State == CommunicationState.Opened)  
                        listener.Close();  
                    else  
                        listener.Abort();  
                }  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="6367a-200">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6367a-200">See Also</span></span>  
[<span data-ttu-id="6367a-201">开发 SQL 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="6367a-201">Develop SQL applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)