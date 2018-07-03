---
title: SELECT 语句中使用 WCF 服务模型轮询 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 521d58e4-73b1-48a8-9a0a-9e733386c1b5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8484acc15d2328ab444a8df6e55dc0ff952899a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000694"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model"></a><span data-ttu-id="dbdd3-102">SELECT 语句中使用 WCF 服务模型轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="dbdd3-102">Poll Oracle E-Business Suite using SELECT statement with the WCF service model</span></span>
<span data-ttu-id="dbdd3-103">你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要接收使用 SELECT 语句，若要连续轮询接口表定期的数据更改消息，接口视图、 表和 Oracle E-business Suite 中的视图。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="dbdd3-104">您可以指定为适配器执行定期轮询 Oracle E-business Suite 的轮询语句的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="dbdd3-105">此外可以指定后轮询 PL/SQL 代码块适配器执行轮询语句执行后。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  

 <span data-ttu-id="dbdd3-106">若要启用轮询，必须指定某些绑定属性，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span>  <span data-ttu-id="dbdd3-107">有关如何在适配器支持轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="dbdd3-108">使用 Oracle E-business Suite 适配器的绑定属性中配置轮询操作</span><span class="sxs-lookup"><span data-stu-id="dbdd3-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="dbdd3-109">下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定属性，用于将适配器配置为接收数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="dbdd3-110">运行轮询应用程序时，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-110">You must specify these binding properties while running the polling application.</span></span>  


|         <span data-ttu-id="dbdd3-111">绑定属性</span><span class="sxs-lookup"><span data-stu-id="dbdd3-111">Binding Property</span></span>         |                                                                                                                                                                                                                            <span data-ttu-id="dbdd3-112">Description</span><span class="sxs-lookup"><span data-stu-id="dbdd3-112">Description</span></span>                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="dbdd3-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="dbdd3-113">**InboundOperationType**</span></span>     |                                                                                                                                                                          <span data-ttu-id="dbdd3-114">指定是否想要执行**轮询**或**通知**的入站操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="dbdd3-115">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-115">Default is **Polling**.</span></span>                                                                                                                                                                          |
| <span data-ttu-id="dbdd3-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="dbdd3-116">**PolledDataAvailableStatement**</span></span> |                                                                                                             <span data-ttu-id="dbdd3-117">指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="dbdd3-118">仅当一条记录不可用，SELECT 语句指定的**PollingInput**将执行属性绑定。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>                                                                                                              |
|       <span data-ttu-id="dbdd3-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="dbdd3-119">**PollingInterval**</span></span>        | <span data-ttu-id="dbdd3-120">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="dbdd3-121">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-121">The default is 30 seconds.</span></span> <span data-ttu-id="dbdd3-122">轮询间隔确定连续轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="dbdd3-123">如果在指定时间间隔内执行该语句，则适配器将休眠的剩余时间间隔中。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span> |
|         <span data-ttu-id="dbdd3-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="dbdd3-124">**PollingInput**</span></span>         |                         <span data-ttu-id="dbdd3-125">指定的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-125">Specifies the polling statement.</span></span> <span data-ttu-id="dbdd3-126">若要轮询使用 SELECT 语句，必须指定此绑定属性的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="dbdd3-127">默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-127">The default is null.</span></span><br /><br /> <span data-ttu-id="dbdd3-128">必须指定的值**PollingInput**绑定属性来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="dbdd3-129">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>                          |
|        <span data-ttu-id="dbdd3-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="dbdd3-130">**PollingAction**</span></span>         |                                                                                                                <span data-ttu-id="dbdd3-131">指定轮询操作的操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="dbdd3-132">您可以确定从服务接口生成的操作使用的轮询操作[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>                                                                                                                |
|      <span data-ttu-id="dbdd3-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="dbdd3-133">**PostPollStatement**</span></span>       |                                                                                                                                                                  <span data-ttu-id="dbdd3-134">指定在指定的语句之后执行的语句块**PollingInput**执行绑定属性。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>                                                                                                                                                                  |
|      <span data-ttu-id="dbdd3-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="dbdd3-135">**PollWhileDataFound**</span></span>      |                                    <span data-ttu-id="dbdd3-136">指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略的轮询间隔，连续执行轮询语句中，如果数据是可用的轮询的表。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="dbdd3-137">如果表中有任何数据，不则适配器将恢复执行轮询语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="dbdd3-138">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-138">Default is false.</span></span>                                     |

 <span data-ttu-id="dbdd3-139">有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="dbdd3-140">有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要轮询 Oracle 数据库，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read further.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="dbdd3-141">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="dbdd3-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="dbdd3-142">本主题演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持接收数据更改使用 SELECT 语句的消息，请在轮询**MS_SAMPLE_EMPLOYEE**中的接口表**应用程序对象库**应用程序。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="dbdd3-143">运行提供的示例在 Oracle E-business Suite 中创建这些对象的 create_apps_artifacts.sql 脚本时创建此表。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  

 <span data-ttu-id="dbdd3-144">为了演示轮询操作，我们执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dbdd3-144">To demonstrate a polling operation, we do the following:</span></span>  

