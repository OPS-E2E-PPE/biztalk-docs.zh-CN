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
# <a name="optimizing-pipeline-performance"></a>优化管道性能
本主题介绍用于优化性能的管道中的指导原则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
## <a name="best-practices-for-optimizing-performance-of-biztalk-server-pipelines"></a>有关优化 BizTalk Server 管道的性能最佳实践  
  
1. 由于管道组件对性能产生重大影响 （例如，直通管道组件执行比 XML 组装器/拆装器管道组件最多 30%），请确保任何自定义管道组件执行在部署中实现它们前以最佳方式。 如果你想要最大化你的 BizTalk 应用程序的整体性能，最小化自定义管道中的管道组件数。  
  
2. 通过减少在管道组件中的消息持久性频率和编码让组件能够最大程度减少冗余，还可以提高整体性能。 每个自定义程序集，特别是可能导致性能，如自定义跟踪组件，可能会中断的项目应进行测试单独系统处理满负荷时观察它们的行为以及查找高负载条件下任何可能的瓶颈。  
  
3. 如果你需要阅读的管道组件中的入站的消息，避免将整个文档加载到内存使用**XmlDocument**对象。 实例所需的空间量**XmlDocument**类来加载和创建 XML 文档的内存中表示形式是实际的消息大小的 10 倍。 为了读取一条消息，则应使用**XmlTextReader**对象以及以下类的实例：  
  
   -   **为 VirtualStream (Microsoft.BizTalk.Streaming.dll)** -此类的源代码位于以下两个管道 SDK 位置，如下所示：: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler 和 SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm。  
  
   -   **ReadOnlySeekableStream (Microsoft.BizTalk.Streaming.dll)**。  
  
   -   **SeekAbleReadOnlyStream** -此类的源代码位于以下两个管道 SDK 位置，如下所示：: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler 和 SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm。  
  
4. 使用 PassThruReceive 和 PassThruTransmit 标准管道，只要有可能。 它们不包含任何管道组件，不执行任何处理消息。 出于此原因，它们将确保在接收或发送消息的最大性能。 如果你需要将二进制文档发布到 BizTalk MessageBox 和 PassThruTransmit 管道在发送端口，如果需要发送二进制消息，可以在接收位置上使用 PassThruReceive 管道。 此外可以在绑定到业务流程，如果消息已经过格式设置，并且是准备要传输的物理发送端口使用 PassThruTransmit 管道。 需要使用不同的方法，如果您需要完成以下操作之一：  
  
   - 升级的入站 XML 或平面文件消息上下文属性。  
  
   - 应用内接收位置映射。  
  
   - 将应用订阅的消息的业务流程中的地图。  
  
   - 将映射应用于订阅的消息的发送端口。  
  
     若要完成以下操作之一，必须探测和发现接收管道中的文档类型，将 （命名空间 #root 的名称） 值分配给 MessageType 上下文属性。 拆装器组件，如 Xml 拆装器组件 (XmlDasmComp) 或平面文件拆装器组件 (FFDasmComp) 通常来完成此操作。 在这种情况下，您需要使用标准 （例如，XmlReceive 管道） 或包含一个标准或自定义拆装器组件的自定义管道。  
  
5. 获取资源，尽可能晚和发布它们尽早地。 例如，如果需要访问数据库上的数据，打开晚尽可能的连接，并尽可能快地将其关闭。 使用 C# using 语句隐式释放可释放对象或 finally 块的 try – catch – finally 语句来显式释放您的对象。 检测源代码以简化调试您的组件。  
  
6. 消除不严格要求，以加快消息处理管道中的任何组件。  
  
7. 在接收管道中，您应将项目升级到消息上下文仅在需要它们的消息路由 （业务流程、 发送端口） 或降级的消息上下文属性 （发送端口）。  
  
