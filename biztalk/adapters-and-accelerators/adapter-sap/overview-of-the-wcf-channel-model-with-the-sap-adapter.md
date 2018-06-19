---
title: 与 SAP 适配器的 WCF 通道模型概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
- WCF channel model, creating messages for the SAP adapter
ms.assetid: 6192d637-efac-4580-8880-b5bae9d16f31
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b5469681f7acce2ebb0b55fe63e285d25192e0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967243"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sap-adapter"></a><span data-ttu-id="2c226-102">与 SAP 适配器的 WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="2c226-102">Overview of the WCF channel model with the SAP adapter</span></span>
<span data-ttu-id="2c226-103">若要在 SAP 系统中，调用 Rfc、 tRFCs 或 BAPIs 或将 IDOC 发送到 SAP 系统，你的代码将充当 WCF 客户端，并将出站操作发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="2c226-103">To invoke RFCs, tRFCs, or BAPIs on an SAP system, or to send IDOCS to an SAP system, your code acts as a WCF client and sends outbound operations to the adapter.</span></span> <span data-ttu-id="2c226-104">在 WCF 通道模型中，你的代码时，将调用在适配器上的操作通过在通道上发送请求消息。</span><span class="sxs-lookup"><span data-stu-id="2c226-104">In the WCF channel model, your code invokes operations on the adapter by sending a request message over a channel.</span></span>  
  
 <span data-ttu-id="2c226-105">若要充当 tRFC 或 RFC 到 SAP 系统的服务器，你的代码的行为作为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="2c226-105">To act as a tRFC or RFC server to an SAP system, your code behaves as a WCF service.</span></span> <span data-ttu-id="2c226-106">适配器，即你的代码上的入站的操作时，将调用 — 例如，RFC 或 ReceiveIdoc 操作 （以接收从 SAP 系统的字符串格式的 IDOC）。</span><span class="sxs-lookup"><span data-stu-id="2c226-106">That is, the adapter invokes an inbound operation on your code—for example, an RFC or the ReceiveIdoc operation (to receive an IDOC in string format from an SAP system).</span></span> <span data-ttu-id="2c226-107">在此方案中，你的代码通过从适配器通道接收到针对该操作的请求消息。</span><span class="sxs-lookup"><span data-stu-id="2c226-107">In this scenario, your code receives a request message for the operation over a channel from the adapter.</span></span>  
  
 <span data-ttu-id="2c226-108">本部分中的主题提供使用的概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="2c226-108">The topics in this section provide an overview of using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with the WCF channel model.</span></span>  
  
## <a name="wcf-channel-model-overview"></a><span data-ttu-id="2c226-109">WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="2c226-109">WCF Channel Model Overview</span></span>  
 <span data-ttu-id="2c226-110">通过交换 SOAP 消息，客户端和服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="2c226-110">Clients and services communicate by exchanging SOAP messages.</span></span> <span data-ttu-id="2c226-111">WCF 通道模型是此消息交换的低级别抽象。</span><span class="sxs-lookup"><span data-stu-id="2c226-111">The WCF channel model is a low-level abstraction of this message exchange.</span></span> <span data-ttu-id="2c226-112">它提供接口和使您能够发送和接收消息，通过使用调用的通道堆栈的分层的协议堆栈的类型。</span><span class="sxs-lookup"><span data-stu-id="2c226-112">It provides interfaces and types that enable you to send and receive messages by using a layered protocol stack called a channel stack.</span></span> <span data-ttu-id="2c226-113">堆栈的每个层组成一个通道，并且每个通道创建从 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="2c226-113">Each layer of the stack is composed of a channel, and each channel is created from a WCF binding.</span></span> <span data-ttu-id="2c226-114">在最低层是传输通道。</span><span class="sxs-lookup"><span data-stu-id="2c226-114">At the lowest layer is the transport channel.</span></span> <span data-ttu-id="2c226-115">传输通道可实现服务和客户端之间的底层传输机制并显示到较高层 （和最终使用方应用程序） 的每条消息，并且**System.ServiceModel.Message**。</span><span class="sxs-lookup"><span data-stu-id="2c226-115">The transport channel implements the underlying transport mechanism between a service and a client and presents each message to the higher layers (and ultimately the consuming application) as a **System.ServiceModel.Message**.</span></span> <span data-ttu-id="2c226-116">WCF**消息**类是 SOAP 消息的抽象。</span><span class="sxs-lookup"><span data-stu-id="2c226-116">The WCF **Message** class is an abstraction of a SOAP message.</span></span> <span data-ttu-id="2c226-117">WCF 提供了多个通道接口，调用的基本 SOAP 消息交换模式进行建模，如请求-答复或单向通道形状。</span><span class="sxs-lookup"><span data-stu-id="2c226-117">WCF provides several channel interfaces, called channel shapes, that model the basic SOAP message exchange patterns, such as request-reply or one-way.</span></span> <span data-ttu-id="2c226-118">WCF 传输绑定提供的实现的一个或多个更高版本上层的通道形状可以用于发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="2c226-118">A WCF transport binding provides an implementation of one or more channel shapes that higher layers can use to send and receive messages.</span></span> <span data-ttu-id="2c226-119">有关 WCF 通道模型的详细信息，请参阅[通道模型概述](https://msdn.microsoft.com/library/ms729840.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2c226-119">For more information about the WCF channel model, see [Channel Model Overview](https://msdn.microsoft.com/library/ms729840.aspx).</span></span>
  
 <span data-ttu-id="2c226-120">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是公开的 SAP 系统作为 WCF 服务的 WCF 自定义传输绑定。</span><span class="sxs-lookup"><span data-stu-id="2c226-120">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom transport binding that exposes an SAP system as a WCF service.</span></span>  
  
## <a name="supported-channel-shapes-for-the-sap-adapter"></a><span data-ttu-id="2c226-121">SAP 适配器支持通道形状</span><span class="sxs-lookup"><span data-stu-id="2c226-121">Supported Channel Shapes for the SAP Adapter</span></span>  
 <span data-ttu-id="2c226-122">适配器实现以下的 WCF 通道形状：</span><span class="sxs-lookup"><span data-stu-id="2c226-122">The adapter implements the following WCF channel shapes:</span></span>  
  
-   <span data-ttu-id="2c226-123">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。</span><span class="sxs-lookup"><span data-stu-id="2c226-123">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**).</span></span> <span data-ttu-id="2c226-124">**IRequestChannel**接口实现请求-答复消息交换的客户端。</span><span class="sxs-lookup"><span data-stu-id="2c226-124">The **IRequestChannel** interface implements the client side of a request-reply message exchange.</span></span> <span data-ttu-id="2c226-125">你可以使用**IRequestChannel**执行你想要使用的响应，例如调用 RFC 返回数据的 SAP 系统上的操作。</span><span class="sxs-lookup"><span data-stu-id="2c226-125">You can use an **IRequestChannel** to perform operations for which you want to consume a response, for example to invoke an RFC on the SAP system that returns data.</span></span>  
  