-   <span data-ttu-id="dbdd3-145">指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性，以确定其中接口表正在轮询一次 (MS_SAMPLE_EMPLOYEE) 有任何数据。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="dbdd3-146">在此示例中，可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="dbdd3-146">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="dbdd3-147">这可确保只有 MS_SAMPLE_EMPLOYEE 接口表有某些记录时，适配器都将执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  

-   <span data-ttu-id="dbdd3-148">指定 SELECT 语句，以**PollingInput**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="dbdd3-149">此语句检索 MS_SAMPLE_EMPLOYEE 接口表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="dbdd3-150">在此示例中，可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="dbdd3-150">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="dbdd3-151">有关 FOR UPDATE 子句的 SELECT 语句中使用的信息，请参阅[从 Oracle E-business Suite 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  

-   <span data-ttu-id="dbdd3-152">指定 DELETE 语句的一部分**PostPollStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="dbdd3-153">此语句将 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="dbdd3-154">在此示例中，可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="dbdd3-154">In this example, you can set this binding property as:</span></span>  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="dbdd3-155">发生这种情况后下, 一次为指定的语句**PollingInput**将执行，它将不提取任何数据。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  

-   <span data-ttu-id="dbdd3-156">之前更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，将无法获得任何轮询消息，因此必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新的记录。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="dbdd3-157">可以通过运行这些示例提供的 insert_apps_data.sql 脚本执行操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="dbdd3-158">在运行此脚本后下, 一个轮询操作将提取新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  

## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="dbdd3-159">在 WCF 服务模型中配置轮询</span><span class="sxs-lookup"><span data-stu-id="dbdd3-159">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="dbdd3-160">若要轮询接口表使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 WCF 服务模型，您必须：</span><span class="sxs-lookup"><span data-stu-id="dbdd3-160">To poll an interface table using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF service model, you must:</span></span>  

- <span data-ttu-id="dbdd3-161">为生成的 WCF 服务协定 （接口）**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-161">Generate a WCF service contract (interface) for the **Poll** operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="dbdd3-162">若要执行此操作，可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-162">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

- <span data-ttu-id="dbdd3-163">实现此接口中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-163">Implement a WCF service from this interface.</span></span>  

- <span data-ttu-id="dbdd3-164">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-164">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="dbdd3-165">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="dbdd3-165">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="dbdd3-166">本主题中的示例轮询 MS_SAMPLE_EMPLOYEE 接口表。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-166">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="dbdd3-167">这些示例提供了一个脚本来生成表。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-167">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="dbdd3-168">有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-168">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="dbdd3-169">示例中， **SelectPolling_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-169">A sample, **SelectPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="dbdd3-170">WCF 服务约定和类</span><span class="sxs-lookup"><span data-stu-id="dbdd3-170">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="dbdd3-171">可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 服务协定 （接口） 和支持类**轮询**操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-171">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="dbdd3-172">有关生成的 WCF 服务协定的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-172">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="dbdd3-173">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="dbdd3-173">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="dbdd3-174">下面的代码演示 WCF 服务协定 （接口） 为生成**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-174">The following code shows the WCF service contract (interface) generated for the **Poll** operation on MS_SAMPLE_EMPLOYEE interface table.</span></span>  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE")]  
public interface InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE")]  
    void Poll(Poll request);  
}  
```  

### <a name="the-message-contracts"></a><span data-ttu-id="dbdd3-175">消息协定</span><span class="sxs-lookup"><span data-stu-id="dbdd3-175">The Message Contracts</span></span>  
 <span data-ttu-id="dbdd3-176">下面是用于消息协定**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-176">Following is the message contract for the **Poll** operation on MS_SAMPLE_EMPLOYEE interface table.</span></span>  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Poll", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
    "_EMPLOYEE", IsWrapped=true)]  
public partial class Poll {  

    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
        "_EMPLOYEE", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA;  

    public Poll() {  
    }  

    public Poll(schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA) {  
        this.DATA = DATA;  
    }  
}  
```  

