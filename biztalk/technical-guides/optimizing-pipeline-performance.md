---
title: 优化管道性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5137747-0dcf-4c96-90a7-01afb92f56a6
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34d83aad4a393df0cc0532545d5518fff9e0f8e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291355"
---
# <a name="optimizing-pipeline-performance"></a><span data-ttu-id="1febc-102">优化管道性能</span><span class="sxs-lookup"><span data-stu-id="1febc-102">Optimizing Pipeline Performance</span></span>
<span data-ttu-id="1febc-103">本主题介绍用于优化性能的管道中的指导原则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="1febc-103">This topic describes guidelines for optimizing performance of pipelines in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a><span data-ttu-id="1febc-104">有关优化 BizTalk Server 管道的性能最佳实践</span><span class="sxs-lookup"><span data-stu-id="1febc-104">Best practices for optimizing performance of BizTalk Server pipelines</span></span>  
  
1. <span data-ttu-id="1febc-105">由于管道组件对性能产生重大影响 （例如，直通管道组件执行比 XML 组装器/拆装器管道组件最多 30%），请确保任何自定义管道组件执行在部署中实现它们前以最佳方式。</span><span class="sxs-lookup"><span data-stu-id="1febc-105">Because pipeline components have a significant impact on performance (for example, a pass-through pipeline component performs up to 30 percent better than an XML assembler/disassembler pipeline component), make sure that any custom pipeline components perform optimally before implementing them in your deployment.</span></span> <span data-ttu-id="1febc-106">如果你想要最大化你的 BizTalk 应用程序的整体性能，最小化自定义管道中的管道组件数。</span><span class="sxs-lookup"><span data-stu-id="1febc-106">Minimize the number of pipeline components in your custom pipelines if you want to maximize the overall performance of your BizTalk application.</span></span>  
  
2. <span data-ttu-id="1febc-107">通过减少在管道组件中的消息持久性频率和编码让组件能够最大程度减少冗余，还可以提高整体性能。</span><span class="sxs-lookup"><span data-stu-id="1febc-107">You also can improve overall performance by reducing the message persistence frequency in your pipeline component and by coding your component to minimize redundancy.</span></span> <span data-ttu-id="1febc-108">每个自定义程序集，特别是可能导致性能，如自定义跟踪组件，可能会中断的项目应进行测试单独系统处理满负荷时观察它们的行为以及查找高负载条件下任何可能的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="1febc-108">Every custom assembly and in particular artifacts that could potentially disrupt performance, like custom tracking components, should be tested separately under heavy load condition to observe their behavior when the system is working at full capacity and to find any possible bottlenecks.</span></span>  
  
3. <span data-ttu-id="1febc-109">如果你需要阅读的管道组件中的入站的消息，避免将整个文档加载到内存使用**XmlDocument**对象。</span><span class="sxs-lookup"><span data-stu-id="1febc-109">If you need to read the inbound message inside a pipeline component, avoid loading the entire document into memory using an **XmlDocument** object.</span></span> <span data-ttu-id="1febc-110">实例所需的空间量**XmlDocument**类来加载和创建 XML 文档的内存中表示形式是实际的消息大小的 10 倍。</span><span class="sxs-lookup"><span data-stu-id="1febc-110">The amount of space required by an instance of the **XmlDocument** class to load and create an in-memory representation of a XML document is up to 10 times the actual message size.</span></span> <span data-ttu-id="1febc-111">为了读取一条消息，则应使用**XmlTextReader**对象以及以下类的实例：</span><span class="sxs-lookup"><span data-stu-id="1febc-111">In order to read a message, you should use an **XmlTextReader** object along with an instance of the following classes:</span></span>  
  
   -   <span data-ttu-id="1febc-112">**为 VirtualStream (Microsoft.BizTalk.Streaming.dll)** -此类的源代码位于以下两个管道 SDK 位置，如下所示：: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler 和 SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm。</span><span class="sxs-lookup"><span data-stu-id="1febc-112">**VirtualStream (Microsoft.BizTalk.Streaming.dll)** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
   -   <span data-ttu-id="1febc-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**。</span><span class="sxs-lookup"><span data-stu-id="1febc-113">**ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**.</span></span>  
  
   -   <span data-ttu-id="1febc-114">**SeekAbleReadOnlyStream** -此类的源代码位于以下两个管道 SDK 位置，如下所示：: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler 和 SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm。</span><span class="sxs-lookup"><span data-stu-id="1febc-114">**SeekAbleReadOnlyStream** - The source code for this class is located in two locations under the Pipelines SDK as follows: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler and SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.</span></span>  
  
