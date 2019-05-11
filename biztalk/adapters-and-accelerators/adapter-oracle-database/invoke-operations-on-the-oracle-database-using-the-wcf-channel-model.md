---
title: 调用上使用 WCF 通道模型，在 Oracle 数据库的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking operations, using the WCF channel model
- WCF channel model, invoking operations
- invoking operations
- operations, invoking
ms.assetid: 6dd95c18-8f78-46d0-8845-b74890614c33
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95220f03bb427d2a849b23e278763d3beb0d3632
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376500"
---
# <a name="invoke-operations-on-the-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="fe62c-102">调用上使用 WCF 通道模型，在 Oracle 数据库的操作</span><span class="sxs-lookup"><span data-stu-id="fe62c-102">Invoke Operations on the Oracle Database Using the WCF Channel Model</span></span>
<span data-ttu-id="fe62c-103">可在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过使用**IRequestChannel**或**IOutputChannel**形状将消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="fe62c-103">You can invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using an **IRequestChannel** or **IOutputChannel** shape to send messages to the adapter.</span></span> <span data-ttu-id="fe62c-104">基本模式是通过使用绑定创建通道工厂为所需的通道形状 (**OracleDBBinding**) 并创建从一个连接 URI 的终结点。</span><span class="sxs-lookup"><span data-stu-id="fe62c-104">The basic pattern is to create a channel factory for the required channel shape by using a binding (**OracleDBBinding**) and an endpoint created from a connection URI.</span></span> <span data-ttu-id="fe62c-105">然后，创建**消息**为目标操作的消息架构表示符合的 SOAP 消息的实例。</span><span class="sxs-lookup"><span data-stu-id="fe62c-105">You then create a **Message** instance that represents a SOAP message that conforms to the message schema for your target operation.</span></span> <span data-ttu-id="fe62c-106">然后可以将发送这**消息**到[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用从通道工厂创建的通道。</span><span class="sxs-lookup"><span data-stu-id="fe62c-106">You can then send this **Message** to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using a channel created from the channel factory.</span></span> <span data-ttu-id="fe62c-107">如果使用的**IRequestChannel**，你收到的响应。</span><span class="sxs-lookup"><span data-stu-id="fe62c-107">If you are using an **IRequestChannel**, you receive a response.</span></span> <span data-ttu-id="fe62c-108">如果执行对 Oracle 数据库的操作问题[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将引发**Microsoft.ServiceModel.Channels.Common.TargetSystemException**。</span><span class="sxs-lookup"><span data-stu-id="fe62c-108">If there is a problem executing the operation on the Oracle database, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws a **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span></span>  
  
 <span data-ttu-id="fe62c-109">有关如何发送操作使用的概述**IRequestChannel**在 WCF 中，查看"客户端通道级编程 》 [ http://go.microsoft.com/fwlink/?LinkId=106081 ](http://go.microsoft.com/fwlink/?LinkId=106081)。</span><span class="sxs-lookup"><span data-stu-id="fe62c-109">For an overview of how to send operations using an **IRequestChannel** in WCF, see "Client Channel-Level Programming" at [http://go.microsoft.com/fwlink/?LinkId=106081](http://go.microsoft.com/fwlink/?LinkId=106081).</span></span>  
  
 <span data-ttu-id="fe62c-110">本主题中的部分提供信息以帮助您在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="fe62c-110">The sections in this topic provide information to help you invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] using the WCF channel model.</span></span>  
  
## <a name="creating-and-consuming-messages-for-outbound-operations"></a><span data-ttu-id="fe62c-111">创建和使用的消息的出站操作</span><span class="sxs-lookup"><span data-stu-id="fe62c-111">Creating and Consuming Messages for Outbound Operations</span></span>  
 <span data-ttu-id="fe62c-112">若要在调用的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，发送请求消息的目标操作使用**IRequestChannel**或**IOutputChannel**。</span><span class="sxs-lookup"><span data-stu-id="fe62c-112">To invoke an operation on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you send the request message for the target operation using either an **IRequestChannel** or an **IOutputChannel**.</span></span> <span data-ttu-id="fe62c-113">如果您使用**IRequestChannel**适配器返回的响应消息中的操作的结果。</span><span class="sxs-lookup"><span data-stu-id="fe62c-113">If you use an **IRequestChannel** the adapter returns the results of the operation in the response message.</span></span>  
  
 <span data-ttu-id="fe62c-114">详细了解请求和响应消息架构和每个操作的消息操作的详细信息，请参阅[消息和消息架构的 Oracle 数据库的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="fe62c-114">For more detailed information about the request and response message schemas and the message actions for each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="fe62c-115">创建请求消息和使用响应消息的方式确定是否在适配器执行节点流式处理或流式处理的节点的值。</span><span class="sxs-lookup"><span data-stu-id="fe62c-115">How you create the request message and consume the response message determines whether node streaming or node-value streaming is performed by the adapter.</span></span> <span data-ttu-id="fe62c-116">这反过来确定是否为受支持的操作执行端到端的 LOB 数据的流式处理。</span><span class="sxs-lookup"><span data-stu-id="fe62c-116">This in turn determines whether end-to-end streaming of LOB data is performed for supported operations.</span></span>  
  
### <a name="creating-the-request-message"></a><span data-ttu-id="fe62c-117">创建请求消息</span><span class="sxs-lookup"><span data-stu-id="fe62c-117">Creating the request message</span></span>  
 <span data-ttu-id="fe62c-118">可以通过两种方式之一创建请求消息：</span><span class="sxs-lookup"><span data-stu-id="fe62c-118">You can create the request message in one of two ways:</span></span>  
  
- <span data-ttu-id="fe62c-119">若要创建一条消息，可用于节点值流式传输，必须将传递的消息正文**XmlBodyWriter**实现节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="fe62c-119">To create a message that can be used for node-value streaming you must pass the message body in an **XmlBodyWriter** that implements node-value streaming.</span></span>  
  
- <span data-ttu-id="fe62c-120">若要创建一条消息，可用于节点流式传输，可传递的消息正文**XmlReader**。</span><span class="sxs-lookup"><span data-stu-id="fe62c-120">To create a message that can be used for node streaming you can pass the message body in an **XmlReader**.</span></span>  
  
  <span data-ttu-id="fe62c-121">通常使用的流式处理以支持端到端流式处理的请求消息中的 Oracle LOB 数据的节点的值。</span><span class="sxs-lookup"><span data-stu-id="fe62c-121">You typically use node-value streaming to support end-to-end streaming of Oracle LOB data in the request message.</span></span> <span data-ttu-id="fe62c-122">支持此功能的唯一操作是 UpdateLOB。</span><span class="sxs-lookup"><span data-stu-id="fe62c-122">The only operation that supports this feature is UpdateLOB.</span></span>  
  
### <a name="consuming-the-response-message"></a><span data-ttu-id="fe62c-123">使用响应消息</span><span class="sxs-lookup"><span data-stu-id="fe62c-123">Consuming the response message</span></span>  
 <span data-ttu-id="fe62c-124">可使用响应消息的两种方式之一：</span><span class="sxs-lookup"><span data-stu-id="fe62c-124">You can consume the response message in one of two ways:</span></span>  
  
- <span data-ttu-id="fe62c-125">若要使用此消息使用节点值流式传输，必须调用**WriteBodyContents**方法在响应消息，并将其传递**XmlDictionaryWriter**实现节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="fe62c-125">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
- <span data-ttu-id="fe62c-126">若要使用可调用使用节点流式处理的消息**GetReaderAtBodyContents**若要获取在响应消息**XmlReader**。</span><span class="sxs-lookup"><span data-stu-id="fe62c-126">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
  <span data-ttu-id="fe62c-127">通常使用节点值的流式处理以支持端到端流式处理的 Oracle LOB 的响应消息中的数据。</span><span class="sxs-lookup"><span data-stu-id="fe62c-127">You typically use node-value streaming to support end-to-end streaming of Oracle LOB data in the response message.</span></span> <span data-ttu-id="fe62c-128">有一些支持此功能的许多操作。</span><span class="sxs-lookup"><span data-stu-id="fe62c-128">There are many operations that support this feature.</span></span>  
  
### <a name="lob-data-and-message-streaming-support"></a><span data-ttu-id="fe62c-129">LOB 数据和消息流式处理支持</span><span class="sxs-lookup"><span data-stu-id="fe62c-129">LOB Data and Message Streaming Support</span></span>  
 <span data-ttu-id="fe62c-130">详细了解如何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持流式处理 LOB 数据，请参阅[流式处理大型对象数据类型在 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fe62c-130">For more information about how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports streaming on LOB data, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="fe62c-131">有关实现节点值在您的代码以支持端到端流式处理的 LOB 数据的流式处理的详细信息，请参阅[流式处理 Oracle 数据库 LOB 数据类型使用的 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="fe62c-131">For more information about implementing node-value streaming in your code to support end-to-end streaming of LOB data, see [Streaming Oracle Database LOB Data Types Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="transaction-support-on-outbound-operations-in-the-wcf-channel-model"></a><span data-ttu-id="fe62c-132">对 WCF 通道模型中的出站操作的事务支持。</span><span class="sxs-lookup"><span data-stu-id="fe62c-132">Transaction Support on Outbound Operations in the WCF Channel Model.</span></span>  
 <span data-ttu-id="fe62c-133">适配器将执行对 Oracle 数据库专用事务内调用每个操作。</span><span class="sxs-lookup"><span data-stu-id="fe62c-133">The adapter executes each operation you invoke inside a dedicated transaction on the Oracle database.</span></span> <span data-ttu-id="fe62c-134">可以通过设置控制这些事务的隔离级别**TransactionIsolationLevel**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="fe62c-134">You can control the isolation level of these transactions by setting the **TransactionIsolationLevel** binding property.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="fe62c-135">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="fe62c-135">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="fe62c-136">本主题中的示例使用了 SCOTT。ACCOUNTACTIVITY 表。</span><span class="sxs-lookup"><span data-stu-id="fe62c-136">The example in this topic uses the SCOTT.ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="fe62c-137">使用 SDK 示例提供了一个脚本来生成这些项目。</span><span class="sxs-lookup"><span data-stu-id="fe62c-137">A script to generate these artifacts is supplied with the SDK samples.</span></span> <span data-ttu-id="fe62c-138">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="fe62c-138">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a><span data-ttu-id="fe62c-139">如何通过使用对通道调用的操作？</span><span class="sxs-lookup"><span data-stu-id="fe62c-139">How Do I Invoke an Operation by Using a Channel?</span></span>  
 <span data-ttu-id="fe62c-140">若要通过使用调用的操作**IRequestChannel**，执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="fe62c-140">To invoke an operation by using an **IRequestChannel**, perform the following steps.</span></span>  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a><span data-ttu-id="fe62c-141">如何通过使用 IRequestChannel 的实例调用的操作</span><span class="sxs-lookup"><span data-stu-id="fe62c-141">How to invoke an operation by using an instance of IRequestChannel</span></span>  
  
1. <span data-ttu-id="fe62c-142">生成通道工厂 (**ChannelFactory\<IRequestChannel\>**)。</span><span class="sxs-lookup"><span data-stu-id="fe62c-142">Build a channel factory (**ChannelFactory\<IRequestChannel\>**).</span></span> <span data-ttu-id="fe62c-143">若要执行此操作，必须指定一个绑定 (**OracleDBBinding**) 和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="fe62c-143">To do this, you must specify a binding (**OracleDBBinding**) and an endpoint address.</span></span> <span data-ttu-id="fe62c-144">您可以在代码中以强制方式或在配置中以声明方式指定绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="fe62c-144">You can specify the binding and endpoint address either imperatively in your code or declaratively in configuration.</span></span> <span data-ttu-id="fe62c-145">有关如何在配置中指定的绑定和终结点地址的详细信息，请参阅[创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="fe62c-145">For more information about how to specify the binding and endpoint address in configuration, see [Create a channel using Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).</span></span>  
  
   ```  
   // Create a binding  
   OracleDBBinding binding = new OracleDBBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. <span data-ttu-id="fe62c-146">通过设置用户名称密码凭据的通道工厂**ClientCredentials**属性。</span><span class="sxs-lookup"><span data-stu-id="fe62c-146">Set the user name password credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
   ```  
   factory.Credentials.UserName.UserName = "SCOTT";  
   factory.Credentials.UserName.Password = "TIGER";  
   ```  
  
3. <span data-ttu-id="fe62c-147">打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="fe62c-147">Open the channel factory.</span></span>  
  
   ```  
   factory.Open();  
   ```  
  
4. <span data-ttu-id="fe62c-148">从工厂获取通道并将其打开。</span><span class="sxs-lookup"><span data-stu-id="fe62c-148">Get a channel from the factory and open it.</span></span>  
  
   ```  
   IRequestChannel channel = factory.CreateChannel();  
   channel.Open();  
   ```  
  
5. <span data-ttu-id="fe62c-149">创建**消息**目标操作的实例。</span><span class="sxs-lookup"><span data-stu-id="fe62c-149">Create a **Message** instance for the target operation.</span></span> <span data-ttu-id="fe62c-150">请确保指定目标操作的消息操作。</span><span class="sxs-lookup"><span data-stu-id="fe62c-150">Be sure that the message action for the target operation is specified.</span></span> <span data-ttu-id="fe62c-151">在此示例中，消息正文传递通过创建**XmlReader**放在某个文件。</span><span class="sxs-lookup"><span data-stu-id="fe62c-151">In this example, the message body is passed by creating an **XmlReader** over a file.</span></span> <span data-ttu-id="fe62c-152">目标操作是 SCOTT/EMP 表上的选择操作。</span><span class="sxs-lookup"><span data-stu-id="fe62c-152">The target operation is a Select operation on the SCOTT/EMP table.</span></span>  
  
   ```  
   XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
   Message messageIn = Message.CreateMessage(MessageVersion.Default,  
       "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
       readerIn);  
   ```  
  
6. <span data-ttu-id="fe62c-153">调用**请求**方法将消息发送到在通道上的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]并接收回复。</span><span class="sxs-lookup"><span data-stu-id="fe62c-153">Invoke the **Request** method on the channel to send the message to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] and receive the reply.</span></span> <span data-ttu-id="fe62c-154">如果 Oracle 数据库时遇到异常，适配器将引发**TargetSystemException**。</span><span class="sxs-lookup"><span data-stu-id="fe62c-154">If the Oracle database encounters an exception, the adapter throws a **TargetSystemException**.</span></span> <span data-ttu-id="fe62c-155">（其他异常是可能的非 Oracle 异常。）可以获取从 Oracle 错误的说明**InnerException.Message**的属性**TargetSystemException**。</span><span class="sxs-lookup"><span data-stu-id="fe62c-155">(Other exceptions are possible for non Oracle exceptions.) You can get a description of the Oracle error from the **InnerException.Message** property of the **TargetSystemException**.</span></span>  
  
   ```  
   try  
   {  
       Message messageOut = channel.Request(messageIn);  
   }  
   catch (Exception ex)  
   {  
       // handle exception  
   }  
   ```  
  
7. <span data-ttu-id="fe62c-156">处理响应。</span><span class="sxs-lookup"><span data-stu-id="fe62c-156">Process the response.</span></span> <span data-ttu-id="fe62c-157">在此示例中， **GetReaderAtBodyContents**调用以获取消息正文的响应消息。</span><span class="sxs-lookup"><span data-stu-id="fe62c-157">In this example, **GetReaderAtBodyContents** is called on the response message to get the message body.</span></span>  
  
   ```  
   XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
   ```  
  
8. <span data-ttu-id="fe62c-158">完成处理响应消息时，关闭读取器和消息。</span><span class="sxs-lookup"><span data-stu-id="fe62c-158">When you are done processing the response message, close the reader and the message.</span></span>  
  
   ```  
   readerOut.Close();  
   messageOut.Close();  
   ```  
  
9. <span data-ttu-id="fe62c-159">完成后使用通道和通道工厂，将其关闭。</span><span class="sxs-lookup"><span data-stu-id="fe62c-159">When you are done using the channel and the channel factory, close them.</span></span> <span data-ttu-id="fe62c-160">关闭工厂将关闭所有使用它创建的通道。</span><span class="sxs-lookup"><span data-stu-id="fe62c-160">Closing the factory will close all channels that were created with it.</span></span>  
  
    ```  
    channel.Close()  
    factory.Close();  
  
    ```  
  
   <span data-ttu-id="fe62c-161">请按照相同的步骤来发送邮件时使用**IOutputChannel**形状除外：</span><span class="sxs-lookup"><span data-stu-id="fe62c-161">You follow the same steps to send a message using the **IOutputChannel** shape except:</span></span>  
  
-   <span data-ttu-id="fe62c-162">您创建**ChannelFactory\<IOutputChannel\>** 步骤 1 中。</span><span class="sxs-lookup"><span data-stu-id="fe62c-162">You create a **ChannelFactory\<IOutputChannel\>** in step 1.</span></span>  
  
-   <span data-ttu-id="fe62c-163">在调用**发送**步骤 6 中的通道上的方法。</span><span class="sxs-lookup"><span data-stu-id="fe62c-163">You call the **Send** method on the channel in step 6.</span></span> <span data-ttu-id="fe62c-164">`channel.Send(messageIn);` 的用户。</span><span class="sxs-lookup"><span data-stu-id="fe62c-164">`channel.Send(messageIn);`.</span></span>  
  
-   <span data-ttu-id="fe62c-165">不没有返回任何响应消息**IOutputChannel**。</span><span class="sxs-lookup"><span data-stu-id="fe62c-165">There is no response message returned for an **IOutputChannel**.</span></span>  
  
### <a name="example"></a><span data-ttu-id="fe62c-166">示例</span><span class="sxs-lookup"><span data-stu-id="fe62c-166">Example</span></span>  
 <span data-ttu-id="fe62c-167">下面的示例演示如何使用调用 Select 操作**IRequestChannel**通道。</span><span class="sxs-lookup"><span data-stu-id="fe62c-167">The following example shows how to invoke a Select operation by using an **IRequestChannel** channel.</span></span> <span data-ttu-id="fe62c-168">选择响应消息将通过使用消费**XmlReader**和返回的记录数写入到控制台。</span><span class="sxs-lookup"><span data-stu-id="fe62c-168">The Select response message is consumed by using an **XmlReader** and the number of records returned is written to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
using System.Xml;  
using System.IO;  
using System.Runtime.Serialization;  
  
namespace RequestChanneSample  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The Select operation request message  
            const string selectRequestString =  
                "\<Select xmlns=\"http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY\"\>" +  
                    "<COLUMN_NAMES>*</COLUMN_NAMES>" +  
                    "<FILTER>ACCOUNT = 100002</FILTER>" +  
                "</Select>";  
            try  
            {  
                // Create binding -- specify binding properties before you open the factory.  
                OracleDBBinding odbBinding = new OracleDBBinding();  
  
                // Create address.  
                EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
                // Create channel factory from binding and address.  
                ChannelFactory<IRequestChannel> factory =   
                    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
                // Specify credentials   
                factory.Credentials.UserName.UserName = "SCOTT";  
                factory.Credentials.UserName.Password = "TIGER";  
  
                // Open the factory.  
                factory.Open();  
  
                // Get a channel.  
                IRequestChannel channel = factory.CreateChannel();  
  
                // Open the channel.  
                channel.Open();  
  
                // Create the request message from the string  
                StringReader strReader = new StringReader(selectRequestString);  
                XmlReader readerIn = XmlReader.Create(strReader);  
  
                Message requestMessage = Message.CreateMessage(MessageVersion.Default,  
                    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
                    readerIn);  
  
                Send the message and get a respone  
                Message responseMessage = channel.Request(requestMessage);  
  
                // Get an XmlReader from the message  
                XmlReader readerOut = (XmlReader) responseMessage.GetReaderAtBodyContents();  
  
                // Count the number of records returned and write to the console.  
                readerOut.MoveToContent();  
                int numberOfRecordsReturned = 0;  
                while (readerOut.Read())  
                {  
                    if (readerOut.NodeType == XmlNodeType.Element && readerOut.Name == "ACCOUNTACTIVITYRECORDSELECT")  
                        numberOfRecordsReturned++;  
                }  
  
                Console.WriteLine("{0} records returned.", numberOfRecordsReturned);  
  
                // Close the output reader and message  
                readerOut.Close();  
                responseMessage.Close();  
  
                //Close channel  
                channel.Close();  
  
                //Close the factory  
                factory.Close();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe62c-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe62c-169">See Also</span></span>  
 [<span data-ttu-id="fe62c-170">开发 Oracle 数据库应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="fe62c-170">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)