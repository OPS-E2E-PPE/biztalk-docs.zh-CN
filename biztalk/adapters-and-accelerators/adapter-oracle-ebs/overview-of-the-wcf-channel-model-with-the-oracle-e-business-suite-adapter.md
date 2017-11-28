---
title: "与 Oracle E-business Suite 适配器的 WCF 通道模型概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3afd2a97-5734-4c25-87a3-702d8461898b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d59965b4fe5a94ae29ac8459ef8b8d80999c1dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="e23f5-102">与 Oracle E-business Suite 适配器的 WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="e23f5-102">Overview of the WCF channel model with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="e23f5-103">若要在调用操作[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，你的代码充当 WCF 客户端，并将出站操作发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="e23f5-103">To invoke operations on the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], your code acts as a WCF client and sends outbound operations to the adapter.</span></span> <span data-ttu-id="e23f5-104">在 WCF 通道模型中，你的代码时，将调用在适配器上的操作通过在通道上发送请求消息。</span><span class="sxs-lookup"><span data-stu-id="e23f5-104">In the WCF channel model, your code invokes operations on the adapter by sending a request message over a channel.</span></span>  
  
 <span data-ttu-id="e23f5-105">若要调用等基于轮询的数据更改使用接收消息的入站的操作**轮询**操作提供的适配器，通过你的代码充当 WCF 服务，并且从适配器接收入站的操作。</span><span class="sxs-lookup"><span data-stu-id="e23f5-105">To invoke inbound operations, such as receiving polling-based data-changed messages using the **Poll** operation provided by the adapter, your code acts as a WCF service and receives the inbound operation from the adapter.</span></span> <span data-ttu-id="e23f5-106">换而言之，你的代码的请求消息从适配器接收通过通道。</span><span class="sxs-lookup"><span data-stu-id="e23f5-106">In other words, your code receives a request message from the adapter over a channel.</span></span>  
  
 <span data-ttu-id="e23f5-107">本部分中的主题提供使用的概述[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="e23f5-107">The topics in this section provide an overview of using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF channel model.</span></span>  
  
## <a name="wcf-channel-model-overview"></a><span data-ttu-id="e23f5-108">WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="e23f5-108">WCF Channel Model Overview</span></span>  
 <span data-ttu-id="e23f5-109">通过交换 SOAP 消息，客户端和服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="e23f5-109">Clients and services communicate by exchanging SOAP messages.</span></span> <span data-ttu-id="e23f5-110">WCF 通道模型是此消息交换的低级别抽象。</span><span class="sxs-lookup"><span data-stu-id="e23f5-110">The WCF channel model is a low-level abstraction of this message exchange.</span></span> <span data-ttu-id="e23f5-111">它提供接口和使您能够发送和接收消息，通过使用调用的通道堆栈的分层的协议堆栈的类型。</span><span class="sxs-lookup"><span data-stu-id="e23f5-111">It provides interfaces and types that enable you to send and receive messages by using a layered protocol stack called a channel stack.</span></span> <span data-ttu-id="e23f5-112">堆栈的每个层组成一个通道，并且每个通道创建从 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="e23f5-112">Each layer of the stack is composed of a channel, and each channel is created from a WCF binding.</span></span> <span data-ttu-id="e23f5-113">在最低层是传输通道。</span><span class="sxs-lookup"><span data-stu-id="e23f5-113">At the lowest layer is the transport channel.</span></span> <span data-ttu-id="e23f5-114">传输通道可实现服务和客户端之间的底层传输机制并显示到较高层 （和最终使用方应用程序） 的每条消息，并且**System.ServiceModel.Message**。</span><span class="sxs-lookup"><span data-stu-id="e23f5-114">The transport channel implements the underlying transport mechanism between a service and a client and presents each message to the higher layers (and ultimately the consuming application) as a **System.ServiceModel.Message**.</span></span> <span data-ttu-id="e23f5-115">WCF**消息**类是 SOAP 消息的抽象。</span><span class="sxs-lookup"><span data-stu-id="e23f5-115">The WCF **Message** class is an abstraction of a SOAP message.</span></span> <span data-ttu-id="e23f5-116">WCF 提供了多个通道接口，调用的基本 SOAP 消息交换模式进行建模，如请求-答复或单向通道形状。</span><span class="sxs-lookup"><span data-stu-id="e23f5-116">WCF provides several channel interfaces, called channel shapes, that model the basic SOAP message exchange patterns, such as request-reply or one-way.</span></span> <span data-ttu-id="e23f5-117">WCF 传输绑定提供的实现的一个或多个更高版本上层的通道形状可以用于发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="e23f5-117">A WCF transport binding provides an implementation of one or more channel shapes that higher layers can use to send and receive messages.</span></span> <span data-ttu-id="e23f5-118">有关 WCF 通道模型的详细信息，请参阅"通道模型概述"在[http://go.microsoft.com/fwlink/?LinkId=82614](http://go.microsoft.com/fwlink/?LinkId=82614)。</span><span class="sxs-lookup"><span data-stu-id="e23f5-118">For more information about the WCF channel model, see "Channel Model Overview" at [http://go.microsoft.com/fwlink/?LinkId=82614](http://go.microsoft.com/fwlink/?LinkId=82614).</span></span>  
  
 <span data-ttu-id="e23f5-119">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是公开 Oracle E-business Suite 项目作为一个 WCF 服务的 WCF 自定义传输绑定。</span><span class="sxs-lookup"><span data-stu-id="e23f5-119">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom transport binding that exposes an Oracle E-Business Suite artifact as a WCF service.</span></span>  
  
## <a name="supported-channel-shapes-for-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="e23f5-120">为 Oracle E-business Suite 适配器支持通道形状</span><span class="sxs-lookup"><span data-stu-id="e23f5-120">Supported Channel Shapes for the Oracle E-Business Suite Adapter</span></span>  
 <span data-ttu-id="e23f5-121">适配器实现以下的 WCF 通道形状：</span><span class="sxs-lookup"><span data-stu-id="e23f5-121">The adapter implements the following WCF channel shapes:</span></span>  
  
-   <span data-ttu-id="e23f5-122">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。</span><span class="sxs-lookup"><span data-stu-id="e23f5-122">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**).</span></span> <span data-ttu-id="e23f5-123">**IRequestChannel**接口实现请求-答复消息交换的客户端。</span><span class="sxs-lookup"><span data-stu-id="e23f5-123">The **IRequestChannel** interface implements the client side of a request-reply message exchange.</span></span> <span data-ttu-id="e23f5-124">你可以使用**IRequestChannel**若要执行你想要使用响应的操作，例如，若要执行 SELECT 查询接口表上。</span><span class="sxs-lookup"><span data-stu-id="e23f5-124">You can use an **IRequestChannel** to perform operations for which you want to consume a response, for example to perform a SELECT query on an interface table.</span></span>  
  
-   <span data-ttu-id="e23f5-125">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。</span><span class="sxs-lookup"><span data-stu-id="e23f5-125">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**).</span></span> <span data-ttu-id="e23f5-126">此形状实现单向消息交换的客户端。</span><span class="sxs-lookup"><span data-stu-id="e23f5-126">This shape implements the client side of a one-way message exchange.</span></span> <span data-ttu-id="e23f5-127">你可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如，调用过程没有 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="e23f5-127">You can use an **IOutputChannel** to invoke an operation for which you do not need to consume a response, for example to call a procedure that has no OUT parameters.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e23f5-128">适配器对 Oracle 客户端的所有基础的调用是同步的。</span><span class="sxs-lookup"><span data-stu-id="e23f5-128">All underlying calls by the adapter to the Oracle client are synchronous.</span></span> <span data-ttu-id="e23f5-129">这包括调用 Oracle 客户端通过调用操作的结果**IOutputChannel**。</span><span class="sxs-lookup"><span data-stu-id="e23f5-129">This includes calls to the Oracle client that are the result of operations invoked over an **IOutputChannel**.</span></span> <span data-ttu-id="e23f5-130">当你使用**IOutputChannel**，适配器放弃从 Oracle 客户端收到的响应。</span><span class="sxs-lookup"><span data-stu-id="e23f5-130">When you use an **IOutputChannel**, the adapter discards the response received from the Oracle client.</span></span>  
  
