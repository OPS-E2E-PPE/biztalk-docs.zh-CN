---
title: 使用 WCF 服务模型从 SQL Server 接收强类型基于轮询的数据更改消息 |Microsoft Docs
description: 使用.NET 应用程序配置类型化的轮询或使用 BizTalk Server 中的 WCF SQL 适配器使用 WCF 服务的强类型轮询
ms.custom: ''
ms.date: 10/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adf6f1e322485521504259f24dade00bb33a4539
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012646"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a><span data-ttu-id="d2762-103">使用 WCF 服务模型从 SQL Server 接收强类型基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="d2762-103">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>
<span data-ttu-id="d2762-104">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收强类型的轮询消息。</span><span class="sxs-lookup"><span data-stu-id="d2762-104">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive strongly-typed polling messages from SQL Server.</span></span> <span data-ttu-id="d2762-105">可以指定适配器轮询数据库将执行的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="d2762-105">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="d2762-106">轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。</span><span class="sxs-lookup"><span data-stu-id="d2762-106">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="d2762-107">在方案中必须使用强类型轮询你想要接收的强类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="d2762-107">You must use strongly-typed polling in a scenario where you want to receive a strongly-typed result set.</span></span> <span data-ttu-id="d2762-108">适配器如何支持强类型轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="d2762-108">For more information on how the adapter supports strongly-typed polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="d2762-109">如果想要在单个应用程序中有多个轮询操作，则必须指定**InboundID**连接属性连接 URI，使其成为唯一的一部分。</span><span class="sxs-lookup"><span data-stu-id="d2762-109">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="d2762-110">指定的入站的 ID 添加到要使其成为唯一的操作命名空间。</span><span class="sxs-lookup"><span data-stu-id="d2762-110">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="d2762-111">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="d2762-111">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="d2762-112">本主题演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持接收强类型化数据更改消息、 创建.NET 应用程序和生成的 WCF 服务协定**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-112">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving strongly-typed data change messages, create a .NET application and generate the WCF service contract for the **TypedPolling** operation.</span></span> <span data-ttu-id="d2762-113">请确保指定以下内容时生成的 WCF 服务协定：</span><span class="sxs-lookup"><span data-stu-id="d2762-113">Make sure you specify the following while generating the WCF service contract:</span></span>  

- <span data-ttu-id="d2762-114">必须指定**InboundID**连接 URI 的一部分。</span><span class="sxs-lookup"><span data-stu-id="d2762-114">You must specify an **InboundID** as part of the connection URI.</span></span>  

- <span data-ttu-id="d2762-115">必须指定的轮询语句**PollingStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="d2762-115">You must specify a polling statement for the **PollingStatement** binding property.</span></span>  

  <span data-ttu-id="d2762-116">此外，如果你想要指定其他轮询相关生成代理类时的绑定属性指定**PolledDataAvailableStatement**作为：</span><span class="sxs-lookup"><span data-stu-id="d2762-116">Additionally, if you want to specify other polling related binding properties while generating the proxy class, specify the **PolledDataAvailableStatement** as:</span></span>  

```  
SELECT COUNT(*) FROM Employee  
```  

 <span data-ttu-id="d2762-117">**PolledDataAvailableStatement**必须返回的结果集包含正值的第一个单元格。</span><span class="sxs-lookup"><span data-stu-id="d2762-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="d2762-118">如果第一个单元格不包含正值，适配器将不会执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="d2762-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  

 <span data-ttu-id="d2762-119">轮询语句的一部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d2762-119">As part of the polling statement, perform the following operations:</span></span>  

1. <span data-ttu-id="d2762-120">从 Employee 表选择所有行。</span><span class="sxs-lookup"><span data-stu-id="d2762-120">Select all the rows from the Employee table.</span></span>  

2. <span data-ttu-id="d2762-121">执行存储的过程 (MOVE_EMP_DATA) 将所有记录从 Employee 表移动到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="d2762-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  

