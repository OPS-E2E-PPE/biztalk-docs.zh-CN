---
title: "使用 WCF 服务模型使用存储的过程的轮询 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47dcb866-9161-4b28-9481-2761794ce805
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3fb7ebcbccb1f0edb3370176192f55f0db4985a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model"></a><span data-ttu-id="c82be-102">轮询 Oracle E-business Suite 与 WCF 服务模型使用存储的过程</span><span class="sxs-lookup"><span data-stu-id="c82be-102">Poll Oracle E-Business Suite using stored procedures with the WCF service model</span></span>
<span data-ttu-id="c82be-103">你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收定期的数据更改消息通过使用存储的过程来定期轮询 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="c82be-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using stored procedures to periodically poll the Oracle database.</span></span> <span data-ttu-id="c82be-104">你可以指定为适配器执行定期轮询 Oracle 数据库的轮询语句的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="c82be-104">You can specify a stored procedure as a polling statement that the adapter executes periodically to poll the Oracle database.</span></span>  
  
 <span data-ttu-id="c82be-105">若要启用轮询，必须指定某些绑定属性，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="c82be-105">To enable polling, you must specify certain binding properties as described in this topic.</span></span>  <span data-ttu-id="c82be-106">有关如何适配器支持轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="c82be-106">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="c82be-107">使用 Oracle E-business 适配器绑定属性中配置的轮询操作</span><span class="sxs-lookup"><span data-stu-id="c82be-107">Configuring a Polling Operation with Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="c82be-108">下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-108">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="c82be-109">在运行轮询应用程序时，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-109">You must specify these binding properties while running the polling application.</span></span>  
  
