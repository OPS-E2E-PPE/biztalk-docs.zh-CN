---
title: 优化流式处理的内存使用情况 |Microsoft 文档
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
ms.openlocfilehash: 0e1707007eab19a86e4fabedfe9e16bfa9c8fc59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299341"
---
# <a name="optimizing-memory-usage-with-streaming"></a><span data-ttu-id="016e3-102">优化流式处理的内存使用情况</span><span class="sxs-lookup"><span data-stu-id="016e3-102">Optimizing Memory Usage with Streaming</span></span>
<span data-ttu-id="016e3-103">本主题提供使用流式处理模式以最大程度减少消息内存空间占用量时发送或接收大消息的 WCF 传输或加载在业务流程中的消息时的建议。</span><span class="sxs-lookup"><span data-stu-id="016e3-103">This topic provides recommendations for using streaming patterns to minimize message memory footprints when sending or receiving large messages with a WCF transport or when loading messages in orchestrations.</span></span>   
<span data-ttu-id="016e3-104">当在业务流程中使用代码以读取一条消息的内容，避免使用 XmlDocument 变量。</span><span class="sxs-lookup"><span data-stu-id="016e3-104">When using code in an orchestration to read the contents of a message, avoid using XmlDocument variables.</span></span> <span data-ttu-id="016e3-105">加载到一个 XmlDocument 变量的一条消息会产生很大的开销，尤其是对于大型消息。</span><span class="sxs-lookup"><span data-stu-id="016e3-105">Loading a message into an XmlDocument variable incurs significant overhead, especially for large messages.</span></span> <span data-ttu-id="016e3-106">在内存使用量和处理，以生成内存中结构方面是这种开销。</span><span class="sxs-lookup"><span data-stu-id="016e3-106">This overhead is in terms of memory usage and processing to build the in-memory structures.</span></span> <span data-ttu-id="016e3-107">使用 XmlDocument 实例强制要以生成对象图的文档对象模块 (DOM) 加载到内存的整个消息内容。</span><span class="sxs-lookup"><span data-stu-id="016e3-107">The use of an XmlDocument instance forces the entire message contents to be loaded into memory in order to build the object graph for the Document Object Module (DOM).</span></span> <span data-ttu-id="016e3-108">此类的实例使用总量可以是内存的实际的消息大小的大约 10 倍。</span><span class="sxs-lookup"><span data-stu-id="016e3-108">The total amount of memory used by an instance of this class can be around 10 times the actual message size.</span></span> <span data-ttu-id="016e3-109">有关在加载到一个 XmlDocument 变量的一条消息时所需的内存需求量的详细信息，请参阅[章 9 – 提高 XML 性能](http://go.microsoft.com/fwlink/?LinkId=139772)(http://go.microsoft.com/fwlink/?LinkId=139772) MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="016e3-109">For more information about the memory footprint required when loading a message into an XmlDocument variable, see [Chapter 9 – Improving XML Performance](http://go.microsoft.com/fwlink/?LinkId=139772) (http://go.microsoft.com/fwlink/?LinkId=139772) on MSDN.</span></span>   
<span data-ttu-id="016e3-110">本主题的其余部分提供用于读取不需要加载到一个 XmlDocument 变量的一条消息的消息内容替代方法。</span><span class="sxs-lookup"><span data-stu-id="016e3-110">The remainder of this topic provides alternative methods for reading message contents that do not require loading a message into an XmlDocument variable.</span></span>  
  
## <a name="use-streaming-when-sending-or-receiving-large-messages-with-a-wcf-transport"></a><span data-ttu-id="016e3-111">使用流式处理时发送或接收的 WCF 传输大型消息</span><span class="sxs-lookup"><span data-stu-id="016e3-111">Use streaming when sending or receiving large messages with a WCF transport</span></span>  
 <span data-ttu-id="016e3-112">当发送或接收与 WCF 传输大型消息时，使用 WCF 自定义或 WCF CustomIsolated 适配器使用和配置支持的绑定类型**传输模式 = Streamed**选项，例如，下列绑定：</span><span class="sxs-lookup"><span data-stu-id="016e3-112">When sending or receiving large messages with a WCF transport, use the WCF-Custom or WCF-CustomIsolated adapter and configure with a binding type that supports the **transferMode = Streamed** option, such as the following bindings:</span></span>  
  
-   <span data-ttu-id="016e3-113">**basicHttpBinding + BasicHttpBindingElement，传输模式 = Streamed**</span><span class="sxs-lookup"><span data-stu-id="016e3-113">**basicHttpBinding + BasicHttpBindingElement, transferMode = Streamed**</span></span>  
  
-   <span data-ttu-id="016e3-114">**netTcpBinding + NetTcpBindingElement，传输模式 = Streamed**</span><span class="sxs-lookup"><span data-stu-id="016e3-114">**netTcpBinding + NetTcpBindingElement, transferMode = Streamed**</span></span>  
  
-   <span data-ttu-id="016e3-115">**customBinding + HttpTransportElement，传输模式 = Streamed**</span><span class="sxs-lookup"><span data-stu-id="016e3-115">**customBinding + HttpTransportElement, transferMode = Streamed**</span></span>  
  
-   <span data-ttu-id="016e3-116">**customBinding + ConnectionOrientedTransportElement，传输模式 = Streamed**</span><span class="sxs-lookup"><span data-stu-id="016e3-116">**customBinding +ConnectionOrientedTransportElement, transferMode = Streamed**</span></span>  
  
 <span data-ttu-id="016e3-117">选择以及支持的绑定的 WCF 自定义或 WCF CustomIsolated 适配器**传输模式 = Streamed**选项将实现流式传输到文件系统的大消息根据需要并将缓解潜在内存不足问题。</span><span class="sxs-lookup"><span data-stu-id="016e3-117">Choosing a WCF-Custom or WCF-CustomIsolated adapter along with a binding that supports the **transferMode = Streamed** option will implement streaming of large messages to the file system as needed, and will mitigate potential out-of-memory issues.</span></span>  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-orchestrations"></a><span data-ttu-id="016e3-118">使用流式处理程度地减少在加载在业务流程中的消息时所需的内存需求量</span><span class="sxs-lookup"><span data-stu-id="016e3-118">Use streaming to minimize the memory footprint required when loading messages in orchestrations</span></span>  
 <span data-ttu-id="016e3-119">下面的方法介绍如何加载到业务流程的消息时最大程度减少一条消息的内存需求量。</span><span class="sxs-lookup"><span data-stu-id="016e3-119">The following techniques describe how to minimize the memory footprint of a message when loading the message into an orchestration.</span></span>  
  
### <a name="use-an-xlangmessage-variable-to-process-the-contents-of-a-message-or-message-part"></a><span data-ttu-id="016e3-120">用 XLANGMessage 变量来处理消息或消息部分的内容</span><span class="sxs-lookup"><span data-stu-id="016e3-120">Use an XLANGMessage variable to process the contents of a message or message part</span></span>  
 <span data-ttu-id="016e3-121">当将从业务流程的一条消息传递给.NET 类库中，不将它们作为传递 XmlDocument 变量，本主题中; 前面所述的原因请改用 XLANGMessage 变量。</span><span class="sxs-lookup"><span data-stu-id="016e3-121">When passing a message from an orchestration to .NET class libraries, do not pass them as XmlDocument variables, for reasons mentioned earlier in this topic; use XLANGMessage variables instead.</span></span> <span data-ttu-id="016e3-122">以下技术说明了读取的消息或消息部分使用 XLANGMessage 变量的方法。</span><span class="sxs-lookup"><span data-stu-id="016e3-122">The following techniques illustrate methods for reading a message or message part using an XLANGMessage variable.</span></span>  
  
-   <span data-ttu-id="016e3-123">**处理消息 XMLReader** -若要将处理与 XmlReader 实例消息、 将消息传递给为 XLANGMessage 的.NET 代码和检索使用 XmlReader 部分内容。</span><span class="sxs-lookup"><span data-stu-id="016e3-123">**Process messages with XMLReader** - To process a message with an XmlReader instance, pass the message to .NET code as an XLANGMessage, and retrieve the Part content using XmlReader.</span></span>  
  
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
  
-   <span data-ttu-id="016e3-124">**检索消息的内容读入一个字符串与 StreamReader** -XmlDocument 在业务流程中的常见用途之一是以 XML 字符串使用 XmlDocument.OuterXml() 检索消息。</span><span class="sxs-lookup"><span data-stu-id="016e3-124">**Retrieve the contents of a message into a string with StreamReader** - One of the common uses of XmlDocument in orchestrations is to retrieve the message as an XML string using XmlDocument.OuterXml().</span></span> <span data-ttu-id="016e3-125">下面的代码示例演示了一种替代方法，该字符串使用 XLANGMessage 变量中检索消息。</span><span class="sxs-lookup"><span data-stu-id="016e3-125">The following code example illustrates an alternative method which retrieves the message as a string using an XLANGMessage variable.</span></span>  
  
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
  
-   <span data-ttu-id="016e3-126">**转换为字符串检索的简单.NET 消息的内容**-如果消息的类型是简单的.NET 类型，则可以检索为该类型的消息。</span><span class="sxs-lookup"><span data-stu-id="016e3-126">**Retrieve the contents of simple .NET messages into a string** - If the type of the message is a simple .NET type, you can retrieve the message as that type.</span></span> <span data-ttu-id="016e3-127">例如，若要获取字符串形式的消息，将消息传递给 XLANGMessage 的.NET 代码，并检索一部分内容作为字符串。</span><span class="sxs-lookup"><span data-stu-id="016e3-127">For example, to get the message as a string, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as a string.</span></span>  
  
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
  
-   <span data-ttu-id="016e3-128">**检索到流的消息的内容**-若要将获取以流的形式的消息、 将消息传递给 XLANGMessage 的.NET 代码和检索作为流的一部分内容。</span><span class="sxs-lookup"><span data-stu-id="016e3-128">**Retrieve the contents of a message into a stream** - To get the message as a stream, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as a stream.</span></span>  
  
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
  
-   <span data-ttu-id="016e3-129">**检索消息的内容转换为.NET 对象**-若要将获取将消息作为.NET 对象，将消息传递给 XLANGMessage 的.NET 代码并作为一个.NET 类的实例检索部分内容。</span><span class="sxs-lookup"><span data-stu-id="016e3-129">**Retrieve the contents of a message into a .NET object** - To get the message as a .NET object, pass the message to the .NET code as an XLANGMessage and retrieve the Part content as an instance of a .NET class.</span></span> <span data-ttu-id="016e3-130">创建此后者从使用 Visual Studio 2010 提供的 XML 架构定义工具 (Xsd.exe) 工具的消息的 Xml 架构。</span><span class="sxs-lookup"><span data-stu-id="016e3-130">Create this latter from the Xml Schema of the message using the XML Schema Definition Tool (Xsd.exe) tool provided by Visual Studio 2010.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="016e3-131">只有在小消息时，此方法相当有效。</span><span class="sxs-lookup"><span data-stu-id="016e3-131">This technique is valid only when messages are small.</span></span> <span data-ttu-id="016e3-132">否则，此方法可能会导致在很大的开销来反序列化为.NET 对象的实际的消息。</span><span class="sxs-lookup"><span data-stu-id="016e3-132">Otherwise, this approach could incur in a significant overhead to de-serialize the actual message into a .NET object.</span></span>  
  
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
>  <span data-ttu-id="016e3-133">利用**dispose （)** 从.NET 代码返回前由 XLANGMessage 参数公开的方法是特别重要循环方案和长时间运行业务流程可以累积的实例而不释放它们随着时间的推移 XLANGMessage 对象。</span><span class="sxs-lookup"><span data-stu-id="016e3-133">Use of the **Dispose()** method exposed by the XLANGMessage parameter before returning from the .NET code is particularly important in looping scenarios and long-running orchestrations that can accumulate instances of the XLANGMessage object without releasing them over time.</span></span> <span data-ttu-id="016e3-134">调用消息有关的详细信息。Dispose （） 以这种方式，请参阅[消息表示为 XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) BizTalk Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="016e3-134">For more information about calling message.Dispose() in this manner, see [Messages Represented as XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) in the BizTalk Server documentation.</span></span> <span data-ttu-id="016e3-135">本主题还提供使用 IStreamFactory 构造 XLANGMessage 变量在用户代码中使用一种基于流的方法的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="016e3-135">This topic also provides best practices for using IStreamFactory to construct XLANGMessage variables in user code using a stream-based approach.</span></span>  
  
 <span data-ttu-id="016e3-136">有关处理 XLANGMessage 由业务流程调用帮助器组件中的不同方法的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="016e3-136">For more information about the different ways to process an XLANGMessage within an helper component invoked by an orchestration, see the following topics:</span></span>  
  