3. <span data-ttu-id="d2762-122">执行存储的过程 (ADD_EMP_DETAILS) 若要将新记录添加到 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="d2762-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="d2762-123">此过程将雇员姓名、 designation 和薪金作为参数。</span><span class="sxs-lookup"><span data-stu-id="d2762-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  

   <span data-ttu-id="d2762-124">若要执行这些操作，必须指定以下**PollingStatement**属性绑定在生成 WCF 服务协定和帮助程序类时：</span><span class="sxs-lookup"><span data-stu-id="d2762-124">To perform these operations, you must specify the following for the **PollingStatement** binding property while generating the WCF service contract and helper classes:</span></span>  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 <span data-ttu-id="d2762-125">执行轮询语句后，选择从 Employee 表的所有记录，并接收到来自 SQL Server 的消息。</span><span class="sxs-lookup"><span data-stu-id="d2762-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="d2762-126">MOVE_EMP_DATA 存储过程执行适配器后，所有这些记录会移到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="d2762-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="d2762-127">然后，执行 ADD_EMP_DETAILS 存储过程以将新记录添加到 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="d2762-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="d2762-128">下一次轮询执行将仅返回一条记录。</span><span class="sxs-lookup"><span data-stu-id="d2762-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="d2762-129">此循环将一直继续，直到您关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="d2762-129">This cycle continues until you close the service host.</span></span>  

## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="d2762-130">配置与 SQL 适配器的绑定属性的类型化的轮询</span><span class="sxs-lookup"><span data-stu-id="d2762-130">Configuring Typed Polling with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="d2762-131">下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="d2762-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="d2762-132">以外**PollingStatement**绑定属性，在本部分中列出的所有其他绑定属性所需的.NET 应用程序在运行时。</span><span class="sxs-lookup"><span data-stu-id="d2762-132">Other than the **PollingStatement** binding property, all the other binding properties listed in this section are required while running the .NET application.</span></span> <span data-ttu-id="d2762-133">必须指定**PollingStatement**之前生成的 WCF 服务协定绑定属性**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-133">You must specify the **PollingStatement** binding property before generating the WCF service contract **TypedPolling** operation.</span></span>  


|         <span data-ttu-id="d2762-134">绑定属性</span><span class="sxs-lookup"><span data-stu-id="d2762-134">Binding Property</span></span>         |                                                                                                                                                                                                                                                                                              <span data-ttu-id="d2762-135">Description</span><span class="sxs-lookup"><span data-stu-id="d2762-135">Description</span></span>                                                                                                                                                                                                                                                                                              |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="d2762-136">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="d2762-136">**InboundOperationType**</span></span>     |                                                                                                                                                                                             <span data-ttu-id="d2762-137">指定是否想要执行**轮询**， **TypedPolling**，或**通知**的入站操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-137">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="d2762-138">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="d2762-138">Default is **Polling**.</span></span> <span data-ttu-id="d2762-139">若要接收强类型的轮询消息，请将此设置为**TypedPolling**。</span><span class="sxs-lookup"><span data-stu-id="d2762-139">To receive strongly-typed polling messages, set this to **TypedPolling**.</span></span>                                                                                                                                                                                             |
| <span data-ttu-id="d2762-140">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="d2762-140">**PolledDataAvailableStatement**</span></span> |                                                                                                                                           <span data-ttu-id="d2762-141">指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="d2762-141">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="d2762-142">SQL 语句必须返回的结果集由行和列组成。</span><span class="sxs-lookup"><span data-stu-id="d2762-142">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="d2762-143">仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行属性绑定。</span><span class="sxs-lookup"><span data-stu-id="d2762-143">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>                                                                                                                                            |
|   <span data-ttu-id="d2762-144">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="d2762-144">**PollingIntervalInSeconds**</span></span>   |                                                                              <span data-ttu-id="d2762-145">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="d2762-145">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="d2762-146">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="d2762-146">The default is 30 seconds.</span></span> <span data-ttu-id="d2762-147">轮询间隔确定连续轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="d2762-147">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="d2762-148">如果在指定时间间隔内执行该语句，则适配器将等待间隔中的剩余时间。</span><span class="sxs-lookup"><span data-stu-id="d2762-148">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>                                                                              |
|       <span data-ttu-id="d2762-149">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="d2762-149">**PollingStatement**</span></span>       | <span data-ttu-id="d2762-150">指定要轮询 SQL Server 数据库表的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="d2762-150">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="d2762-151">您可以指定简单的 SELECT 语句或存储的过程轮询语句。</span><span class="sxs-lookup"><span data-stu-id="d2762-151">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="d2762-152">默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="d2762-152">The default is null.</span></span> <span data-ttu-id="d2762-153">必须指定的值**PollingStatement**来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="d2762-153">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="d2762-154">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="d2762-154">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="d2762-155">可以指定任意数量的以分号分隔的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="d2762-155">You can specify any number of SQL statements separated by a semi-colon.</span></span> <span data-ttu-id="d2762-156">**重要说明：** 有关**TypedPolling**，生成元数据之前，必须指定此绑定属性。</span><span class="sxs-lookup"><span data-stu-id="d2762-156">**Important:**  For **TypedPolling**, you must specify this binding property before generating metadata.</span></span> |
|      <span data-ttu-id="d2762-157">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="d2762-157">**PollWhileDataFound**</span></span>      |                                                                                 <span data-ttu-id="d2762-158">指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略的轮询间隔，并持续执行 SQL 语句为指定**PolledDataAvailableStatement**绑定属性，如果数据是可用的轮询的表。</span><span class="sxs-lookup"><span data-stu-id="d2762-158">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="d2762-159">如果表中有任何数据，不则适配器将恢复执行 SQL 语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="d2762-159">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="d2762-160">默认值是**false**。</span><span class="sxs-lookup"><span data-stu-id="d2762-160">Default is **false**.</span></span>                                                                                 |

 <span data-ttu-id="d2762-161">有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d2762-161">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="d2762-162">有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="d2762-162">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  