|<span data-ttu-id="c82be-110">绑定属性</span><span class="sxs-lookup"><span data-stu-id="c82be-110">Binding Property</span></span>|<span data-ttu-id="c82be-111">Description</span><span class="sxs-lookup"><span data-stu-id="c82be-111">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="c82be-112">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="c82be-112">**InboundOperationType**</span></span>|<span data-ttu-id="c82be-113">指定是否想要执行**轮询**或**通知**入站操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-113">Specifies whether you want to perform a **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="c82be-114">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="c82be-114">Default is **Polling**.</span></span>|  
|<span data-ttu-id="c82be-115">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="c82be-115">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="c82be-116">指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="c82be-116">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="c82be-117">仅当一条记录时，存储的过程指定为**PollingInput**将执行绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-117">Only if a record is available, the stored procedure you specified for the **PollingInput** binding property will be executed.</span></span>|  
|<span data-ttu-id="c82be-118">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="c82be-118">**PollingInterval**</span></span>|<span data-ttu-id="c82be-119">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-119">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="c82be-120">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="c82be-120">The default is 30 seconds.</span></span> <span data-ttu-id="c82be-121">轮询间隔确定连续两次轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c82be-121">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="c82be-122">如果在指定间隔内执行该语句，该适配器休眠的剩余时间的时间间隔内。</span><span class="sxs-lookup"><span data-stu-id="c82be-122">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="c82be-123">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="c82be-123">**PollingInput**</span></span>|<span data-ttu-id="c82be-124">指定的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="c82be-124">Specifies the polling statement.</span></span> <span data-ttu-id="c82be-125">若要轮询使用存储的过程，必须指定此绑定属性的整个请求消息。</span><span class="sxs-lookup"><span data-stu-id="c82be-125">To poll using a stored procedure, you must specify the entire request message for this binding property.</span></span> <span data-ttu-id="c82be-126">请求消息必须是相同的调用存储的过程作为出站操作发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="c82be-126">The request message must be the same that you send to the adapter for invoking the stored procedure as an outbound operation.</span></span> <span data-ttu-id="c82be-127">默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="c82be-127">The default is null.</span></span><br /><br /> <span data-ttu-id="c82be-128">必须指定的值**PollingInput**绑定属性来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="c82be-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="c82be-129">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>|  
|<span data-ttu-id="c82be-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="c82be-130">**PollingAction**</span></span>|<span data-ttu-id="c82be-131">指定轮询操作的操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="c82be-132">你可以确定此轮询操作的生成操作使用的服务接口[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c82be-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>|  
|<span data-ttu-id="c82be-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="c82be-133">**PostPollStatement**</span></span>|<span data-ttu-id="c82be-134">指定在指定的语句之后执行的语句块**PollingInput**绑定属性执行。</span><span class="sxs-lookup"><span data-stu-id="c82be-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>|  
|<span data-ttu-id="c82be-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="c82be-135">**PollWhileDataFound**</span></span>|<span data-ttu-id="c82be-136">指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略轮询间隔和连续执行轮询语句中，如果数据中轮询的表。</span><span class="sxs-lookup"><span data-stu-id="c82be-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="c82be-137">如果表中可用的任何数据不，该适配器将恢复执行轮询语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="c82be-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="c82be-138">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="c82be-138">Default is false.</span></span>|  
  
 <span data-ttu-id="c82be-139">有关这些属性的更完整说明，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c82be-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="c82be-140">有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要轮询，请阅读以下部分。</span><span class="sxs-lookup"><span data-stu-id="c82be-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll, read the following sections.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="c82be-141">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="c82be-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="c82be-142">在此主题中，以演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收使用存储的过程的消息，你使用 GET_ACTIVITYS 的数据更改的支持存储过程来轮询 Oracle 数据库中的 ACCOUNTACTIVITY 表。</span><span class="sxs-lookup"><span data-stu-id="c82be-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using stored procedures, you use the GET_ACTIVITYS stored procedure to poll the ACCOUNTACTIVITY table in the Oracle database.</span></span> <span data-ttu-id="c82be-143">此存储的过程时使用 ACCOUNT_PKG 包。</span><span class="sxs-lookup"><span data-stu-id="c82be-143">This stored procedure is available with the ACCOUNT_PKG package.</span></span> <span data-ttu-id="c82be-144">你可以运行这些示例数据库中创建这些对象提供的 SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="c82be-144">You can run the SQL scripts provided with the samples to create these objects in the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c82be-145">此主题轮询中 ACCOUNTACTIVITY 表，其中基数据库表创建通过运行这些示例提供的脚本的示例。</span><span class="sxs-lookup"><span data-stu-id="c82be-145">The example in this topic polls the ACCOUNTACTIVITY table, which is a base database table created by running the scripts provided with the samples.</span></span> <span data-ttu-id="c82be-146">若要轮询任何其他表，包括接口表本主题中所述，你必须执行类似的过程。</span><span class="sxs-lookup"><span data-stu-id="c82be-146">You must perform similar procedures as described in this topic to poll any other table, including interface tables.</span></span>  
  
 <span data-ttu-id="c82be-147">为了演示轮询操作，我们执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c82be-147">To demonstrate a polling operation, we do the following:</span></span>  
  
-   <span data-ttu-id="c82be-148">指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性以确定其中表轮询 (ACCOUNTACTIVITY) 有任何数据。</span><span class="sxs-lookup"><span data-stu-id="c82be-148">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the table being polled (ACCOUNTACTIVITY) has any data.</span></span> <span data-ttu-id="c82be-149">在此示例中，你可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="c82be-149">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  
  
     <span data-ttu-id="c82be-150">这可确保仅当 ACCOUNTACTIVITY 表具有某些记录时，适配器都将执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="c82be-150">This ensures that the adapter executes the polling statement only when the ACCOUNTACTIVITY table has some records.</span></span>  
  
-   <span data-ttu-id="c82be-151">通过提供作为的一部分的请求消息执行存储的过程，GET_ACTIVITYS， **PollingInput**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-151">Execute a stored procedure, GET_ACTIVITYS, by providing the request message as part of the **PollingInput** binding property.</span></span> <span data-ttu-id="c82be-152">此存储的过程将检索 ACCOUNTACTIVITY 表中的所有行，并且你将获得该适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="c82be-152">This stored procedure will retrieve all the rows in the ACCOUNTACTIVITY table and you will get a response message from the adapter.</span></span>  
  