8. 如果您需要包含元数据与一条消息，并且在未使用元数据进行路由或降级的目的，使用**IBaseMessageContext.Write**方法而不是**IBaseMessageContext.Promote**方法。  
  
9. 如果你需要从使用 XPath 表达式的消息中提取信息，避免将整个文档加载到内存使用**XmlDocument**对象只是为了使用**SelectNodes**或**SelectSingleNode**方法。 或者，使用中所述的技术[与流式处理优化内存使用情况](../technical-guides/optimizing-memory-usage-with-streaming.md)。  
  
## <a name="use-streaming-to-minimize-the-memory-footprint-required-when-loading-messages-in-pipelines"></a>使用流式处理时加载在管道中的消息所需的内存占用量降至最低  
 以下技术描述如何将消息加载到管道时，消息的内存占用量降至最低。  
  
### <a name="use-readonlyseekablestream-and-virtualstream-to-process-a-message-from-a-pipeline-component"></a>使用 ReadOnlySeekableStream 和为 VirtualStream 来处理来自管道组件的消息  
 它被视为最佳做法来避免整个消息加载到内存中内部管道组件。 更好的办法是将包装的入站的流使用自定义流实现，然后为已读请求，自定义流实现读取底层的已包装流，并处理数据 （在纯流式处理方式） 读取。 这可以是很难实现，并不太可能，具体取决于需要使用流执行的操作的内容。 在这种情况下，使用**ReadOnlySeekableStream**并**为 VirtualStream** Microsoft.BizTalk.Streaming.dll 所公开的类。 中还提供了其中一个实现[任意 XPath 属性处理程序 （BizTalk Server 示例）](http://go.microsoft.com/fwlink/?LinkId=160069) (http://go.microsoft.com/fwlink/?LinkId=160069) BizTalk SDK 中。**ReadOnlySeekableStream**可确保光标，可重新定位到流的开头。 **为 VirtualStream**在内部，将使用 MemoryStream，除非大小为高于指定阈值，在这种情况下它将流写入到文件系统。 结合使用这两个流的使用 (使用**为 VirtualStream**作为持久性存储**ReadOnlySeekableStream**) 提供了"seekability"和"溢出到文件系统"功能。 这不将整个消息加载到内存的情况下适合于处理大消息。 下面的代码可以在管道组件，用于实现此功能。  
  
```  
int bufferSize = 0x280;  
int thresholdSize = 0x100000;  
Stream vStream = new VirtualStream(bufferSize, thresholdSize);  
Stream seekStream = new ReadOnlySeekableStream(inboundStream, vStream, bufferSize);  
```  
  
 此代码通过公开 bufferSize 提供"溢出阈值"和 thresholdSize 变量在每个接收位置或发送端口配置。 然后可以通过开发人员或管理员针对不同消息类型和不同配置 （例如 32 位与调整此溢出阈值。64 位)。  
  
### <a name="using-xpathreader-and-xpathcollection-to-extract-a-given-ibasemessage-object-from-within-a-custom-pipeline-component"></a>使用 XPathReader 和 XPathCollection 来提取从自定义管道组件中的给定的 IBaseMessage 对象。  
 如果需要从 XML 文档，而不是使用请求特定的值**SelectNodes**并**SelectSingleNode** XmlDocument 类公开的方法使用 XPathReader 类的实例下面的代码示例中所示 Microsoft.BizTalk.XPathReader.dll 程序集提供。  
  
> [!NOTE]  
>  对于较小的消息尤其是，使用 XmlDocument 和 SelectNodes 或 SelectSingleNode 可能提供更好的性能比使用 XPathReader，但 XPathReader 可以保留你的应用程序的平面内存配置文件。  
  
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
  