### <a name="wcf-service-class"></a><span data-ttu-id="dbdd3-177">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="dbdd3-177">WCF Service Class</span></span>  
 <span data-ttu-id="dbdd3-178">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有实现服务协定 （接口） 中的 WCF 服务类的存根文件。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-178">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="dbdd3-179">文件的名称是 OracleEBSBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-179">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="dbdd3-180">您可以将逻辑来处理**轮询**直接在此类操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-180">You can insert the logic to process the **Poll** operation directly into this class.</span></span> <span data-ttu-id="dbdd3-181">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-181">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

```  
namespace OracleEBSBindingNamespace {  

    public class OracleEBSBindingService : InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Poll(Poll request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receiving-inbound-messages-for-the-poll-operation-using-a-select-statement"></a><span data-ttu-id="dbdd3-182">使用 SELECT 语句轮询操作接收入站的消息</span><span class="sxs-lookup"><span data-stu-id="dbdd3-182">Receiving Inbound Messages for the Poll Operation Using a SELECT Statement</span></span>  
 <span data-ttu-id="dbdd3-183">本部分说明了如何编写.NET 应用程序以接收使用入站的轮询消息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-183">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

#### <a name="to-receive-polling-messages-using-a-select-statement"></a><span data-ttu-id="dbdd3-184">若要接收轮询消息使用的 SELECT 语句</span><span class="sxs-lookup"><span data-stu-id="dbdd3-184">To receive polling messages using a SELECT statement</span></span>  

1. <span data-ttu-id="dbdd3-185">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 服务协定 （接口） 和帮助器类实现**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-185">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Poll** operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="dbdd3-186">有关详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-186">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="dbdd3-187">在生成服务协定和帮助程序类时，可以选择指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-187">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="dbdd3-188">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-188">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="dbdd3-189">实现在步骤 1 中生成的接口和帮助程序类中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-189">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="dbdd3-190">**轮询**此类方法可以处理从接收的数据中遇到错误时引发异常中止轮询事务**轮询**操作; 否则该方法不执行返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-190">The **Poll** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Poll** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="dbdd3-191">必须按如下所示属性的 WCF 服务类：</span><span class="sxs-lookup"><span data-stu-id="dbdd3-191">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="dbdd3-192">内**轮询**方法，可以直接实现应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-192">Within the **Poll** method, you can implement your application logic directly.</span></span> <span data-ttu-id="dbdd3-193">可以 OracleEBSBindingService.cs 中找到此类。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-193">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="dbdd3-194">此代码在此示例中的嵌套类**OracleEBSBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-194">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="dbdd3-195">此代码中，在轮询消息收到并写入到控制台。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-195">In this code, the polling message received and is written to the console.</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
   {  
       public override void Poll(Poll request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
           for (int i = 0; i < request.DATA.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.DATA[i].EMP_NO,  
               request.DATA[i].NAME,  
               request.DATA[i].DESIGNATION,  
               request.DATA[i].SALARY);  
           }  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. <span data-ttu-id="dbdd3-196">必须实现以下的类，以避免将凭据作为 URI 的一部分传递。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-196">You must implement the following class to avoid passing credentials as part of the URI.</span></span> <span data-ttu-id="dbdd3-197">在应用程序的后半部分，将实例化此类，以传递凭据。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-197">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  

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

4. <span data-ttu-id="dbdd3-198">创建**OracleEBSBinding**和配置轮询操作时，指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-198">Create an **OracleEBSBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="dbdd3-199">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-199">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="dbdd3-200">至少，您必须指定**InboundOperationType**， **PolledDataAvailableStatement**， **PollingInput**，和**PollingAction**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-200">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span>  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

5. <span data-ttu-id="dbdd3-201">由于轮询接口表，还必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-201">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="dbdd3-202">有关应用程序上下文和所需的设置应用程序上下文的绑定属性的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-202">For more information about application context and the binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  

6. <span data-ttu-id="dbdd3-203">指定 Oracle E-business Suite 凭据通过实例化**PollingCredentials**步骤 3 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-203">Specify Oracle E-Business Suite credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

7. <span data-ttu-id="dbdd3-204">创建在步骤 2 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-204">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

8. <span data-ttu-id="dbdd3-205">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和基本连接 URI。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-205">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="dbdd3-206">如果指定的基本连接 URI 不能包含的入站的 ID。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-206">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="dbdd3-207">你还必须在此处传递凭据。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-207">You must also pass the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

9. <span data-ttu-id="dbdd3-208">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-208">Add a service endpoint to the service host.</span></span> <span data-ttu-id="dbdd3-209">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dbdd3-209">To do this:</span></span>  

   - <span data-ttu-id="dbdd3-210">使用在步骤 4 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-210">Use the binding created in step 4.</span></span>  

   - <span data-ttu-id="dbdd3-211">指定连接 URI，其中包含的凭据，如果需要，入站 id。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-211">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   - <span data-ttu-id="dbdd3-212">作为"InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE"轮询 MS_SAMPLE_EMPLOYEE 接口表中指定的协定。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-212">Specify the contract as "InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE" to poll the MS_SAMPLE_EMPLOYEE interface table.</span></span>  

     ```  
     // Add service endpoint: be sure to specify InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE as the contract  
     Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
     serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
     ```  

10. <span data-ttu-id="dbdd3-213">若要接收轮询数据，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-213">To receive polling data, open the service host.</span></span> <span data-ttu-id="dbdd3-214">只要查询返回结果集，则适配器将返回数据。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-214">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

11. <span data-ttu-id="dbdd3-215">若要终止轮询，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-215">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="dbdd3-216">该适配器将继续轮询，直到关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-216">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="dbdd3-217">示例</span><span class="sxs-lookup"><span data-stu-id="dbdd3-217">Example</span></span>  
 <span data-ttu-id="dbdd3-218">下面的示例显示了轮询 MS_SAMPLE_EMPLOYEE 接口表的轮询应用程序。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-218">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="dbdd3-219">**PollingInput**属性包含读取 MS_SAMPLE_EMPLOYEE 表中的所有数据的 select 语句和轮询后语句从同一个表中删除所有数据。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-219">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="dbdd3-220">第一个的轮询消息会从 MS_SAMPLE_EMPLOYEE 接口表提供的所有记录。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-220">The first polling message gives all the records from the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="dbdd3-221">由于轮询后语句中删除记录，后续轮询消息将不包含任何记录。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-221">Subsequent polling messages will not contain any records because the post poll statement deletes the records.</span></span> <span data-ttu-id="dbdd3-222">之前更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，您将无法获得任何轮询消息。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-222">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages.</span></span> <span data-ttu-id="dbdd3-223">因此，您必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新的记录。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-223">So, you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="dbdd3-224">可以通过运行这些示例提供的 insert_apps_data.sql 脚本执行操作。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-224">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="dbdd3-225">在运行此脚本后下, 一个轮询操作将提取新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-225">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="dbdd3-226">适配器将继续轮询，直到按关闭服务主机`<RETURN>`。</span><span class="sxs-lookup"><span data-stu-id="dbdd3-226">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

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

namespace SelectPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Poll(Poll request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
            for (int i = 0; i < request.DATA.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.DATA[i].EMP_NO,  
                request.DATA[i].NAME,  
                request.DATA[i].DESIGNATION,  
                request.DATA[i].SALARY);  
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
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "myOracleEBSUserName";  
                binding.OraclePassword = "myOracleEBSPassword";  
                binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  

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
                serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
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

## <a name="see-also"></a><span data-ttu-id="dbdd3-227">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbdd3-227">See Also</span></span>  
 [<span data-ttu-id="dbdd3-228">使用 WCF 服务模型轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="dbdd3-228">Poll Oracle E-Business Suite using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)