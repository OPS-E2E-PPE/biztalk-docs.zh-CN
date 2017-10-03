---
title: "使用 WCF 通道模型使用 SELECT 语句的轮询 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 495b9010-856f-4782-bd19-1522bc3eb950
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f689b035f926e0fd5bbdaa159e1450fbad92b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model"></a><span data-ttu-id="04606-102">轮询 Oracle E-business Suite SELECT 语句中使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="04606-102">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>
<span data-ttu-id="04606-103">你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要通过使用 SELECT 语句持续轮询接口表接收定期的数据更改消息，接口视图、 表和 Oracle E-business Suite 中的视图。</span><span class="sxs-lookup"><span data-stu-id="04606-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="04606-104">你可以指定为适配器执行定期轮询 Oracle E-business Suite 的轮询语句的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="04606-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="04606-105">你还可以指定后轮询 PL/SQL 代码块适配器执行执行轮询语句后。</span><span class="sxs-lookup"><span data-stu-id="04606-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  
  
 <span data-ttu-id="04606-106">若要启用轮询，必须指定某些绑定属性，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="04606-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span> <span data-ttu-id="04606-107">有关如何适配器支持轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="04606-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="04606-108">使用 Oracle E-business Suite 适配器绑定属性中配置的轮询操作</span><span class="sxs-lookup"><span data-stu-id="04606-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="04606-109">下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]更改消息的绑定属性，用于配置适配器，以接收数据。</span><span class="sxs-lookup"><span data-stu-id="04606-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="04606-110">在运行轮询应用程序时，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="04606-110">You must specify these binding properties while running the polling application.</span></span>  
  