## <a name="use-xmlreader-and-xmlwriter-with-xmltranslatorstream-to-process-a-message-from-a-pipeline-component"></a>将与 XMLTranslatorStream XMLReader 和 XMLWriter，以处理来自管道组件的消息  
 用于实现一个自定义管道组件，它使用流式处理方法的另一种方法是使用.NET **XmlReader**并**XmlWriter**类以及**XmlTranslatorStream**由 BizTalk Server 提供的类。 例如， **NamespaceTranslatorStream** Microsoft.BizTalk.Pipeline.Components 程序集中包含的类继承自**XmlTranslatorStream**和可以用于替换旧的命名空间用新的流中包含的 XML 文档中。 若要使用自定义管道组件内的此功能，可以包装的消息正文部分的新实例与原始数据流**NamespaceTranslatorStream**类，并返回后者。 以这种方式将入站的消息不是读取或处理在管道组件，但仅在流读取的相同管道中的后续组件或最后由消息代理之前将文档发布到 BizTalk Server 时MessageBox。  
  
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
 管道组件应管理所创建的对象的生存期和这些对象不再需要立即执行垃圾回收。  如果管道组件想对象到最后一个管道执行结束前的生存期，则必须将此类对象添加到你的管道可能会从管道上下文中提取的资源跟踪器。  
  
 资源跟踪器用于以下类型的对象：  
  
- Stream 对象  
  
- COM 对象  
  
- IDisposable 对象  
  
  消息引擎可确保在适当的时间，即完全执行管道，无论是成功还是失败后将发布添加到的资源跟踪器的所有本机资源。 管道上下文对象由管理的资源跟踪器实例和它正在跟踪的对象的生存期。 管道上下文对所有类型的实现 IPipelineContext 接口的对象通过管道组件都可用。  
  
  例如，下面的代码段是一个示例，说明了如何在自定义管道组件中使用 ResourceTracker 属性。 若要使用 ResourceTracker 属性，则代码片段将使用以下参数`IPipelineContext.ResourceTracker.AddResource`。 在此参数：  
  
- IPipelineContext 接口定义用于访问所有文档处理特定于接口的方法。  
  
- ResourceTracker 属性引用 IPipelineContext，用于跟踪的管道处理结束时将显式释放的对象。  
  
- ResourceTracker.AddResource 方法用于跟踪的 COM 对象、 可释放的对象和流，并应始终使用自定义管道组件内显式关闭 （流）、 释放 （IDisposable 对象） 或这些释放 （COM 对象）类型的资源在一条消息发布到 BizTalk MessageBox。  
  
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
  
## <a name="comparison-of-loading-messages-into-pipelines-using-an-in-memory-approach-and-using-a-streaming-approach"></a>正在加载消息到管道中使用内存中的方法，并使用流式处理方法的比较  
 以下信息摘自 Nic Barden 博客[ http://blogs.objectsharp.com/cs/blogs/nbarden/archive/2008/04/14/developing-streaming-pipeline-components-part-1.aspx ](http://go.microsoft.com/fwlink/?LinkId=160228) (http://go.microsoft.com/fwlink/?LinkId=160228)。 此表提供到管道中使用内存中的方法，并使用流式处理方法加载消息的汇总的比较。  
  
|比较...|流式处理|在内存中|  
|----------------------|---------------|---------------|  
|每个消息的内存使用情况|低，而不考虑消息大小|高 （消息大小而异）|  
|用于处理 XML 数据的通用类|生成和自定义派生的：<br /><br /> XmlTranslatorStream、 XmlReader 和 XmlWriter|XmlDocument、 XPathDocument、 MemoryStream 和为 VirtualStream|  
|文档|差 – 许多不受支持的和未有案可稽 BizTalk 类|很好的.NET Framework 类|  
|"处理逻辑"代码的位置|-"绑定"读取器和流通过 Execute 方法。<br />-实际的执行发生在读取器和流中读取数据。|直接从管道组件的 Execute 方法。|  
|数据|重新创建在每个包装层，通过它读取数据。|读取、 修改并写出在之前被调用的下一个组件的每个组件。|  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server 应用程序](../technical-guides/optimizing-biztalk-server-applications.md)