4. <span data-ttu-id="1febc-115">使用 PassThruReceive 和 PassThruTransmit 标准管道，只要有可能。</span><span class="sxs-lookup"><span data-stu-id="1febc-115">Use the PassThruReceive and the PassThruTransmit standard pipelines whenever possible.</span></span> <span data-ttu-id="1febc-116">它们不包含任何管道组件，不执行任何处理消息。</span><span class="sxs-lookup"><span data-stu-id="1febc-116">They do not contain any pipeline component and do not perform any processing of the message.</span></span> <span data-ttu-id="1febc-117">出于此原因，它们将确保在接收或发送消息的最大性能。</span><span class="sxs-lookup"><span data-stu-id="1febc-117">For this reason, they ensure maximum performance in receiving or sending messages.</span></span> <span data-ttu-id="1febc-118">如果你需要将二进制文档发布到 BizTalk MessageBox 和 PassThruTransmit 管道在发送端口，如果需要发送二进制消息，可以在接收位置上使用 PassThruReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="1febc-118">You can use a PassThruReceive pipeline on a receive location if you need to publish a binary document to the BizTalk MessageBox and a PassThruTransmit pipeline on a send port if you need to send out a binary message.</span></span> <span data-ttu-id="1febc-119">此外可以在绑定到业务流程，如果消息已经过格式设置，并且是准备要传输的物理发送端口使用 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="1febc-119">You can also use the PassThruTransmit pipeline on a physical send port bound to an orchestration if the message has been formatted and is ready to be transmitted.</span></span> <span data-ttu-id="1febc-120">需要使用不同的方法，如果您需要完成以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="1febc-120">You will need to use a different approach if you need to accomplish one of the following actions:</span></span>  
  
   - <span data-ttu-id="1febc-121">升级的入站 XML 或平面文件消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="1febc-121">Promote properties on the context of an inbound XML or Flat File message.</span></span>  
  
   - <span data-ttu-id="1febc-122">应用内接收位置映射。</span><span class="sxs-lookup"><span data-stu-id="1febc-122">Apply a map inside a receive location.</span></span>  
  
   - <span data-ttu-id="1febc-123">将应用订阅的消息的业务流程中的地图。</span><span class="sxs-lookup"><span data-stu-id="1febc-123">Apply a map in an orchestration that subscribes to a message.</span></span>  
  
   - <span data-ttu-id="1febc-124">将映射应用于订阅的消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="1febc-124">Apply a map on a send port that subscribes to a message.</span></span>  
  
     <span data-ttu-id="1febc-125">若要完成以下操作之一，必须探测和发现接收管道中的文档类型，将 （命名空间 #root 的名称） 值分配给 MessageType 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="1febc-125">To accomplish one of these actions, you must probe and discover the document type inside the receive pipeline and assign the (namespace#root-name) value to the MessageType context property.</span></span> <span data-ttu-id="1febc-126">拆装器组件，如 Xml 拆装器组件 (XmlDasmComp) 或平面文件拆装器组件 (FFDasmComp) 通常来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1febc-126">This operation is typically accomplished by a disassembler component such as the Xml Disassembler component (XmlDasmComp) or the Flat File disassembler component (FFDasmComp).</span></span> <span data-ttu-id="1febc-127">在这种情况下，您需要使用标准 （例如，XmlReceive 管道） 或包含一个标准或自定义拆装器组件的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="1febc-127">In this case, you need to use a standard (for instance, XmlReceive pipeline) or a custom pipeline that contains a standard or a custom disassembler component.</span></span>  
  
