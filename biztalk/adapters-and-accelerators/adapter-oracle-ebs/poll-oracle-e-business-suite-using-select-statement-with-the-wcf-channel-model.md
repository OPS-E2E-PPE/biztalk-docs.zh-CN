---
title: SELECT 语句中使用 WCF 通道模型轮询 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495b9010-856f-4782-bd19-1522bc3eb950
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57288b62249e7ba3de7fb9fb8e5667c3247f5829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375010"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model"></a><span data-ttu-id="053be-102">SELECT 语句中使用 WCF 通道模型轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="053be-102">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>
<span data-ttu-id="053be-103">你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要接收使用 SELECT 语句，若要连续轮询接口表定期的数据更改消息，接口视图、 表和 Oracle E-business Suite 中的视图。</span><span class="sxs-lookup"><span data-stu-id="053be-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="053be-104">您可以指定为适配器执行定期轮询 Oracle E-business Suite 的轮询语句的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="053be-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="053be-105">此外可以指定后轮询 PL/SQL 代码块适配器执行轮询语句执行后。</span><span class="sxs-lookup"><span data-stu-id="053be-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  

 <span data-ttu-id="053be-106">若要启用轮询，必须指定某些绑定属性，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="053be-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span> <span data-ttu-id="053be-107">有关如何在适配器支持轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="053be-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="053be-108">使用 Oracle E-business Suite 适配器的绑定属性中配置轮询操作</span><span class="sxs-lookup"><span data-stu-id="053be-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="053be-109">下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定属性，用于将适配器配置为接收数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="053be-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="053be-110">运行轮询应用程序时，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="053be-110">You must specify these binding properties while running the polling application.</span></span>  