-   <span data-ttu-id="2c226-126">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。</span><span class="sxs-lookup"><span data-stu-id="2c226-126">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**).</span></span> <span data-ttu-id="2c226-127">此形状实现单向消息交换的客户端。</span><span class="sxs-lookup"><span data-stu-id="2c226-127">This shape implements the client side of a one-way message exchange.</span></span> <span data-ttu-id="2c226-128">你可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如，若要调用不返回任何数据的 SAP 系统上的 RFC。</span><span class="sxs-lookup"><span data-stu-id="2c226-128">You can use an **IOutputChannel** to invoke an operation for which you do not need to consume a response, for example to invoke an RFC on the SAP system that does not return any data.</span></span>  
  
-   <span data-ttu-id="2c226-129">**IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**)。</span><span class="sxs-lookup"><span data-stu-id="2c226-129">**IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**).</span></span> <span data-ttu-id="2c226-130">此形状实现请求-答复消息交换的服务端。</span><span class="sxs-lookup"><span data-stu-id="2c226-130">This shape implements the service side of a request-reply message exchange.</span></span> <span data-ttu-id="2c226-131">你可以使用**IReplyChannel**实现的 RFC 或 tRFC 服务器或从 SAP 系统接收到的 Idoc。</span><span class="sxs-lookup"><span data-stu-id="2c226-131">You can use an **IReplyChannel** to implement an RFC or tRFC server or to receive IDOCs from a SAP system.</span></span>  
  
 <span data-ttu-id="2c226-132">如任何 WCF 绑定，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用工厂模式提供到应用程序代码的通道。</span><span class="sxs-lookup"><span data-stu-id="2c226-132">Like any WCF binding, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses a factory pattern to provide channels to application code.</span></span> <span data-ttu-id="2c226-133">你使用**Microsoft.Adapters.SAPBinding**对象创建的实例：</span><span class="sxs-lookup"><span data-stu-id="2c226-133">You use a **Microsoft.Adapters.SAPBinding** object to create instances of:</span></span>  
  
-   <span data-ttu-id="2c226-134">**System.ServiceModel.ChannelFactory\<IRequestChannel\>** 提供**IRequestChannel**通道可用于调用在适配器上的请求-响应操作。</span><span class="sxs-lookup"><span data-stu-id="2c226-134">**System.ServiceModel.ChannelFactory\<IRequestChannel\>** to provide **IRequestChannel** channels you can use to invoke request-response operations on the adapter.</span></span>  
  