-   <span data-ttu-id="c82be-153">作为的一部分执行一个 PL/SQL 块**PostPollStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-153">Execute a PL/SQL block as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="c82be-154">此语句将所有数据从 ACCOUNTACTIVITY 表都移到数据库中的另一个表。</span><span class="sxs-lookup"><span data-stu-id="c82be-154">This statement will move all data from ACCOUNTACTIVITY table to another table in the database.</span></span> <span data-ttu-id="c82be-155">发生这种情况下, 一次后**PollingInput**是执行，它将不提取任何数据，因此 GET_ACTIVITYS 存储过程将返回一个空响应消息。</span><span class="sxs-lookup"><span data-stu-id="c82be-155">After this happens, the next time **PollingInput** is executed, it will not fetch any data and hence the GET_ACTIVITYS stored procedure will return an empty response message.</span></span>  
  
-   <span data-ttu-id="c82be-156">更多的数据添加到 ACCOUNTACTIVITY 表，直到你将继续获取空的响应消息，因此必须重新填充的新记录所在 ACCOUNTACTIVITY 的表。</span><span class="sxs-lookup"><span data-stu-id="c82be-156">Until more data is added to the ACCOUNTACTIVITY table, you will continue to get empty response messages so you must repopulate the ACCOUNTACTIVITY table with new records.</span></span> <span data-ttu-id="c82be-157">你可以通过运行这些示例使用提供的 more_activity_data.sql 脚本来实现。</span><span class="sxs-lookup"><span data-stu-id="c82be-157">You can do so by running the more_activity_data.sql script provided with the samples.</span></span> <span data-ttu-id="c82be-158">运行此脚本后下, 一个轮询操作将获取新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="c82be-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="c82be-159">在 WCF 服务模型中配置轮询</span><span class="sxs-lookup"><span data-stu-id="c82be-159">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="c82be-160">若要轮询使用存储的过程与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 WCF 服务模型，你必须：</span><span class="sxs-lookup"><span data-stu-id="c82be-160">To poll using stored procedures with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="c82be-161">使用要轮询该存储过程生成的 WCF 服务协定 （接口）。</span><span class="sxs-lookup"><span data-stu-id="c82be-161">Generate a WCF service contract (interface) for the stored procedure using which you are going to poll.</span></span> <span data-ttu-id="c82be-162">对于此示例，必须生成的 WCF 服务协定**GET_ACTIVITYS**入站操作的形式存储过程。</span><span class="sxs-lookup"><span data-stu-id="c82be-162">For this example, you must generate the WCF service contract for the **GET_ACTIVITYS** stored procedure as an inbound operation.</span></span> <span data-ttu-id="c82be-163">若要执行此操作，你无法使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c82be-163">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="c82be-164">实现此接口从 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="c82be-164">Implement a WCF service from this interface.</span></span>  
  
