---
title: 优化流式处理的内存使用量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8ba8820-65b4-4161-9f7a-3ae3d39e3d11
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c86fafdab538dcf60f52265e10711b1a43340a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024147"
---
# <a name="optimizing-memory-usage-with-streaming"></a><span data-ttu-id="12a11-102">通过流式处理优化内存使用情况</span><span class="sxs-lookup"><span data-stu-id="12a11-102">Optimizing Memory Usage with Streaming</span></span>
<span data-ttu-id="12a11-103">本主题提供有关使用流模式来尽量减少消息内存占用时发送或接收大型消息与 WCF 传输或加载业务流程中的消息时的建议。</span><span class="sxs-lookup"><span data-stu-id="12a11-103">This topic provides recommendations for using streaming patterns to minimize message memory footprints when sending or receiving large messages with a WCF transport or when loading messages in orchestrations.</span></span>   
<span data-ttu-id="12a11-104">当在业务流程中使用代码以读取消息的内容，应避免使用 XmlDocument 变量。</span><span class="sxs-lookup"><span data-stu-id="12a11-104">When using code in an orchestration to read the contents of a message, avoid using XmlDocument variables.</span></span> <span data-ttu-id="12a11-105">加载到 XmlDocument 变量的一条消息会产生很大的开销，尤其是对于大型消息。</span><span class="sxs-lookup"><span data-stu-id="12a11-105">Loading a message into an XmlDocument variable incurs significant overhead, especially for large messages.</span></span> <span data-ttu-id="12a11-106">内存使用情况和处理，以生成内存中结构方面是这种开销。</span><span class="sxs-lookup"><span data-stu-id="12a11-106">This overhead is in terms of memory usage and processing to build the in-memory structures.</span></span> <span data-ttu-id="12a11-107">使用 XmlDocument 实例强制整个消息内容必须加载到内存，才能生成的文档对象模块 (DOM) 的对象图。</span><span class="sxs-lookup"><span data-stu-id="12a11-107">The use of an XmlDocument instance forces the entire message contents to be loaded into memory in order to build the object graph for the Document Object Module (DOM).</span></span> <span data-ttu-id="12a11-108">此类的实例所使用总量可以是内存的实际的消息大小的大约 10 倍。</span><span class="sxs-lookup"><span data-stu-id="12a11-108">The total amount of memory used by an instance of this class can be around 10 times the actual message size.</span></span> <span data-ttu-id="12a11-109">有关在加载到 XmlDocument 变量的一条消息时所需的内存占用量的详细信息，请参阅[第 9 章-提高 XML 性能](http://go.microsoft.com/fwlink/?LinkId=139772)(http://go.microsoft.com/fwlink/?LinkId=139772) MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="12a11-109">For more information about the memory footprint required when loading a message into an XmlDocument variable, see [Chapter 9 – Improving XML Performance](http://go.microsoft.com/fwlink/?LinkId=139772) (http://go.microsoft.com/fwlink/?LinkId=139772) on MSDN.</span></span>   
<span data-ttu-id="12a11-110">此主题的其余部分提供了用于读取消息内容不需要加载到 XmlDocument 变量的一条消息的替代方法。</span><span class="sxs-lookup"><span data-stu-id="12a11-110">The remainder of this topic provides alternative methods for reading message contents that do not require loading a message into an XmlDocument variable.</span></span>  
  
## <a name="use-streaming-when-sending-or-receiving-large-messages-with-a-wcf-transport"></a><span data-ttu-id="12a11-111">使用流式处理发送或接收 WCF 传输的大型消息时</span><span class="sxs-lookup"><span data-stu-id="12a11-111">Use streaming when sending or receiving large messages with a WCF transport</span></span>  
 <span data-ttu-id="12a11-112">发送或接收 WCF 传输的大型消息时, 使用 Wcf-custom 或 Wcf-customisolated 适配器，并使用支持的绑定类型配置**transferMode = Streamed**选项，例如，以下绑定：</span><span class="sxs-lookup"><span data-stu-id="12a11-112">When sending or receiving large messages with a WCF transport, use the WCF-Custom or WCF-CustomIsolated adapter and configure with a binding type that supports the **transferMode = Streamed** option, such as the following bindings:</span></span>  
  
- <span data-ttu-id="12a11-113">**basicHttpBinding + BasicHttpBindingElement，transferMode = Streamed**</span><span class="sxs-lookup"><span data-stu-id="12a11-113">**basicHttpBinding + BasicHttpBindingElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="12a11-114">**netTcpBinding + NetTcpBindingElement，transferMode = Streamed**</span><span class="sxs-lookup"><span data-stu-id="12a11-114">**netTcpBinding + NetTcpBindingElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="12a11-115">**customBinding + HttpTransportElement，transferMode = Streamed**</span><span class="sxs-lookup"><span data-stu-id="12a11-115">**customBinding + HttpTransportElement, transferMode = Streamed**</span></span>  
  
- <span data-ttu-id="12a11-116">**customBinding + ConnectionOrientedTransportElement，transferMode = Streamed**</span><span class="sxs-lookup"><span data-stu-id="12a11-116">**customBinding +ConnectionOrientedTransportElement, transferMode = Streamed**</span></span>  
  
  <span data-ttu-id="12a11-117">选择以及支持的绑定的 Wcf-custom 或 Wcf-customisolated 适配器**transferMode = Streamed**选项将实现流式处理到文件系统的大消息，根据需要并将缓解潜在内存不足问题。</span><span class="sxs-lookup"><span data-stu-id="12a11-117">Choosing a WCF-Custom or WCF-CustomIsolated adapter along with a binding that supports the **transferMode = Streamed** option will implement streaming of large messages to the file system as needed, and will mitigate potential out-of-memory issues.</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-orchestrations"></a><span data-ttu-id="12a11-118">使用流式处理时加载业务流程中的消息所需的内存占用量降至最低</span><span class="sxs-lookup"><span data-stu-id="12a11-118">Use streaming to minimize the memory footprint required when loading messages in orchestrations</span></span>  
 <span data-ttu-id="12a11-119">以下技术描述如何将消息加载到业务流程时，消息的内存占用量降至最低。</span><span class="sxs-lookup"><span data-stu-id="12a11-119">The following techniques describe how to minimize the memory footprint of a message when loading the message into an orchestration.</span></span>  
  
### <a name="use-an-xlangmessage-variable-to-process-the-contents-of-a-message-or-message-part"></a><span data-ttu-id="12a11-120">使用 XLANGMessage 变量来处理消息或消息部分的内容</span><span class="sxs-lookup"><span data-stu-id="12a11-120">Use an XLANGMessage variable to process the contents of a message or message part</span></span>  
 <span data-ttu-id="12a11-121">当将一条消息从业务流程传递给.NET 类库，不将它们作为传递 XmlDocument 变量，此主题; 前面提到的原因改为使用 XLANGMessage 变量。</span><span class="sxs-lookup"><span data-stu-id="12a11-121">When passing a message from an orchestration to .NET class libraries, do not pass them as XmlDocument variables, for reasons mentioned earlier in this topic; use XLANGMessage variables instead.</span></span> <span data-ttu-id="12a11-122">以下方法演示了用于读取消息或消息部分使用 XLANGMessage 变量的方法。</span><span class="sxs-lookup"><span data-stu-id="12a11-122">The following techniques illustrate methods for reading a message or message part using an XLANGMessage variable.</span></span>  
  
-   <span data-ttu-id="12a11-123">**处理消息使用 XMLReader** -若要将处理与 XmlReader 实例消息，将消息传递给.NET 代码作为 XLANGMessage，并检索使用 XmlReader 的部分内容。</span><span class="sxs-lookup"><span data-stu-id="12a11-123">**Process messages with XMLReader** - To process a message with an XmlReader instance, pass the message to .NET code as an XLANGMessage, and retrieve the Part content using XmlReader.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
        {  
            using (XmlReader reader = message[0].RetrieveAs(typeof(XmlReader)) as XmlReader)  
            if (reader != null)  
            {  
                ...  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
    }  
    ```  
  
-   <span data-ttu-id="12a11-124">**检索消息的内容转换为字符串使用 StreamReader** -XmlDocument 的业务流程中的常见用途之一是作为 XML 字符串使用 XmlDocument.OuterXml() 检索消息。</span><span class="sxs-lookup"><span data-stu-id="12a11-124">**Retrieve the contents of a message into a string with StreamReader** - One of the common uses of XmlDocument in orchestrations is to retrieve the message as an XML string using XmlDocument.OuterXml().</span></span> <span data-ttu-id="12a11-125">下面的代码示例说明了一种替代方法，该字符串使用 XLANGMessage 变量中检索消息。</span><span class="sxs-lookup"><span data-stu-id="12a11-125">The following code example illustrates an alternative method which retrieves the message as a string using an XLANGMessage variable.</span></span>  
  
    ```  
    public static string MessageToString(XLANGMessage message)  
    {  
        string strResults;  
        try  
        {  
            using (Stream stream = message[0].RetrieveAs(typeof(Stream)) as Stream)  
            {  
                using (StreamReader reader = new StreamReader(stream))  
                {  
                    strResults = reader.ReadToEnd();  
                }  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
        return strResults;  
    }  
    ```  
  
-   <span data-ttu-id="12a11-126">**检索的简单.NET 消息内容转换为字符串**-如果消息类型是简单的.NET 类型，则可以检索与该类型的消息。</span><span class="sxs-lookup"><span data-stu-id="12a11-126">**Retrieve the contents of simple .NET messages into a string** - If the type of the message is a simple .NET type, you can retrieve the message as that type.</span></span> <span data-ttu-id="12a11-127">例如，若要获取字符串形式的消息，将消息传递到作为 XLANGMessage 的.NET 代码和检索字符串形式的一部分内容。</span><span class="sxs-lookup"><span data-stu-id="12a11-127">For example, to get the message as a string, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as a string.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
        {  
            string content = message[0].RetrieveAs(typeof(string)) as string;  
            if (!string.IsNullOrEmpty(content))  
            {  
                ...  
            }  
        }  
        finally  
        {  
            message.Dispose();  
        }  
    }  
    ```  
  
-   <span data-ttu-id="12a11-128">**检索消息的内容到流**-若要将获取以流的形式的消息、 将消息传递到作为 XLANGMessage 的.NET 代码和检索部分内容流的形式。</span><span class="sxs-lookup"><span data-stu-id="12a11-128">**Retrieve the contents of a message into a stream** - To get the message as a stream, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as a stream.</span></span>  
  
    ```  
    public Stream ProcessRequestReturnStream(XLANGMessage message, int bufferSize, int thresholdSize)  
    {  
       ...  
       try  
       {  
          using (VirtualStream virtualStream = new VirtualStream(bufferSize, thresholdSize))  
          {  
             using (Stream partStream = (Stream)message[0].RetrieveAs(typeof(Stream)))  
             //Note that when calling this code, if the XmlDocument is quite large, keeping it in a memory with a MemoryStream may have an adverse effect on performance.   
             //In this case, it may be worthwhile to consider an approach that uses a VirtualStream + ReadonlySeekableStream to buffer it to the file system, if its size is bigger than the thresholdSize parameter.  
             //Keep in mind that:  
             // - If the message size is smaller than the threshold size, the VirtualStream class buffers the stream to a MemoryStream.  
             // - If the message size is bigger than the threshold size, the VirtualStream class buffers the stream to a temporary file.  
                using (ReadOnlySeekableStream readOnlySeekableStream = new ReadOnlySeekableStream(partStream, virtualStream, bufferSize))  
                {  
                   using (XmlReader reader = XmlReader.Create(readOnlySeekableStream))  
                   {  
  
                   }  
                }  
             }  
          }  
       }  
       catch (Exception ex)  
       {  
  
       }  
       finally  
       {  
          message.Dispose();  
       }  
       return stream;  
    }  
    ```  
  
-   <span data-ttu-id="12a11-129">**检索消息的内容转换为.NET 对象**-要获取.NET 对象形式的消息、 将消息传递到作为 XLANGMessage 的.NET 代码和作为.NET 类的实例中检索的部分内容。</span><span class="sxs-lookup"><span data-stu-id="12a11-129">**Retrieve the contents of a message into a .NET object** - To get the message as a .NET object, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as an instance of a .NET class.</span></span> <span data-ttu-id="12a11-130">创建这后一种从使用 Visual Studio 2010 提供的 XML 架构定义工具 (Xsd.exe) 工具的消息的 Xml 架构。</span><span class="sxs-lookup"><span data-stu-id="12a11-130">Create this latter from the Xml Schema of the message using the XML Schema Definition Tool (Xsd.exe) tool provided by Visual Studio 2010.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="12a11-131">仅当消息很小，这种方法才有效。</span><span class="sxs-lookup"><span data-stu-id="12a11-131">This technique is valid only when messages are small.</span></span> <span data-ttu-id="12a11-132">否则，此方法可能会造成很大的开销要转换为.NET 对象反序列化的实际消息中。</span><span class="sxs-lookup"><span data-stu-id="12a11-132">Otherwise, this approach could incur in a significant overhead to de-serialize the actual message into a .NET object.</span></span>  
  
    ```  
    public void ProcessMessage(XLANGMessage message)  
    {  
        try  
          {  
          Request request = message[0].RetrieveAs(typeof(Request)) as Request;  
          if (request != null)  
          {  
             ...  
          }  
       }  
       finally  
       {  
          message.Dispose();  
       }  
  
    }  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="12a11-133">利用**dispose （)** 从.NET 代码返回之前由 XLANGMessage 参数公开的方法是尤为重要，在循环方案和长时间运行的业务流程会累积的实例无需释放它们随着时间的推移 XLANGMessage 对象。</span><span class="sxs-lookup"><span data-stu-id="12a11-133">Use of the **Dispose()** method exposed by the XLANGMessage parameter before returning from the .NET code is particularly important in looping scenarios and long-running orchestrations that can accumulate instances of the XLANGMessage object without releasing them over time.</span></span> <span data-ttu-id="12a11-134">有关调用消息的详细信息。Dispose （） 以这种方式，请参阅[消息表示为 XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) BizTalk Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="12a11-134">For more information about calling message.Dispose() in this manner, see [Messages Represented as XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) in the BizTalk Server documentation.</span></span> <span data-ttu-id="12a11-135">本主题还提供了使用 IStreamFactory 构造 XLANGMessage 变量在用户代码中使用的基于流的方法的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="12a11-135">This topic also provides best practices for using IStreamFactory to construct XLANGMessage variables in user code using a stream-based approach.</span></span>  
  
 <span data-ttu-id="12a11-136">有关不同的方式来处理 XLANGMessage 中由业务流程调用一个帮助程序组件的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="12a11-136">For more information about the different ways to process an XLANGMessage within an helper component invoked by an orchestration, see the following topics:</span></span>  
  
-   <span data-ttu-id="12a11-137">[4 种不同的方法来处理中的第 1 部分业务流程的帮助器组件 XLANGMessage](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420)。</span><span class="sxs-lookup"><span data-stu-id="12a11-137">[4 Different ways to process an XLANGMessage within an helper component invoked by an orchestration Part 1](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420).</span></span>  
  
-   <span data-ttu-id="12a11-138">[4 种不同的方法来处理中的第 2 部分业务流程的帮助器组件 XLANGMessage](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421)。</span><span class="sxs-lookup"><span data-stu-id="12a11-138">[4 Different ways to process an XLANGMessage within an helper component invoked by an orchestration Part 2](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-value-from-an-xlangmessage-object-from-a-method-invoked-by-an-orchestration"></a><span data-ttu-id="12a11-139">使用 XPathReader 和 XPathCollection 从 XLANGMessage 对象从方法调用的业务流程中提取值</span><span class="sxs-lookup"><span data-stu-id="12a11-139">Using XPathReader and XPathCollection to extract a value from an XLANGMessage object from a method invoked by an orchestration</span></span>  
 <span data-ttu-id="12a11-140">避免使用 XMLDocument 类读取 XML 消息的内容从自定义代码，如自定义管道组件或业务流程调用的帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="12a11-140">Avoid using the XMLDocument class to read the contents of XML messages from custom code, such as custom pipeline components or helper classes invoked by orchestrations.</span></span> <span data-ttu-id="12a11-141">当使用 XMLDocument 实例来加载 XML 消息，则会将整个消息加载到内存中，这会导致效率低下，可能需要最多 10 次的消息的实际大小的内存。</span><span class="sxs-lookup"><span data-stu-id="12a11-141">When using an XMLDocument instance to load an XML message, the entire message is loaded into memory, which is inefficient and may require memory up to 10 times the actual size of the message.</span></span> <span data-ttu-id="12a11-142">读取的 XML 消息内容的更高效的方法是使用流处理技术来包装原始流与 Microsoft.BizTalk.Streaming.dll 程序集提供的流类之一。</span><span class="sxs-lookup"><span data-stu-id="12a11-142">A more efficient way of reading the contents of XML messages is to use a streaming technique to wrap the original stream with one of the stream classes provided by the Microsoft.BizTalk.Streaming.dll assembly.</span></span> <span data-ttu-id="12a11-143">加载大型消息时，此方法会特别有用。</span><span class="sxs-lookup"><span data-stu-id="12a11-143">This technique is particularly useful when loading large messages.</span></span>  
  
 <span data-ttu-id="12a11-144">如果需要从 XML 文档，而不是使用由 XmlDocument 类公开的 SelectNodes 和 SelectSingleNode 方法请求特定值使用提供的 Microsoft.BizTalk.XPathReader.dll 程序集的 XPathReader 类的实例下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="12a11-144">If specific values need to be pulled from an XML document, instead of using the SelectNodes and SelectSingleNode methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
-   <span data-ttu-id="12a11-145">此示例演示如何使用 XPathReader 和 XPathCollection 从 XLANGMessage 对象在方法中调用的业务流程提取给定的值。</span><span class="sxs-lookup"><span data-stu-id="12a11-145">This example illustrates using the XPathReader and XPathCollection to extract a given value from an XLANGMessage object inside a method invoked by an orchestration.</span></span>  
  
    ```  
    public static string SelectSingleNode(XLANGMessage message, string xPath)   
    {  
        try  
        {  
            if (message == null || string.IsNullOrEmpty(xPath))  
            {  
                return string.Empty;  
            }  
            using (XmlReader reader = (XmlReader)message[0].RetrieveAs(typeof(XmlReader)))  
            {  
                XPathCollection xPathCollection = new XPathCollection();  
                XPathReader xPathReader = new XPathReader(reader, xPathCollection);  
                xPathCollection.Add(xPath);  
                while (xPathReader.ReadUntilMatch())  
                {  
                    if (xPathReader.Match(0))  
                    {  
                        return xPathReader.ReadString();  
                    }  
                }  
            }  
        }  
        catch (Exception ex)  
        {  
            ...  
        }  
        finally  
        {  
            message.Dispose();  
        }  
        return string.Empty;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="12a11-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="12a11-146">See Also</span></span>  
 [<span data-ttu-id="12a11-147">优化 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="12a11-147">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)