|<span data-ttu-id="04606-111">绑定属性</span><span class="sxs-lookup"><span data-stu-id="04606-111">Binding Property</span></span>|<span data-ttu-id="04606-112">Description</span><span class="sxs-lookup"><span data-stu-id="04606-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="04606-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="04606-113">**InboundOperationType**</span></span>|<span data-ttu-id="04606-114">指定是否想要执行**轮询**或**通知**入站操作。</span><span class="sxs-lookup"><span data-stu-id="04606-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="04606-115">默认值是**轮询**。</span><span class="sxs-lookup"><span data-stu-id="04606-115">Default is **Polling**.</span></span>|  
|<span data-ttu-id="04606-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="04606-116">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="04606-117">指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="04606-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="04606-118">仅当一条记录时，SELECT 语句你为指定**PollingInput**将执行绑定属性。</span><span class="sxs-lookup"><span data-stu-id="04606-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>|  
|<span data-ttu-id="04606-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="04606-119">**PollingInterval**</span></span>|<span data-ttu-id="04606-120">指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="04606-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="04606-121">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="04606-121">The default is 30 seconds.</span></span> <span data-ttu-id="04606-122">轮询间隔确定连续两次轮询之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="04606-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="04606-123">如果在指定间隔内执行该语句，该适配器休眠的剩余时间的时间间隔内。</span><span class="sxs-lookup"><span data-stu-id="04606-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="04606-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="04606-124">**PollingInput**</span></span>|<span data-ttu-id="04606-125">指定的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="04606-125">Specifies the polling statement.</span></span> <span data-ttu-id="04606-126">若要轮询使用 SELECT 语句，必须指定此绑定属性的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="04606-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="04606-127">默认值为 null。</span><span class="sxs-lookup"><span data-stu-id="04606-127">The default is null.</span></span><br /><br /> <span data-ttu-id="04606-128">必须指定的值**PollingInput**绑定属性来启用轮询。</span><span class="sxs-lookup"><span data-stu-id="04606-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="04606-129">仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="04606-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>|  
|<span data-ttu-id="04606-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="04606-130">**PollingAction**</span></span>|<span data-ttu-id="04606-131">指定轮询操作的操作。</span><span class="sxs-lookup"><span data-stu-id="04606-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="04606-132">你可以确定此轮询操作的生成操作使用的服务接口[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04606-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>|  
|<span data-ttu-id="04606-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="04606-133">**PostPollStatement**</span></span>|<span data-ttu-id="04606-134">指定在指定的语句之后执行的语句块**PollingInput**绑定属性执行。</span><span class="sxs-lookup"><span data-stu-id="04606-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>|  
|<span data-ttu-id="04606-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="04606-135">**PollWhileDataFound**</span></span>|<span data-ttu-id="04606-136">指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略轮询间隔和连续执行轮询语句中，如果数据中轮询的表。</span><span class="sxs-lookup"><span data-stu-id="04606-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="04606-137">如果表中可用的任何数据不，该适配器将恢复执行轮询语句按照指定的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="04606-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="04606-138">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="04606-138">Default is false.</span></span>|  
  
 <span data-ttu-id="04606-139">有关这些属性的更完整说明，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="04606-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="04606-140">有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要轮询的 Oracle 数据库，请阅读此主题的其余部分。</span><span class="sxs-lookup"><span data-stu-id="04606-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read the remainder of this topic.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="04606-141">本主题演示轮询的方式</span><span class="sxs-lookup"><span data-stu-id="04606-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="04606-142">在此主题中，以演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收数据的支持更改使用 SELECT 语句的消息，轮询**MS_SAMPLE_EMPLOYEE**接口中的表**应用程序对象库**应用程序。</span><span class="sxs-lookup"><span data-stu-id="04606-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="04606-143">运行示例后，在 Oracle E-business Suite 中创建这些对象提供的 create_apps_artifacts.sql 脚本时创建此表。</span><span class="sxs-lookup"><span data-stu-id="04606-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="04606-144">为了演示轮询操作，我们执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="04606-144">To demonstrate a polling operation, we do the following:</span></span>  
  
-   <span data-ttu-id="04606-145">指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性以确定其中接口表轮询 (MS_SAMPLE_EMPLOYEE) 有任何数据。</span><span class="sxs-lookup"><span data-stu-id="04606-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="04606-146">在此示例中，你可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="04606-146">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     <span data-ttu-id="04606-147">这可确保仅当 MS_SAMPLE_EMPLOYEE 接口表具有某些记录时，适配器都将执行轮询语句。</span><span class="sxs-lookup"><span data-stu-id="04606-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  
  
-   <span data-ttu-id="04606-148">指定 SELECT 语句，以**PollingInput**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="04606-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="04606-149">此语句将检索 MS_SAMPLE_EMPLOYEE 接口表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="04606-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="04606-150">在此示例中，你可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="04606-150">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="04606-151">有关 FOR UPDATE 子句的 SELECT 语句中使用的信息，请参阅[从 Oracle E-business Suite 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="04606-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  
  
-   <span data-ttu-id="04606-152">指定作为的一部分的 DELETE 语句**PostPollStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="04606-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="04606-153">此语句将从 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。</span><span class="sxs-lookup"><span data-stu-id="04606-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="04606-154">在此示例中，你可以设置为此绑定属性：</span><span class="sxs-lookup"><span data-stu-id="04606-154">In this example, you can set this binding property as:</span></span>  
  
    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     <span data-ttu-id="04606-155">发生这种情况后下, 一次为指定的语句**PollingInput**将执行，它将不提取任何数据。</span><span class="sxs-lookup"><span data-stu-id="04606-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  
  
-   <span data-ttu-id="04606-156">直到更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，因此必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新记录将不会获取任何轮询消息。</span><span class="sxs-lookup"><span data-stu-id="04606-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="04606-157">你可以通过运行这些示例使用提供的 insert_apps_data.sql 脚本来实现。</span><span class="sxs-lookup"><span data-stu-id="04606-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="04606-158">运行此脚本后下, 一个轮询操作将获取新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="04606-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  
  
## <a name="consuming-the-polling-request-message"></a><span data-ttu-id="04606-159">使用轮询请求消息</span><span class="sxs-lookup"><span data-stu-id="04606-159">Consuming the Polling Request Message</span></span>  
 <span data-ttu-id="04606-160">适配器调用于你的代码来轮询 Oracle E-business Suite 轮询操作。</span><span class="sxs-lookup"><span data-stu-id="04606-160">The adapter invokes the polling operation on your code to poll the Oracle E-Business Suite.</span></span> <span data-ttu-id="04606-161">也就是说，该适配器通过 IInputChannel 通道形状发送轮询请求消息，你将收到。</span><span class="sxs-lookup"><span data-stu-id="04606-161">That is, the adapter sends a polling request message that you receive over an IInputChannel channel shape.</span></span> <span data-ttu-id="04606-162">轮询请求消息包含由指定的查询的结果集**PollingInput**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="04606-162">The polling request message contains the result set of the query specified by the **PollingInput** binding property.</span></span> <span data-ttu-id="04606-163">你可以使用两种方式之一中的轮询消息：</span><span class="sxs-lookup"><span data-stu-id="04606-163">You can consume the polling message in one of two ways:</span></span>  
  
-   <span data-ttu-id="04606-164">若要使用使用节点值流式处理的消息，必须调用**WriteBodyContents**方法则会在响应消息并将其传递**XmlDictionaryWriter**实现节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="04606-164">To consume the message using node-value streaming, you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="04606-165">若要使用使用节点流式处理的消息，你可以调用**GetReaderAtBodyContents**若要获取的响应消息**XmlReader**。</span><span class="sxs-lookup"><span data-stu-id="04606-165">To consume the message using node streaming, you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="04606-166">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="04606-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="04606-167">本主题中的示例轮询 MS_SAMPLE_EMPLOYEE 接口表。</span><span class="sxs-lookup"><span data-stu-id="04606-167">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="04606-168">在示例提供了一个脚本以生成表。</span><span class="sxs-lookup"><span data-stu-id="04606-168">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="04606-169">有关这些示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="04606-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="04606-170">示例中， **SelectPolling_ChannelModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="04606-170">A sample, **SelectPolling_ChannelModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a><span data-ttu-id="04606-171">使用 WCF 通道模型的轮询操作接收入站的消息</span><span class="sxs-lookup"><span data-stu-id="04606-171">Receiving Inbound Messages for Polling Operation Using the WCF Channel Model</span></span>  
 <span data-ttu-id="04606-172">此部分提供有关如何编写一个.NET 应用程序 （通道模型） 来接收使用的入站的轮询消息说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04606-172">This section provides instructions on how to write a .NET application (channel model) to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-adapter"></a><span data-ttu-id="04606-173">从适配器接收轮询消息</span><span class="sxs-lookup"><span data-stu-id="04606-173">To receive polling messages from the adapter</span></span>  
  
1.  <span data-ttu-id="04606-174">创建一个在 Microsoft Visual C#® 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04606-174">Create a Microsoft Visual C#® project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="04606-175">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="04606-175">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="04606-176">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。</span><span class="sxs-lookup"><span data-stu-id="04606-176">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="04606-177">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="04606-177">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="04606-178">指定连接 URI。</span><span class="sxs-lookup"><span data-stu-id="04606-178">Specify a connection URI.</span></span> <span data-ttu-id="04606-179">有关 URI 的适配器连接的详细信息，请参阅[创建 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="04606-179">For more information about the adapter connection URI, see [Create the Oracle E-Business Suite connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  
  
    ```  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    ```  
  
5.  <span data-ttu-id="04606-180">创建的实例**OracleEBSBinding**并设置配置轮询所需的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="04606-180">Create an instance of **OracleEBSBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="04606-181">至少必须设置**InboundOperationType**， **PolledDataAvailableStatement**， **PollingInput**，和**PollingAction**绑定的属性。</span><span class="sxs-lookup"><span data-stu-id="04606-181">At a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span> <span data-ttu-id="04606-182">有关绑定属性用于配置轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。</span><span class="sxs-lookup"><span data-stu-id="04606-182">For more information about binding properties used to configure polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
    binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
    binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
    binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
    ```  
  
6.  <span data-ttu-id="04606-183">因为轮询接口表，你还必须设置应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="04606-183">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="04606-184">有关应用程序上下文和所需的设置应用程序上下文的绑定属性的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="04606-184">For more information about application context and binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "<Enter user name here>";  
    binding.OraclePassword = "<Enter password here>";  
    binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
    ```  
  
7.  <span data-ttu-id="04606-185">创建一个绑定参数集合，并设置凭据。</span><span class="sxs-lookup"><span data-stu-id="04606-185">Create a binding parameter collection and set the credentials.</span></span>  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
8.  <span data-ttu-id="04606-186">创建一个通道侦听器，并将其打开。</span><span class="sxs-lookup"><span data-stu-id="04606-186">Create a channel listener and open it.</span></span> <span data-ttu-id="04606-187">通过调用创建侦听器**BuildChannelListener < IInputChannel\>** 方法**OracleEBSBinding**。</span><span class="sxs-lookup"><span data-stu-id="04606-187">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **OracleEBSBinding**.</span></span>  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
9. <span data-ttu-id="04606-188">获取**IInputChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。</span><span class="sxs-lookup"><span data-stu-id="04606-188">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
10. <span data-ttu-id="04606-189">调用**接收**从适配器获取下一步的入站的消息在通道上。</span><span class="sxs-lookup"><span data-stu-id="04606-189">Invoke **Receive** on the channel to get the next inbound message from the adapter.</span></span>  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
11. <span data-ttu-id="04606-190">使用入站操作返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="04606-190">Consume the result set returned by the inbound operation.</span></span> <span data-ttu-id="04606-191">你可以使用使用消息**XmlReader**或**XmlDictionaryWriter**。</span><span class="sxs-lookup"><span data-stu-id="04606-191">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
12. <span data-ttu-id="04606-192">已完成处理请求时，请关闭通道。</span><span class="sxs-lookup"><span data-stu-id="04606-192">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="04606-193">在完成处理入站的操作后，您必须关闭通道。</span><span class="sxs-lookup"><span data-stu-id="04606-193">You must close the channel after you have finished processing the inbound operation.</span></span> <span data-ttu-id="04606-194">未能关闭通道可能会影响你代码的行为。</span><span class="sxs-lookup"><span data-stu-id="04606-194">Failure to close the channel may affect the behavior of your code.</span></span>  
  
13. <span data-ttu-id="04606-195">在完成接收数据更改消息时，请关闭该侦听器。</span><span class="sxs-lookup"><span data-stu-id="04606-195">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="04606-196">关闭侦听器不会关闭使用侦听器创建的通道。</span><span class="sxs-lookup"><span data-stu-id="04606-196">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="04606-197">您必须显式关闭使用侦听器创建每个通道。</span><span class="sxs-lookup"><span data-stu-id="04606-197">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="04606-198">示例</span><span class="sxs-lookup"><span data-stu-id="04606-198">Example</span></span>  
 <span data-ttu-id="04606-199">下面的示例演示的轮询应用程序轮询 MS_SAMPLE_EMPLOYEE 接口表。</span><span class="sxs-lookup"><span data-stu-id="04606-199">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="04606-200">**PollingInput**属性包含从 MS_SAMPLE_EMPLOYEE 表中读取所有数据的 select 语句和 post 轮询语句从同一个表中删除所有数据。</span><span class="sxs-lookup"><span data-stu-id="04606-200">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="04606-201">轮询消息写入到`C:\PollingOutput.xml`。</span><span class="sxs-lookup"><span data-stu-id="04606-201">The polling message is written to `C:\PollingOutput.xml`.</span></span>  
  
 <span data-ttu-id="04606-202">更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表之前，后续的轮询消息将不包含任何记录。</span><span class="sxs-lookup"><span data-stu-id="04606-202">Subsequent polling messages will not contain any records until more data is added to the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="04606-203">你可以通过运行这些示例使用提供的 insert_apps_data.sql 脚本来实现。</span><span class="sxs-lookup"><span data-stu-id="04606-203">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="04606-204">运行此脚本后下, 一个轮询操作将获取新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="04606-204">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="04606-205">适配器将继续轮询，直到按关闭服务主机\<返回 >。</span><span class="sxs-lookup"><span data-stu-id="04606-205">The adapter will continue to poll until you close the service host by pressing \<RETURN>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04606-206">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04606-206">See Also</span></span>  
 [<span data-ttu-id="04606-207">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="04606-207">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)