-   <span data-ttu-id="2c226-135">**System.ServiceModel.ChannelFactory\<IOutputChannel\>** 提供**IOutputChannel**通道可用于调用在适配器上的单向操作。</span><span class="sxs-lookup"><span data-stu-id="2c226-135">**System.ServiceModel.ChannelFactory\<IOutputChannel\>** to provide **IOutputChannel** channels you can use to invoke one-way operations on the adapter.</span></span>  
  
-   <span data-ttu-id="2c226-136">**System.ServiceModel.IChannelListener\<IReplyChannel\>** 提供**IReplyChannel**通道可用于从适配器接收请求-响应操作。</span><span class="sxs-lookup"><span data-stu-id="2c226-136">**System.ServiceModel.IChannelListener\<IReplyChannel\>** to provide **IReplyChannel** channels you can use to receive request-response operations from the adapter.</span></span>  
  
## <a name="creating-messages-for-the-sap-adapter-in-the-wcf-channel-model"></a><span data-ttu-id="2c226-137">正在创建的 WCF 通道模型中的 SAP 适配器消息</span><span class="sxs-lookup"><span data-stu-id="2c226-137">Creating Messages for the SAP Adapter in the WCF Channel Model</span></span>  
 <span data-ttu-id="2c226-138">在 WCF 中**System.ServiceModel.Channels.Message**类提供内存中的 SOAP 消息的表示形式。</span><span class="sxs-lookup"><span data-stu-id="2c226-138">In WCF the **System.ServiceModel.Channels.Message** class provides an in memory representation of a SOAP message.</span></span> <span data-ttu-id="2c226-139">你创建**消息**实例通过调用静态**Message.Create**方法。</span><span class="sxs-lookup"><span data-stu-id="2c226-139">You create a **Message** instance by invoking the static **Message.Create** method.</span></span>  
  
 <span data-ttu-id="2c226-140">有两个重要构造时必须指定的 SOAP 消息部分**消息**实例将发送到[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2c226-140">There are two important parts to the SOAP message that you must specify when you construct a **Message** instance to send to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
-   <span data-ttu-id="2c226-141">消息操作是一个字符串，它的 SOAP 消息标头的一部分。</span><span class="sxs-lookup"><span data-stu-id="2c226-141">The message action is a string that is part of the SOAP message header.</span></span> <span data-ttu-id="2c226-142">消息操作标识应在调用操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2c226-142">The message action identifies the operation that should be invoked on [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="2c226-143">下面的示例演示了指定用于调用 SD_RFC_CUSTOMER_GET RFC SAP 系统上的消息操作： `http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`。</span><span class="sxs-lookup"><span data-stu-id="2c226-143">The following shows the message action that is specified to invoke the SD_RFC_CUSTOMER_GET RFC on an SAP system: `http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`.</span></span>  
  
-   <span data-ttu-id="2c226-144">消息正文包含操作的参数数据。</span><span class="sxs-lookup"><span data-stu-id="2c226-144">The message body contains the parameter data for the operation.</span></span> <span data-ttu-id="2c226-145">消息正文组成对应于预期的消息架构的格式正确的 XML[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]请求的操作。</span><span class="sxs-lookup"><span data-stu-id="2c226-145">The message body is composed of well-formed XML that corresponds to the message schema expected by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for the requested operation.</span></span> <span data-ttu-id="2c226-146">以下的消息正文的 SAP 系统上 SD_RFC_CUSTOMER_GET RFC 中包含的参数。</span><span class="sxs-lookup"><span data-stu-id="2c226-146">The following message body contains the parameters for the SD_RFC_CUSTOMER_GET RFC on an SAP system.</span></span>  
  
    ```  
    <SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>  
    ```  
  
 <span data-ttu-id="2c226-147">璝惠[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]消息架构和消息操作的操作，请参阅[消息和消息架构用于 mySAP Business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="2c226-147">For information about the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] message schemas and message actions for operations, see [Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
 <span data-ttu-id="2c226-148">**Message.Create**方法重载方法，提供了多种不同的选项，用于提供消息正文。</span><span class="sxs-lookup"><span data-stu-id="2c226-148">The **Message.Create** method is overloaded and offers many different options for providing the message body.</span></span> <span data-ttu-id="2c226-149">下面的代码演示如何创建**消息**实例使用**System.Xml.XmlReader**提供消息正文。</span><span class="sxs-lookup"><span data-stu-id="2c226-149">The following code shows how to create a **Message** instance by using an **System.Xml.XmlReader** to supply the message body.</span></span> <span data-ttu-id="2c226-150">在此代码中，从字符串常量读取消息正文。</span><span class="sxs-lookup"><span data-stu-id="2c226-150">In this code, the message body is read from a string constant.</span></span>  
  
```  
//create an XML message to send to the SAP system  
//We are invoking the SD_RFC_CUSTOMER_GET RFC.  
//The XML below specifies that we want to search for customers with names starting with "AB"  
string inputXml = "<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
//create an XML reader from the input XML  
XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
//create a WCF message from the XML reader  
Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c226-151">必须提供中的消息操作你**消息**实例。</span><span class="sxs-lookup"><span data-stu-id="2c226-151">You must provide a message action in your **Message** instance.</span></span> <span data-ttu-id="2c226-152">这通常完成时**消息**创建实例。</span><span class="sxs-lookup"><span data-stu-id="2c226-152">This is typically done when the **Message** instance is created.</span></span>  
  
## <a name="streaming-support-on-the-sap-adapter-in-the-wcf-channel-model"></a><span data-ttu-id="2c226-153">在 WCF 通道模型中的 SAP 适配器上的流式处理支持</span><span class="sxs-lookup"><span data-stu-id="2c226-153">Streaming Support on the SAP Adapter in the WCF Channel Model</span></span>  
 <span data-ttu-id="2c226-154">如何创建和使用与 SAP 适配器交换的消息确定如何对消息流式处理你的代码和适配器之间。</span><span class="sxs-lookup"><span data-stu-id="2c226-154">How you create and consume the messages that you exchange with the SAP adapter determines how the message is streamed between your code and the adapter.</span></span>  
  
### <a name="node-streaming"></a><span data-ttu-id="2c226-155">流式处理的节点</span><span class="sxs-lookup"><span data-stu-id="2c226-155">Node streaming</span></span>  
 <span data-ttu-id="2c226-156">节点流是流式处理支持除 SendIdoc 和 ReceiveIdoc 操作的所有操作的唯一级别。</span><span class="sxs-lookup"><span data-stu-id="2c226-156">Node streaming is the only level of streaming supported for all operations except the SendIdoc and ReceiveIdoc operations.</span></span>  
  
 <span data-ttu-id="2c226-157">若要执行节点流式处理的消息，你：</span><span class="sxs-lookup"><span data-stu-id="2c226-157">To perform node streaming for a message, you:</span></span>  
  
-   <span data-ttu-id="2c226-158">创建出站消息使用**XmlReader**提供消息正文。</span><span class="sxs-lookup"><span data-stu-id="2c226-158">Create an outbound message using an **XmlReader** to supply the message body.</span></span>  
  
-   <span data-ttu-id="2c226-159">使用入站的消息使用**XmlReader**。</span><span class="sxs-lookup"><span data-stu-id="2c226-159">Consume an inbound message using an **XmlReader**.</span></span> <span data-ttu-id="2c226-160">通过调用获取读取器**GetReaderAtBodyContents**方法在入站**消息**。</span><span class="sxs-lookup"><span data-stu-id="2c226-160">You get the reader by calling the **GetReaderAtBodyContents** method on the inbound **Message**.</span></span>  
  
### <a name="node-value-streaming"></a><span data-ttu-id="2c226-161">节点值流式处理</span><span class="sxs-lookup"><span data-stu-id="2c226-161">Node-value Streaming</span></span>  
 <span data-ttu-id="2c226-162">因为 SendIdoc 和 ReceiveIdoc 操作包含在单个 XML 节点的字符串中的 IDOC 数据 (\<idocData\>) 的适配器支持节点的值流式处理这些操作。</span><span class="sxs-lookup"><span data-stu-id="2c226-162">Because the SendIdoc and ReceiveIdoc operations contain the IDOC data in a string under a single XML node (\<idocData\>), the adapter supports node-value streaming on these operations.</span></span>  
  
 <span data-ttu-id="2c226-163">若要执行这些操作流式处理节点的值，你可以：</span><span class="sxs-lookup"><span data-stu-id="2c226-163">To perform node-value streaming for these operations, you can:</span></span>  
  
-   <span data-ttu-id="2c226-164">创建 SendIdoc 请求消息 （出站） 使用**BodyWriter**实现流提供消息正文的节点的值。</span><span class="sxs-lookup"><span data-stu-id="2c226-164">Create the SendIdoc request message (outbound) using a **BodyWriter** that implements node-value streaming to supply the message body.</span></span>  
  
-   <span data-ttu-id="2c226-165">使用 ReceiveIdoc 请求消息 （入站） 通过调用**WriteBodyContents**方法对于消息**XmlDictionaryWriter**实现节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="2c226-165">Consume the ReceiveIdoc request message (inbound) by calling the **WriteBodyContents** method on the message with an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
 <span data-ttu-id="2c226-166">有关流式处理平面文件 （字符串） Idoc 使用 WCF 通道模型的详细信息，请参阅[SAP 使用 WCF 通道模型中流式处理平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="2c226-166">For more information about streaming flat file (string) IDOCs using the WCF channel model, see [Streaming Flat-File IDOCs in SAP using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c226-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c226-167">See Also</span></span>  
[<span data-ttu-id="2c226-168">使用 WCF 通道模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="2c226-168">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)