5. <span data-ttu-id="1febc-128">获取资源，尽可能晚和发布它们尽早地。</span><span class="sxs-lookup"><span data-stu-id="1febc-128">Acquire resources as late as possible and release them as early as possible.</span></span> <span data-ttu-id="1febc-129">例如，如果需要访问数据库上的数据，打开晚尽可能的连接，并尽可能快地将其关闭。</span><span class="sxs-lookup"><span data-stu-id="1febc-129">For example, if you need to access data on a database, open the connection as late as possible and close it as soon as possible.</span></span> <span data-ttu-id="1febc-130">使用 C# using 语句隐式释放可释放对象或 finally 块的 try – catch – finally 语句来显式释放您的对象。</span><span class="sxs-lookup"><span data-stu-id="1febc-130">Use the C# using statement to implicitly release disposable objects or the finally block of a try-catch-finally statement to explicitly dispose your objects.</span></span> <span data-ttu-id="1febc-131">检测源代码以简化调试您的组件。</span><span class="sxs-lookup"><span data-stu-id="1febc-131">Instrument your source code to make your components simple to debug.</span></span>  
  
6. <span data-ttu-id="1febc-132">消除不严格要求，以加快消息处理管道中的任何组件。</span><span class="sxs-lookup"><span data-stu-id="1febc-132">Eliminate any components from your pipelines that are not strictly required to speed up message processing.</span></span>  
  
7. <span data-ttu-id="1febc-133">在接收管道中，您应将项目升级到消息上下文仅在需要它们的消息路由 （业务流程、 发送端口） 或降级的消息上下文属性 （发送端口）。</span><span class="sxs-lookup"><span data-stu-id="1febc-133">Inside a receive pipeline, you should promote items to the message context only if you need them for message routing (Orchestrations, Send Ports) or demotion of message context properties (Send Ports).</span></span>  
  
8. <span data-ttu-id="1febc-134">如果您需要包含元数据与一条消息，并且在未使用元数据进行路由或降级的目的，使用**IBaseMessageContext.Write**方法而不是**IBaseMessageContext.Promote**方法。</span><span class="sxs-lookup"><span data-stu-id="1febc-134">If you need to include metadata with a message, and you don't use the metadata for routing or demotion purposes, use the **IBaseMessageContext.Write** method instead of the **IBaseMessageContext.Promote** method.</span></span>  
  
