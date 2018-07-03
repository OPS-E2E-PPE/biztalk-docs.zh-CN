---
title: 使用 Oracle E-business Suite 适配器的 WCF 通道模型概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3afd2a97-5734-4c25-87a3-702d8461898b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcabe727b720c2319b253517ea78c573242df76c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987430"
---
# <a name="overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="d6f41-102">使用 Oracle E-business Suite 适配器的 WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="d6f41-102">Overview of the WCF channel model with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="d6f41-103">若要在调用操作[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，你的代码可用作 WCF 客户端，并将出站操作发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="d6f41-103">To invoke operations on the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], your code acts as a WCF client and sends outbound operations to the adapter.</span></span> <span data-ttu-id="d6f41-104">在 WCF 通道模型中，你的代码的通道上发送请求消息来调用在适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="d6f41-104">In the WCF channel model, your code invokes operations on the adapter by sending a request message over a channel.</span></span>  
  
 <span data-ttu-id="d6f41-105">若要调用入站的操作，例如接收基于轮询的数据更改消息使用**轮询**操作适配器提供的你的代码可用作 WCF 服务，并接收来自适配器的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="d6f41-105">To invoke inbound operations, such as receiving polling-based data-changed messages using the **Poll** operation provided by the adapter, your code acts as a WCF service and receives the inbound operation from the adapter.</span></span> <span data-ttu-id="d6f41-106">换而言之，你的代码的请求消息从适配器接收通过通道。</span><span class="sxs-lookup"><span data-stu-id="d6f41-106">In other words, your code receives a request message from the adapter over a channel.</span></span>  
  
 <span data-ttu-id="d6f41-107">在本部分中的主题提供使用概述[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="d6f41-107">The topics in this section provide an overview of using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF channel model.</span></span>  
  
## <a name="wcf-channel-model-overview"></a><span data-ttu-id="d6f41-108">WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="d6f41-108">WCF Channel Model Overview</span></span>  
 <span data-ttu-id="d6f41-109">通过交换 SOAP 消息，客户端和服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="d6f41-109">Clients and services communicate by exchanging SOAP messages.</span></span> <span data-ttu-id="d6f41-110">WCF 通道模型是此消息交换的低级别抽象。</span><span class="sxs-lookup"><span data-stu-id="d6f41-110">The WCF channel model is a low-level abstraction of this message exchange.</span></span> <span data-ttu-id="d6f41-111">它提供了接口和类型，您可以发送和接收消息，通过使用分层的协议堆栈，称为通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="d6f41-111">It provides interfaces and types that enable you to send and receive messages by using a layered protocol stack called a channel stack.</span></span> <span data-ttu-id="d6f41-112">堆栈中的每个层组成的一个通道，并且从 WCF 绑定创建的每个通道。</span><span class="sxs-lookup"><span data-stu-id="d6f41-112">Each layer of the stack is composed of a channel, and each channel is created from a WCF binding.</span></span> <span data-ttu-id="d6f41-113">在最低层是传输通道。</span><span class="sxs-lookup"><span data-stu-id="d6f41-113">At the lowest layer is the transport channel.</span></span> <span data-ttu-id="d6f41-114">传输通道可实现服务和客户端之间的基础传输机制并显示每条消息到较高的层 （和最终使用方应用程序），并且**System.ServiceModel.Message**。</span><span class="sxs-lookup"><span data-stu-id="d6f41-114">The transport channel implements the underlying transport mechanism between a service and a client and presents each message to the higher layers (and ultimately the consuming application) as a **System.ServiceModel.Message**.</span></span> <span data-ttu-id="d6f41-115">WCF**消息**类是抽象的 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="d6f41-115">The WCF **Message** class is an abstraction of a SOAP message.</span></span> <span data-ttu-id="d6f41-116">WCF 提供了多个通道接口，名为的基本 SOAP 消息交换模式进行建模，例如请求-答复或单向通道形状。</span><span class="sxs-lookup"><span data-stu-id="d6f41-116">WCF provides several channel interfaces, called channel shapes, that model the basic SOAP message exchange patterns, such as request-reply or one-way.</span></span> <span data-ttu-id="d6f41-117">WCF 传输绑定提供的实现的一个或更高版本层的详细通道形状可用于发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="d6f41-117">A WCF transport binding provides an implementation of one or more channel shapes that higher layers can use to send and receive messages.</span></span> <span data-ttu-id="d6f41-118">有关 WCF 通道模型的详细信息，请参阅"通道模型概述"处[ http://go.microsoft.com/fwlink/?LinkId=82614 ](http://go.microsoft.com/fwlink/?LinkId=82614)。</span><span class="sxs-lookup"><span data-stu-id="d6f41-118">For more information about the WCF channel model, see "Channel Model Overview" at [http://go.microsoft.com/fwlink/?LinkId=82614](http://go.microsoft.com/fwlink/?LinkId=82614).</span></span>  
  
 <span data-ttu-id="d6f41-119">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是公开 Oracle E-business Suite 项目作为 WCF 服务的 WCF 自定义传输绑定。</span><span class="sxs-lookup"><span data-stu-id="d6f41-119">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom transport binding that exposes an Oracle E-Business Suite artifact as a WCF service.</span></span>  
  
## <a name="supported-channel-shapes-for-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="d6f41-120">支持 Oracle E-business Suite 适配器的通道形状</span><span class="sxs-lookup"><span data-stu-id="d6f41-120">Supported Channel Shapes for the Oracle E-Business Suite Adapter</span></span>  
 <span data-ttu-id="d6f41-121">适配器实现以下 WCF 通道形状：</span><span class="sxs-lookup"><span data-stu-id="d6f41-121">The adapter implements the following WCF channel shapes:</span></span>  
  
- <span data-ttu-id="d6f41-122">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。</span><span class="sxs-lookup"><span data-stu-id="d6f41-122">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**).</span></span> <span data-ttu-id="d6f41-123">**IRequestChannel**接口实现请求-答复消息交换的客户端。</span><span class="sxs-lookup"><span data-stu-id="d6f41-123">The **IRequestChannel** interface implements the client side of a request-reply message exchange.</span></span> <span data-ttu-id="d6f41-124">可以使用**IRequestChannel**若要执行你想要使用响应的操作，例如若要执行 SELECT 查询在界面表。</span><span class="sxs-lookup"><span data-stu-id="d6f41-124">You can use an **IRequestChannel** to perform operations for which you want to consume a response, for example to perform a SELECT query on an interface table.</span></span>  
  
- <span data-ttu-id="d6f41-125">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。</span><span class="sxs-lookup"><span data-stu-id="d6f41-125">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**).</span></span> <span data-ttu-id="d6f41-126">此形状实现单向消息交换的客户端。</span><span class="sxs-lookup"><span data-stu-id="d6f41-126">This shape implements the client side of a one-way message exchange.</span></span> <span data-ttu-id="d6f41-127">可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如若要调用具有不带参数的过程。</span><span class="sxs-lookup"><span data-stu-id="d6f41-127">You can use an **IOutputChannel** to invoke an operation for which you do not need to consume a response, for example to call a procedure that has no OUT parameters.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="d6f41-128">适配器对 Oracle 客户端的所有基础的调用是同步的。</span><span class="sxs-lookup"><span data-stu-id="d6f41-128">All underlying calls by the adapter to the Oracle client are synchronous.</span></span> <span data-ttu-id="d6f41-129">这包括调用 Oracle 客户端通过调用操作的结果**IOutputChannel**。</span><span class="sxs-lookup"><span data-stu-id="d6f41-129">This includes calls to the Oracle client that are the result of operations invoked over an **IOutputChannel**.</span></span> <span data-ttu-id="d6f41-130">当你使用**IOutputChannel**，适配器将放弃从 Oracle 客户端收到的响应。</span><span class="sxs-lookup"><span data-stu-id="d6f41-130">When you use an **IOutputChannel**, the adapter discards the response received from the Oracle client.</span></span>  
  