-   <span data-ttu-id="016e3-137">[四种不同的方法来处理由业务流程第 1 部分调用的帮助程序组件内 XLANGMessage](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420)。</span><span class="sxs-lookup"><span data-stu-id="016e3-137">[4 Different ways to process an XLANGMessage within an helper component invoked by an orchestration Part 1](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420).</span></span>  
  
-   <span data-ttu-id="016e3-138">[四种不同的方法来处理由业务流程第 2 部分调用的帮助程序组件内 XLANGMessage](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421)。</span><span class="sxs-lookup"><span data-stu-id="016e3-138">[4 Different ways to process an XLANGMessage within an helper component invoked by an orchestration Part 2](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421).</span></span>  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-value-from-an-xlangmessage-object-from-a-method-invoked-by-an-orchestration"></a><span data-ttu-id="016e3-139">使用 XPathReader 和 XPathCollection 从由业务流程调用的方法从 XLANGMessage 对象中提取值</span><span class="sxs-lookup"><span data-stu-id="016e3-139">Using XPathReader and XPathCollection to extract a value from an XLANGMessage object from a method invoked by an orchestration</span></span>  
 <span data-ttu-id="016e3-140">避免使用 XMLDocument 类读取 XML 消息的内容从自定义代码，例如自定义管道组件或由业务流程调用的帮助器类。</span><span class="sxs-lookup"><span data-stu-id="016e3-140">Avoid using the XMLDocument class to read the contents of XML messages from custom code, such as custom pipeline components or helper classes invoked by orchestrations.</span></span> <span data-ttu-id="016e3-141">当使用 XMLDocument 实例来加载 XML 消息，则会将整个消息加载到内存中，这很低，并且可能需要最多 10 次消息的实际大小的内存。</span><span class="sxs-lookup"><span data-stu-id="016e3-141">When using an XMLDocument instance to load an XML message, the entire message is loaded into memory, which is inefficient and may require memory up to 10 times the actual size of the message.</span></span> <span data-ttu-id="016e3-142">读取 XML 消息的内容更高效的方法是使用流处理技术，可以使用一个由 Microsoft.BizTalk.Streaming.dll 程序集提供的流类包装原始流。</span><span class="sxs-lookup"><span data-stu-id="016e3-142">A more efficient way of reading the contents of XML messages is to use a streaming technique to wrap the original stream with one of the stream classes provided by the Microsoft.BizTalk.Streaming.dll assembly.</span></span> <span data-ttu-id="016e3-143">加载大型消息时，此方法十分特别有用。</span><span class="sxs-lookup"><span data-stu-id="016e3-143">This technique is particularly useful when loading large messages.</span></span>  
  
 <span data-ttu-id="016e3-144">如果需要从 XML 文档，而不是使用由 XmlDocument 类，公开的 SelectNodes 和 SelectSingleNode 方法请求特定值使用提供的 Microsoft.BizTalk.XPathReader.dll 程序集的 XPathReader 类的实例下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="016e3-144">If specific values need to be pulled from an XML document, instead of using the SelectNodes and SelectSingleNode methods exposed by the XmlDocument class, use an instance of the XPathReader class provided by the Microsoft.BizTalk.XPathReader.dll assembly as illustrated in the following code example.</span></span>  
  
-   <span data-ttu-id="016e3-145">此示例演示如何使用 XPathReader 和 XPathCollection 从由业务流程调用的方法内的 XLANGMessage 对象提取给定的值。</span><span class="sxs-lookup"><span data-stu-id="016e3-145">This example illustrates using the XPathReader and XPathCollection to extract a given value from an XLANGMessage object inside a method invoked by an orchestration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="016e3-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="016e3-146">See Also</span></span>  
 [<span data-ttu-id="016e3-147">优化 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="016e3-147">Optimizing BizTalk Server Applications</span></span>](../technical-guides/optimizing-biztalk-server-applications.md)