-   <span data-ttu-id="c82be-165">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="c82be-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="c82be-166">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="c82be-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="c82be-167">此主题轮询使用 GET_ACTIVITYS ACCOUNTACTIVITY 数据库表中的示例存储过程。</span><span class="sxs-lookup"><span data-stu-id="c82be-167">The examples in this topic poll the ACCOUNTACTIVITY database table using the GET_ACTIVITYS stored procedure.</span></span> <span data-ttu-id="c82be-168">在示例提供了一个脚本以生成表和存储的过程。</span><span class="sxs-lookup"><span data-stu-id="c82be-168">A script to generate the table and the stored procedure is supplied with the samples.</span></span> <span data-ttu-id="c82be-169">有关这些示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="c82be-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="c82be-170">示例中， **StoredProcPolling_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="c82be-170">A sample, **StoredProcPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="c82be-171">WCF 服务协定和类</span><span class="sxs-lookup"><span data-stu-id="c82be-171">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="c82be-172">你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 WCF 服务协定 （接口） 和支持类**GET_ACTIVITYS**入站操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-172">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **GET_ACTIVITYS** inbound operation.</span></span> <span data-ttu-id="c82be-173">有关生成的 WCF 服务协定的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="c82be-173">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="c82be-174">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="c82be-174">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="c82be-175">下面的代码演示为生成的 WCF 服务协定 （接口） **GET_ACTIVITYS**入站操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-175">The following code shows the WCF service contract (interface) generated for the **GET_ACTIVITYS** inbound operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="PollingPackageApis_APPS_ACCOUNT_PKG")]  
public interface PollingPackageApis_APPS_ACCOUNT_PKG {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS")]  
    void GET_ACTIVITYS(GET_ACTIVITYS request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="c82be-176">消息协定</span><span class="sxs-lookup"><span data-stu-id="c82be-176">The Message Contracts</span></span>  
 <span data-ttu-id="c82be-177">以下是消息协定**GET_ACTIVITYS**入站操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-177">Following is the message contract for the **GET_ACTIVITYS** inbound operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="GET_ACTIVITYS", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
    "G", IsWrapped=true)]  
public partial class GET_ACTIVITYS {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
        "G", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS;  
  
    public GET_ACTIVITYS() {  
    }  
  