- <span data-ttu-id="d6f41-131">**IInputChannel** (**System.ServiceModel.Channels.IInputChannel**)。</span><span class="sxs-lookup"><span data-stu-id="d6f41-131">**IInputChannel** (**System.ServiceModel.Channels.IInputChannel**).</span></span> <span data-ttu-id="d6f41-132">此形状实现单向消息交换在服务端。</span><span class="sxs-lookup"><span data-stu-id="d6f41-132">This shape implements the service side of a one-way message exchange.</span></span> <span data-ttu-id="d6f41-133">您使用**IInputChannel**以接收来自适配器的入站的消息。</span><span class="sxs-lookup"><span data-stu-id="d6f41-133">You use an **IInputChannel** to receive inbound messages from the adapter.</span></span>  
  
  <span data-ttu-id="d6f41-134">像任何 WCF 绑定，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用工厂模式来提供到应用程序代码的通道。</span><span class="sxs-lookup"><span data-stu-id="d6f41-134">Like any WCF binding, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses a factory pattern to provide channels to application code.</span></span> <span data-ttu-id="d6f41-135">您使用**Microsoft.Adapters.OracleEBSBinding**对象创建的实例：</span><span class="sxs-lookup"><span data-stu-id="d6f41-135">You use a **Microsoft.Adapters.OracleEBSBinding** object to create instances of:</span></span>  
  