9. <span data-ttu-id="1febc-135">如果你需要从使用 XPath 表达式的消息中提取信息，避免将整个文档加载到内存使用**XmlDocument**对象只是为了使用**SelectNodes**或**SelectSingleNode**方法。</span><span class="sxs-lookup"><span data-stu-id="1febc-135">If you need to extract information from a message using an XPath expression, avoid loading the entire document into memory using an **XmlDocument** object just to use the **SelectNodes** or **SelectSingleNode** methods.</span></span> <span data-ttu-id="1febc-136">或者，使用中所述的技术[与流式处理优化内存使用情况](../technical-guides/optimizing-memory-usage-with-streaming.md)。</span><span class="sxs-lookup"><span data-stu-id="1febc-136">Alternatively, use the techniques described in [Optimizing Memory Usage with Streaming](../technical-guides/optimizing-memory-usage-with-streaming.md).</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a><span data-ttu-id="1febc-137">使用流式处理时加载在管道中的消息所需的内存占用量降至最低</span><span class="sxs-lookup"><span data-stu-id="1febc-137">Use streaming to minimize the memory footprint required when loading messages in pipelines</span></span>  
 <span data-ttu-id="1febc-138">以下技术描述如何将消息加载到管道时，消息的内存占用量降至最低。</span><span class="sxs-lookup"><span data-stu-id="1febc-138">The following techniques describe how to minimize the memory footprint of a message when loading the message into a pipeline.</span></span>  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="1febc-139">使用 ReadOnlySeekableStream 和为 VirtualStream 来处理来自管道组件的消息</span><span class="sxs-lookup"><span data-stu-id="1febc-139">Use ReadOnlySeekableStream and VirtualStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="1febc-140">它被视为最佳做法来避免整个消息加载到内存中内部管道组件。</span><span class="sxs-lookup"><span data-stu-id="1febc-140">It is considered a best practice to avoid loading the entire message into memory inside pipeline components.</span></span> <span data-ttu-id="1febc-141">更好的办法是将包装的入站的流使用自定义流实现，然后为已读请求，自定义流实现读取底层的已包装流，并处理数据 （在纯流式处理方式） 读取。</span><span class="sxs-lookup"><span data-stu-id="1febc-141">A preferable approach is to wrap the inbound stream with a custom stream implementation, and then as read requests are made, the custom stream implementation reads the underlying, wrapped stream and processes the data as it is read (in a pure streaming manner).</span></span> <span data-ttu-id="1febc-142">这可以是很难实现，并不太可能，具体取决于需要使用流执行的操作的内容。</span><span class="sxs-lookup"><span data-stu-id="1febc-142">This can be very hard to implement and may not be possible, depending on what needs to be done with the stream.</span></span> <span data-ttu-id="1febc-143">在这种情况下，使用**ReadOnlySeekableStream**并**为 VirtualStream** Microsoft.BizTalk.Streaming.dll 所公开的类。</span><span class="sxs-lookup"><span data-stu-id="1febc-143">In this case, use the **ReadOnlySeekableStream** and **VirtualStream** classes exposed by the Microsoft.BizTalk.Streaming.dll.</span></span> <span data-ttu-id="1febc-144">中还提供了其中一个实现[任意 XPath 属性处理程序 （BizTalk Server 示例）](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) BizTalk SDK 中。**ReadOnlySeekableStream**可确保光标，可重新定位到流的开头。</span><span class="sxs-lookup"><span data-stu-id="1febc-144">An implementation of these is also provided in [Arbitrary XPath Property Handler (BizTalk Server Sample)](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) in the BizTalk SDK.**ReadOnlySeekableStream** ensures that the cursor can be repositioned to the beginning of the stream.</span></span> <span data-ttu-id="1febc-145">**为 VirtualStream**在内部，将使用 MemoryStream，除非大小为高于指定阈值，在这种情况下它将流写入到文件系统。</span><span class="sxs-lookup"><span data-stu-id="1febc-145">The **VirtualStream** will use a MemoryStream internally, unless the size is over a specified threshold, in which case it will write the stream to the file system.</span></span> <span data-ttu-id="1febc-146">结合使用这两个流的使用 (使用**为 VirtualStream**作为持久性存储**ReadOnlySeekableStream**) 提供了"seekability"和"溢出到文件系统"功能。</span><span class="sxs-lookup"><span data-stu-id="1febc-146">Use of these two streams in combination (using **VirtualStream** as persistent storage for the **ReadOnlySeekableStream**) provides both “seekability” and “overflow to file system” capabilities.</span></span> <span data-ttu-id="1febc-147">这不将整个消息加载到内存的情况下适合于处理大消息。</span><span class="sxs-lookup"><span data-stu-id="1febc-147">This accommodates the processing of large messages without loading the entire message into memory.</span></span> <span data-ttu-id="1febc-148">下面的代码可以在管道组件，用于实现此功能。</span><span class="sxs-lookup"><span data-stu-id="1febc-148">The following code could be used in a pipeline component to implement this functionality.</span></span>  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 <span data-ttu-id="1febc-149">此代码通过公开 bufferSize 提供"溢出阈值"和 thresholdSize 变量在每个接收位置或发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="1febc-149">This code provides an “overflow threshold” by exposing bufferSize and thresholdSize variables on each receive location or send port configuration.</span></span> <span data-ttu-id="1febc-150">然后可以通过开发人员或管理员针对不同消息类型和不同配置 （例如 32 位与调整此溢出阈值。64 位)。</span><span class="sxs-lookup"><span data-stu-id="1febc-150">This overflow threshold can then be adjusted by developers or administrators for different message types and different configurations (such as 32-bit vs. 64-bit).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a><span data-ttu-id="1febc-151">使用 XPathReader 和 XPathCollection 来提取从自定义管道组件中的给定的 IBaseMessage 对象。</span><span class="sxs-lookup"><span data-stu-id="1febc-151">Using XPathReader and XPathCollection to extract a given IBaseMessage object from within a custom pipeline component.</span></span>  
 <span data-ttu-id="1febc-152">如果需要从 XML 文档，而不是使用请求特定的值**SelectNodes**并**SelectSingleNode** XmlDocument 类公开的方法使用 XPathReader 类的实例下面的代码示例中所示 Microsoft.BizTalk.XPathReader.dll 程序集提供。</span><span class="sxs-lookup"><span data-stu-id="1febc-152">If specific values need to be pulled from an XML document, instead of using the **SelectNodes** and **SelectSingleNode** methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1febc-153">对于较小的消息尤其是，使用 XmlDocument 和 SelectNodes 或 SelectSingleNode 可能提供更好的性能比使用 XPathReader，但 XPathReader 可以保留你的应用程序的平面内存配置文件。</span><span class="sxs-lookup"><span data-stu-id="1febc-153">For smaller messages especially, using an XmlDocument with SelectNodes or SelectSingleNode may provide better performance than using XPathReader, but XPathReader allows you to keep a flat memory profile for your application.</span></span>  
  
 <span data-ttu-id="1febc-154">此示例演示如何使用 XPathReader 和 XPathCollection 提取给定**IBaseMessage**从对象中的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="1febc-154">This example shows how to use the XPathReader and XPathCollection to extract a given **IBaseMessage** object from within a custom pipeline component.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage message)  
{  
    try  
    {  
        ...  
        IBaseMessageContext messageContext = message.Context;  
        if (string.IsNullOrEmpty(xPath) && string.IsNullOrEmpty(propertyValue))  
        {  
            throw new ArgumentException(...);  
        }  
        IBaseMessagePart bodyPart = message.BodyPart;  
        Stream inboundStream = bodyPart.GetOriginalDataStream();  
        VirtualStream virtualStream = new VirtualStream(bufferSize, thresholdSize);  
        ReadOnlySeekableStream readOnlySeekableStream = new ReadOnlySeekableStream(inboundStream, virtualStream, bufferSize);  
        XmlTextReader xmlTextReader = new XmlTextReader(readOnlySeekableStream);  
        XPathCollection xPathCollection = new XPathCollection();  
        XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
        xPathCollection.Add(xPath);  
        bool ok = false;  
        while (xPathReader.ReadUntilMatch())  
        {  
            if (xPathReader.Match(0) && !ok)  
            {  
                propertyValue = xPathReader.ReadString();  
                messageContext.Promote(propertyName, propertyNamespace, propertyValue);  
                ok = true;  
            }  
        }  
        readOnlySeekableStream.Position = 0;  
        bodyPart.Data = readOnlySeekableStream;  
    }  
    catch (Exception ex)  
    {  
        if (message != null)  
        {  
            message.SetErrorInfo(ex);  
        }  
        ...  
        throw ex;  
    }  
    return message;  
}  
```  
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a><span data-ttu-id="1febc-155">将与 XMLTranslatorStream XMLReader 和 XMLWriter，以处理来自管道组件的消息</span><span class="sxs-lookup"><span data-stu-id="1febc-155">Use XMLReader and XMLWriter with XMLTranslatorStream to process a message from a pipeline component</span></span>  
 <span data-ttu-id="1febc-156">用于实现一个自定义管道组件，它使用流式处理方法的另一种方法是使用.NET **XmlReader**并**XmlWriter**类以及**XmlTranslatorStream**由 BizTalk Server 提供的类。</span><span class="sxs-lookup"><span data-stu-id="1febc-156">Another method for implementing a custom pipeline component which uses a streaming approach is to use the .NET **XmlReader** and **XmlWriter** classes in conjunction with the **XmlTranslatorStream** class provided by BizTalk Server.</span></span> <span data-ttu-id="1febc-157">例如， **NamespaceTranslatorStream** Microsoft.BizTalk.Pipeline.Components 程序集中包含的类继承自**XmlTranslatorStream**和可以用于替换旧的命名空间用新的流中包含的 XML 文档中。</span><span class="sxs-lookup"><span data-stu-id="1febc-157">For example, the **NamespaceTranslatorStream** class contained in the Microsoft.BizTalk.Pipeline.Components assembly inherits from **XmlTranslatorStream** and can be used to replace an old namespace with a new one in the XML document contained in the stream.</span></span> <span data-ttu-id="1febc-158">若要使用自定义管道组件内的此功能，可以包装的消息正文部分的新实例与原始数据流**NamespaceTranslatorStream**类，并返回后者。</span><span class="sxs-lookup"><span data-stu-id="1febc-158">In order to use this functionality inside a custom a pipeline component, you can wrap the original data stream of the message body part with a new instance of the **NamespaceTranslatorStream** class and return the latter.</span></span> <span data-ttu-id="1febc-159">以这种方式将入站的消息不是读取或处理在管道组件，但仅在流读取的相同管道中的后续组件或最后由消息代理之前将文档发布到 BizTalk Server 时MessageBox。</span><span class="sxs-lookup"><span data-stu-id="1febc-159">In this way the inbound message is not read or processed inside the pipeline component, but only when the stream is read by a subsequent component in the same pipeline or is finally consumed by the Message Agent before publishing the document to the BizTalk Server MessageBox.</span></span>  
  
 <span data-ttu-id="1febc-160">下面的示例演示如何使用此功能。</span><span class="sxs-lookup"><span data-stu-id="1febc-160">The following example illustrates how to use this functionality.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext context, IBaseMessage message)  
{  
   IBaseMessage outboundMessage = message;  
   try  
   {  
      if (context == null)  
      {  
         throw new ArgumentException(Resources.ContextIsNullMessage);  
      }  
      if (message == null)  
      {  
         throw new ArgumentException(Resources.InboundMessageIsNullMessage);  
      }  
  
      IBaseMessagePart bodyPart = message.BodyPart;  
      Stream stream = new NamespaceTranslatorStream(context,   
                                                    bodyPart.GetOriginalDataStream(),   
                                                    oldNamespace,   
                                                    newNamespace);  
      context.ResourceTracker.AddResource(stream);  
      bodyPart.Data = stream;  
   }  
   catch (Exception ex)  
   {  
      if (message != null)  
      {  
         message.SetErrorInfo(ex);  
      }  
  
      throw ex;  
   }  
   return outboundMessage;  
}  
```  
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a><span data-ttu-id="1febc-161">在自定义管道组件中使用 ResourceTracker</span><span class="sxs-lookup"><span data-stu-id="1febc-161">Using ResourceTracker in Custom Pipeline Components</span></span>  
 <span data-ttu-id="1febc-162">管道组件应管理所创建的对象的生存期和这些对象不再需要立即执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="1febc-162">A pipeline component should manage the lifetime of the objects it creates and perform garbage collection as soon as these objects are no longer required.</span></span>  <span data-ttu-id="1febc-163">如果管道组件想对象到最后一个管道执行结束前的生存期，则必须将此类对象添加到你的管道可能会从管道上下文中提取的资源跟踪器。</span><span class="sxs-lookup"><span data-stu-id="1febc-163">If the pipeline component wants the lifetime of the objects to last until the end of pipeline execution, then you must add such objects to the resource tracker that your pipeline may fetch from the pipeline context.</span></span>  
  
 <span data-ttu-id="1febc-164">资源跟踪器用于以下类型的对象：</span><span class="sxs-lookup"><span data-stu-id="1febc-164">The resource tracker is used for the following types of objects:</span></span>  
  
