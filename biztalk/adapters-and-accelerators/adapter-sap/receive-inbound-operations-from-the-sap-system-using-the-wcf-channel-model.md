---
title: 使用 WCF 通道模型的 SAP 系统从接收的入站的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming inbound flat-file IDOCs
- WCF channel model, receiving inbound operations from the SAP system
- WCF channel model, raising an exception
ms.assetid: d71d0537-fda4-44ab-85dc-6e27aad23caf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c0c819372cf23842eb5311df8636e55e28c72a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969678"
---
# <a name="receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model"></a><span data-ttu-id="25733-102">使用 WCF 通道模型的 SAP 系统从接收的入站的操作</span><span class="sxs-lookup"><span data-stu-id="25733-102">Receive Inbound Operations from the SAP System Using the WCF Channel Model</span></span>
<span data-ttu-id="25733-103">若要为 RFC 服务器和接收操作 （如发送 IDOC 或调用 RFC） SAP 系统调用，必须创建可通过侦听来自 SAP 程序 ID 的消息的通道侦听器**System.ServiceModel.Channels.IReplyChannel**通道形状。</span><span class="sxs-lookup"><span data-stu-id="25733-103">To act as an RFC server and receive operations invoked by the SAP system (such as sending an IDOC or invoking an RFC), you must create a channel listener that can listen for messages from a SAP Program ID over a **System.ServiceModel.Channels.IReplyChannel** channel shape.</span></span>  
  
 <span data-ttu-id="25733-104">通道侦听器 (**System.ServiceModel.Channels.IChannelListener**) 是可用于从特定的 WCF 终结点接收消息的 WCF 通信对象。</span><span class="sxs-lookup"><span data-stu-id="25733-104">A channel listener (**System.ServiceModel.Channels.IChannelListener**) is a WCF communication object that can be used to receive messages from specific WCF endpoints.</span></span> <span data-ttu-id="25733-105">通道侦听器充当通过它可以创建对其可由你的服务接收调用的客户端 （SAP 系统） 的消息的通道工厂。</span><span class="sxs-lookup"><span data-stu-id="25733-105">The channel listener functions as a factory from which you can create channels over which messages invoked by a client (the SAP system) can be received by your service.</span></span> <span data-ttu-id="25733-106">创建通道侦听器，通过从**Microsoft.Adapters.SAP.SAPBinding**对象通过调用**BuildChannelListener**方法。</span><span class="sxs-lookup"><span data-stu-id="25733-106">You create a channel listener by from a **Microsoft.Adapters.SAP.SAPBinding** object by invoking the **BuildChannelListener** method.</span></span> <span data-ttu-id="25733-107">提供的 SAP 连接 URI，指定 SAP 程序 ID 将从其接收的入站的操作到此方法。</span><span class="sxs-lookup"><span data-stu-id="25733-107">You supply an SAP connection URI that specifies the SAP Program ID from which inbound operations will be received to this method.</span></span>  
  
 <span data-ttu-id="25733-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持**IReplyChannel**通道形状。</span><span class="sxs-lookup"><span data-stu-id="25733-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the **IReplyChannel** channel shape.</span></span> <span data-ttu-id="25733-109">**IReplyChannel**通道支持入站的请求-响应消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="25733-109">**IReplyChannel** channels support an inbound request-response message exchange pattern.</span></span> <span data-ttu-id="25733-110">也就是说，外部程序将请求消息发送通过通道和应用程序的模式返回响应。</span><span class="sxs-lookup"><span data-stu-id="25733-110">That is, a pattern in which an external program sends a request message over the channel and your program returns a response.</span></span>  
  
 <span data-ttu-id="25733-111">有关如何接收操作使用的概述**IReplyChannel**在 WCF 中，请参阅[服务通道级编程](https://msdn.microsoft.com/library/ms789029.aspx)。</span><span class="sxs-lookup"><span data-stu-id="25733-111">For an overview of how to receive operations using an **IReplyChannel** in WCF, see [Service Channel-Level Programming](https://msdn.microsoft.com/library/ms789029.aspx).</span></span>
  
 <span data-ttu-id="25733-112">本部分介绍的是特定于 SAP 系统从接收操作的以下主题：</span><span class="sxs-lookup"><span data-stu-id="25733-112">This section covers the following topics that are specific to receiving operations from a SAP system:</span></span>  
  
-   <span data-ttu-id="25733-113">如何筛选对特定操作使用的通道侦听器。</span><span class="sxs-lookup"><span data-stu-id="25733-113">How to filter for specific operations using the channel listener.</span></span>  
  
-   <span data-ttu-id="25733-114">如何引发异常的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="25733-114">How to raise an exception on the SAP system.</span></span>  
  
-   <span data-ttu-id="25733-115">从 SAP 适配器的入站的平面文件 Idoc 进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="25733-115">Streaming inbound flat-file IDOCs from the SAP adapter.</span></span>  
  
-   <span data-ttu-id="25733-116">如何从 SAP 系统接收操作。</span><span class="sxs-lookup"><span data-stu-id="25733-116">How to receive operations from the SAP system.</span></span>  
  
## <a name="how-do-i-filter-operations-using-the-channel-listener"></a><span data-ttu-id="25733-117">如何筛选使用通道侦听器的操作？</span><span class="sxs-lookup"><span data-stu-id="25733-117">How Do I Filter Operations Using the Channel Listener?</span></span>  
  
### <a name="using-an-inboundactioncollection-to-filter-operations"></a><span data-ttu-id="25733-118">使用 InboundActionCollection 来筛选操作</span><span class="sxs-lookup"><span data-stu-id="25733-118">Using an InboundActionCollection to Filter Operations</span></span>  
 <span data-ttu-id="25733-119">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了**Microsoft.ServiceModel.Channels.InboundActionCollection**类，以使您能够筛选操作是由通道侦听器接收，并已传递给应用程序代码。</span><span class="sxs-lookup"><span data-stu-id="25733-119">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides the **Microsoft.ServiceModel.Channels.InboundActionCollection** class to enable you to filter operations that are received by a channel listener and passed to your application code.</span></span> <span data-ttu-id="25733-120">若要筛选对特定操作，请使用侦听器终结点 URI 创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="25733-120">To filter for specific operations, you create an instance of this class by using the listener endpoint URI.</span></span> <span data-ttu-id="25733-121">然后将每个目标操作 （请求） 消息操作添加到集合。</span><span class="sxs-lookup"><span data-stu-id="25733-121">Then you add the (request) message action for each target operation to the collection.</span></span> <span data-ttu-id="25733-122">最后，添加到的入站的操作集合**System.ServiceModel.Channels.BindingParameterCollection**对象，然后将此绑定参数集合传递到创建的通道侦听器的调用。</span><span class="sxs-lookup"><span data-stu-id="25733-122">Finally, you add the inbound action collection to a **System.ServiceModel.Channels.BindingParameterCollection** object and then pass this binding parameter collection into the call to create the channel listener.</span></span>  
  
 <span data-ttu-id="25733-123">如果 SAP 系统将调用不在入站的操作集合中的操作：</span><span class="sxs-lookup"><span data-stu-id="25733-123">If the SAP system invokes an operation that is not in the inbound action collection:</span></span>  
  
- <span data-ttu-id="25733-124">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]具有以下消息的 SAP 系统上向调用方返回一个异常异常:"未处理 Rfc 服务器上的传入 RFC 调用 [RFC_NAME]"。</span><span class="sxs-lookup"><span data-stu-id="25733-124">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] returns an EXCEPTION exception to the caller on the SAP system with the following message: "The incoming RFC call [RFC_NAME] on the Rfc Server is not handled".</span></span> <span data-ttu-id="25733-125">此消息中，[RFC_NAME] 是 RFC (例如，IDOC_INBOUND_ASYNCHRONOUS) 的名称。</span><span class="sxs-lookup"><span data-stu-id="25733-125">In this message, [RFC_NAME] is the name of the RFC (for example, IDOC_INBOUND_ASYNCHRONOUS).</span></span>  
  
