---
title: 与 SQL 适配器的 WCF 通道模型概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5e5f77c-c922-4039-92c7-38d2b7638459
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad124e7ce9fdf8c3dac6a1ac0ffda122127becb9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966019"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sql-adapter"></a><span data-ttu-id="b3996-102">与 SQL 适配器的 WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="b3996-102">Overview of the WCF channel model with the SQL adapter</span></span>
<span data-ttu-id="b3996-103">若要在调用操作[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，你的代码充当 WCF 客户端，并将出站操作发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="b3996-103">To invoke operations on the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], your code acts as a WCF client and sends outbound operations to the adapter.</span></span> <span data-ttu-id="b3996-104">在 WCF 通道模型中，你的代码时，将调用在适配器上的操作通过在通道上发送请求消息。</span><span class="sxs-lookup"><span data-stu-id="b3996-104">In the WCF channel model, your code invokes operations on the adapter by sending a request message over a channel.</span></span>  
  
 <span data-ttu-id="b3996-105">若要接收轮询基于的数据更改消息使用适配器，你的代码将充当 WCF 服务和接收入站**轮询**， **TypedPolling**，或**通知**适配器中的操作。</span><span class="sxs-lookup"><span data-stu-id="b3996-105">To receive polling-based data-changed messages using the adapter, your code acts as a WCF service and receives the inbound **Polling**, **TypedPolling**, or **Notification** operation from the adapter.</span></span> <span data-ttu-id="b3996-106">换而言之，你的代码这些操作的请求消息从适配器接收通过通道。</span><span class="sxs-lookup"><span data-stu-id="b3996-106">In other words, your code receives a request message for these operations from the adapter over a channel.</span></span>  
  
 <span data-ttu-id="b3996-107">本部分中的主题提供使用的概述[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="b3996-107">The topics in this section provide an overview of using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with the WCF channel model.</span></span>  
  
## <a name="wcf-channel-model-overview"></a><span data-ttu-id="b3996-108">WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="b3996-108">WCF Channel Model Overview</span></span>  
 <span data-ttu-id="b3996-109">通过交换 SOAP 消息，客户端和服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="b3996-109">Clients and services communicate by exchanging SOAP messages.</span></span> <span data-ttu-id="b3996-110">WCF 通道模型是此消息交换的低级别抽象。</span><span class="sxs-lookup"><span data-stu-id="b3996-110">The WCF channel model is a low-level abstraction of this message exchange.</span></span> <span data-ttu-id="b3996-111">它提供接口和使您能够发送和接收消息，通过使用调用的通道堆栈的分层的协议堆栈的类型。</span><span class="sxs-lookup"><span data-stu-id="b3996-111">It provides interfaces and types that enable you to send and receive messages by using a layered protocol stack called a channel stack.</span></span> <span data-ttu-id="b3996-112">堆栈的每个层组成一个通道，并且每个通道创建从 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="b3996-112">Each layer of the stack is composed of a channel, and each channel is created from a WCF binding.</span></span> <span data-ttu-id="b3996-113">在最低层是传输通道。</span><span class="sxs-lookup"><span data-stu-id="b3996-113">At the lowest layer is the transport channel.</span></span> <span data-ttu-id="b3996-114">传输通道可实现服务和客户端之间的底层传输机制并显示到较高层 （和最终使用方应用程序） 的每条消息，并且**System.ServiceModel.Message**。</span><span class="sxs-lookup"><span data-stu-id="b3996-114">The transport channel implements the underlying transport mechanism between a service and a client and presents each message to the higher layers (and ultimately the consuming application) as a **System.ServiceModel.Message**.</span></span> <span data-ttu-id="b3996-115">WCF**消息**类是 SOAP 消息的抽象。</span><span class="sxs-lookup"><span data-stu-id="b3996-115">The WCF **Message** class is an abstraction of a SOAP message.</span></span> <span data-ttu-id="b3996-116">WCF 提供了多个通道接口，调用的基本 SOAP 消息交换模式进行建模，如请求-答复或单向通道形状。</span><span class="sxs-lookup"><span data-stu-id="b3996-116">WCF provides several channel interfaces, called channel shapes, that model the basic SOAP message exchange patterns, such as request-reply or one-way.</span></span> <span data-ttu-id="b3996-117">WCF 传输绑定提供的实现的一个或多个更高版本上层的通道形状可以用于发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="b3996-117">A WCF transport binding provides an implementation of one or more channel shapes that higher layers can use to send and receive messages.</span></span> <span data-ttu-id="b3996-118">有关 WCF 通道模型的详细信息，请参阅[通道模型概述](https://msdn.microsoft.com/library/ms729840.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b3996-118">For more information about the WCF channel model, see [Channel Model Overview](https://msdn.microsoft.com/library/ms729840.aspx).</span></span>
  
 <span data-ttu-id="b3996-119">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是公开 SQL Server 数据库作为 WCF 服务的 WCF 自定义传输绑定。</span><span class="sxs-lookup"><span data-stu-id="b3996-119">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom transport binding that exposes a SQL Server database as a WCF service.</span></span>  
  
## <a name="supported-channel-shapes-for-the-sql-server-adapter"></a><span data-ttu-id="b3996-120">支持 SQL Server 适配器通道形状</span><span class="sxs-lookup"><span data-stu-id="b3996-120">Supported Channel Shapes for the SQL Server Adapter</span></span>  
 <span data-ttu-id="b3996-121">适配器实现以下的 WCF 通道形状：</span><span class="sxs-lookup"><span data-stu-id="b3996-121">The adapter implements the following WCF channel shapes:</span></span>  
  
-   <span data-ttu-id="b3996-122">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。</span><span class="sxs-lookup"><span data-stu-id="b3996-122">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**).</span></span> <span data-ttu-id="b3996-123">**IRequestChannel**接口实现请求-答复消息交换的客户端。</span><span class="sxs-lookup"><span data-stu-id="b3996-123">The **IRequestChannel** interface implements the client side of a request-reply message exchange.</span></span> <span data-ttu-id="b3996-124">你可以使用**IRequestChannel**若要执行你想要使用响应的操作，例如，若要执行 SELECT 查询的表。</span><span class="sxs-lookup"><span data-stu-id="b3996-124">You can use an **IRequestChannel** to perform operations for which you want to consume a response, for example to perform a SELECT query on a table.</span></span>  
  
-   <span data-ttu-id="b3996-125">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。</span><span class="sxs-lookup"><span data-stu-id="b3996-125">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**).</span></span> <span data-ttu-id="b3996-126">此形状实现单向消息交换的客户端。</span><span class="sxs-lookup"><span data-stu-id="b3996-126">This shape implements the client side of a one-way message exchange.</span></span> <span data-ttu-id="b3996-127">你可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如，若要调用没有返回参数的过程。</span><span class="sxs-lookup"><span data-stu-id="b3996-127">You can use an **IOutputChannel** to invoke an operation for which you do not need to consume a response, for example to call a procedure that has no return parameters.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b3996-128">适配器对 SQL Server 客户端的所有基础的调用是同步的。</span><span class="sxs-lookup"><span data-stu-id="b3996-128">All underlying calls by the adapter to the SQL Server client are synchronous.</span></span> <span data-ttu-id="b3996-129">这包括调用 SQL Server 客户端通过调用操作的结果**IOutputChannel**。</span><span class="sxs-lookup"><span data-stu-id="b3996-129">This includes calls to the SQL Server client that are the result of operations invoked over an **IOutputChannel**.</span></span> <span data-ttu-id="b3996-130">当你使用**IOutputChannel**，适配器放弃从 SQL Server 客户端收到的响应。</span><span class="sxs-lookup"><span data-stu-id="b3996-130">When you use an **IOutputChannel**, the adapter discards the response received from the SQL Server client.</span></span>  
  