## <a name="configure-strongly-typed-polling-in-the-wcf-service-model"></a><span data-ttu-id="d2762-163">配置 WCF 服务模型中的强类型轮询</span><span class="sxs-lookup"><span data-stu-id="d2762-163">Configure Strongly-typed Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="d2762-164">若要接收**轮询**操作使用 WCF 服务模型时，您必须：</span><span class="sxs-lookup"><span data-stu-id="d2762-164">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  

1. <span data-ttu-id="d2762-165">为生成的 WCF 服务协定 （接口） **TypedPolling**从由适配器公开的元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-165">Generate a WCF service contract (interface) for the **TypedPolling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="d2762-166">若要执行此操作，可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2762-166">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="d2762-167">在生成此示例中的 WCF 服务协定，请确保：</span><span class="sxs-lookup"><span data-stu-id="d2762-167">While generating the WCF service contract for this example, make sure:</span></span>  

   -   <span data-ttu-id="d2762-168">您指定**InboundID**作为**员工**。</span><span class="sxs-lookup"><span data-stu-id="d2762-168">You specify the **InboundID** as **Employee**.</span></span>  

   -   <span data-ttu-id="d2762-169">指定的轮询语句**PollingStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="d2762-169">You specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="d2762-170">对于此示例中，指定轮询语句作为:</span><span class="sxs-lookup"><span data-stu-id="d2762-170">For this example, specify the polling statement as:</span></span>  

       ```  
       SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
       ```  

2. <span data-ttu-id="d2762-171">实现此接口中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="d2762-171">Implement a WCF service from this interface.</span></span>  

3. <span data-ttu-id="d2762-172">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="d2762-172">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="d2762-173">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="d2762-173">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="d2762-174">本主题中的示例轮询 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="d2762-174">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="d2762-175">此示例还使用 MOVE_EMP_DATA 和 ADD_EMP_DETAILS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="d2762-175">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="d2762-176">这些示例提供了一个脚本来生成这些项目。</span><span class="sxs-lookup"><span data-stu-id="d2762-176">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="d2762-177">有关示例的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d2762-177">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="d2762-178">示例中， **TypedPolling_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="d2762-178">A sample, **TypedPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="d2762-179">WCF 服务约定和类</span><span class="sxs-lookup"><span data-stu-id="d2762-179">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="d2762-180">可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 服务协定 （接口） 和支持类**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-180">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="d2762-181">有关生成的 WCF 服务协定的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="d2762-181">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="d2762-182">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="d2762-182">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="d2762-183">下面的代码演示 WCF 服务协定 （接口） 为生成**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-183">The following code shows the WCF service contract (interface) generated for the **TypedPolling** operation.</span></span>  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="TypedPolling_Employee")]  
public interface TypedPolling_Employee {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="TypedPolling")]  
    void TypedPolling(TypedPolling request);  
}  
```  

### <a name="the-message-contracts"></a><span data-ttu-id="d2762-184">消息协定</span><span class="sxs-lookup"><span data-stu-id="d2762-184">The Message Contracts</span></span>  
 <span data-ttu-id="d2762-185">通过修改消息协定命名空间**InboundID**中的连接 URI，如果指定的参数。</span><span class="sxs-lookup"><span data-stu-id="d2762-185">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="d2762-186">在此示例中，指定入站的 ID 作为**员工**。</span><span class="sxs-lookup"><span data-stu-id="d2762-186">In this example, you specified the inbound ID as **Employee**.</span></span> <span data-ttu-id="d2762-187">请求消息返回强类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="d2762-187">The request message returns a strongly-typed result set.</span></span>  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="TypedPolling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", IsWrapped=true)]  
public partial class TypedPolling {  

[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=0)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0;  

[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=1)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1;  

    public TypedPolling() {  
    }  

    public TypedPolling(schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0, schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1) {  
        this.TypedPollingResultSet0 = TypedPollingResultSet0;  
        this.TypedPollingResultSet1 = TypedPollingResultSet1;  
    }  
}  
```  