- <span data-ttu-id="25733-126">适配器将引发**Microsoft.ServiceModel.Channels.Common.AdapterException**并显示消息，指示接收到的操作。</span><span class="sxs-lookup"><span data-stu-id="25733-126">The adapter throws a **Microsoft.ServiceModel.Channels.Common.AdapterException** with a message that indicates the operation that was received.</span></span> <span data-ttu-id="25733-127">有关如何使用此异常的示例，请参阅本主题末尾处的示例。</span><span class="sxs-lookup"><span data-stu-id="25733-127">For an example of how to use this exception, see the example at the end of this topic.</span></span>  
  
  <span data-ttu-id="25733-128">下面的代码示例演示如何使用**InboundActionCollection**创建适用于单个 RFC，Z_RFC_MKD_DIV 筛选器的通道侦听器。</span><span class="sxs-lookup"><span data-stu-id="25733-128">The following code example shows how to use an **InboundActionCollection** to create a channel listener that filters for a single RFC, Z_RFC_MKD_DIV.</span></span>  
  
```  
// The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
// and credentials.  
Uri listeneraddress =  
    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
// Create a binding and set AcceptCredentialsInUri to true  
SAPBinding binding = new SAPBinding();  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying the binding parameter collection (to filter for the Z_RFC_MKD_DIV action)  
listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
```  
  
