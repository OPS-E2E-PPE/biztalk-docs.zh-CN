---
title: 优化管道性能 |Microsoft 文档
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
ms.openlocfilehash: 4311efd0d23e29b63f02fc34b1650a894d29d335
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299549"
---
# <a name="optimizing-pipeline-performance"></a>优化管道性能
本主题介绍有关优化性能的管道中的准则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a>有关优化的 BizTalk Server 管道的性能最佳实践  
  
1.  因为管道组件对性能有显著的影响 （例如，传递管道组件执行优于 XML 汇编/反汇编程序管道组件最多 30%），请确保任何自定义管道组件执行以最佳方式之前在你的部署中实施这些。 如果你想要最大化 BizTalk 应用程序的整体性能，最小化的自定义管道中的管道组件的数目。  
  
2.  通过减少管道组件中的消息持久性频率以及编码组件以最大程度减少冗余，您还可以改善整体性能。 每个自定义程序集，特别是无法可能降低性能，如自定义跟踪组件的项目应进行测试单独低于负荷条件以系统处理到满负荷时观察它们的行为并查找任何可能的瓶颈。  
  
3.  如果你需要阅读管道组件中的入站的消息，避免将整个文档加载到内存使用**XmlDocument**对象。 由的实例所需的空间量**XmlDocument**类来加载和创建 XML 文档的内存中表示为实际的消息大小的最多 10 倍。 要读取的消息，你应该使用**XmlTextReader**对象以及以下类的实例：  
  
    -   **VirtualStream (Microsoft.BizTalk.Streaming.dll)** -此类的源代码位于管道 SDK 下两个位置，如下所示： SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler 和 SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm。  
  
    -   **ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**。  
  
    -   **SeekAbleReadOnlyStream** -此类的源代码位于管道 SDK 下两个位置，如下所示： SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler 和 SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm。  
  
4.  使用 PassThruReceive 和 PassThruTransmit 标准管道，只要有可能。 它们不包含任何管道组件，并不会进行任何处理消息。 出于此原因，他们可以确保在接收或发送消息的最大性能。 如果你需要将二进制文档发布到 BizTalk MessageBox 和 PassThruTransmit 管道发送端口上的，如果你需要发送二进制消息的情况下，可以在接收位置上使用 PassThruReceive 管道。 你还可以在绑定到业务流程，如果消息已格式化，并且已准备好要传输的物理发送端口上使用 PassThruTransmit 管道。 你将需要使用不同的方法，如果你需要完成以下操作之一：  
  
    -   升级的入站 XML 或平面文件消息的上下文的属性。  
  
    -   应用内接收位置映射。  
  
    -   应用业务流程中订阅的消息映射。  
  
    -   将地图应用于订阅一条消息发送端口。  
  
     若要完成以下操作之一，你必须探测和发现接收管道中的文档类型并将 （命名空间 #root-名称） 值分配给 MessageType 上下文属性。 此操作通常是通过反汇编程序组件，如 Xml 反汇编程序组件 (XmlDasmComp) 或平面文件反汇编程序组件 (FFDasmComp) 实现的。 在这种情况下，你需要使用一种标准 （例如，XmlReceive 管道） 或包含一个标准或自定义反汇编程序组件的自定义管道。  
  
5.  尽可能晚获取资源和发布它们尽早尽可能。 例如，如果你需要访问在数据库上的数据，请打开尽可能晚作为可能的连接，并尽可能快地关闭。 使用 C# using 语句以隐式释放可释放对象或最后一个 try – catch – finally 语句来显式释放对象的块。 对你的源代码可简化调试你的组件进行检测。  
  
6.  消除不是严格需要，以加快消息处理你管道中的任何组件。  
  
7.  在接收管道，你应将项目升级到消息上下文仅当你的需要的邮件路由 （发送端口中的业务流程） 或降级消息上下文属性 （发送端口）。  
  
8.  如果你需要包括元数据与一条消息，并且在未使用元数据进行路由或降级目的，使用**IBaseMessageContext.Write**方法而不是**IBaseMessageContext.Promote**方法。  
  
9. 如果你需要从使用 XPath 表达式的消息中提取信息，避免将整个文档加载到内存使用**XmlDocument**对象只是为了使用**SelectNodes**或**SelectSingleNode**方法。 或者，使用中所述的技术[优化流式处理的内存使用情况](../technical-guides/optimizing-memory-usage-with-streaming.md)。  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a>使用流式处理程度地减少在加载管道中的消息时所需的内存需求量  
 下面的方法介绍如何加载到管道的消息时最大程度减少一条消息的内存需求量。  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a>使用 ReadOnlySeekableStream 和 VirtualStream 来处理管道组件的消息  
 它被视为最佳做法来避免加载到内存中内部管道组件的整个消息。 更可取的方法是将自定义流的实现，然后读取请求的入站的流、 自定义流实现读取底层的已包装的流，并读取 （以纯流的方式） 处理数据。 这可以是很难实现，并可能不可行的具体取决于什么需要与流执行的操作。 在这种情况下，使用**ReadOnlySeekableStream**和**VirtualStream**由 Microsoft.BizTalk.Streaming.dll 公开的类。 中还提供的这些实现[任意 XPath 属性处理程序 （BizTalk Server 示例）](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) BizTalk SDK 中。**ReadOnlySeekableStream**可确保光标，可重新定位到的流的开头。 **VirtualStream**内部，将使用一个 MemoryStream，除非大小高于指定阈值，在这种情况下它将写入到文件系统的流。 利用结合这两个流 (使用**VirtualStream**作为持久性存储区， **ReadOnlySeekableStream**) 提供了"seekability"和"溢出到文件系统"功能。 这样，就能适应大型消息的处理而无需加载到内存的整个消息。 下面的代码无法在管道组件，用于实现此功能。  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 此代码通过公开 bufferSize 提供"溢出阈值"和 thresholdSize 变量在每个接收位置或发送端口配置。 然后可以通过开发人员或管理员不同消息类型和不同配置 （例如 32 位与调整此溢出阈值。64 位)。  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a>使用 XPathReader 和 XPathCollection 提取从自定义管道组件内的给定的 IBaseMessage 对象。  
 如果需要从 XML 文档，而不是使用请求特定值**SelectNodes**和**SelectSingleNode** XmlDocument 类公开的方法使用 XPathReader 类的实例由 Microsoft.BizTalk.XPathReader.dll 程序集，如下面的代码示例中所示。  
  
