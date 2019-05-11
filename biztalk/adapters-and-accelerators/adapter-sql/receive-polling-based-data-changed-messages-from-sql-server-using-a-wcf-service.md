---
title: 使用 WCF 服务模型从 SQL Server 接收基于轮询的数据更改消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8713dd38-65ff-4d89-b23b-a93c06c5ff22
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f302a286bef165f5708d9f3c34fc7c3137451a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368571"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-the-wcf-service-model"></a><span data-ttu-id="8e370-102">使用 WCF 服务模型从 SQL Server 接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="8e370-102">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>
<span data-ttu-id="8e370-103">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收定期的数据更改消息的 SQL Server 表或视图。</span><span class="sxs-lookup"><span data-stu-id="8e370-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="8e370-104">可以指定适配器轮询数据库将执行的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="8e370-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="8e370-105">轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。</span><span class="sxs-lookup"><span data-stu-id="8e370-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  

 <span data-ttu-id="8e370-106">适配器如何支持轮询的详细信息，请参阅[在使用 SQL 适配器的 SQL Server 中轮询](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8e370-106">For more information on how the adapter supports polling, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="8e370-107">本主题演示如何使用**轮询**的入站操作使用轮询消息。</span><span class="sxs-lookup"><span data-stu-id="8e370-107">This topic demonstrates how to use the **Polling** inbound operation to use polling messages.</span></span> <span data-ttu-id="8e370-108">轮询操作的消息不是强的类型。</span><span class="sxs-lookup"><span data-stu-id="8e370-108">The message for the Polling operation is not strongly-typed.</span></span> <span data-ttu-id="8e370-109">如果你想要获取强类型的轮询消息，则必须使用**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-109">If you want to get strongly-typed polling message, you must use the **TypedPolling** operation.</span></span> <span data-ttu-id="8e370-110">此外必须使用**TypedPolling**操作在单个应用程序中有多个轮询操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-110">You must also use the **TypedPolling** operation to have multiple polling operations in a single application.</span></span> <span data-ttu-id="8e370-111">有关如何执行的说明**TypedPolling**操作，请参阅[接收强类型基于轮询的数据更改消息从 SQL Server 使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="8e370-111">For instructions on how to perform **TypedPolling** operation, see [Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md).</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="8e370-112">如果想要在单个应用程序中有多个轮询操作，则必须指定**InboundID**连接属性连接 URI，使其成为唯一的一部分。</span><span class="sxs-lookup"><span data-stu-id="8e370-112">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="8e370-113">指定的入站的 ID 添加到要使其成为唯一的操作命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e370-113">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="8e370-114">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="8e370-114">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="8e370-115">本主题演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持接收数据更改消息、 创建.NET 应用程序和生成的 WCF 服务协定**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-115">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a .NET application and generate the WCF service contract for the **Polling** operation.</span></span> <span data-ttu-id="8e370-116">如果你想要指定轮询相关属性绑定生成 WCF 服务约定时，指定**PolledDataAvailableStatement**作为：</span><span class="sxs-lookup"><span data-stu-id="8e370-116">If you want to specify the polling related binding properties while generating the WCF service contract, specify the **PolledDataAvailableStatement** as:</span></span>  

```  
SELECT COUNT(*) FROM Employee  
```  

 <span data-ttu-id="8e370-117">**PolledDataAvailableStatement**必须返回的结果集包含正值的第一个单元格。</span><span class="sxs-lookup"><span data-stu-id="8e370-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="8e370-118">如果第一个单元格不包含正值，适配器将不会执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="8e370-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  

 <span data-ttu-id="8e370-119">轮询语句的一部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e370-119">As part of the polling statement, perform the following operations:</span></span>  

1. <span data-ttu-id="8e370-120">从 Employee 表选择所有行。</span><span class="sxs-lookup"><span data-stu-id="8e370-120">Select all the rows from the Employee table.</span></span>  

2. <span data-ttu-id="8e370-121">执行存储的过程 (MOVE_EMP_DATA) 将所有记录从 Employee 表移动到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="8e370-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  

3. <span data-ttu-id="8e370-122">执行存储的过程 (ADD_EMP_DETAILS) 若要将新记录添加到 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="8e370-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="8e370-123">此过程将雇员姓名、 designation 和薪金作为参数。</span><span class="sxs-lookup"><span data-stu-id="8e370-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  

   <span data-ttu-id="8e370-124">若要执行这些操作，必须指定以下**PollingStatement**绑定属性：</span><span class="sxs-lookup"><span data-stu-id="8e370-124">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 <span data-ttu-id="8e370-125">执行轮询语句后，选择从 Employee 表的所有记录，并接收到来自 SQL Server 的消息。</span><span class="sxs-lookup"><span data-stu-id="8e370-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="8e370-126">MOVE_EMP_DATA 存储过程执行适配器后，所有这些记录会移到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="8e370-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="8e370-127">然后，执行 ADD_EMP_DETAILS 存储过程以将新记录添加到 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="8e370-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="8e370-128">下一次轮询执行将仅返回一条记录。</span><span class="sxs-lookup"><span data-stu-id="8e370-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="8e370-129">此循环将一直继续，直到您关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="8e370-129">This cycle continues until you close the service host.</span></span>  

## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="8e370-130">使用 SQL 适配器的绑定属性中配置轮询查询</span><span class="sxs-lookup"><span data-stu-id="8e370-130">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="8e370-131">下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="8e370-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="8e370-132">轮询的.NET 应用程序的一部分，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="8e370-132">You must specify these binding properties as part of the .NET application for polling.</span></span>  


|         <span data-ttu-id="8e370-133">绑定属性</span><span class="sxs-lookup"><span data-stu-id="8e370-133">Binding Property</span></span>         |                                                                                                                                                                                                                                         <span data-ttu-id="8e370-134">Description</span><span class="sxs-lookup"><span data-stu-id="8e370-134">Description</span></span>                                                                                                                                                                                                                                          |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="8e370-135">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="8e370-135">**InboundOperationType**</span></span>     |                                                                                                                                                                             <span data-ttu-id="8e370-136">指定是否想要执行**轮询**， **TypedPolling**，或**通知**的入站操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-136">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="8e370-137">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="8e370-137">Default is **Polling**.</span></span>                                                                                                                                                                              |
| <span data-ttu-id="8e370-138">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="8e370-138">**PolledDataAvailableStatement**</span></span> |                                                                                       <span data-ttu-id="8e370-139">指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="8e370-139">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="8e370-140">SQL 语句必须返回的结果集由行和列组成。</span><span class="sxs-lookup"><span data-stu-id="8e370-140">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="8e370-141">仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行属性绑定。</span><span class="sxs-lookup"><span data-stu-id="8e370-141">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>                                                                                       |
|   <span data-ttu-id="8e370-142">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="8e370-142">**PollingIntervalInSeconds**</span></span>   |                         <span data-ttu-id="8e370-143">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="8e370-143">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="8e370-144">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="8e370-144">The default is 30 seconds.</span></span> <span data-ttu-id="8e370-145">轮询间隔确定连续轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8e370-145">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="8e370-146">如果在指定时间间隔内执行该语句，则适配器将等待间隔中的剩余时间。</span><span class="sxs-lookup"><span data-stu-id="8e370-146">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>                          |
|       <span data-ttu-id="8e370-147">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="8e370-147">**PollingStatement**</span></span>       | <span data-ttu-id="8e370-148">指定要轮询 SQL Server 数据库表的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="8e370-148">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="8e370-149">您可以指定简单的 SELECT 语句或存储的过程轮询语句。</span><span class="sxs-lookup"><span data-stu-id="8e370-149">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="8e370-150">默认值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8e370-150">The default is null.</span></span> <span data-ttu-id="8e370-151">必须指定的值**PollingStatement**来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="8e370-151">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="8e370-152">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="8e370-152">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="8e370-153">可以指定任意数量的以分号分隔的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="8e370-153">You can specify any number of SQL statements separated by a semi-colon.</span></span> |
|      <span data-ttu-id="8e370-154">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="8e370-154">**PollWhileDataFound**</span></span>      |                            <span data-ttu-id="8e370-155">指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略的轮询间隔，并持续执行 SQL 语句为指定**PolledDataAvailableStatement**绑定属性，如果数据是可用的轮询的表。</span><span class="sxs-lookup"><span data-stu-id="8e370-155">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="8e370-156">如果表中有任何数据，不则适配器将恢复执行 SQL 语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="8e370-156">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="8e370-157">默认值是**false**。</span><span class="sxs-lookup"><span data-stu-id="8e370-157">Default is **false**.</span></span>                             |

 <span data-ttu-id="8e370-158">有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="8e370-158">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="8e370-159">有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="8e370-159">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  

## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="8e370-160">在 WCF 服务模型中配置轮询</span><span class="sxs-lookup"><span data-stu-id="8e370-160">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="8e370-161">若要接收**轮询**操作使用 WCF 服务模型时，您必须：</span><span class="sxs-lookup"><span data-stu-id="8e370-161">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  

1. <span data-ttu-id="8e370-162">为生成的 WCF 服务协定 （接口）**轮询**从由适配器公开的元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-162">Generate a WCF service contract (interface) for the **Polling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="8e370-163">若要执行此操作，可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e370-163">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  

2. <span data-ttu-id="8e370-164">实现此接口中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="8e370-164">Implement a WCF service from this interface.</span></span>  

3. <span data-ttu-id="8e370-165">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="8e370-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="8e370-166">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="8e370-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="8e370-167">本主题中的示例轮询 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="8e370-167">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="8e370-168">此示例还使用 MOVE_EMP_DATA 和 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="8e370-168">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="8e370-169">这些示例提供了一个脚本来生成这些项目。</span><span class="sxs-lookup"><span data-stu-id="8e370-169">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="8e370-170">有关示例的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8e370-170">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="8e370-171">示例中， **Polling_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="8e370-171">A sample, **Polling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="8e370-172">WCF 服务约定和类</span><span class="sxs-lookup"><span data-stu-id="8e370-172">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="8e370-173">可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 服务协定 （接口） 和支持类**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-173">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="8e370-174">有关生成的 WCF 服务协定的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="8e370-174">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="8e370-175">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="8e370-175">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="8e370-176">下面的代码演示 WCF 服务协定 （接口） 为生成**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-176">The following code shows the WCF service contract (interface) generated for the **Polling** operation.</span></span>  

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

### <a name="the-message-contracts"></a><span data-ttu-id="8e370-177">消息协定</span><span class="sxs-lookup"><span data-stu-id="8e370-177">The Message Contracts</span></span>  
 <span data-ttu-id="8e370-178">通过修改消息协定命名空间**InboundID**中的连接 URI，如果指定的参数。</span><span class="sxs-lookup"><span data-stu-id="8e370-178">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="8e370-179">在此示例中，你未指定连接 URI 中的入站的 ID。</span><span class="sxs-lookup"><span data-stu-id="8e370-179">In this example, you did not specify an inbound ID in the connection URI.</span></span> <span data-ttu-id="8e370-180">请求消息返回的数据集。</span><span class="sxs-lookup"><span data-stu-id="8e370-180">The request message returns a DataSet.</span></span>  

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

### <a name="wcf-service-class"></a><span data-ttu-id="8e370-181">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="8e370-181">WCF Service Class</span></span>  
 <span data-ttu-id="8e370-182">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有实现服务协定 （接口） 中的 WCF 服务类的存根文件。</span><span class="sxs-lookup"><span data-stu-id="8e370-182">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="8e370-183">文件的名称是 SqlAdapterBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="8e370-183">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="8e370-184">您可以将逻辑来处理**轮询**直接在此类操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-184">You can insert the logic to process the **Polling** operation directly into this class.</span></span> <span data-ttu-id="8e370-185">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e370-185">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

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

## <a name="receiving-inbound-messages-for-polling-operation"></a><span data-ttu-id="8e370-186">轮询操作接收入站的消息</span><span class="sxs-lookup"><span data-stu-id="8e370-186">Receiving Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="8e370-187">本部分说明了如何编写.NET 应用程序以接收使用入站的轮询消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e370-187">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="8e370-188">若要从 SQL 适配器接收轮询消息</span><span class="sxs-lookup"><span data-stu-id="8e370-188">To receive polling messages from the SQL adapter</span></span>  

1. <span data-ttu-id="8e370-189">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 服务协定 （接口） 和帮助器类实现**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-189">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Polling** operation.</span></span> <span data-ttu-id="8e370-190">有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="8e370-190">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="8e370-191">在生成服务协定和帮助程序类时，可以选择指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="8e370-191">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="8e370-192">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="8e370-192">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="8e370-193">实现在步骤 1 中生成的接口和帮助程序类中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="8e370-193">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="8e370-194">**轮询**此类方法可以处理从接收的数据中遇到错误时引发异常中止轮询事务**轮询**操作; 否则该方法执行不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="8e370-194">The **Polling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Polling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="8e370-195">必须按如下所示属性的 WCF 服务类：</span><span class="sxs-lookup"><span data-stu-id="8e370-195">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="8e370-196">内**轮询**方法，可以直接实现应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="8e370-196">Within the **Polling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="8e370-197">可以 SqlAdapterBindingService.cs 中找到此类。</span><span class="sxs-lookup"><span data-stu-id="8e370-197">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="8e370-198">此代码在此示例中的嵌套类**SqlAdapterBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="8e370-198">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="8e370-199">在此代码中，接收到作为数据集的轮询消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="8e370-199">In this code, the polling message received as a DataSet is written to the console.</span></span>  

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

3. <span data-ttu-id="8e370-200">因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不接受凭据的连接 URI 的一部分，必须实现以下类用于传递 SQL Server 数据库的凭据。</span><span class="sxs-lookup"><span data-stu-id="8e370-200">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="8e370-201">在应用程序的后半部分，将实例化此类，以传递的 SQL Server 凭据。</span><span class="sxs-lookup"><span data-stu-id="8e370-201">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  

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

4. <span data-ttu-id="8e370-202">创建**SqlAdapterBinding**和配置轮询操作时，指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="8e370-202">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="8e370-203">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8e370-203">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="8e370-204">至少，您必须指定**InboundOperationType**， **PolledDataAvailableStatement**，并**PollingStatement**。</span><span class="sxs-lookup"><span data-stu-id="8e370-204">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

5. <span data-ttu-id="8e370-205">通过实例化指定的 SQL Server 数据库凭据**PollingCredentials**步骤 3 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="8e370-205">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. <span data-ttu-id="8e370-206">创建在步骤 2 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="8e370-206">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. <span data-ttu-id="8e370-207">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和基本连接 URI。</span><span class="sxs-lookup"><span data-stu-id="8e370-207">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="8e370-208">如果指定的基本连接 URI 不能包含的入站的 ID。</span><span class="sxs-lookup"><span data-stu-id="8e370-208">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="8e370-209">你还应指定下面的凭据。</span><span class="sxs-lookup"><span data-stu-id="8e370-209">You should also specify the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. <span data-ttu-id="8e370-210">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="8e370-210">Add a service endpoint to the service host.</span></span> <span data-ttu-id="8e370-211">若要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="8e370-211">To do this:</span></span>  

   -   <span data-ttu-id="8e370-212">使用在步骤 4 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="8e370-212">Use the binding created in step 4.</span></span>  

   -   <span data-ttu-id="8e370-213">指定连接 URI，其中包含的凭据，如果需要，入站 id。</span><span class="sxs-lookup"><span data-stu-id="8e370-213">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   -   <span data-ttu-id="8e370-214">作为"PollingOperation"指定的协定。</span><span class="sxs-lookup"><span data-stu-id="8e370-214">Specify the contract as "PollingOperation".</span></span>  

   ```  
   // Add service endpoint: be sure to specify PollingOperation as the contract  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
   serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
   ```  

9. <span data-ttu-id="8e370-215">若要接收轮询数据，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="8e370-215">To receive polling data, open the service host.</span></span> <span data-ttu-id="8e370-216">只要查询返回结果集，则适配器将返回数据。</span><span class="sxs-lookup"><span data-stu-id="8e370-216">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

10. <span data-ttu-id="8e370-217">若要终止轮询，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="8e370-217">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="8e370-218">该适配器将继续轮询，直到关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="8e370-218">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="8e370-219">示例</span><span class="sxs-lookup"><span data-stu-id="8e370-219">Example</span></span>  
 <span data-ttu-id="8e370-220">下面的示例演示执行 Employee 表的轮询查询。</span><span class="sxs-lookup"><span data-stu-id="8e370-220">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="8e370-221">轮询语句将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8e370-221">The polling statement performs the following tasks:</span></span>  

1. <span data-ttu-id="8e370-222">从 Employee 表中选择的所有记录。</span><span class="sxs-lookup"><span data-stu-id="8e370-222">Selects all the records from the Employee table.</span></span>  

2. <span data-ttu-id="8e370-223">执行上述 MOVE_EMP_DATA 存储过程以将所有记录从 Employee 表都移动到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="8e370-223">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  

3. <span data-ttu-id="8e370-224">执行上述 ADD_EMP_DETAILS 存储过程以将一条记录添加到 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="8e370-224">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  

   <span data-ttu-id="8e370-225">第一个轮询消息将包含从 Employee 表的所有记录。</span><span class="sxs-lookup"><span data-stu-id="8e370-225">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="8e370-226">后续轮询消息将包含仅由 ADD_EMP_DETAILS 存储过程插入的最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="8e370-226">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="8e370-227">适配器将继续轮询，直到按关闭服务主机`<RETURN>`。</span><span class="sxs-lookup"><span data-stu-id="8e370-227">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="8e370-228">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e370-228">See Also</span></span>  
 [<span data-ttu-id="8e370-229">SQL 适配器使用 WCF 服务模型轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e370-229">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)