-   <span data-ttu-id="b3996-131">**IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。</span><span class="sxs-lookup"><span data-stu-id="b3996-131">**IInputChannel** (**System.ServiceModel.Channels.IInputChannel**).</span></span> <span data-ttu-id="b3996-132">此形状实现单向消息交换的服务端。</span><span class="sxs-lookup"><span data-stu-id="b3996-132">This shape implements the service side of a one-way message exchange.</span></span> <span data-ttu-id="b3996-133">你使用**IInputChannel**来接收消息入站操作，如**轮询**或**通知**，从适配器。</span><span class="sxs-lookup"><span data-stu-id="b3996-133">You use an **IInputChannel** to receive messages for inbound operations, such as **Polling** or **Notification**, from the adapter.</span></span>  
  
 <span data-ttu-id="b3996-134">如任何 WCF 绑定，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用工厂模式提供到应用程序代码的通道。</span><span class="sxs-lookup"><span data-stu-id="b3996-134">Like any WCF binding, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses a factory pattern to provide channels to application code.</span></span> <span data-ttu-id="b3996-135">你使用**Microsoft.Adapters.SQLBinding**对象创建的实例：</span><span class="sxs-lookup"><span data-stu-id="b3996-135">You use a **Microsoft.Adapters.SQLBinding** object to create instances of:</span></span>  
  
-   <span data-ttu-id="b3996-136">**System.ServiceModel.ChannelFactory\<IRequestChannel\>** 提供**IRequestChannel**通道可用于调用在适配器上的请求-响应操作。</span><span class="sxs-lookup"><span data-stu-id="b3996-136">**System.ServiceModel.ChannelFactory\<IRequestChannel\>** to provide **IRequestChannel** channels you can use to invoke request-response operations on the adapter.</span></span>  
  
-   <span data-ttu-id="b3996-137">**System.ServiceModel.ChannelFactory\<IOutputChannel\>** 提供**IOutputChannel**通道可用于调用在适配器上的单向操作。</span><span class="sxs-lookup"><span data-stu-id="b3996-137">**System.ServiceModel.ChannelFactory\<IOutputChannel\>** to provide **IOutputChannel** channels you can use to invoke one-way operations on the adapter.</span></span>  
  