> [!NOTE]  
>  对于较小的邮件尤其是 SelectNodes 或 SelectSingleNode 中使用 XmlDocument 可能提供更好的性能比使用 XPathReader，但 XPathReader 让你使你的应用程序的平面内存配置文件。  
  
 此示例演示如何使用 XPathReader 和 XPathCollection 提取给定**IBaseMessage**从对象中的自定义管道组件。  
  
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
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a>使用具有 XMLTranslatorStream XMLReader 和 XMLWriter，来处理从管道组件消息  
 实现使用流式处理方法的自定义管道组件的另一种方法是使用.NET **XmlReader**和**XmlWriter**结合类**XmlTranslatorStream** BizTalk Server 提供的类。 例如， **NamespaceTranslatorStream** Microsoft.BizTalk.Pipeline.Components 集中包含的类继承自**XmlTranslatorStream**和可以用于替换旧的命名空间替换为新的流中包含的 XML 文档中。 若要使用此功能的自定义管道组件内，您可以将使用的新实例的消息正文部分的原始数据流包装**NamespaceTranslatorStream**类，并返回后者。 以这种方式入站的消息是不可读取或处理在管道组件，但仅在流中相同的管道的后续组件读取或最后由消息代理之前将文档发布到 BizTalk Server 时MessageBox。  
  
 下面的示例演示如何使用此功能。  
  
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
  
## <a name="using-resourcetracker-in-custom-pipeline-components"></a>在自定义管道组件中使用 ResourceTracker  
 管道组件应管理它创建的对象的生存期和执行垃圾回收，只要这些对象不再需要。  如果管道组件想至最后一管道执行结束前的对象的生存期，则必须将此类对象添加到的资源跟踪器管道可能从管道上下文中提取。  
  
 资源跟踪器用于以下类型的对象：  
  
-   流对象  
  
-   COM 对象  
  
-   IDisposable 的对象  
  
 消息引擎可确保添加到资源跟踪器的所有本机资源释放在适当的时间，之后完全执行管道，无论它是成功还是失败。 管道的上下文对象由管理的资源跟踪器实例以及在跟踪的对象的生存期。 管道上下文可供所有类型的实现 IPipelineContext 接口的对象通过管道组件。  
  
 例如，下面的代码段是一个示例，演示了如何在自定义管道组件中使用 ResourceTracker 属性。 若要使用 ResourceTracker 属性，则代码片段将使用以下参数`IPipelineContext.ResourceTracker.AddResource`。 在此参数：  
  
-   IPipelineContext 接口定义用于访问所有文档处理特定接口的方法。  
  
-   ResourceTracker 属性引用 IPipelineContext，用于跟踪的管道处理的末尾将显式释放的对象。  
  
-   ResourceTracker.AddResource 方法可用于跟踪的 COM 对象、 可释放的对象和流，并应始终可以使用在自定义管道组件来显式关闭 （流）、 释放 （IDisposable 的对象） 或这些释放 （COM 对象）类型的资源时消息发布到 BizTalk MessageBox。  
  
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
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a>将消息加载到管道使用内存中方法和使用流式处理方法的比较  
 以下信息来自 Nic Barden 博客[http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228)。 此表提供加载消息的摘要的比较管道使用内存中方法和使用流式处理方法。  
  
|比较...|流式传输|在内存中|  
|----------------------|---------------|---------------|  
|每个消息的内存使用量|低，而不考虑消息大小|（消息大小而异） 高|  
|用于处理 XML 数据的通用类|生成在和自定义派生的：<br /><br /> XmlTranslatorStream、 XmlReader 和 XmlWriter|XmlDocument、 XPathDocument、 MemoryStream 和 VirtualStream|  
|文档|差 – 许多不受支持且未有记录 BizTalk 类|很好的.NET Framework 类|  
|"处理逻辑"代码的位置|-"连接"读取器和流通过 Execute 方法。<br />的读取数据，则将出现实际执行在读取器和流中。|直接从管道组件的 Execute 方法。|  
|data|重新创建在每个包装层，通过它读取数据。|读取、 修改并写出在之前调用的下一个组件的每个组件。|  
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server 应用程序](../technical-guides/optimizing-biztalk-server-applications.md)