- <span data-ttu-id="1febc-165">Stream 对象</span><span class="sxs-lookup"><span data-stu-id="1febc-165">Stream objects</span></span>  
  
- <span data-ttu-id="1febc-166">COM 对象</span><span class="sxs-lookup"><span data-stu-id="1febc-166">COM objects</span></span>  
  
- <span data-ttu-id="1febc-167">IDisposable 对象</span><span class="sxs-lookup"><span data-stu-id="1febc-167">IDisposable objects</span></span>  
  
  <span data-ttu-id="1febc-168">消息引擎可确保在适当的时间，即完全执行管道，无论是成功还是失败后将发布添加到的资源跟踪器的所有本机资源。</span><span class="sxs-lookup"><span data-stu-id="1febc-168">The message engine ensures that all the native resources that are added to the resource tracker are released at an appropriate time, that is after the pipeline is completely executed, regardless of whether it was successful or failed.</span></span> <span data-ttu-id="1febc-169">管道上下文对象由管理的资源跟踪器实例和它正在跟踪的对象的生存期。</span><span class="sxs-lookup"><span data-stu-id="1febc-169">The lifetime of the Resource Tracker instance and the objects that it is tracking is managed by the pipeline context object.</span></span> <span data-ttu-id="1febc-170">管道上下文对所有类型的实现 IPipelineContext 接口的对象通过管道组件都可用。</span><span class="sxs-lookup"><span data-stu-id="1febc-170">The pipeline context is made available to all types of pipeline components through an object that implements the IPipelineContext interface.</span></span>  
  
  <span data-ttu-id="1febc-171">例如，下面的代码段是一个示例，说明了如何在自定义管道组件中使用 ResourceTracker 属性。</span><span class="sxs-lookup"><span data-stu-id="1febc-171">For example, the following code snippet is a sample that illustrates how to use ResourceTracker property in custom pipeline components.</span></span> <span data-ttu-id="1febc-172">若要使用 ResourceTracker 属性，则代码片段将使用以下参数`IPipelineContext.ResourceTracker.AddResource`。</span><span class="sxs-lookup"><span data-stu-id="1febc-172">To use ResourceTracker property, the code snippet uses the following parameter `IPipelineContext.ResourceTracker.AddResource`.</span></span> <span data-ttu-id="1febc-173">在此参数：</span><span class="sxs-lookup"><span data-stu-id="1febc-173">In this parameter:</span></span>  
  