### <a name="manually-filtering-operations"></a><span data-ttu-id="25733-129">手动筛选操作</span><span class="sxs-lookup"><span data-stu-id="25733-129">Manually Filtering Operations</span></span>  
 <span data-ttu-id="25733-130">如果未指定的通道侦听器的入站的操作集合，调用的 SAP 系统的所有操作将都传递到你的代码。</span><span class="sxs-lookup"><span data-stu-id="25733-130">If you do not specify an inbound action collection for the channel listener, then all operations invoked by the SAP system will be passed to your code.</span></span> <span data-ttu-id="25733-131">通过检查入站请求的消息操作，可以手动筛选此类操作。</span><span class="sxs-lookup"><span data-stu-id="25733-131">You can manually filter such operations by checking the message action of inbound requests.</span></span>  
  
 <span data-ttu-id="25733-132">也可能是想要筛选根据其内容的操作的方案。</span><span class="sxs-lookup"><span data-stu-id="25733-132">There may also be scenarios in which you want to filter an operation based on its content.</span></span> <span data-ttu-id="25733-133">例如，如果你收到的 Idoc 中：</span><span class="sxs-lookup"><span data-stu-id="25733-133">For example if you are receiving IDOCs in:</span></span>  
  
- <span data-ttu-id="25733-134">字符串格式 ( **ReceiveIDocFormat**绑定属性是**字符串**); 所有使用 ReceiveIdoc 操作接收 Idoc。</span><span class="sxs-lookup"><span data-stu-id="25733-134">String format (the **ReceiveIDocFormat** binding property is **String**); all IDOCs are received using the ReceiveIdoc operation.</span></span>  
  
- <span data-ttu-id="25733-135">Rfc 格式 ( **ReceiveIDocFormat**绑定属性是**Rfc**); 所有使用 IDOC_INBOUND_ASYNCHRONOUS RFC 或 INBOUND_IDOC_PROCESS RFC 接收 Idoc。</span><span class="sxs-lookup"><span data-stu-id="25733-135">Rfc format (the **ReceiveIDocFormat** binding property is **Rfc**); all IDOCs are received using either the IDOC_INBOUND_ASYNCHRONOUS RFC or the INBOUND_IDOC_PROCESS RFC.</span></span>  
  
  <span data-ttu-id="25733-136">在此方案中可能想要实现筛选基于在代码中特定 IDOC 参数 （如 IDOC 类型）。</span><span class="sxs-lookup"><span data-stu-id="25733-136">In this scenario you may want to implement filtering based on specific IDOC parameters (such as the IDOC type) in your code.</span></span>  
  
  <span data-ttu-id="25733-137">当手动筛选操作时，可返回到错误[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]的未处理的操作。</span><span class="sxs-lookup"><span data-stu-id="25733-137">When you filter operations manually, you can return a fault to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for operations that you don't handle.</span></span> <span data-ttu-id="25733-138">这将引发到 SAP 系统上调用方的异常异常。</span><span class="sxs-lookup"><span data-stu-id="25733-138">This will raise the EXCEPTION exception to the caller on the SAP System.</span></span> <span data-ttu-id="25733-139">如果不想要引发异常的 SAP，还可以返回一个空响应。</span><span class="sxs-lookup"><span data-stu-id="25733-139">You can also return an empty response if you don't want to raise an exception on SAP.</span></span>  
  
  <span data-ttu-id="25733-140">下面的代码演示如何手动 Z_RFC_MKD_DIV 操作筛选器。</span><span class="sxs-lookup"><span data-stu-id="25733-140">The following code shows how to filter manually for the Z_RFC_MKD_DIV operation.</span></span>  
  
```  
// Get the message from the channel  
RequestContext rc = channel.ReceiveRequest();  
Message reqMessage = rc.RequestMessage;  
  
// Filter based on the message action.  
if (reqMessage.Headers.Action == "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV")  
{  
  
    // Process message and return response.  
    ...  
  
}  
else  
{  
    // If this isn't the correct message return an empty response or a fault message.  
    // This example returns an empty response.  
    rc.Reply(Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response"));  
}  
```  
  