-   <span data-ttu-id="b3996-138">**System.ServiceModel.IChannelListener\<IInputChannel\>** 提供**IInputChannel**通道可用于收到入站操作的消息，例如**轮询**或**通知**，从适配器。</span><span class="sxs-lookup"><span data-stu-id="b3996-138">**System.ServiceModel.IChannelListener\<IInputChannel\>** to provide **IInputChannel** channels you can use to receive messages for inbound operations, such as **Polling** or **Notification**, from the adapter.</span></span>  
  
### <a name="creating-messages-for-the-sql-server-database-adapter-in-the-wcf-channel-model"></a><span data-ttu-id="b3996-139">为 SQL Server 数据库适配器 WCF 通道模型中创建消息</span><span class="sxs-lookup"><span data-stu-id="b3996-139">Creating Messages for the SQL Server Database Adapter in the WCF Channel Model</span></span>  
 <span data-ttu-id="b3996-140">在 WCF 中**System.ServiceModel.Channels.Message**类提供内存中的 SOAP 消息的表示形式。</span><span class="sxs-lookup"><span data-stu-id="b3996-140">In WCF the **System.ServiceModel.Channels.Message** class provides an in memory representation of a SOAP message.</span></span> <span data-ttu-id="b3996-141">你创建**消息**实例通过调用静态**Message.Create**方法。</span><span class="sxs-lookup"><span data-stu-id="b3996-141">You create a **Message** instance by invoking the static **Message.Create** method.</span></span>  
  
 <span data-ttu-id="b3996-142">有两个重要部分，你必须指定当创建的 SOAP 消息**消息**实例将发送到[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b3996-142">There are two important parts to the SOAP message that you must specify when you create a **Message** instance to send to the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="b3996-143">消息操作是一个字符串，它的 SOAP 消息标头的一部分。</span><span class="sxs-lookup"><span data-stu-id="b3996-143">The message action is a string that is part of the SOAP message header.</span></span> <span data-ttu-id="b3996-144">消息操作标识应在数据库调用的操作。</span><span class="sxs-lookup"><span data-stu-id="b3996-144">The message action identifies the operation that should be invoked on the database.</span></span> <span data-ttu-id="b3996-145">下面的示例演示指定要调用员工表上的选择操作的消息操作： `TableOp/Select/dbo/Employee`。</span><span class="sxs-lookup"><span data-stu-id="b3996-145">The following shows the message action specified to invoke the Select operation on the Employee table: `TableOp/Select/dbo/Employee`.</span></span>  
  
-   <span data-ttu-id="b3996-146">消息正文包含操作的参数数据。</span><span class="sxs-lookup"><span data-stu-id="b3996-146">The message body contains the parameter data for the operation.</span></span> <span data-ttu-id="b3996-147">消息正文组成对应于预期的消息架构的格式正确的 XML[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]请求的操作。</span><span class="sxs-lookup"><span data-stu-id="b3996-147">The message body is composed of well-formed XML that corresponds to the message schema expected by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] for the requested operation.</span></span> <span data-ttu-id="b3996-148">以下的消息正文指定员工表选择操作 (选择 \* 从员工 WHERE Employee_ID = 10001)。</span><span class="sxs-lookup"><span data-stu-id="b3996-148">The following message body specifies a Select operation on the Employee table (SELECT \* FROM Employee WHERE Employee_ID=10001).</span></span>  
  
    ```  
    <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <Columns>*</Columns>  
      <Query>where Employee_ID=10001</Query>  
    </Select>  
  
    ```  
  
 <span data-ttu-id="b3996-149">璝惠[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]消息架构和消息操作的操作，请参阅[消息和消息架构用于 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b3996-149">For information about the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] message schemas and message actions for operations, see [Messages and Message Schemas for BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>  
  
 <span data-ttu-id="b3996-150">这**创建**方法重载方法，提供了多种不同的选项，用于提供消息正文。</span><span class="sxs-lookup"><span data-stu-id="b3996-150">This **Create** method is overloaded and offers many different options for providing the message body.</span></span> <span data-ttu-id="b3996-151">下面的代码演示如何创建**消息**实例使用**XmlReader**提供消息正文。</span><span class="sxs-lookup"><span data-stu-id="b3996-151">The following code shows how to create a **Message** instance by using an **XmlReader** to supply the message body.</span></span> <span data-ttu-id="b3996-152">在此代码中，从文件中读取消息正文。</span><span class="sxs-lookup"><span data-stu-id="b3996-152">In this code, the message body is read from a file.</span></span>  
  
```  
XmlReader readerIn = XmlReader.Create("SelectInput.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "TableOp/Select/dbo/Employee",  
    readerIn);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="b3996-153">必须提供中的消息操作你**消息**实例。</span><span class="sxs-lookup"><span data-stu-id="b3996-153">You must provide a message action in your **Message** instance.</span></span> <span data-ttu-id="b3996-154">这通常完成时**消息**创建实例。</span><span class="sxs-lookup"><span data-stu-id="b3996-154">This is typically done when the **Message** instance is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3996-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3996-155">See Also</span></span>  
[<span data-ttu-id="b3996-156">使用 WCF 通道模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="b3996-156">Develop applications using the WCF Channel model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)