- <span data-ttu-id="1febc-174">IPipelineContext 接口定义用于访问所有文档处理特定于接口的方法。</span><span class="sxs-lookup"><span data-stu-id="1febc-174">IPipelineContext interface defines the methods used to access all document processing-specific interfaces.</span></span>  
  
- <span data-ttu-id="1febc-175">ResourceTracker 属性引用 IPipelineContext，用于跟踪的管道处理结束时将显式释放的对象。</span><span class="sxs-lookup"><span data-stu-id="1febc-175">ResourceTracker property references IPipelineContext and is used to keep track of objects that will be explicitly disposed at the end of pipeline processing.</span></span>  
  
- <span data-ttu-id="1febc-176">ResourceTracker.AddResource 方法用于跟踪的 COM 对象、 可释放的对象和流，并应始终使用自定义管道组件内显式关闭 （流）、 释放 （IDisposable 对象） 或这些释放 （COM 对象）类型的资源在一条消息发布到 BizTalk MessageBox。</span><span class="sxs-lookup"><span data-stu-id="1febc-176">ResourceTracker.AddResource method is used to keep track of COM objects, Disposable objects and Streams, and should always be used inside a custom pipeline component to explicitly close (streams), dispose (IDisposable objects) or release (COM objects) these types of resources when a message is published to the BizTalk MessageBox.</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
  