    public GET_ACTIVITYS(schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS) {  
        this.OUTRECS = OUTRECS;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="c82be-178">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="c82be-178">WCF Service Class</span></span>  
 <span data-ttu-id="c82be-179">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有为 WCF 服务类实现服务协定 （接口） 从存根 （stub） 文件。</span><span class="sxs-lookup"><span data-stu-id="c82be-179">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="c82be-180">文件的名称是 OracleEBSBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="c82be-180">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="c82be-181">你可以将插入的逻辑来处理**GET_ACTIVITYS**直接插入此类操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-181">You can insert the logic to process the **GET_ACTIVITYS** operation directly into this class.</span></span> <span data-ttu-id="c82be-182">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c82be-182">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleEBSBindingNamespace {  
  
    public class OracleEBSBindingService : PollingPackageApis_APPS_ACCOUNT_PKG {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void GET_ACTIVITYS(GET_ACTIVITYS request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-inbound-messages-for-polling-using-a-stored-procedure"></a><span data-ttu-id="c82be-183">有关使用存储的过程轮询接收入站的消息</span><span class="sxs-lookup"><span data-stu-id="c82be-183">Receiving Inbound Messages For Polling Using a Stored Procedure</span></span>  
 <span data-ttu-id="c82be-184">此部分提供有关如何编写.NET 应用程序以接收使用的入站的轮询消息说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c82be-184">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-using-a-stored-procedure"></a><span data-ttu-id="c82be-185">若要接收使用存储的过程的轮询消息</span><span class="sxs-lookup"><span data-stu-id="c82be-185">To receive polling messages using a stored procedure</span></span>  
  
1.  <span data-ttu-id="c82be-186">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]以生成 WCF 服务协定 （接口） 和用于帮助器类**GET_ACTIVITYS**入站操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-186">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **GET_ACTIVITYS** inbound operation.</span></span> <span data-ttu-id="c82be-187">有关详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="c82be-187">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="c82be-188">生成服务协定和帮助程序类时，可以选择指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-188">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="c82be-189">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="c82be-189">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="c82be-190">实现 WCF 服务从步骤 1 中生成的接口和帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="c82be-190">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="c82be-191">**GET_ACTIVITYS**此类的方法可以处理从接收的数据遇到错误时引发异常中止轮询事务， **GET_ACTIVITYS**操作; 否则为该方法不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="c82be-191">The **GET_ACTIVITYS** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **GET_ACTIVITYS** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="c82be-192">必须属性 WCF 服务类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c82be-192">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="c82be-193">在**GET_ACTIVITYS**方法，你可以直接实现你的应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="c82be-193">Within the **GET_ACTIVITYS** method, you can implement your application logic directly.</span></span> <span data-ttu-id="c82be-194">OracleEBSBindingService.cs 中找不到此类。</span><span class="sxs-lookup"><span data-stu-id="c82be-194">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="c82be-195">此示例中的此代码子类**OracleEBSBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="c82be-195">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="c82be-196">在此代码中，轮询接收该消息，写入控制台。</span><span class="sxs-lookup"><span data-stu-id="c82be-196">In this code, the polling message received and is written to the console.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
            for (int i = 0; i < request.OUTRECS.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.OUTRECS[i].TID,  
                request.OUTRECS[i].ACCOUNT,  
                request.OUTRECS[i].AMOUNT,  
                request.OUTRECS[i].PROCESSED);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="c82be-197">必须实现以下类用于避免将凭据传递作为 URI 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c82be-197">You must implement the following class to avoid passing credentials as part of the URI.</span></span> <span data-ttu-id="c82be-198">在应用程序的后半部分，将实例化此类，以传递凭据。</span><span class="sxs-lookup"><span data-stu-id="c82be-198">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
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
  
4.  <span data-ttu-id="c82be-199">创建**OracleEBSBinding**和通过指定绑定属性中配置的轮询操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-199">Create an **OracleEBSBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="c82be-200">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c82be-200">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="c82be-201">至少，你必须指定**InboundOperationType**， **PolledDataAvailableStatement**， **PollingInput**，和**PollingAction**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-201">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
    binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
    binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c82be-202">请注意，值**PollingInput**绑定属性包含用于调用的请求消息**GET_ACTIVITYS**出站操作的形式存储过程。</span><span class="sxs-lookup"><span data-stu-id="c82be-202">Note that the value for the **PollingInput** binding property contains the request message for invoking the **GET_ACTIVITYS** stored procedure as an outbound operation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c82be-203">在此示例中，因为轮询数据库表，你不需要设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="c82be-203">In this example, because you are polling a database table, you do not need to set the applications context.</span></span> <span data-ttu-id="c82be-204">但是，如果你已轮询接口表，则必须设置应用程序上下文通过指定**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c82be-204">However, if you were polling an interface table, you must set the applications context by specifying the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="c82be-205">有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="c82be-205">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
5.  <span data-ttu-id="c82be-206">指定 Oracle E-business Suite 凭据，方法是实例化**PollingCredentials**在步骤 3 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="c82be-206">Specify Oracle E-Business Suite credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  <span data-ttu-id="c82be-207">创建在步骤 2 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="c82be-207">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  <span data-ttu-id="c82be-208">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。</span><span class="sxs-lookup"><span data-stu-id="c82be-208">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="c82be-209">如果指定，则基连接 URI 不能包含的入站的 ID。</span><span class="sxs-lookup"><span data-stu-id="c82be-209">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="c82be-210">你还必须在此处传递凭据。</span><span class="sxs-lookup"><span data-stu-id="c82be-210">You must also pass the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  <span data-ttu-id="c82be-211">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="c82be-211">Add a service endpoint to the service host.</span></span> <span data-ttu-id="c82be-212">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c82be-212">To do this:</span></span>  
  
    -   <span data-ttu-id="c82be-213">使用在步骤 4 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="c82be-213">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="c82be-214">指定连接 URI，其中包含凭据，如果需要，一个入站的 id。</span><span class="sxs-lookup"><span data-stu-id="c82be-214">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="c82be-215">作为"PollingPackageApis_APPS_ACCOUNT_PKG"轮询 MS_SAMPLE_EMPLOYEE 接口表中指定的协定。</span><span class="sxs-lookup"><span data-stu-id="c82be-215">Specify the contract as "PollingPackageApis_APPS_ACCOUNT_PKG" to poll the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify PollingPackageApis_APPS_ACCOUNT_PKG as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
    ```  
  
9. <span data-ttu-id="c82be-216">若要接收轮询数据，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="c82be-216">To receive polling data, open the service host.</span></span> <span data-ttu-id="c82be-217">每当查询返回一个结果集，该适配器将返回数据。</span><span class="sxs-lookup"><span data-stu-id="c82be-217">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. <span data-ttu-id="c82be-218">若要终止轮询，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="c82be-218">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c82be-219">适配器将继续轮询，直到关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="c82be-219">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="c82be-220">示例</span><span class="sxs-lookup"><span data-stu-id="c82be-220">Example</span></span>  
 <span data-ttu-id="c82be-221">下面的示例演示的轮询应用程序轮询使用 GET_ACTIVITYS ACCOUNTACTIVITY 数据库表的存储过程。</span><span class="sxs-lookup"><span data-stu-id="c82be-221">The following example shows a polling application that polls the ACCOUNTACTIVITY database table using the GET_ACTIVITYS stored procedure.</span></span> <span data-ttu-id="c82be-222">**PollingInput**绑定属性包含要调用从 ACCOUNTACTIVITY 表中读取所有数据 GET_ACTIVITYS 存储过程的请求消息和 post 轮询语句将从 ACCOUNTACTIVITY 移动所有数据到 ACTIVITYHISTORY 表。</span><span class="sxs-lookup"><span data-stu-id="c82be-222">The **PollingInput** binding property contains the request message to invoke the GET_ACTIVITYS stored procedure that reads all the data from the ACCOUNTACTIVITY table and the post poll statement moves all the data from ACCOUNTACTIVITY to ACTIVITYHISTORY table.</span></span>  
  
 <span data-ttu-id="c82be-223">第一条的轮询消息 ACCOUNTACTIVITY 表中提供的所有记录。</span><span class="sxs-lookup"><span data-stu-id="c82be-223">The first polling message gives all the records from the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="c82be-224">后续的轮询消息将不包含任何记录，因为 post 轮询语句删除记录。</span><span class="sxs-lookup"><span data-stu-id="c82be-224">Subsequent polling messages will not contain any records because the post poll statement deletes the records.</span></span> <span data-ttu-id="c82be-225">更多的数据添加到 ACCOUNTACTIVITY 表之前将无法获取任何轮询消息，因此必须重新填充的新记录所在 ACCOUNTACTIVITY 的表。</span><span class="sxs-lookup"><span data-stu-id="c82be-225">Until more data is added to the ACCOUNTACTIVITY table, you will not get any polling messages so you must repopulate the ACCOUNTACTIVITY table with new records.</span></span> <span data-ttu-id="c82be-226">你可以通过运行这些示例使用提供的 more_activity_data.sql 脚本来实现。</span><span class="sxs-lookup"><span data-stu-id="c82be-226">You can do so by running the more_activity_data.sql script provided with the samples.</span></span>  
  
 <span data-ttu-id="c82be-227">运行此脚本后下, 一个轮询操作将获取新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="c82be-227">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="c82be-228">适配器将继续轮询，直到按关闭服务主机`<RETURN>`。</span><span class="sxs-lookup"><span data-stu-id="c82be-228">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.Adapters.OracleEBS;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace StoredProcPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
            for (int i = 0; i < request.OUTRECS.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.OUTRECS[i].TID,  
                request.OUTRECS[i].ACCOUNT,  
                request.OUTRECS[i].AMOUNT,  
                request.OUTRECS[i].PROCESSED);  
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
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
                binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
                binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
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
  
## <a name="see-also"></a><span data-ttu-id="c82be-229">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c82be-229">See Also</span></span>  
 [<span data-ttu-id="c82be-230">使用 WCF 服务模型的轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="c82be-230">Poll Oracle E-Business Suite using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)