|         <span data-ttu-id="053be-111">绑定属性</span><span class="sxs-lookup"><span data-stu-id="053be-111">Binding Property</span></span>         |                                                                                                                                                                                                                            <span data-ttu-id="053be-112">Description</span><span class="sxs-lookup"><span data-stu-id="053be-112">Description</span></span>                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="053be-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="053be-113">**InboundOperationType**</span></span>     |                                                                                                                                                                          <span data-ttu-id="053be-114">指定是否想要执行**轮询**或**通知**的入站操作。</span><span class="sxs-lookup"><span data-stu-id="053be-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="053be-115">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="053be-115">Default is **Polling**.</span></span>                                                                                                                                                                          |
| <span data-ttu-id="053be-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="053be-116">**PolledDataAvailableStatement**</span></span> |                                                                                                             <span data-ttu-id="053be-117">指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="053be-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="053be-118">仅当一条记录不可用，SELECT 语句指定的**PollingInput**将执行属性绑定。</span><span class="sxs-lookup"><span data-stu-id="053be-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>                                                                                                              |
|       <span data-ttu-id="053be-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="053be-119">**PollingInterval**</span></span>        | <span data-ttu-id="053be-120">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="053be-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="053be-121">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="053be-121">The default is 30 seconds.</span></span> <span data-ttu-id="053be-122">轮询间隔确定连续轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="053be-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="053be-123">如果在指定时间间隔内执行该语句，则适配器将休眠的剩余时间间隔中。</span><span class="sxs-lookup"><span data-stu-id="053be-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span> |
|         <span data-ttu-id="053be-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="053be-124">**PollingInput**</span></span>         |                         <span data-ttu-id="053be-125">指定的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="053be-125">Specifies the polling statement.</span></span> <span data-ttu-id="053be-126">若要轮询使用 SELECT 语句，必须指定此绑定属性的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="053be-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="053be-127">默认值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="053be-127">The default is null.</span></span><br /><br /> <span data-ttu-id="053be-128">必须指定的值**PollingInput**绑定属性来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="053be-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="053be-129">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="053be-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>                          |
|        <span data-ttu-id="053be-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="053be-130">**PollingAction**</span></span>         |                                                                                                                <span data-ttu-id="053be-131">指定轮询操作的操作。</span><span class="sxs-lookup"><span data-stu-id="053be-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="053be-132">您可以确定从服务接口生成的操作使用的轮询操作[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="053be-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>                                                                                                                |
|      <span data-ttu-id="053be-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="053be-133">**PostPollStatement**</span></span>       |                                                                                                                                                                  <span data-ttu-id="053be-134">指定在指定的语句之后执行的语句块**PollingInput**执行绑定属性。</span><span class="sxs-lookup"><span data-stu-id="053be-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>                                                                                                                                                                  |
|      <span data-ttu-id="053be-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="053be-135">**PollWhileDataFound**</span></span>      |                                    <span data-ttu-id="053be-136">指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略的轮询间隔，连续执行轮询语句中，如果数据是可用的轮询的表。</span><span class="sxs-lookup"><span data-stu-id="053be-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="053be-137">如果表中有任何数据，不则适配器将恢复执行轮询语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="053be-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="053be-138">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="053be-138">Default is false.</span></span>                                     |

 <span data-ttu-id="053be-139">有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="053be-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="053be-140">有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要轮询 Oracle 数据库，请参阅此主题的其余部分。</span><span class="sxs-lookup"><span data-stu-id="053be-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read the remainder of this topic.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="053be-141">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="053be-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="053be-142">本主题演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持接收数据更改使用 SELECT 语句的消息，请在轮询**MS_SAMPLE_EMPLOYEE**中的接口表**应用程序对象库**应用程序。</span><span class="sxs-lookup"><span data-stu-id="053be-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="053be-143">运行提供的示例在 Oracle E-business Suite 中创建这些对象的 create_apps_artifacts.sql 脚本时创建此表。</span><span class="sxs-lookup"><span data-stu-id="053be-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  

 <span data-ttu-id="053be-144">为了演示轮询操作，我们执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="053be-144">To demonstrate a polling operation, we do the following:</span></span>  

-   <span data-ttu-id="053be-145">指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性，以确定其中接口表正在轮询一次 (MS_SAMPLE_EMPLOYEE) 有任何数据。</span><span class="sxs-lookup"><span data-stu-id="053be-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="053be-146">在此示例中，可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="053be-146">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="053be-147">这可确保只有 MS_SAMPLE_EMPLOYEE 接口表有某些记录时，适配器都将执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="053be-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  

-   <span data-ttu-id="053be-148">指定 SELECT 语句，以**PollingInput**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="053be-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="053be-149">此语句检索 MS_SAMPLE_EMPLOYEE 接口表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="053be-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="053be-150">在此示例中，可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="053be-150">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="053be-151">有关 FOR UPDATE 子句的 SELECT 语句中使用的信息，请参阅[从 Oracle E-business Suite 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="053be-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  

-   <span data-ttu-id="053be-152">指定 DELETE 语句的一部分**PostPollStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="053be-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="053be-153">此语句将 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。</span><span class="sxs-lookup"><span data-stu-id="053be-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="053be-154">在此示例中，可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="053be-154">In this example, you can set this binding property as:</span></span>  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="053be-155">发生这种情况后下, 一次为指定的语句**PollingInput**将执行，它将不提取任何数据。</span><span class="sxs-lookup"><span data-stu-id="053be-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  

-   <span data-ttu-id="053be-156">之前更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，将无法获得任何轮询消息，因此必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新的记录。</span><span class="sxs-lookup"><span data-stu-id="053be-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="053be-157">可以通过运行这些示例提供的 insert_apps_data.sql 脚本执行操作。</span><span class="sxs-lookup"><span data-stu-id="053be-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="053be-158">在运行此脚本后下, 一个轮询操作将提取新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="053be-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  

## <a name="consuming-the-polling-request-message"></a><span data-ttu-id="053be-159">使用轮询请求消息</span><span class="sxs-lookup"><span data-stu-id="053be-159">Consuming the Polling Request Message</span></span>  
 <span data-ttu-id="053be-160">适配器调用代码来轮询 Oracle E-business Suite 轮询操作。</span><span class="sxs-lookup"><span data-stu-id="053be-160">The adapter invokes the polling operation on your code to poll the Oracle E-Business Suite.</span></span> <span data-ttu-id="053be-161">也就是说，适配器通过 IInputChannel 通道形状发送您收到的轮询请求消息。</span><span class="sxs-lookup"><span data-stu-id="053be-161">That is, the adapter sends a polling request message that you receive over an IInputChannel channel shape.</span></span> <span data-ttu-id="053be-162">轮询请求消息中包含由指定的查询的结果集**PollingInput**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="053be-162">The polling request message contains the result set of the query specified by the **PollingInput** binding property.</span></span> <span data-ttu-id="053be-163">可以使用两种方式之一中的轮询消息：</span><span class="sxs-lookup"><span data-stu-id="053be-163">You can consume the polling message in one of two ways:</span></span>  

-   <span data-ttu-id="053be-164">若要使用使用节点值流式处理的消息，必须调用**WriteBodyContents**方法在响应消息，并将其传递**XmlDictionaryWriter**实现节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="053be-164">To consume the message using node-value streaming, you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  

-   <span data-ttu-id="053be-165">若要使用使用节点流式处理的消息，可以调用**GetReaderAtBodyContents**若要获取在响应消息**XmlReader**。</span><span class="sxs-lookup"><span data-stu-id="053be-165">To consume the message using node streaming, you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="053be-166">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="053be-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="053be-167">本主题中的示例轮询 MS_SAMPLE_EMPLOYEE 接口表。</span><span class="sxs-lookup"><span data-stu-id="053be-167">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="053be-168">这些示例提供了一个脚本来生成表。</span><span class="sxs-lookup"><span data-stu-id="053be-168">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="053be-169">有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="053be-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="053be-170">示例中， **SelectPolling_ChannelModel**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="053be-170">A sample, **SelectPolling_ChannelModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a><span data-ttu-id="053be-171">轮询操作使用 WCF 通道模型接收入站的消息</span><span class="sxs-lookup"><span data-stu-id="053be-171">Receiving Inbound Messages for Polling Operation Using the WCF Channel Model</span></span>  
 <span data-ttu-id="053be-172">本部分说明了如何编写.NET 应用程序 （通道模型） 接收使用入站的轮询消息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="053be-172">This section provides instructions on how to write a .NET application (channel model) to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

#### <a name="to-receive-polling-messages-from-the-adapter"></a><span data-ttu-id="053be-173">若要从适配器接收轮询消息</span><span class="sxs-lookup"><span data-stu-id="053be-173">To receive polling messages from the adapter</span></span>  

1. <span data-ttu-id="053be-174">创建一个在 Microsoft Visual C#® 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="053be-174">Create a Microsoft Visual C#® project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="053be-175">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="053be-175">For this topic, create a console application.</span></span>  

2. <span data-ttu-id="053be-176">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。</span><span class="sxs-lookup"><span data-stu-id="053be-176">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  

3. <span data-ttu-id="053be-177">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="053be-177">Open the Program.cs file and add the following namespaces:</span></span>  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

   -   `System.ServiceModel.Description`  

   -   `System.ServiceModel.Channels`  

   -   `System.Xml`  

4. <span data-ttu-id="053be-178">指定连接 URI。</span><span class="sxs-lookup"><span data-stu-id="053be-178">Specify a connection URI.</span></span> <span data-ttu-id="053be-179">有关适配器的连接 URI 的详细信息，请参阅[创建的 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="053be-179">For more information about the adapter connection URI, see [Create the Oracle E-Business Suite connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  

   ```  
   Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
   ```  

5. <span data-ttu-id="053be-180">创建的实例**OracleEBSBinding**并设置配置轮询所需的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="053be-180">Create an instance of **OracleEBSBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="053be-181">至少必须设置**InboundOperationType**， **PolledDataAvailableStatement**， **PollingInput**，以及**PollingAction**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="053be-181">At a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span> <span data-ttu-id="053be-182">有关绑定属性用于配置轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="053be-182">For more information about binding properties used to configure polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

6. <span data-ttu-id="053be-183">由于轮询接口表，还必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="053be-183">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="053be-184">有关应用程序上下文和所需的设置应用程序上下文的绑定属性的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="053be-184">For more information about application context and binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

   ```  
   binding.OracleUserName = "<Enter user name here>";  
   binding.OraclePassword = "<Enter password here>";  
   binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
   ```  

7. <span data-ttu-id="053be-185">创建绑定参数集合并设置凭据。</span><span class="sxs-lookup"><span data-stu-id="053be-185">Create a binding parameter collection and set the credentials.</span></span>  

   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  

   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  

8. <span data-ttu-id="053be-186">创建通道侦听器，并将其打开。</span><span class="sxs-lookup"><span data-stu-id="053be-186">Create a channel listener and open it.</span></span> <span data-ttu-id="053be-187">通过调用创建侦听器**BuildChannelListener < IInputChannel\>** 方法**OracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="053be-187">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **OracleEBSBinding**.</span></span>  

   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  

9. <span data-ttu-id="053be-188">获取**IInputChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。</span><span class="sxs-lookup"><span data-stu-id="053be-188">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  

    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  

10. <span data-ttu-id="053be-189">调用**接收**从适配器获取下一步的入站的消息的通道上。</span><span class="sxs-lookup"><span data-stu-id="053be-189">Invoke **Receive** on the channel to get the next inbound message from the adapter.</span></span>  

    ```  
    Message message = channel.Receive();  
    ```  

11. <span data-ttu-id="053be-190">使用入站操作返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="053be-190">Consume the result set returned by the inbound operation.</span></span> <span data-ttu-id="053be-191">可以使用使用的消息**XmlReader**或**XmlDictionaryWriter**。</span><span class="sxs-lookup"><span data-stu-id="053be-191">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  

    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  

12. <span data-ttu-id="053be-192">已完成处理请求时，请关闭通道。</span><span class="sxs-lookup"><span data-stu-id="053be-192">Close the channel when you have completed processing the request.</span></span>  

    ```  
    channel.Close()  
    ```  

    > [!IMPORTANT]
    >  <span data-ttu-id="053be-193">在完成处理入站的操作后，您必须关闭通道。</span><span class="sxs-lookup"><span data-stu-id="053be-193">You must close the channel after you have finished processing the inbound operation.</span></span> <span data-ttu-id="053be-194">未能关闭通道可能会影响你的代码的行为。</span><span class="sxs-lookup"><span data-stu-id="053be-194">Failure to close the channel may affect the behavior of your code.</span></span>  

13. <span data-ttu-id="053be-195">在完成接收数据更改消息时，请关闭侦听器。</span><span class="sxs-lookup"><span data-stu-id="053be-195">Close the listener when you are finished receiving data-changed messages.</span></span>  

    ```  
    listener.Close()  
    ```  

    > [!IMPORTANT]
    >  <span data-ttu-id="053be-196">关闭侦听器不会关闭创建使用侦听器通道。</span><span class="sxs-lookup"><span data-stu-id="053be-196">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="053be-197">您必须显式关闭使用侦听器创建的每个通道。</span><span class="sxs-lookup"><span data-stu-id="053be-197">You must explicitly close each channel created using the listener.</span></span>  

### <a name="example"></a><span data-ttu-id="053be-198">示例</span><span class="sxs-lookup"><span data-stu-id="053be-198">Example</span></span>  
 <span data-ttu-id="053be-199">下面的示例显示了轮询 MS_SAMPLE_EMPLOYEE 接口表的轮询应用程序。</span><span class="sxs-lookup"><span data-stu-id="053be-199">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="053be-200">**PollingInput**属性包含读取 MS_SAMPLE_EMPLOYEE 表中的所有数据的 select 语句和轮询后语句从同一个表中删除所有数据。</span><span class="sxs-lookup"><span data-stu-id="053be-200">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="053be-201">轮询消息写入到`C:\PollingOutput.xml`。</span><span class="sxs-lookup"><span data-stu-id="053be-201">The polling message is written to `C:\PollingOutput.xml`.</span></span>  

 <span data-ttu-id="053be-202">更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表之前，后续轮询消息将不包含任何记录。</span><span class="sxs-lookup"><span data-stu-id="053be-202">Subsequent polling messages will not contain any records until more data is added to the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="053be-203">可以通过运行这些示例提供的 insert_apps_data.sql 脚本执行操作。</span><span class="sxs-lookup"><span data-stu-id="053be-203">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="053be-204">在运行此脚本后下, 一个轮询操作将提取新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="053be-204">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="053be-205">适配器将继续轮询，直到您关闭服务主机通过按\<返回\>。</span><span class="sxs-lookup"><span data-stu-id="053be-205">The adapter will continue to poll until you close the service host by pressing \<RETURN\>.</span></span>  

```  
using System;  
using Microsoft.Adapters.OracleEBS;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Xml;  

namespace SelectPolling_ChannelModel  
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

                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "<Enter user name here>";  
                binding.OraclePassword = "<Enter password here>";  
                binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  

                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  

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
                Console.ReadLine();  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                    Console.ReadLine();  
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

## <a name="see-also"></a><span data-ttu-id="053be-206">请参阅</span><span class="sxs-lookup"><span data-stu-id="053be-206">See Also</span></span>  
 [<span data-ttu-id="053be-207">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="053be-207">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)