- <span data-ttu-id="d6f41-136">**System.ServiceModel.ChannelFactory\<IRequestChannel\>** 提供**IRequestChannel**通道可用来调用在适配器上的请求-响应操作。</span><span class="sxs-lookup"><span data-stu-id="d6f41-136">**System.ServiceModel.ChannelFactory\<IRequestChannel\>** to provide **IRequestChannel** channels you can use to invoke request-response operations on the adapter.</span></span>  
  
- <span data-ttu-id="d6f41-137">**System.ServiceModel.ChannelFactory\<IOutputChannel\>** 提供**IOutputChannel**通道可用来调用在适配器上的单向操作。</span><span class="sxs-lookup"><span data-stu-id="d6f41-137">**System.ServiceModel.ChannelFactory\<IOutputChannel\>** to provide **IOutputChannel** channels you can use to invoke one-way operations on the adapter.</span></span>  
  
- <span data-ttu-id="d6f41-138">**System.ServiceModel.IChannelListener\<IInputChannel\>** 提供**IInputChannel**可用于接收来自适配器的入站的消息的通道。</span><span class="sxs-lookup"><span data-stu-id="d6f41-138">**System.ServiceModel.IChannelListener\<IInputChannel\>** to provide **IInputChannel** channels you can use to receive inbound messages from the adapter.</span></span>  
  