{  
      IBaseMessage outMessage = pContext.GetMessageFactory().CreateMessage();  
  
      IBaseMessagePart outMsgBodyPart = pContext.GetMessageFactory().CreateMessagePart();  
  
      outMsgBodyPart.Charset = Encoding.UTF8.WebName;   
  
      outMsgBodyPart.ContentType = "text/xml";  
  
//Code to load message content in the MemoryStream object//  
  
      MemoryStream messageData = new MemoryStream();  
  
   //The MemoryStream needs to be closed after the whole pipeline has executed, thus adding it into ResourceTracker//  
  
      pContext.ResourceTracker.AddResource(messageData);  
  
//Custom pipeline code to load message data into xmlPayload//  
  
      XmlDocument xmlPayLoad = new XmlDocument();  
  
      xmlPayLoad.Save(messageData);  
  
      messageData.Seek(0, SeekOrigin.Begin);  
  
//The new stream is assigned to the message part’s data//  
  
      outMsgBodyPart.Data = messageData;  
  
// Pipeline component logic here//  
  
      return outMessage;  
  
}  
```  
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a><span data-ttu-id="1febc-177">正在加载消息到管道中使用内存中的方法，并使用流式处理方法的比较</span><span class="sxs-lookup"><span data-stu-id="1febc-177">Comparison of loading messages into pipelines using an in-memory approach and using a streaming approach</span></span>  
 <span data-ttu-id="1febc-178">以下信息摘自 Nic Barden 博客[ http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx ](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228)。</span><span class="sxs-lookup"><span data-stu-id="1febc-178">The following information was taken from Nic Barden’s blog, [http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228).</span></span> <span data-ttu-id="1febc-179">此表提供到管道中使用内存中的方法，并使用流式处理方法加载消息的汇总的比较。</span><span class="sxs-lookup"><span data-stu-id="1febc-179">This table provides a summarized comparison of loading messages into pipelines using an in-memory approach and using a streaming approach.</span></span>  
  
|<span data-ttu-id="1febc-180">比较...</span><span class="sxs-lookup"><span data-stu-id="1febc-180">Comparison of...</span></span>|<span data-ttu-id="1febc-181">流式处理</span><span class="sxs-lookup"><span data-stu-id="1febc-181">Streaming</span></span>|<span data-ttu-id="1febc-182">在内存中</span><span class="sxs-lookup"><span data-stu-id="1febc-182">In memory</span></span>|  
|----------------------|---------------|---------------|  
|<span data-ttu-id="1febc-183">每个消息的内存使用情况</span><span class="sxs-lookup"><span data-stu-id="1febc-183">Memory usage per message</span></span>|<span data-ttu-id="1febc-184">低，而不考虑消息大小</span><span class="sxs-lookup"><span data-stu-id="1febc-184">Low, regardless of message size</span></span>|<span data-ttu-id="1febc-185">高 （消息大小而异）</span><span class="sxs-lookup"><span data-stu-id="1febc-185">High (varies depending on message size)</span></span>|  
|<span data-ttu-id="1febc-186">用于处理 XML 数据的通用类</span><span class="sxs-lookup"><span data-stu-id="1febc-186">Common classes used to process XML data</span></span>|<span data-ttu-id="1febc-187">生成和自定义派生的：</span><span class="sxs-lookup"><span data-stu-id="1febc-187">Built in and custom derivations of:</span></span><br /><br /> <span data-ttu-id="1febc-188">XmlTranslatorStream、 XmlReader 和 XmlWriter</span><span class="sxs-lookup"><span data-stu-id="1febc-188">XmlTranslatorStream, XmlReader and XmlWriter</span></span>|<span data-ttu-id="1febc-189">XmlDocument、 XPathDocument、 MemoryStream 和为 VirtualStream</span><span class="sxs-lookup"><span data-stu-id="1febc-189">XmlDocument, XPathDocument, MemoryStream and VirtualStream</span></span>|  
|<span data-ttu-id="1febc-190">文档</span><span class="sxs-lookup"><span data-stu-id="1febc-190">Documentation</span></span>|<span data-ttu-id="1febc-191">差 – 许多不受支持的和未有案可稽 BizTalk 类</span><span class="sxs-lookup"><span data-stu-id="1febc-191">Poor – many un-supported and un-documented BizTalk classes</span></span>|<span data-ttu-id="1febc-192">很好的.NET Framework 类</span><span class="sxs-lookup"><span data-stu-id="1febc-192">Very good - .NET Framework classes</span></span>|  
|<span data-ttu-id="1febc-193">"处理逻辑"代码的位置</span><span class="sxs-lookup"><span data-stu-id="1febc-193">Location of “Processing Logic” code</span></span>|<span data-ttu-id="1febc-194">-"绑定"读取器和流通过 Execute 方法。</span><span class="sxs-lookup"><span data-stu-id="1febc-194">-   “Wire up” readers and streams via Execute method.</span></span><br /><span data-ttu-id="1febc-195">-实际的执行发生在读取器和流中读取数据。</span><span class="sxs-lookup"><span data-stu-id="1febc-195">-   Actual execution occurs in the readers and streams as the data is read.</span></span>|<span data-ttu-id="1febc-196">直接从管道组件的 Execute 方法。</span><span class="sxs-lookup"><span data-stu-id="1febc-196">Directly from the Execute method of the pipeline component.</span></span>|  
|<span data-ttu-id="1febc-197">数据</span><span class="sxs-lookup"><span data-stu-id="1febc-197">Data</span></span>|<span data-ttu-id="1febc-198">重新创建在每个包装层，通过它读取数据。</span><span class="sxs-lookup"><span data-stu-id="1febc-198">Re-created at each wrapping layer as data is read through it.</span></span>|<span data-ttu-id="1febc-199">读取、 修改并写出在之前被调用的下一个组件的每个组件。</span><span class="sxs-lookup"><span data-stu-id="1febc-199">Read in, modified and written out at each component prior to next component being called.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1febc-200">请参阅</span><span class="sxs-lookup"><span data-stu-id="1febc-200">See Also</span></span>  
 [<span data-ttu-id="1febc-201">优化 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="1febc-201">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)