## <a name="how-do-i-raise-an-exception-on-the-sap-system"></a><span data-ttu-id="25733-141">如何引发异常的 SAP 系统？</span><span class="sxs-lookup"><span data-stu-id="25733-141">How Do I Raise an Exception on the SAP System?</span></span>  
 <span data-ttu-id="25733-142">若要指示一个错误，SAP 系统上调用方可以回复 SOAP 错误的请求消息。</span><span class="sxs-lookup"><span data-stu-id="25733-142">To indicate an error to the caller on the SAP system you can reply to a request message with a SOAP fault.</span></span> <span data-ttu-id="25733-143">当您返回到 SOAP 错误[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，适配器返回到调用方 SAP 系统上的异常的异常。</span><span class="sxs-lookup"><span data-stu-id="25733-143">When you return a SOAP fault to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the adapter returns an EXCEPTION exception to the caller on the SAP system.</span></span> <span data-ttu-id="25733-144">从 SOAP 错误的元素将创建的异常消息。</span><span class="sxs-lookup"><span data-stu-id="25733-144">The exception message is created from the elements of the SOAP fault.</span></span>  
  
 <span data-ttu-id="25733-145">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]创建以下优先顺序根据 SAP 异常消息：</span><span class="sxs-lookup"><span data-stu-id="25733-145">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] creates the message for the SAP EXCEPTION according to the following order of precedence:</span></span>  
  
1.  <span data-ttu-id="25733-146">如果 SOAP 错误中包含详细信息对象，该适配器序列化到字符串的详细信息和异常消息设置为此字符串。</span><span class="sxs-lookup"><span data-stu-id="25733-146">If the SOAP fault contains a detail object, the adapter serializes the detail to a string and the exception message is set to this string.</span></span>  
  
2.  <span data-ttu-id="25733-147">如果 SOAP 错误中包含一个原因，异常消息设置为它的值。</span><span class="sxs-lookup"><span data-stu-id="25733-147">If the SOAP fault contains a reason, the exception message is set to its value.</span></span>  
  
3.  <span data-ttu-id="25733-148">否则，适配器将序列化为**MessageFault**为字符串，并在异常消息对象本身设置为此字符串。</span><span class="sxs-lookup"><span data-stu-id="25733-148">Otherwise, the adapter serializes the **MessageFault** object itself to a string and the exception message is set to this string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25733-149">适配器仅使用错误消息来创建 SAP 系统所引发的异常中返回的异常消息因此，这些实体设置的值完全是由您决定。</span><span class="sxs-lookup"><span data-stu-id="25733-149">The adapter only uses the fault message to create the exception message returned in the exception raised on the SAP system; therefore, the values that you set for these entities is completely up to you.</span></span>  
  
 <span data-ttu-id="25733-150">WCF 提供了**System.ServiceModel.Channels.MessageFault**类来封装的 SOAP 错误的内存中表示形式。</span><span class="sxs-lookup"><span data-stu-id="25733-150">WCF provides the **System.ServiceModel.Channels.MessageFault** class to encapsulate an in-memory representation of a SOAP fault.</span></span> <span data-ttu-id="25733-151">您可以使用任何静态，重载**MessageFault.CreateFault**方法来创建新的 SOAP 错误，通过它你然后可以创建错误消息通过调用适当**Message.CreateMessage**重载。</span><span class="sxs-lookup"><span data-stu-id="25733-151">You can use any of the static, overloaded **MessageFault.CreateFault** methods to create a new SOAP fault from which you can then create a fault message by invoking the appropriate **Message.CreateMessage** overload.</span></span> <span data-ttu-id="25733-152">WCF 还提供了重载**CreateMessage** ，而无需使用创建的错误消息**MessageFault**对象。</span><span class="sxs-lookup"><span data-stu-id="25733-152">WCF also provides overloads of **CreateMessage** that create a fault message without using a **MessageFault** object.</span></span>  
  
 <span data-ttu-id="25733-153">您使用**System.ServiceModel.Channels.RequestContext.Reply**方法以返回到适配器的错误消息。</span><span class="sxs-lookup"><span data-stu-id="25733-153">You use the **System.ServiceModel.Channels.RequestContext.Reply** method to return the fault message to the adapter.</span></span> <span data-ttu-id="25733-154">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将忽略错误消息的消息操作，因此可以将消息操作设置为任何值。</span><span class="sxs-lookup"><span data-stu-id="25733-154">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ignores the message action for fault messages, so you can set the message action to any value.</span></span>  
  
 <span data-ttu-id="25733-155">下面的示例演示如何返回到的错误消息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="25733-155">The following example shows how to return a fault message to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="25733-156">此示例中省略创建的通道侦听器和通道的步骤。</span><span class="sxs-lookup"><span data-stu-id="25733-156">This example omits the steps to create the channel listener and channel.</span></span>  
  