-   <span data-ttu-id="e23f5-131">**IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。</span><span class="sxs-lookup"><span data-stu-id="e23f5-131">**IInputChannel** (**System.ServiceModel.Channels.IInputChannel**).</span></span> <span data-ttu-id="e23f5-132">此形状实现单向消息交换的服务端。</span><span class="sxs-lookup"><span data-stu-id="e23f5-132">This shape implements the service side of a one-way message exchange.</span></span> <span data-ttu-id="e23f5-133">你使用**IInputChannel**从适配器接收入站的消息。</span><span class="sxs-lookup"><span data-stu-id="e23f5-133">You use an **IInputChannel** to receive inbound messages from the adapter.</span></span>  
  
 <span data-ttu-id="e23f5-134">如任何 WCF 绑定，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用工厂模式提供到应用程序代码的通道。</span><span class="sxs-lookup"><span data-stu-id="e23f5-134">Like any WCF binding, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses a factory pattern to provide channels to application code.</span></span> <span data-ttu-id="e23f5-135">你使用**Microsoft.Adapters.OracleEBSBinding**对象创建的实例：</span><span class="sxs-lookup"><span data-stu-id="e23f5-135">You use a **Microsoft.Adapters.OracleEBSBinding** object to create instances of:</span></span>  
  
