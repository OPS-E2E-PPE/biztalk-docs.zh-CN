---
title: "使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, receiving polling-based messages
- how to, receive polling-based messages by using the WCF channel model
ms.assetid: 13f501e4-cff7-497c-a9da-fdd6382c779f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e1596c0b0676db916068ff9a33a8be9d6a9fa3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="6817a-102">使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="6817a-102">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="6817a-103">你可以配置[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]轮询的 Oracle 数据库表或视图的任何数据更改。</span><span class="sxs-lookup"><span data-stu-id="6817a-103">You can configure the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to poll an Oracle database table or view for any data changes.</span></span> <span data-ttu-id="6817a-104">若要执行此类轮询操作，该适配器定期执行对 Oracle 表或视图后, 跟一个可选的 PL/SQL 代码块的 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="6817a-104">To perform such a polling operation, the adapter periodically executes a SQL query against an Oracle table or view followed by an optional PL/SQL code block.</span></span> <span data-ttu-id="6817a-105">然后返回 SQL 查询的结果[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到你的代码作为强类型的结果集在入站 POLLINGSTMT 操作中。</span><span class="sxs-lookup"><span data-stu-id="6817a-105">The results of the SQL query are then returned by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to your code as a strongly-typed result set in an inbound POLLINGSTMT operation.</span></span> <span data-ttu-id="6817a-106">有关用于配置和对 Oracle 执行轮询机制的详细信息数据库使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6817a-106">For more information about the mechanism used to configure and perform polling on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="6817a-107">强烈建议你阅读然后再继续本主题。</span><span class="sxs-lookup"><span data-stu-id="6817a-107">It is strongly recommended that you read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="6817a-108">你配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到轮询和 Oracle 数据库表或视图中的实例上设置绑定属性**OracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="6817a-108">You configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll and Oracle database table or view by setting binding properties on an instance of **OracleDBBinding**.</span></span> <span data-ttu-id="6817a-109">在 WCF 通道模型中，您然后使用此绑定来生成通道侦听器，从中可以获取**IInputChannel**通道从适配器接收 POLLINGSTMT 操作。</span><span class="sxs-lookup"><span data-stu-id="6817a-109">In the WCF channel model, you then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive the POLLINGSTMT operation from the adapter.</span></span>  
  
 <span data-ttu-id="6817a-110">有关如何接收操作使用的概述**IInputChannel**在 WCF 中，请参阅[服务通道级编程](https://msdn.microsoft.com/library/ms789029.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6817a-110">For an overview of how to receive operations using an **IInputChannel** in WCF, see [Service Channel-Level Programming](https://msdn.microsoft.com/library/ms789029.aspx).</span></span> 
  
 <span data-ttu-id="6817a-111">此主题中的部分提供信息来帮助你对 Oracle 数据库表执行轮询和视图使用的是 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="6817a-111">The sections in this topic provide information to help you perform polling on Oracle database tables and views using the WCF channel model.</span></span>  
  
## <a name="consuming-the-pollingstmt-request-message"></a><span data-ttu-id="6817a-112">使用 POLLINGSTMT 请求消息</span><span class="sxs-lookup"><span data-stu-id="6817a-112">Consuming the POLLINGSTMT request message</span></span>  
 <span data-ttu-id="6817a-113">适配器调用 POLLINGSTMT 操作于你的代码来轮询 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="6817a-113">The adapter invokes the POLLINGSTMT operation on your code to poll the Oracle database.</span></span> <span data-ttu-id="6817a-114">适配器将通过接收 POLLINGSTMT 请求消息发送的即**IInputChannel**通道形状。</span><span class="sxs-lookup"><span data-stu-id="6817a-114">That is, the adapter sends a POLLINGSTMT request message that you receive over an **IInputChannel** channel shape.</span></span> <span data-ttu-id="6817a-115">POLLINGSTMT 请求消息包含由指定的查询的结果集**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6817a-115">The POLLINGSTMT request message contains the result set of the query specified by the **PollingStatement** binding property.</span></span> <span data-ttu-id="6817a-116">你可以使用两种方式之一中的 POLLINGSTMT 消息：</span><span class="sxs-lookup"><span data-stu-id="6817a-116">You can consume the POLLINGSTMT message in one of two ways:</span></span>  
  
-   <span data-ttu-id="6817a-117">若要使用使用流式处理你的节点的值的消息必须调用**WriteBodyContents**方法则会在响应消息并将其传递**XmlDictionaryWriter**实现节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="6817a-117">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="6817a-118">若要使用的消息使用节点流可以调用**GetReaderAtBodyContents**若要获取的响应消息**XmlReader**。</span><span class="sxs-lookup"><span data-stu-id="6817a-118">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
 <span data-ttu-id="6817a-119">你通常使用流式处理以使用包含 Oracle LOB 数据列的结果集的节点的值。</span><span class="sxs-lookup"><span data-stu-id="6817a-119">You typically use node-value streaming to consume result sets that contain Oracle LOB data columns.</span></span>  
  
 <span data-ttu-id="6817a-120">有关 POLLINGSTMT 操作的消息结构的详细信息，请参阅[轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)。</span><span class="sxs-lookup"><span data-stu-id="6817a-120">For more information about the message structure of the POLLINGSTMT operation, see [Message Schemas for the Polling Operations](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md).</span></span>  
  
 <span data-ttu-id="6817a-121">有关详细信息，如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持流式处理 LOB 数据，请参阅[流式处理 Oracle 数据库适配器中的大型对象数据类型](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6817a-121">For more information about how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports streaming on LOB data, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="6817a-122">有关实现节点值在你的代码以支持端到端流式处理的 LOB 数据的流式处理的详细信息，请参阅[流式处理 Oracle 数据库 LOB 数据类型使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="6817a-122">For more information about implementing node-value streaming in your code to support end-to-end streaming of LOB data, see [Streaming Oracle Database LOB Data Types Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="6817a-123">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="6817a-123">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="6817a-124">本主题中的示例使用 SCOTT。ACCOUNTACTIVITY 表和 SCOTT。ACCOUNT_PKG。PROCESS_ACTIVITY 函数。</span><span class="sxs-lookup"><span data-stu-id="6817a-124">The example in this topic uses the SCOTT.ACCOUNTACTIVITY table and the SCOTT.ACCOUNT_PKG.PROCESS_ACTIVITY function.</span></span> <span data-ttu-id="6817a-125">在示例提供了一个脚本以生成这些项目。</span><span class="sxs-lookup"><span data-stu-id="6817a-125">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="6817a-126">该示例执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6817a-126">The example performs the following operations:</span></span>  
  
-   <span data-ttu-id="6817a-127">作为轮询语句的一部分，从该 ACCOUNTACTIVITY 表并在控制台上的显示选择的所有记录。</span><span class="sxs-lookup"><span data-stu-id="6817a-127">As part of the polling statement, selects all the records from the ACCOUNTACTIVITY table and displays on the console.</span></span>  
  
-   <span data-ttu-id="6817a-128">作为 post 轮询语句的一部分，该示例调用移动到 ACTIVITYHISTORY 表中从 ACCOUNTACTIVITY 表的所有记录的 PROCESS_ACTIVITY 函数。</span><span class="sxs-lookup"><span data-stu-id="6817a-128">As part of the post poll statement, the example invokes the PROCESS_ACTIVITY function that moves all the records from ACCOUNTACTIVITY table to ACTIVITYHISTORY table.</span></span>  
  
-   <span data-ttu-id="6817a-129">后续轮询 ACCOUNTACTIVITY 表上的不会返回任何记录。</span><span class="sxs-lookup"><span data-stu-id="6817a-129">Subsequent polls on the ACCOUNTACTIVITY table do not return any records.</span></span> <span data-ttu-id="6817a-130">但是，如果你想要作为轮询操作的一部分返回更多记录的示例，你必须在 ACCOUNTACTIVITY 表中插入一些记录。</span><span class="sxs-lookup"><span data-stu-id="6817a-130">However, if you want the example to return more records as part of the polling operation, you must insert some records in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="6817a-131">你可以通过运行这些示例使用提供的 more_activity_data.sql 脚本来实现。</span><span class="sxs-lookup"><span data-stu-id="6817a-131">You can do so by running the more_activity_data.sql script provided with the samples.</span></span>  
  
 <span data-ttu-id="6817a-132">有关这些示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="6817a-132">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="how-do-i-poll-an-oracle-database-using-an-iinputchannel"></a><span data-ttu-id="6817a-133">如何轮询使用 IInputChannel Oracle 数据库？</span><span class="sxs-lookup"><span data-stu-id="6817a-133">How Do I Poll an Oracle Database Using an IInputChannel?</span></span>  
 <span data-ttu-id="6817a-134">若要轮询的 Oracle 数据库表或视图，以接收数据更改消息使用 WCF 通道模型，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="6817a-134">To poll an Oracle database table or view to receive data-change messages using the WCF channel model, perform the following steps.</span></span>  
  
#### <a name="to-receive-data-changed-messages-using-an-iinputchannel"></a><span data-ttu-id="6817a-135">接收数据更改消息使用 IInputChannel</span><span class="sxs-lookup"><span data-stu-id="6817a-135">To receive data-changed messages using an IInputChannel</span></span>  
  
1.  <span data-ttu-id="6817a-136">创建 Visual C# 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6817a-136">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="6817a-137">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="6817a-137">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="6817a-138">在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleDB`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。</span><span class="sxs-lookup"><span data-stu-id="6817a-138">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleDB`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="6817a-139">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="6817a-139">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleDB`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
    -   `System.Runtime.Serialization`  
  
    -   `System.IO`  
  
    -   `Microsoft.ServiceModel.Channels.Common`  
  
4.  <span data-ttu-id="6817a-140">创建的实例**OracleDBBinding**并设置配置轮询所需的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6817a-140">Create an instance of **OracleDBBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="6817a-141">至少必须设置**InboundOperationType**， **PollingStatement**，和**PollingInterval**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6817a-141">At a minimum you must set the **InboundOperationType**, **PollingStatement**, and **PollingInterval** binding properties.</span></span> <span data-ttu-id="6817a-142">对于此示例中，你还设置**PostPollStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="6817a-142">For this example, you also set the **PostPollStatement** binding property.</span></span> <span data-ttu-id="6817a-143">有关绑定属性用于配置轮询的详细信息，请参阅[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6817a-143">For more information about binding properties used to configure polling, see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span>  
  
    ```  
    OracleDBBinding binding = new OracleDBBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PollingInterval = 30;  
    binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;"  
    ```  
  
5.  <span data-ttu-id="6817a-144">创建一个绑定参数集合，并设置凭据。</span><span class="sxs-lookup"><span data-stu-id="6817a-144">Create a binding parameter collection and set the credentials.</span></span>  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "SCOTT";  
    credentials.UserName.Password = "TIGER";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
6.  <span data-ttu-id="6817a-145">创建一个通道侦听器，并将其打开。</span><span class="sxs-lookup"><span data-stu-id="6817a-145">Create a channel listener and open it.</span></span> <span data-ttu-id="6817a-146">通过调用创建侦听器**BuildChannelListener < IInputChannel\>** 方法**OracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="6817a-146">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **OracleDBBinding**.</span></span> <span data-ttu-id="6817a-147">你可以通过在连接 URI 设置 PollingId 属性修改 POLLINGSTMT 操作的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="6817a-147">You can modify the target namespace for the POLLINGSTMT operation by setting the PollingId property in the connection URI.</span></span> <span data-ttu-id="6817a-148">有关 URI 的适配器连接的详细信息，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="6817a-148">For more information about the adapter connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
7.  <span data-ttu-id="6817a-149">获取**IInputChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。</span><span class="sxs-lookup"><span data-stu-id="6817a-149">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
8.  <span data-ttu-id="6817a-150">调用**接收**从适配器获取下一步的 POLLINGSTMT 消息在通道上。</span><span class="sxs-lookup"><span data-stu-id="6817a-150">Invoke **Receive** on the channel to get the next POLLINGSTMT message from the adapter.</span></span>  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
9. <span data-ttu-id="6817a-151">使用 POLLINGSTMT 操作返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="6817a-151">Consume the result set returned by the POLLINGSTMT operation.</span></span> <span data-ttu-id="6817a-152">你可以使用使用消息**XmlReader**或**XmlDictionaryWriter**。</span><span class="sxs-lookup"><span data-stu-id="6817a-152">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
10. <span data-ttu-id="6817a-153">已完成处理请求时，请关闭通道。</span><span class="sxs-lookup"><span data-stu-id="6817a-153">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6817a-154">处理 POLLINGSTMT 操作之后，您必须关闭通道。</span><span class="sxs-lookup"><span data-stu-id="6817a-154">You must close the channel after you have finished processing the POLLINGSTMT operation.</span></span> <span data-ttu-id="6817a-155">未能关闭通道可能会影响你代码的行为。</span><span class="sxs-lookup"><span data-stu-id="6817a-155">Failure to close the channel may affect the behavior of your code.</span></span>  
  
11. <span data-ttu-id="6817a-156">在完成接收数据更改消息时，请关闭该侦听器。</span><span class="sxs-lookup"><span data-stu-id="6817a-156">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6817a-157">关闭侦听器不会关闭使用侦听器创建的通道。</span><span class="sxs-lookup"><span data-stu-id="6817a-157">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="6817a-158">您必须显式关闭使用侦听器创建每个通道。</span><span class="sxs-lookup"><span data-stu-id="6817a-158">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="6817a-159">示例</span><span class="sxs-lookup"><span data-stu-id="6817a-159">Example</span></span>  
 <span data-ttu-id="6817a-160">下面的示例演示如何配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]轮询 Oracle 数据库表和视图和接收 POLLLINGSTMT 操作使用的是 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="6817a-160">The following example shows how to configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll Oracle database tables and views and receive the POLLLINGSTMT operation using the WCF channel model.</span></span> <span data-ttu-id="6817a-161">POLLINGSTMT 操作中返回的结果集通过向控制台写入**XmlReader**。</span><span class="sxs-lookup"><span data-stu-id="6817a-161">The result set returned in the POLLINGSTMT operation is written to the console by using an **XmlReader**.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Add this namespace for channel model  
using System.ServiceModel.Channels;  
  
using System.Xml;  
using System.Runtime.Serialization;  
using System.IO;  
  
// Include this namespace for the WCF LOB Adapter SDK and Oracle exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
namespace OraclePollingCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Uri connectionUri = new Uri("oracleDB://ADAPTER/");  
  
            IChannelListener<IInputChannel> listener = null;  
            IInputChannel channel = null;  
  
            // set timeout to receive POLLINGSTMT message  
            TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
            Console.WriteLine("Sample Started");  
  
            try  
            {  
                // Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the           
                // PollingStatement,and the PostPollStatement.  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingInterval = 30;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Create a binding parameter collection and set the credentials  
                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "SCOTT";  
                credentials.UserName.Password = "TIGER";  
  
                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  
  
                Console.WriteLine("Opening listener");  
                // get a listener  from the binding  
                listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
                listener.Open();  
  
                Console.WriteLine("Opening channel");  
                // get a channel from the listener  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel opened -- waiting for polled data");  
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
  
                    // Write the TID, ACCOUNT, AMOUNT, and TRANSDATE for each record to the Console  
                    Console.WriteLine("\nPolling data received for request number {0}", i+1);  
                    Console.WriteLine("Tx ID\tACCOUNT\tAMOUNT\tTx DATE");  
  
                    while (reader.Read())  
                    {  
                        if (reader.IsStartElement())  
                        {  
                            switch (reader.Name)  
                            {  
                                case "POLLINGSTMTRECORD":  
                                    Console.Write("\n");  
                                    break;  
  
                                case "TID":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "ACCOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
                                case "AMOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "TRANSDATE":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                default:  
                                    break;  
                            }  
                        }  
                    }  
  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    //            To save the polling data to a file you can REPLACE the code above with the following  
                    //  
                    //            XmlDocument doc = new XmlDocument();  
                    //            doc.Load(reader);  
                    //            using (XmlWriter writer = XmlWriter.Create("PollingOutput.xml"))  
                    //            {  
                    //                doc.WriteTo(writer);  
                    //            }  
                    message.Close();  
                }  
  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
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
  
## <a name="see-also"></a><span data-ttu-id="6817a-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6817a-162">See Also</span></span>  
 [<span data-ttu-id="6817a-163">开发 Oracle 数据库应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="6817a-163">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)