```  
RequestContext rc = channel.ReceiveRequest();  
…  
// Start processing the inbound message  
…  
// If an error is encountered return a fault to the SAP system  
// This example uses CreateMessage overload to create a fault message.  
// The overload takes a SOAP version, fault code, reason, and message action  
// The SAP adapter ignores the message action for a fault so you can set it to any value you want.   
Message faultMessage = Message.CreateMessage(MessageVersion.Default, new FaultCode("SAP Example Fault"), "Testing SAP Faults", rc.RequestMessage.Headers.Action + "/fault");  
  
rc.Reply(faultMessage);  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-sap-adapter"></a><span data-ttu-id="25733-157">从 SAP 适配器的流式处理入站的平面文件 Idoc</span><span class="sxs-lookup"><span data-stu-id="25733-157">Streaming Inbound Flat-File IDOCs from the SAP Adapter</span></span>  
 <span data-ttu-id="25733-158">接收平面文件 （字符串） Idoc 从入站 ReceiveIdoc 操作中的适配器。</span><span class="sxs-lookup"><span data-stu-id="25733-158">You receive flat-file (string) IDOCs from the adapter in the inbound ReceiveIdoc operation.</span></span> <span data-ttu-id="25733-159">IDOC 数据表示为此操作中的单个节点下的字符串。</span><span class="sxs-lookup"><span data-stu-id="25733-159">The IDOC data is represented as a string under a single node in this operation.</span></span> <span data-ttu-id="25733-160">出于此原因，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持节点值流处理的请求消息。</span><span class="sxs-lookup"><span data-stu-id="25733-160">For this reason, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports node-value streaming on the request message.</span></span> <span data-ttu-id="25733-161">若要执行节点值流式处理，必须使用 ReceiveIdoc 操作的请求消息通过调用**Message.WriteBodyContents**方法替换**System.Xml.XmlDictionaryWriter** ，它能够流式传输 IDOC 的数据。</span><span class="sxs-lookup"><span data-stu-id="25733-161">To perform node-value streaming, you must consume the request message for the ReceiveIdoc operation by invoking the **Message.WriteBodyContents** method with a **System.Xml.XmlDictionaryWriter** that is capable of streaming the IDOC data.</span></span> <span data-ttu-id="25733-162">有关如何执行此操作的信息，请参阅[流式处理中使用 WCF 通道模型的 SAP 的平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="25733-162">For information about how to do this, see [Streaming Flat-File IDOCs in SAP using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="how-do-i-receive-operations-from-a-sap-system-using-an-ireplychannel"></a><span data-ttu-id="25733-163">如何从使用 IReplyChannel 的 SAP 系统接收操作？</span><span class="sxs-lookup"><span data-stu-id="25733-163">How Do I Receive Operations from a SAP System Using an IReplyChannel?</span></span>  
 <span data-ttu-id="25733-164">若要通过使用 WCF 通道模型接收来自 SAP 系统的操作，执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="25733-164">To receive operations from a SAP system by using the WCF channel model, perform the following steps.</span></span>  
  
#### <a name="to-receive-operations-from-the-sap-system-using-an-ireplychannel"></a><span data-ttu-id="25733-165">若要从 SAP 系统使用 IReplyChannel 接收操作</span><span class="sxs-lookup"><span data-stu-id="25733-165">To receive operations from the SAP system using an IReplyChannel</span></span>  
  
1.  <span data-ttu-id="25733-166">创建的实例**SAPBinding**并设置你想要接收的操作为所需的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="25733-166">Create an instance of **SAPBinding** and set the binding properties required to for the operations you want to receive.</span></span> <span data-ttu-id="25733-167">至少必须设置**AcceptCredentialsInUri**绑定属性为 true。</span><span class="sxs-lookup"><span data-stu-id="25733-167">At a minimum you must set the **AcceptCredentialsInUri** binding property to true.</span></span> <span data-ttu-id="25733-168">若要充当 tRFC 服务器，必须设置**TidDatabaseConnectionString**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="25733-168">To act as a tRFC server, you must set the **TidDatabaseConnectionString** binding property.</span></span> <span data-ttu-id="25733-169">有关绑定属性的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="25733-169">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    ```  
    SAPBinding binding = new SAPBinding();  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