-   <span data-ttu-id="e23f5-136">**System.ServiceModel.ChannelFactory\<IRequestChannel >**提供**IRequestChannel**通道可用于调用在适配器上的请求-响应操作。</span><span class="sxs-lookup"><span data-stu-id="e23f5-136">**System.ServiceModel.ChannelFactory\<IRequestChannel>** to provide **IRequestChannel** channels you can use to invoke request-response operations on the adapter.</span></span>  
  
-   <span data-ttu-id="e23f5-137">**System.ServiceModel.ChannelFactory\<IOutputChannel >**提供**IOutputChannel**通道可用于调用在适配器上的单向操作。</span><span class="sxs-lookup"><span data-stu-id="e23f5-137">**System.ServiceModel.ChannelFactory\<IOutputChannel>** to provide **IOutputChannel** channels you can use to invoke one-way operations on the adapter.</span></span>  
  
-   <span data-ttu-id="e23f5-138">**System.ServiceModel.IChannelListener\<IInputChannel >**提供**IInputChannel**可用于从适配器接收的入站的消息的通道。</span><span class="sxs-lookup"><span data-stu-id="e23f5-138">**System.ServiceModel.IChannelListener\<IInputChannel>** to provide **IInputChannel** channels you can use to receive inbound messages from the adapter.</span></span>  
  
