---
title: "使用 WCF 服务模型从 SQL Server 接收基于轮询的数据更改消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8713dd38-65ff-4d89-b23b-a93c06c5ff22
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ff5ca099733a59fc5aa64c9ebbe261375f1a488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-the-wcf-service-model"></a><span data-ttu-id="039f3-102">使用 WCF 服务模型从 SQL Server 接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="039f3-102">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>
<span data-ttu-id="039f3-103">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来接收 SQL Server 表或视图的定期的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="039f3-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="039f3-104">你可以指定适配器执行轮询数据库轮询语句。</span><span class="sxs-lookup"><span data-stu-id="039f3-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="039f3-105">轮询语句可以是 SELECT 语句或存储的过程返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="039f3-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  
  
 <span data-ttu-id="039f3-106">有关如何的适配器支持轮询的详细信息，请参阅[轮询在 SQL 服务器上使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="039f3-106">For more information on how the adapter supports polling, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="039f3-107">本主题演示如何使用**轮询**入站操作人员使用轮询消息。</span><span class="sxs-lookup"><span data-stu-id="039f3-107">This topic demonstrates how to use the **Polling** inbound operation to use polling messages.</span></span> <span data-ttu-id="039f3-108">轮询操作的消息不是强的类型。</span><span class="sxs-lookup"><span data-stu-id="039f3-108">The message for the Polling operation is not strongly-typed.</span></span> <span data-ttu-id="039f3-109">如果你想要获取强类型的轮询消息，则必须使用**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-109">If you want to get strongly-typed polling message, you must use the **TypedPolling** operation.</span></span> <span data-ttu-id="039f3-110">你还必须使用**TypedPolling**操作以在单个应用程序中具有多个轮询操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-110">You must also use the **TypedPolling** operation to have multiple polling operations in a single application.</span></span> <span data-ttu-id="039f3-111">有关说明如何执行**TypedPolling**操作，请参阅[接收强类型轮询基于的数据更改消息从 SQL Server 使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="039f3-111">For instructions on how to perform **TypedPolling** operation, see [Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="039f3-112">如果你想要在单个应用程序中具有多个轮询操作，你必须指定**InboundID**作为连接以使其唯一的 URI 的一部分的连接属性。</span><span class="sxs-lookup"><span data-stu-id="039f3-112">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="039f3-113">你指定的入站的 ID 添加到要使之唯一的操作命名空间。</span><span class="sxs-lookup"><span data-stu-id="039f3-113">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="039f3-114">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="039f3-114">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="039f3-115">在此主题中，以演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收数据的支持更改消息、 创建.NET 应用程序和生成的 WCF 服务协定**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-115">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a .NET application and generate the WCF service contract for the **Polling** operation.</span></span> <span data-ttu-id="039f3-116">如果你想要指定轮询相关将属性绑定在生成 WCF 服务约定时，指定**PolledDataAvailableStatement**作为：</span><span class="sxs-lookup"><span data-stu-id="039f3-116">If you want to specify the polling related binding properties while generating the WCF service contract, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="039f3-117">**PolledDataAvailableStatement**必须返回具有包含正值的第一个单元格的结果集。</span><span class="sxs-lookup"><span data-stu-id="039f3-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="039f3-118">如果第一个单元格不包含是正数值，该适配器将不会执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="039f3-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="039f3-119">作为轮询语句的一部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="039f3-119">As part of the polling statement, perform the following operations:</span></span>  
  
1.  <span data-ttu-id="039f3-120">从员工表中选择所有行。</span><span class="sxs-lookup"><span data-stu-id="039f3-120">Select all the rows from the Employee table.</span></span>  
  
2.  <span data-ttu-id="039f3-121">执行存储的过程 (MOVE_EMP_DATA) 将从员工表到 EmployeeHistory 表的所有记录。</span><span class="sxs-lookup"><span data-stu-id="039f3-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="039f3-122">执行存储的过程 (ADD_EMP_DETAILS) 将一条新记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="039f3-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="039f3-123">此过程使用雇员姓名、 名称以及薪金作为参数。</span><span class="sxs-lookup"><span data-stu-id="039f3-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="039f3-124">若要执行这些操作，必须指定以下项作为**PollingStatement**绑定属性：</span><span class="sxs-lookup"><span data-stu-id="039f3-124">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="039f3-125">执行轮询语句后，选择从 Employee 表的所有记录，并接收来自 SQL Server 的消息。</span><span class="sxs-lookup"><span data-stu-id="039f3-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="039f3-126">MOVE_EMP_DATA 存储过程执行适配器后，所有记录被都移动到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="039f3-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="039f3-127">然后，执行 ADD_EMP_DETAILS 存储过程将一条新记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="039f3-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="039f3-128">下一次轮询执行将只返回单个记录。</span><span class="sxs-lookup"><span data-stu-id="039f3-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="039f3-129">此循环会持续关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="039f3-129">This cycle continues until you close the service host.</span></span>  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="039f3-130">配置与 SQL 适配器绑定属性的轮询查询</span><span class="sxs-lookup"><span data-stu-id="039f3-130">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="039f3-131">下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="039f3-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="039f3-132">轮询.NET 应用程序的一部分，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="039f3-132">You must specify these binding properties as part of the .NET application for polling.</span></span>  
  
|<span data-ttu-id="039f3-133">绑定属性</span><span class="sxs-lookup"><span data-stu-id="039f3-133">Binding Property</span></span>|<span data-ttu-id="039f3-134">Description</span><span class="sxs-lookup"><span data-stu-id="039f3-134">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="039f3-135">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="039f3-135">**InboundOperationType**</span></span>|<span data-ttu-id="039f3-136">指定是否想要执行**轮询**， **TypedPolling**，或**通知**入站操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-136">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="039f3-137">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="039f3-137">Default is **Polling**.</span></span>|  
|<span data-ttu-id="039f3-138">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="039f3-138">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="039f3-139">指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="039f3-139">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="039f3-140">SQL 语句必须返回的结果集行和列组成。</span><span class="sxs-lookup"><span data-stu-id="039f3-140">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="039f3-141">仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行绑定属性。</span><span class="sxs-lookup"><span data-stu-id="039f3-141">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="039f3-142">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="039f3-142">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="039f3-143">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="039f3-143">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="039f3-144">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="039f3-144">The default is 30 seconds.</span></span> <span data-ttu-id="039f3-145">轮询间隔确定连续两次轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="039f3-145">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="039f3-146">如果在指定间隔内执行该语句，该适配器将等待的间隔中的剩余时间。</span><span class="sxs-lookup"><span data-stu-id="039f3-146">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="039f3-147">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="039f3-147">**PollingStatement**</span></span>|<span data-ttu-id="039f3-148">指定要轮询的 SQL Server 数据库表的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="039f3-148">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="039f3-149">你可以指定简单的 SELECT 语句或存储的过程轮询语句。</span><span class="sxs-lookup"><span data-stu-id="039f3-149">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="039f3-150">默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="039f3-150">The default is null.</span></span> <span data-ttu-id="039f3-151">必须指定的值**PollingStatement**来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="039f3-151">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="039f3-152">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="039f3-152">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="039f3-153">你可以指定任意数量的以分号分隔的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="039f3-153">You can specify any number of SQL statements separated by a semi-colon.</span></span>|  
|<span data-ttu-id="039f3-154">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="039f3-154">**PollWhileDataFound**</span></span>|<span data-ttu-id="039f3-155">指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略轮询间隔和连续执行为指定的 SQL 语句**PolledDataAvailableStatement**绑定属性，如果数据中轮询的表。</span><span class="sxs-lookup"><span data-stu-id="039f3-155">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="039f3-156">如果表中可用的任何数据不，该适配器将恢复执行 SQL 语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="039f3-156">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="039f3-157">默认值是**false**。</span><span class="sxs-lookup"><span data-stu-id="039f3-157">Default is **false**.</span></span>|  
  
 <span data-ttu-id="039f3-158">有关这些属性的更完整说明，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="039f3-158">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="039f3-159">有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，进一步阅读。</span><span class="sxs-lookup"><span data-stu-id="039f3-159">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="039f3-160">在 WCF 服务模型中配置轮询</span><span class="sxs-lookup"><span data-stu-id="039f3-160">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="039f3-161">若要接收**轮询**操作使用 WCF 服务模型时，你必须：</span><span class="sxs-lookup"><span data-stu-id="039f3-161">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  
  
1.  <span data-ttu-id="039f3-162">为生成的 WCF 服务协定 （接口）**轮询**从适配器公开的元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-162">Generate a WCF service contract (interface) for the **Polling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="039f3-163">若要执行此操作，你无法使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="039f3-163">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  
  
2.  <span data-ttu-id="039f3-164">实现此接口从 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="039f3-164">Implement a WCF service from this interface.</span></span>  
  
3.  <span data-ttu-id="039f3-165">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="039f3-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="039f3-166">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="039f3-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="039f3-167">本主题中的示例轮询员工表。</span><span class="sxs-lookup"><span data-stu-id="039f3-167">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="039f3-168">此示例还使用 MOVE_EMP_DATA 和 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="039f3-168">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="039f3-169">在示例提供了一个脚本以生成这些项目。</span><span class="sxs-lookup"><span data-stu-id="039f3-169">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="039f3-170">有关这些示例的详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="039f3-170">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="039f3-171">示例中， **Polling_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="039f3-171">A sample, **Polling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="039f3-172">WCF 服务协定和类</span><span class="sxs-lookup"><span data-stu-id="039f3-172">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="039f3-173">你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 WCF 服务协定 （接口） 和支持类**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-173">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="039f3-174">有关生成的 WCF 服务协定的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="039f3-174">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="039f3-175">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="039f3-175">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="039f3-176">下面的代码演示为生成的 WCF 服务协定 （接口）**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-176">The following code shows the WCF service contract (interface) generated for the **Polling** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="PollingOperation")]  
public interface PollingOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Polling/) of message Polling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Polling")]  
    [System.ServiceModel.XmlSerializerFormatAttribute()]  
    void Polling(Polling request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="039f3-177">消息协定</span><span class="sxs-lookup"><span data-stu-id="039f3-177">The Message Contracts</span></span>  
 <span data-ttu-id="039f3-178">消息协定命名空间将被修改， **InboundID**中连接 URI，如果指定参数。</span><span class="sxs-lookup"><span data-stu-id="039f3-178">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="039f3-179">在此示例中，你未指定连接 URI 中的入站的 ID。</span><span class="sxs-lookup"><span data-stu-id="039f3-179">In this example, you did not specify an inbound ID in the connection URI.</span></span> <span data-ttu-id="039f3-180">请求消息返回的数据集。</span><span class="sxs-lookup"><span data-stu-id="039f3-180">The request message returns a DataSet.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Polling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Polling/", IsWrapped=true)]  
public partial class Polling {  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Polling/", Order=0)]  
    [System.Xml.Serialization.XmlArrayAttribute(IsNullable=true)]  
    [System.Xml.Serialization.XmlArrayItemAttribute("DataSet", Namespace="http://schemas.datacontract.org/2004/07/System.Data", IsNullable=false)]  
    public System.Data.DataSet[] PolledData;  
  
    public Polling() {  
    }  
  
    public Polling(System.Data.DataSet[] PolledData) {  
        this.PolledData = PolledData;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="039f3-181">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="039f3-181">WCF Service Class</span></span>  
 <span data-ttu-id="039f3-182">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有为 WCF 服务类实现服务协定 （接口） 从存根 （stub） 文件。</span><span class="sxs-lookup"><span data-stu-id="039f3-182">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="039f3-183">文件的名称是 SqlAdapterBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="039f3-183">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="039f3-184">你可以将插入的逻辑来处理**轮询**直接插入此类操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-184">You can insert the logic to process the **Polling** operation directly into this class.</span></span> <span data-ttu-id="039f3-185">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="039f3-185">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : PollingOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Polling/) of message Polling   
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Polling(Polling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-inbound-messages-for-polling-operation"></a><span data-ttu-id="039f3-186">轮询操作接收入站的消息</span><span class="sxs-lookup"><span data-stu-id="039f3-186">Receiving Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="039f3-187">此部分提供有关如何编写.NET 应用程序以接收使用的入站的轮询消息说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="039f3-187">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="039f3-188">从 SQL 适配器接收轮询消息</span><span class="sxs-lookup"><span data-stu-id="039f3-188">To receive polling messages from the SQL adapter</span></span>  
  
1.  <span data-ttu-id="039f3-189">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]以生成 WCF 服务协定 （接口） 和用于帮助器类**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-189">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Polling** operation.</span></span> <span data-ttu-id="039f3-190">有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="039f3-190">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="039f3-191">生成服务协定和帮助程序类时，可以选择指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="039f3-191">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="039f3-192">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="039f3-192">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="039f3-193">实现 WCF 服务从步骤 1 中生成的接口和帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="039f3-193">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="039f3-194">**轮询**此类的方法可以处理从接收的数据遇到错误时引发异常中止轮询事务，**轮询**操作; 否则该方法将执行不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="039f3-194">The **Polling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Polling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="039f3-195">必须属性 WCF 服务类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="039f3-195">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="039f3-196">在**轮询**方法，你可以直接实现你的应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="039f3-196">Within the **Polling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="039f3-197">SqlAdapterBindingService.cs 中找不到此类。</span><span class="sxs-lookup"><span data-stu-id="039f3-197">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="039f3-198">此示例中的此代码子类**SqlAdapterBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="039f3-198">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="039f3-199">在此代码中，接收作为数据集的轮询消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="039f3-199">In this code, the polling message received as a DataSet is written to the console.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
  
    public override void Polling(Polling request)  
    {  
        Console.WriteLine("\nNew Polling Records Received");  
        Console.WriteLine("*************************************************");  
        DataSet[] dataArray = request.PolledData;  
        foreach (DataTable tab in dataArray[0].Tables)  
        {  
            foreach (DataRow row in tab.Rows)  
            {  
                for (int i = 0; i < tab.Columns.Count; i++)  
                {  
                    Console.WriteLine(row[i]);  
                }  
            }  
        }  
        Console.WriteLine("*************************************************");  
        Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="039f3-200">因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不接受凭据作为连接 URI 的一部分，则必须实现以下类用于传递的 SQL Server 数据库的凭据。</span><span class="sxs-lookup"><span data-stu-id="039f3-200">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="039f3-201">在应用程序的后半部分，将实例化此类，以传递的 SQL Server 凭据。</span><span class="sxs-lookup"><span data-stu-id="039f3-201">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  
  
    ```  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="039f3-202">创建**SqlAdapterBinding**和通过指定绑定属性中配置的轮询操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-202">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="039f3-203">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="039f3-203">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="039f3-204">至少，你必须指定**InboundOperationType**， **PolledDataAvailableStatement**，和**PollingStatement**。</span><span class="sxs-lookup"><span data-stu-id="039f3-204">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
5.  <span data-ttu-id="039f3-205">指定 SQL Server 数据库凭据，方法是实例化**PollingCredentials**在步骤 3 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="039f3-205">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  <span data-ttu-id="039f3-206">创建在步骤 2 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="039f3-206">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  <span data-ttu-id="039f3-207">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。</span><span class="sxs-lookup"><span data-stu-id="039f3-207">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="039f3-208">如果指定，则基连接 URI 不能包含的入站的 ID。</span><span class="sxs-lookup"><span data-stu-id="039f3-208">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="039f3-209">你还应指定下面的凭据。</span><span class="sxs-lookup"><span data-stu-id="039f3-209">You should also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  <span data-ttu-id="039f3-210">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="039f3-210">Add a service endpoint to the service host.</span></span> <span data-ttu-id="039f3-211">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="039f3-211">To do this:</span></span>  
  
    -   <span data-ttu-id="039f3-212">使用在步骤 4 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="039f3-212">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="039f3-213">指定连接 URI，其中包含凭据，如果需要，一个入站的 id。</span><span class="sxs-lookup"><span data-stu-id="039f3-213">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="039f3-214">作为"PollingOperation"指定的协定。</span><span class="sxs-lookup"><span data-stu-id="039f3-214">Specify the contract as "PollingOperation".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify PollingOperation as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
    ```  
  
9. <span data-ttu-id="039f3-215">若要接收轮询数据，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="039f3-215">To receive polling data, open the service host.</span></span> <span data-ttu-id="039f3-216">每当查询返回一个结果集，该适配器将返回数据。</span><span class="sxs-lookup"><span data-stu-id="039f3-216">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. <span data-ttu-id="039f3-217">若要终止轮询，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="039f3-217">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="039f3-218">适配器将继续轮询，直到关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="039f3-218">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="039f3-219">示例</span><span class="sxs-lookup"><span data-stu-id="039f3-219">Example</span></span>  
 <span data-ttu-id="039f3-220">下面的示例演示执行员工表的轮询查询。</span><span class="sxs-lookup"><span data-stu-id="039f3-220">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="039f3-221">轮询语句将执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="039f3-221">The polling statement performs the following tasks:</span></span>  
  
1.  <span data-ttu-id="039f3-222">从员工表中选择的所有记录。</span><span class="sxs-lookup"><span data-stu-id="039f3-222">Selects all the records from the Employee table.</span></span>  
  
2.  <span data-ttu-id="039f3-223">执行上述 MOVE_EMP_DATA 存储过程以从员工表的所有记录都移到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="039f3-223">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="039f3-224">执行上述 ADD_EMP_DETAILS 存储过程以将单个记录添加到员工表。</span><span class="sxs-lookup"><span data-stu-id="039f3-224">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  
  
 <span data-ttu-id="039f3-225">第一条的轮询消息将包含从 Employee 表的所有记录。</span><span class="sxs-lookup"><span data-stu-id="039f3-225">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="039f3-226">后续的轮询消息将包含仅由 ADD_EMP_DETAILS 存储过程插入的最新记录。</span><span class="sxs-lookup"><span data-stu-id="039f3-226">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="039f3-227">适配器将继续轮询，直到按关闭服务主机`<RETURN>`。</span><span class="sxs-lookup"><span data-stu-id="039f3-227">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
using System.Data;  
  
namespace Polling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
  
        public override void Polling(Polling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            DataSet[] dataArray = request.PolledData;  
            foreach (DataTable tab in dataArray[0].Tables)  
            {  
                foreach (DataRow row in tab.Rows)  
                {  
                    for (int i = 0; i < tab.Columns.Count; i++)  
                    {  
                        Console.WriteLine(row[i]);  
                    }  
                }  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start polling...");  
                Console.ReadLine();  
  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Polling started...");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="039f3-228">另请参阅</span><span class="sxs-lookup"><span data-stu-id="039f3-228">See Also</span></span>  
 [<span data-ttu-id="039f3-229">使用 WCF 服务模型的 SQL 适配器的轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="039f3-229">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)