2.  <span data-ttu-id="25733-170">创建**BindingParameterCollection**并添加**InboundActionCollection** ，其中包含你想要接收的操作的操作。</span><span class="sxs-lookup"><span data-stu-id="25733-170">Create a **BindingParameterCollection** and add an **InboundActionCollection** that contains the actions of the operations that you want to receive.</span></span> <span data-ttu-id="25733-171">该适配器将到 SAP 系统的所有其他操作返回一个异常。</span><span class="sxs-lookup"><span data-stu-id="25733-171">The adapter will return an exception to the SAP system for all other operations.</span></span> <span data-ttu-id="25733-172">此步骤为可选步骤。</span><span class="sxs-lookup"><span data-stu-id="25733-172">This step is optional.</span></span> <span data-ttu-id="25733-173">有关详细信息，请参阅[接收从使用 WCF 通道模型的 SAP 系统的入站操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="25733-173">For more information, see [Receiving Inbound Operations from the SAP System Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
    ```  
    InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
    actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
    BindingParameterCollection bpcol = new BindingParameterCollection();  
    bpcol.Add(actions);  
    ```  
  
3.  <span data-ttu-id="25733-174">通过调用创建的通道侦听器**BuildChannelListener < IReplyChannel\>** 方法**SAPBinding**并将其打开。</span><span class="sxs-lookup"><span data-stu-id="25733-174">Create a channel listener by invoking **BuildChannelListener<IReplyChannel\>** method on the **SAPBinding** and open it.</span></span> <span data-ttu-id="25733-175">作为此方法的参数之一指定 SAP 连接 URI。</span><span class="sxs-lookup"><span data-stu-id="25733-175">You specify the SAP connection URI as one of the parameters to this method.</span></span> <span data-ttu-id="25733-176">连接 URI 必须包含适用于 SAP 系统的 RFC 目标的参数。</span><span class="sxs-lookup"><span data-stu-id="25733-176">The connection URI must contain parameters for an RFC Destination on the SAP system.</span></span> <span data-ttu-id="25733-177">有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="25733-177">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span> <span data-ttu-id="25733-178">如果您创建**BindingParameterCollection**在步骤 3 中，您还这在创建时指定的通道侦听器。</span><span class="sxs-lookup"><span data-stu-id="25733-178">If you created a **BindingParameterCollection** in step 3, you also specify this when you create the channel listener.</span></span>  
  
    ```  
    Uri listeneraddress =  
        new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
    IChannelListener<IReplyChannel> listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, bpcol);  
    listener.Open();  
    ```  
  
4.  <span data-ttu-id="25733-179">获取**IReplyChannel**通道通过调用**AcceptChannel**对侦听程序的方法并将其打开。</span><span class="sxs-lookup"><span data-stu-id="25733-179">Get an **IReplyChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IReplyChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
5.  <span data-ttu-id="25733-180">调用**ReceiveRequest**上要从适配器获取的下一步操作的请求消息的通道。</span><span class="sxs-lookup"><span data-stu-id="25733-180">Invoke **ReceiveRequest** on the channel to get the request message for the next operation from the adapter.</span></span>  
  
    ```  
    RequestContext rc = channel.ReceiveRequest();  
    ```  
  
6.  <span data-ttu-id="25733-181">使用适配器发送的请求消息。</span><span class="sxs-lookup"><span data-stu-id="25733-181">Consume the request message sent by the adapter.</span></span> <span data-ttu-id="25733-182">获取请求消息从**RequestMessage**的属性**RequestContext**。</span><span class="sxs-lookup"><span data-stu-id="25733-182">You get the request message from the **RequestMessage** property of the **RequestContext**.</span></span> <span data-ttu-id="25733-183">可以使用使用的消息**XmlReader**或**XmlDictionaryWriter**。</span><span class="sxs-lookup"><span data-stu-id="25733-183">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = (XmlReader)rc.RequestMessage.GetReaderAtBodyContents();  
    ```  
  
7.  <span data-ttu-id="25733-184">通过将响应或错误返回到 SAP 系统中完成该操作：</span><span class="sxs-lookup"><span data-stu-id="25733-184">Complete the operation by returning a response or fault to the SAP system:</span></span>  
  
    1.  <span data-ttu-id="25733-185">处理该消息并通过返回到适配器的响应消息返回到 SAP 系统的响应。</span><span class="sxs-lookup"><span data-stu-id="25733-185">Process the message and return a response to the SAP system by returning the response message to the adapter.</span></span> <span data-ttu-id="25733-186">此示例返回一条空消息。</span><span class="sxs-lookup"><span data-stu-id="25733-186">This example returns an empty message.</span></span>  
  
        ```  
        respMessage = Message.CreateMessage(MessageVersion.Default, rc.RequestMessage.Headers.Action + "/response");  
        rc.Reply(respMessage);  
        ```  
  
    2.  <span data-ttu-id="25733-187">通过向适配器返回的错误消息返回到 SAP 系统的一个异常。</span><span class="sxs-lookup"><span data-stu-id="25733-187">Return an exception to the SAP system by returning a fault message to the adapter.</span></span> <span data-ttu-id="25733-188">消息的操作，错误代码和原因，可以使用任何值。</span><span class="sxs-lookup"><span data-stu-id="25733-188">You can use any value for the message action, fault code, and reason.</span></span>  
  
        ```  
        MessageFault fault = MessageFault.CreateFault(new FaultCode("ProcFault"), "Processing Error");  
        Message respMessage = Message.CreateMessage(MessageVersion.Default, fault, String.Empty);  
        rc.Reply(respMessage);  
        ```  
  
8.  <span data-ttu-id="25733-189">在发送消息之后，请关闭请求上下文。</span><span class="sxs-lookup"><span data-stu-id="25733-189">Close the request context after you have sent the message.</span></span>  
  
    ```  
    rc.Close();  
    ```  
  
9. <span data-ttu-id="25733-190">已完成处理请求时，请关闭通道。</span><span class="sxs-lookup"><span data-stu-id="25733-190">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="25733-191">在完成处理该操作后，您必须关闭通道。</span><span class="sxs-lookup"><span data-stu-id="25733-191">You must close the channel after you have finished processing the operation.</span></span> <span data-ttu-id="25733-192">未能关闭通道可能会影响你的代码的行为。</span><span class="sxs-lookup"><span data-stu-id="25733-192">Failure to close the channel may affect the behavior of your code.</span></span>  
  
10. <span data-ttu-id="25733-193">从 SAP 系统接收操作完成后，请关闭侦听器。</span><span class="sxs-lookup"><span data-stu-id="25733-193">Close the listener when you are finished receiving operations from the SAP system.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="25733-194">完成后，必须显式关闭该侦听器使用它;否则，您的程序可能不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="25733-194">You must explicitly close the listener when you are done using it; otherwise, your program may not behave properly.</span></span> <span data-ttu-id="25733-195">关闭侦听器不会关闭创建使用侦听器通道。</span><span class="sxs-lookup"><span data-stu-id="25733-195">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="25733-196">您必须显式关闭使用侦听器创建的每个通道。</span><span class="sxs-lookup"><span data-stu-id="25733-196">You must also explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="25733-197">示例</span><span class="sxs-lookup"><span data-stu-id="25733-197">Example</span></span>  
 <span data-ttu-id="25733-198">下面的示例接收 RFC，SAP 系统从 Z_RFC_MKD_DIV。</span><span class="sxs-lookup"><span data-stu-id="25733-198">The following example receives an RFC, Z_RFC_MKD_DIV from the SAP system.</span></span> <span data-ttu-id="25733-199">此 RFC 将两个数相除。</span><span class="sxs-lookup"><span data-stu-id="25733-199">This RFC divides two numbers.</span></span> <span data-ttu-id="25733-200">在此示例实现使用**InboundActionCollection**筛选 Z_RFC_MKD_DIV 操作而不会以下时收到一条消息：</span><span class="sxs-lookup"><span data-stu-id="25733-200">The implementation in this example uses an **InboundActionCollection** to filter for the Z_RFC_MKD_DIV operation and does the following when a message is received:</span></span>  
  
-   <span data-ttu-id="25733-201">如果除数为非零值，它向控制台写入该除法运算的结果，并将其返回到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="25733-201">If the divisor is non-zero, it writes the result of the division to the console and returns it to the SAP system.</span></span>  
  
-   <span data-ttu-id="25733-202">如果除数为零，它将生成的异常消息写入到控制台，并返回到 SAP 系统的错误。</span><span class="sxs-lookup"><span data-stu-id="25733-202">If the divisor is zero, it writes the resulting exception message to the console and returns a fault to the SAP system.</span></span>  
  
-   <span data-ttu-id="25733-203">如果任何其他操作发送的 SAP 系统，它将一条消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="25733-203">If any other operation is sent by the SAP system, it writes a message to the console.</span></span> <span data-ttu-id="25733-204">在这种情况下，适配器本身到 SAP 系统返回错误。</span><span class="sxs-lookup"><span data-stu-id="25733-204">In this case, the adapter itself returns a fault to the SAP system.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Runtime.Serialization;  
using System.Xml;  
using System.IO;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Add this namespace to use Channel Model   
using System.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This sample demonstrates using the adapter as an rfc server over a channel.  
// The sample implements an RFC, Z_RFC_MKD_DIV that divides two numbers and returns the result  
// 1)  A SAPBinding instance is created and configured (AcceptCredentialsInUri is set true)  
// 2)  A binding parameter collection is created with an InboundAction collection that specifies  
//     target RFC (Z_RFC_MKD_DIV) so that only messages with this action will be received by the  
//     listener (and channel).  
// 3)  An <IReplyChannel> listener is created from the binding and binding parameter collection  
// 4)  A channel is created and opened to receive a request  
// 6)  When Z_RFC_MKD_DIV is received the two parameters are divided and the parameters and result  
//     are written to the console, then the result is returned to the adapter by using a template  
//     message.  
// 7)  If a divide by 0 occurs the exception message is written to the console and a  
//     fault is returned to the SAP system  
// 8)  If any other operation is received an error message is written to the console and the adapter  
///    returns a fault to the SAP system  
// 9)  IMPORTANT you must close the channel and listener to deregister them from the SAP Program ID.  
namespace SapRfcServerCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Variables to hold the listener and channel  
            IChannelListener<IReplyChannel> listener = null;  
            IReplyChannel channel = null;  
  
            Console.WriteLine("Sample started");  
            Console.WriteLine("Initializing and creating channel listener -- please wait");  
            try  
            {  
  
                // The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
                // and also credentials.  
                Uri listeneraddress =  
                    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
                // Create a binding -- set AcceptCredentialsInUri true  
                SAPBinding binding = new SAPBinding();  
                binding.AcceptCredentialsInUri = true;  
  
                // Create a binding parameter collection with a list of SOAP actions to listen on  
                // in this case: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
                // This ensures that only these actions are received on the channel.  
                InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
                actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
                BindingParameterCollection bpcol = new BindingParameterCollection();  
                bpcol.Add(actions);  
  
                // Pass the Uri and the binding parameter collection (to specify the Z_RFC_MKD_DIV action)  
                listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
  
                Console.WriteLine("Opening listener");  
                // Open the listener  
                listener.Open();  
  
                // Get an IReplyChannel  
                channel = listener.AcceptChannel();  
  
                Console.WriteLine("Opening channel");  
                // Open the channel  
                channel.Open();  
  
                Console.WriteLine("\nReady to receive Z_RFC_MKD_DIV RFC");  
  
                try  
                {  
                    // Get the message from the channel  
                    RequestContext rc = channel.ReceiveRequest();  
  
                    // Get the request message sent by SAP  
                    Message reqMessage = rc.RequestMessage;  
  
                    // get the message body  
                    XmlReader reader = reqMessage.GetReaderAtBodyContents();  
  
                    reader.ReadStartElement("Z_RFC_MKD_DIV");  
                    reader.ReadElementString("DEST");  
                    int x_in = int.Parse(reader.ReadElementString("X"));  
                    int y_in = int.Parse(reader.ReadElementString("Y"));  
                    reader.ReadEndElement();  
  
                    Console.WriteLine("\nRfc Received");  
                    Console.WriteLine("X =\t\t" + x_in);  
                    Console.WriteLine("Y =\t\t" + y_in);  
  
                    Message messageOut = null;  
  
                    try   
                    {  
                        int result_out = x_in/y_in;  
  
                        Console.WriteLine("RESULT =\t" + result_out.ToString());  
  
                        string out_xml = "<Z_RFC_MKD_DIVResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"><RESULT>" + result_out + "</RESULT></Z_RFC_MKD_DIVResponse>";  
                        StringReader sr = new StringReader(out_xml);  
                        reader = XmlReader.Create(sr);  
  
                        // create a response message  
                        // be sure to specify the response action  
                        messageOut = Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response", reader);  
  
                    }  
                    catch (DivideByZeroException ex)  
                    {  
                        Console.WriteLine();  
                        Console.WriteLine(ex.Message + " Returning fault to SAP");  
  
                        // Create a message that contains a fault  
                        // The fault code and message action can be any value  
  
                        messageOut = Message.CreateMessage(MessageVersion.Default, new FaultCode("Fault"), ex.Message, string.Empty);  
                    }  
  
                    // Send the reply  
                    rc.Reply(messageOut);  
  
                    // Close the request context  
                    rc.Close();  
  
                }  
                catch (AdapterException aex)  
                {  
                    // Will get here if the message received was not in the InboundActionCollection  
                    Console.WriteLine();  
                    Console.WriteLine(aex.Message);  
                }  
  
                // Wait for a key to exit  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
                Console.WriteLine(tex.InnerException.Message);  
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
                // IMPORTANT: close the channel and listener to stop listening on the Program ID  
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
  
## <a name="see-also"></a><span data-ttu-id="25733-205">请参阅</span><span class="sxs-lookup"><span data-stu-id="25733-205">See Also</span></span>  
[<span data-ttu-id="25733-206">使用 WCF 通道模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="25733-206">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)