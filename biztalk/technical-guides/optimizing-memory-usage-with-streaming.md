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
# <a name="optimizing-memory-usage-with-streaming"></a>优化流式处理的内存使用情况
本主题提供使用流式处理模式以最大程度减少消息内存空间占用量时发送或接收大消息的 WCF 传输或加载在业务流程中的消息时的建议。   
当在业务流程中使用代码以读取一条消息的内容，避免使用 XmlDocument 变量。 加载到一个 XmlDocument 变量的一条消息会产生很大的开销，尤其是对于大型消息。 在内存使用量和处理，以生成内存中结构方面是这种开销。 使用 XmlDocument 实例强制要以生成对象图的文档对象模块 (DOM) 加载到内存的整个消息内容。 此类的实例使用总量可以是内存的实际的消息大小的大约 10 倍。 有关在加载到一个 XmlDocument 变量的一条消息时所需的内存需求量的详细信息，请参阅[章 9 – 提高 XML 性能](http://go.microsoft.com/fwlink/?LinkId=139772)(http://go.microsoft.com/fwlink/?LinkId=139772) MSDN 上。   
本主题的其余部分提供用于读取不需要加载到一个 XmlDocument 变量的一条消息的消息内容替代方法。  
  
## <a name="use-streaming-when-sending-or-receiving-large-messages-with-a-wcf-transport"></a>使用流式处理时发送或接收的 WCF 传输大型消息  
 当发送或接收与 WCF 传输大型消息时，使用 WCF 自定义或 WCF CustomIsolated 适配器使用和配置支持的绑定类型**传输模式 = Streamed**选项，例如，下列绑定：  
  
-   **basicHttpBinding + BasicHttpBindingElement，传输模式 = Streamed**  
  
-   **netTcpBinding + NetTcpBindingElement，传输模式 = Streamed**  
  
-   **customBinding + HttpTransportElement，传输模式 = Streamed**  
  
-   **customBinding + ConnectionOrientedTransportElement，传输模式 = Streamed**  
  
 选择以及支持的绑定的 WCF 自定义或 WCF CustomIsolated 适配器**传输模式 = Streamed**选项将实现流式传输到文件系统的大消息根据需要并将缓解潜在内存不足问题。  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-orchestrations"></a>使用流式处理程度地减少在加载在业务流程中的消息时所需的内存需求量  
 下面的方法介绍如何加载到业务流程的消息时最大程度减少一条消息的内存需求量。  
  
### <a name="use-an-xlangmessage-variable-to-process-the-contents-of-a-message-or-message-part"></a>用 XLANGMessage 变量来处理消息或消息部分的内容  
 当将从业务流程的一条消息传递给.NET 类库中，不将它们作为传递 XmlDocument 变量，本主题中; 前面所述的原因请改用 XLANGMessage 变量。 以下技术说明了读取的消息或消息部分使用 XLANGMessage 变量的方法。  
  
-   **处理消息 XMLReader** -若要将处理与 XmlReader 实例消息、 将消息传递给为 XLANGMessage 的.NET 代码和检索使用 XmlReader 部分内容。  
  
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
  
-   **检索消息的内容读入一个字符串与 StreamReader** -XmlDocument 在业务流程中的常见用途之一是以 XML 字符串使用 XmlDocument.OuterXml() 检索消息。 下面的代码示例演示了一种替代方法，该字符串使用 XLANGMessage 变量中检索消息。  
  
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
  
-   **转换为字符串检索的简单.NET 消息的内容**-如果消息的类型是简单的.NET 类型，则可以检索为该类型的消息。 例如，若要获取字符串形式的消息，将消息传递给 XLANGMessage 的.NET 代码，并检索一部分内容作为字符串。  
  
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
  
-   **检索到流的消息的内容**-若要将获取以流的形式的消息、 将消息传递给 XLANGMessage 的.NET 代码和检索作为流的一部分内容。  
  
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
  
-   **检索消息的内容转换为.NET 对象**-若要将获取将消息作为.NET 对象，将消息传递给 XLANGMessage 的.NET 代码并作为一个.NET 类的实例检索部分内容。 创建此后者从使用 Visual Studio 2010 提供的 XML 架构定义工具 (Xsd.exe) 工具的消息的 Xml 架构。  
  
    > [!NOTE]  
    >  只有在小消息时，此方法相当有效。 否则，此方法可能会导致在很大的开销来反序列化为.NET 对象的实际的消息。  
  
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
>  利用**dispose （)** 从.NET 代码返回前由 XLANGMessage 参数公开的方法是特别重要循环方案和长时间运行业务流程可以累积的实例而不释放它们随着时间的推移 XLANGMessage 对象。 调用消息有关的详细信息。Dispose （） 以这种方式，请参阅[消息表示为 XLANGMessage](http://go.microsoft.com/fwlink/?LinkId=139775) (http://go.microsoft.com/fwlink/?LinkId=139775) BizTalk Server 文档中。 本主题还提供使用 IStreamFactory 构造 XLANGMessage 变量在用户代码中使用一种基于流的方法的最佳实践。  
  
 有关处理 XLANGMessage 由业务流程调用帮助器组件中的不同方法的详细信息，请参阅以下主题：  
  
-   [四种不同的方法来处理由业务流程第 1 部分调用的帮助程序组件内 XLANGMessage](http://go.microsoft.com/fwlink/?LinkID=210420) (http://go.microsoft.com/fwlink/?LinkID=210420)。  
  
-   [四种不同的方法来处理由业务流程第 2 部分调用的帮助程序组件内 XLANGMessage](http://go.microsoft.com/fwlink/?LinkID=210421) (http://go.microsoft.com/fwlink/?LinkID=210421)。  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-value-from-an-xlangmessage-object-from-a-method-invoked-by-an-orchestration"></a>使用 XPathReader 和 XPathCollection 从由业务流程调用的方法从 XLANGMessage 对象中提取值  
 避免使用 XMLDocument 类读取 XML 消息的内容从自定义代码，例如自定义管道组件或由业务流程调用的帮助器类。 当使用 XMLDocument 实例来加载 XML 消息，则会将整个消息加载到内存中，这很低，并且可能需要最多 10 次消息的实际大小的内存。 读取 XML 消息的内容更高效的方法是使用流处理技术，可以使用一个由 Microsoft.BizTalk.Streaming.dll 程序集提供的流类包装原始流。 加载大型消息时，此方法十分特别有用。  
  
 如果需要从 XML 文档，而不是使用由 XmlDocument 类，公开的 SelectNodes 和 SelectSingleNode 方法请求特定值使用提供的 Microsoft.BizTalk.XPathReader.dll 程序集的 XPathReader 类的实例下面的代码示例所示。  
  
-   此示例演示如何使用 XPathReader 和 XPathCollection 从由业务流程调用的方法内的 XLANGMessage 对象提取给定的值。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server 应用程序](../technical-guides/optimizing-biztalk-server-applications.md)