### <a name="creating-messages-for-the-oracle-enterprise-business-solution-in-the-wcf-channel-model"></a><span data-ttu-id="e23f5-139">正在创建的 WCF 通道模型中的 Oracle 企业业务解决方案消息</span><span class="sxs-lookup"><span data-stu-id="e23f5-139">Creating Messages for the Oracle Enterprise Business Solution in the WCF Channel Model</span></span>  
 <span data-ttu-id="e23f5-140">在 WCF 中**System.ServiceModel.Channels.Message**类提供内存中的 SOAP 消息的表示形式。</span><span class="sxs-lookup"><span data-stu-id="e23f5-140">In WCF the **System.ServiceModel.Channels.Message** class provides an in memory representation of a SOAP message.</span></span> <span data-ttu-id="e23f5-141">你创建**消息**实例通过调用静态**Message.Create**方法。</span><span class="sxs-lookup"><span data-stu-id="e23f5-141">You create a **Message** instance by invoking the static **Message.Create** method.</span></span>  
  
 <span data-ttu-id="e23f5-142">有两个重要部分，你必须指定当创建的 SOAP 消息**消息**实例将发送到[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e23f5-142">There are two important parts to the SOAP message that you must specify when you create a **Message** instance to send to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
-   <span data-ttu-id="e23f5-143">消息操作是一个字符串，它的 SOAP 消息标头的一部分。</span><span class="sxs-lookup"><span data-stu-id="e23f5-143">The message action is a string that is part of the SOAP message header.</span></span> <span data-ttu-id="e23f5-144">消息操作标识应在 Oracle E-business Suite 调用的操作。</span><span class="sxs-lookup"><span data-stu-id="e23f5-144">The message action identifies the operation that should be invoked on the Oracle E-Business Suite.</span></span> <span data-ttu-id="e23f5-145">下面的示例演示指定要调用的消息操作**客户接口**下的并发程序**应收帐款**中 Oracle E-business Suite 应用程序： `ConcurrentPrograms/AR/RACUST`。</span><span class="sxs-lookup"><span data-stu-id="e23f5-145">The following shows the message action specified to invoke the **Customer Interface** concurrent program under the **Receivables** application in Oracle E-Business Suite: `ConcurrentPrograms/AR/RACUST`.</span></span>  
  
-   <span data-ttu-id="e23f5-146">消息正文包含操作的参数数据。</span><span class="sxs-lookup"><span data-stu-id="e23f5-146">The message body contains the parameter data for the operation.</span></span> <span data-ttu-id="e23f5-147">消息正文组成对应于预期的消息架构的格式正确的 XML[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]请求的操作。</span><span class="sxs-lookup"><span data-stu-id="e23f5-147">The message body is composed of well-formed XML that corresponds to the message schema expected by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] for the requested operation.</span></span> <span data-ttu-id="e23f5-148">以下的消息正文指定要调用的请求消息**客户接口**并发程序。</span><span class="sxs-lookup"><span data-stu-id="e23f5-148">The following message body specifies a request message to invoke the **Customer Interface** concurrent program.</span></span>  
  
    ```  
    <RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
      <Description>Customer Interface Program</Description>  
      <StartTime></StartTime>  
      <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
      <ORG_ID>203</ORG_ID>  
    </RACUST>  
  
    ```  
  
 <span data-ttu-id="e23f5-149">璝惠[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]消息架构和消息操作的操作，请参阅[消息和消息架构用于 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="e23f5-149">For information about the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] message schemas and message actions for operations, see [Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
 <span data-ttu-id="e23f5-150">**创建**方法重载方法，提供了多种不同的选项，用于提供消息正文。</span><span class="sxs-lookup"><span data-stu-id="e23f5-150">The **Create** method is overloaded and offers many different options for providing the message body.</span></span> <span data-ttu-id="e23f5-151">下面的代码演示如何创建**消息**实例使用**XmlReader**提供消息正文。</span><span class="sxs-lookup"><span data-stu-id="e23f5-151">The following code shows how to create a **Message** instance by using an **XmlReader** to supply the message body.</span></span> <span data-ttu-id="e23f5-152">在此代码中，从文件中读取消息正文。</span><span class="sxs-lookup"><span data-stu-id="e23f5-152">In this code, the message body is read from a file.</span></span>  
  
```  
XmlReader readerIn = XmlReader.Create("ConcProgRequest.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "ConcurrentPrograms/AR/RACUST",  
    readerIn);  
```  
  
 <span data-ttu-id="e23f5-153">其中，ConProgRequest.xml 包含请求消息。</span><span class="sxs-lookup"><span data-stu-id="e23f5-153">where, ConProgRequest.xml contains the request message.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e23f5-154">必须提供中的消息操作你**消息**实例。</span><span class="sxs-lookup"><span data-stu-id="e23f5-154">You must provide a message action in your **Message** instance.</span></span> <span data-ttu-id="e23f5-155">这通常完成时**消息**创建实例。</span><span class="sxs-lookup"><span data-stu-id="e23f5-155">This is typically done when the **Message** instance is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e23f5-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e23f5-156">See Also</span></span>  
 [<span data-ttu-id="e23f5-157">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="e23f5-157">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)