### <a name="wcf-service-class"></a><span data-ttu-id="d2762-188">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="d2762-188">WCF Service Class</span></span>  
 <span data-ttu-id="d2762-189">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有实现服务协定 （接口） 中的 WCF 服务类的存根文件。</span><span class="sxs-lookup"><span data-stu-id="d2762-189">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="d2762-190">文件的名称是 SqlAdapterBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="d2762-190">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="d2762-191">您可以将逻辑来处理**TypedPolling**直接在此类操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-191">You can insert the logic to process the **TypedPolling** operation directly into this class.</span></span> <span data-ttu-id="d2762-192">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2762-192">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

```  
namespace SqlAdapterBindingNamespace {  

    public class SqlAdapterBindingService : TypedPolling_Employee {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void TypedPolling(TypedPolling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receive-strongly-typed-inbound-messages-for-polling-operation"></a><span data-ttu-id="d2762-193">轮询操作接收强类型化的入站的消息</span><span class="sxs-lookup"><span data-stu-id="d2762-193">Receive Strongly-typed Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="d2762-194">本部分说明了如何编写.NET 应用程序以接收使用强类型的入站的轮询消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2762-194">This section provides instructions on how to write a .NET application to receive strongly-typed inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

1. <span data-ttu-id="d2762-195">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 服务协定 （接口） 和帮助器类实现**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-195">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="d2762-196">请确保指定以下内容时生成此示例中的 WCF 服务协定：</span><span class="sxs-lookup"><span data-stu-id="d2762-196">Make sure you specify the following while generating the WCF service contract for this example:</span></span>  

   - <span data-ttu-id="d2762-197">必须指定**InboundID**作为**员工**。</span><span class="sxs-lookup"><span data-stu-id="d2762-197">You must specify the **InboundID** as **Employee**.</span></span>  

   - <span data-ttu-id="d2762-198">必须指定的轮询语句**PollingStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="d2762-198">You must specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="d2762-199">对于此示例中，指定轮询语句作为:</span><span class="sxs-lookup"><span data-stu-id="d2762-199">For this example, specify the polling statement as:</span></span>  

     ```  
     SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
     ```  

     <span data-ttu-id="d2762-200">有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="d2762-200">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="d2762-201">在生成服务协定和帮助程序类时，可以选择指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="d2762-201">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="d2762-202">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="d2762-202">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="d2762-203">实现在步骤 1 中生成的接口和帮助程序类中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="d2762-203">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="d2762-204">**TypedPolling**此类方法可以处理从接收的数据中遇到错误时引发异常中止轮询事务**TypedPolling**操作; 否则为方法不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="d2762-204">The **TypedPolling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **TypedPolling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="d2762-205">必须按如下所示属性的 WCF 服务类：</span><span class="sxs-lookup"><span data-stu-id="d2762-205">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="d2762-206">内**TypedPolling**方法，可以直接实现应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="d2762-206">Within the **TypedPolling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="d2762-207">可以 SqlAdapterBindingService.cs 中找到此类。</span><span class="sxs-lookup"><span data-stu-id="d2762-207">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="d2762-208">此代码在此示例中的嵌套类**SqlAdapterBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="d2762-208">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="d2762-209">在此代码中，作为强类型化结果集接收轮询消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="d2762-209">In this code, the polling message received as a strongly-typed result set is written to the console.</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
   {  
       public override void TypedPolling(TypedPolling request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  

           for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.TypedPollingResultSet0[i].Employee_ID,  
               request.TypedPollingResultSet0[i].Name,  
               request.TypedPollingResultSet0[i].Designation,  
               request.TypedPollingResultSet0[i].Salary);  
           }  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. <span data-ttu-id="d2762-210">因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不接受凭据的连接 URI 的一部分，必须实现以下类用于传递 SQL Server 数据库的凭据。</span><span class="sxs-lookup"><span data-stu-id="d2762-210">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="d2762-211">在应用程序的后半部分，将实例化此类，以传递的 SQL Server 凭据。</span><span class="sxs-lookup"><span data-stu-id="d2762-211">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  

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

4. <span data-ttu-id="d2762-212">创建**SqlAdapterBinding**和配置轮询操作时，指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="d2762-212">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="d2762-213">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d2762-213">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="d2762-214">至少，您必须指定**InboundOperationType**， **PolledDataAvailableStatement**，并**PollingStatement**。</span><span class="sxs-lookup"><span data-stu-id="d2762-214">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.TypedPolling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

5. <span data-ttu-id="d2762-215">通过实例化指定的 SQL Server 数据库凭据**PollingCredentials**步骤 3 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="d2762-215">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. <span data-ttu-id="d2762-216">创建在步骤 2 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="d2762-216">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. <span data-ttu-id="d2762-217">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和基本连接 URI。</span><span class="sxs-lookup"><span data-stu-id="d2762-217">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="d2762-218">基本连接 URI 不能包含入站 id。</span><span class="sxs-lookup"><span data-stu-id="d2762-218">The base connection URI cannot contain the inbound ID.</span></span> <span data-ttu-id="d2762-219">此外必须指定凭据。</span><span class="sxs-lookup"><span data-stu-id="d2762-219">You must also specify the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. <span data-ttu-id="d2762-220">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="d2762-220">Add a service endpoint to the service host.</span></span> <span data-ttu-id="d2762-221">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d2762-221">To do this:</span></span>  

   -   <span data-ttu-id="d2762-222">使用在步骤 4 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="d2762-222">Use the binding created in step 4.</span></span>  

   -   <span data-ttu-id="d2762-223">指定连接 URI，其中包含的凭据，如果需要，入站 id。</span><span class="sxs-lookup"><span data-stu-id="d2762-223">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   -   <span data-ttu-id="d2762-224">作为"TypedPolling_Employee"指定的协定。</span><span class="sxs-lookup"><span data-stu-id="d2762-224">Specify the contract as "TypedPolling_Employee".</span></span>  

   ```  
   // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Employee");  
   serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
   ```  

9. <span data-ttu-id="d2762-225">若要接收轮询数据，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="d2762-225">To receive polling data, open the service host.</span></span> <span data-ttu-id="d2762-226">只要查询返回结果集，则适配器将返回数据。</span><span class="sxs-lookup"><span data-stu-id="d2762-226">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

10. <span data-ttu-id="d2762-227">若要终止轮询，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="d2762-227">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="d2762-228">该适配器将继续轮询，直到关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="d2762-228">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="d2762-229">示例</span><span class="sxs-lookup"><span data-stu-id="d2762-229">Example</span></span>  
 <span data-ttu-id="d2762-230">下面的示例演示执行 Employee 表的轮询查询。</span><span class="sxs-lookup"><span data-stu-id="d2762-230">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="d2762-231">轮询语句将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d2762-231">The polling statement performs the following tasks:</span></span>  

1. <span data-ttu-id="d2762-232">从 Employee 表中选择的所有记录。</span><span class="sxs-lookup"><span data-stu-id="d2762-232">Selects all the records from the Employee table.</span></span>  

2. <span data-ttu-id="d2762-233">执行上述 MOVE_EMP_DATA 存储过程以将所有记录从 Employee 表都移动到 EmployeeHistory 表。</span><span class="sxs-lookup"><span data-stu-id="d2762-233">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  

3. <span data-ttu-id="d2762-234">执行上述 ADD_EMP_DETAILS 存储过程以将一条记录添加到 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="d2762-234">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  

   <span data-ttu-id="d2762-235">第一个轮询消息将包含从 Employee 表的所有记录。</span><span class="sxs-lookup"><span data-stu-id="d2762-235">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="d2762-236">后续轮询消息将包含仅由 ADD_EMP_DETAILS 存储过程插入的最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="d2762-236">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="d2762-237">适配器将继续轮询，直到按关闭服务主机`<RETURN>`。</span><span class="sxs-lookup"><span data-stu-id="d2762-237">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

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

namespace TypedPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  

            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
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
                binding.InboundOperationType = InboundOperation.TypedPolling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  

                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundId=Employee");  

                // This URI is used to initialize the ServiceHost. It cannot contain  
                // the InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  

                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
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

## <a name="see-also"></a><span data-ttu-id="d2762-238">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2762-238">See Also</span></span>  
 [<span data-ttu-id="d2762-239">SQL 适配器使用 WCF 服务模型轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="d2762-239">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)