### <a name="creating-messages-for-the-oracle-enterprise-business-solution-in-the-wcf-channel-model"></a><span data-ttu-id="d6f41-139">正在创建 WCF 通道模型中的 Oracle 企业业务解决方案的消息</span><span class="sxs-lookup"><span data-stu-id="d6f41-139">Creating Messages for the Oracle Enterprise Business Solution in the WCF Channel Model</span></span>  
 <span data-ttu-id="d6f41-140">在 WCF **System.ServiceModel.Channels.Message**类提供了内存中 SOAP 消息的表示形式。</span><span class="sxs-lookup"><span data-stu-id="d6f41-140">In WCF the **System.ServiceModel.Channels.Message** class provides an in memory representation of a SOAP message.</span></span> <span data-ttu-id="d6f41-141">您创建**消息**实例通过调用静态**Message.Create**方法。</span><span class="sxs-lookup"><span data-stu-id="d6f41-141">You create a **Message** instance by invoking the static **Message.Create** method.</span></span>  
  
 <span data-ttu-id="d6f41-142">有两个重要部分，你必须指定当您创建的 SOAP 消息**消息**实例将发送到[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d6f41-142">There are two important parts to the SOAP message that you must specify when you create a **Message** instance to send to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
- <span data-ttu-id="d6f41-143">消息操作是一个字符串，是 SOAP 消息标头的一部分。</span><span class="sxs-lookup"><span data-stu-id="d6f41-143">The message action is a string that is part of the SOAP message header.</span></span> <span data-ttu-id="d6f41-144">消息操作标识应在 Oracle E-business Suite 中调用的操作。</span><span class="sxs-lookup"><span data-stu-id="d6f41-144">The message action identifies the operation that should be invoked on the Oracle E-Business Suite.</span></span> <span data-ttu-id="d6f41-145">下面的示例演示指定要调用的消息操作**的客户界面**下的并发程序**应收帐款**Oracle E-business Suite 中应用程序： `ConcurrentPrograms/AR/RACUST`。</span><span class="sxs-lookup"><span data-stu-id="d6f41-145">The following shows the message action specified to invoke the **Customer Interface** concurrent program under the **Receivables** application in Oracle E-Business Suite: `ConcurrentPrograms/AR/RACUST`.</span></span>  
  
- <span data-ttu-id="d6f41-146">消息正文包含操作的参数数据。</span><span class="sxs-lookup"><span data-stu-id="d6f41-146">The message body contains the parameter data for the operation.</span></span> <span data-ttu-id="d6f41-147">消息正文组成对应于所需的消息架构的格式正确的 XML[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]对请求的操作。</span><span class="sxs-lookup"><span data-stu-id="d6f41-147">The message body is composed of well-formed XML that corresponds to the message schema expected by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] for the requested operation.</span></span> <span data-ttu-id="d6f41-148">以下消息正文指定要调用的请求消息**的客户界面**并发程序。</span><span class="sxs-lookup"><span data-stu-id="d6f41-148">The following message body specifies a request message to invoke the **Customer Interface** concurrent program.</span></span>  
  
  ```  
  <RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
    <Description>Customer Interface Program</Description>  
    <StartTime></StartTime>  
    <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
    <ORG_ID>203</ORG_ID>  
  </RACUST>  
  
  ```  
  
  <span data-ttu-id="d6f41-149">璝惠[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]消息架构和消息操作的操作，请参见[消息和消息架构用于 Oracle E-business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="d6f41-149">For information about the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] message schemas and message actions for operations, see [Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
  <span data-ttu-id="d6f41-150">**创建**方法被重载并提供许多不同的提供消息正文选项。</span><span class="sxs-lookup"><span data-stu-id="d6f41-150">The **Create** method is overloaded and offers many different options for providing the message body.</span></span> <span data-ttu-id="d6f41-151">下面的代码演示如何创建**消息**通过使用实例**XmlReader**提供消息正文。</span><span class="sxs-lookup"><span data-stu-id="d6f41-151">The following code shows how to create a **Message** instance by using an **XmlReader** to supply the message body.</span></span> <span data-ttu-id="d6f41-152">在此代码中，从文件中读取消息正文。</span><span class="sxs-lookup"><span data-stu-id="d6f41-152">In this code, the message body is read from a file.</span></span>  
  
```  
XmlReader readerIn = XmlReader.Create("ConcProgRequest.xml");  
Message messageIn = Message.CreateMessage(MessageVersion.Default,  
    "ConcurrentPrograms/AR/RACUST",  
    readerIn);  
```  
  
 <span data-ttu-id="d6f41-153">其中，ConProgRequest.xml 包含请求消息。</span><span class="sxs-lookup"><span data-stu-id="d6f41-153">where, ConProgRequest.xml contains the request message.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d6f41-154">必须提供中的消息操作，你**消息**实例。</span><span class="sxs-lookup"><span data-stu-id="d6f41-154">You must provide a message action in your **Message** instance.</span></span> <span data-ttu-id="d6f41-155">这通常是何时**消息**创建实例。</span><span class="sxs-lookup"><span data-stu-id="d6f41-155">This is typically done when the **Message** instance is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f41-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6f41-156">See Also</span></span>  
 [<span data-ttu-id="d6f41-157">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="d6f41-157">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)