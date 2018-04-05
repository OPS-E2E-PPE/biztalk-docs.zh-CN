---
title: 流中使用 WCF 通道模型的 SAP 的平面文件 Idoc |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming flat-file IDOCs
ms.assetid: 5010e215-d8d0-47c8-93a6-20cfdeff2951
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8de850022a03a3be0310da3022a2cf496c94f30
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="stream-flat-file-idocs-in-sap-using-the-wcf-channel-model"></a><span data-ttu-id="decfd-102">SAP 使用 WCF 通道模型中的流平面文件 Idoc</span><span class="sxs-lookup"><span data-stu-id="decfd-102">Stream Flat-File IDOCs in SAP using the WCF Channel Model</span></span>
<span data-ttu-id="decfd-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持节点值对于 SendIdoc 和 ReceiveIdoc 操作流式处理。</span><span class="sxs-lookup"><span data-stu-id="decfd-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports node-value streaming for the SendIdoc and ReceiveIdoc operations.</span></span> <span data-ttu-id="decfd-104">这些操作用于发送和接收平面文件 （字符串） Idoc 与其他适配器。</span><span class="sxs-lookup"><span data-stu-id="decfd-104">These operations are used to send and receive flat-file (string) IDOCs to and from the adapter.</span></span> <span data-ttu-id="decfd-105">在这两种操作，整个 IDOC 的数据包含在单个节点下的字符串 (\<idocData\>)。</span><span class="sxs-lookup"><span data-stu-id="decfd-105">In both of these operations, the data for the entire IDOC is contained in a string under a single node (\<idocData\>).</span></span> <span data-ttu-id="decfd-106">对于大型 Idoc，流式处理的 IDOC 数据适配器和代码之间可能会节省大量的内存资源。</span><span class="sxs-lookup"><span data-stu-id="decfd-106">For large IDOCs, streaming the IDOC data between the adapter and your code may save significant memory resources.</span></span>  
  
 <span data-ttu-id="decfd-107">有关如何适配器支持流式处理的背景信息，请参阅[流式处理和 SAP 适配器](../../adapters-and-accelerators/adapter-sap/streaming-and-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="decfd-107">For background information about how the adapter supports streaming, see [Streaming and the SAP Adapter](../../adapters-and-accelerators/adapter-sap/streaming-and-the-sap-adapter.md).</span></span> <span data-ttu-id="decfd-108">您应该阅读然后再继续本主题。</span><span class="sxs-lookup"><span data-stu-id="decfd-108">You should read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="decfd-109">本主题中的各节描述了如何实现节点值时使用 WCF 通道模型对于 SendIdoc 和 ReceiveIdoc 操作流式处理。</span><span class="sxs-lookup"><span data-stu-id="decfd-109">The sections in this topic describe how to implement node-value streaming for the SendIdoc and ReceiveIdoc operations when you use the WCF channel model.</span></span>  
  
## <a name="streaming-outbound-flat-file-idocs-to-the-adapter"></a><span data-ttu-id="decfd-110">流式处理到适配器的出站平面文件 Idoc</span><span class="sxs-lookup"><span data-stu-id="decfd-110">Streaming Outbound Flat-File IDOCs to the Adapter</span></span>  
 <span data-ttu-id="decfd-111">适配器支持节点值 SendIdoc 操作的请求消息流式处理。</span><span class="sxs-lookup"><span data-stu-id="decfd-111">The adapter supports node-value streaming on the request message for the SendIdoc operation.</span></span>  
  
 <span data-ttu-id="decfd-112">若要支持节点值流式处理 SendIdoc 操作以 WCF 通道模型，你必须：</span><span class="sxs-lookup"><span data-stu-id="decfd-112">To support node-value streaming on SendIdoc operations in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="decfd-113">实现**System.ServiceModel.Channels.BodyWriter** ，它能够流式处理 （执行节点值的 IDOC 数据流式处理） 的 IDOC 数据。</span><span class="sxs-lookup"><span data-stu-id="decfd-113">Implement a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the IDOC data (performing node-value streaming on the IDOC data).</span></span>  
  
2.  <span data-ttu-id="decfd-114">创建**System.ServiceModel.Message**用于通过提供与此消息正文中调用该操作**BodyWriter**使用适当的重载**Message.Create**方法。</span><span class="sxs-lookup"><span data-stu-id="decfd-114">Create the **System.ServiceModel.Message** used to invoke the operation by supplying the message body with this **BodyWriter** using an appropriate overload of the **Message.Create** method.</span></span>  
  
### <a name="implementing-a-bodywriter"></a><span data-ttu-id="decfd-115">实现 BodyWriter</span><span class="sxs-lookup"><span data-stu-id="decfd-115">Implementing a BodyWriter</span></span>  
 <span data-ttu-id="decfd-116">下面的示例演示如何实现**BodyWriter**执行节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="decfd-116">The following example shows an implementation of a **BodyWriter** that performs node-value streaming.</span></span>  
  
```  
/// <summary>  
/// This class overrides the OnWriteBodyContents function to do node-value streaming  
/// </summary>  
class StreamingBodyWriter : BodyWriter, IDisposable  
{  
    XmlReader m_reader = null;  
  
    int m_chunkSize;  
    /// <summary>  
    /// Initializes the body writer  
    /// </summary>  
    /// <param name="reader">Reader for input</param>  
    /// <param name="chunkSize">The chunksize in which the data is passed to adapter</param>  
    public StreamingBodyWriter(XmlReader reader, int chunkSize)  
        : base(false)  
    {  
        m_reader = reader;  
        if (chunkSize <= 0)  
            throw new ApplicationException("ChunkSize should be a positive value");  
        m_chunkSize = chunkSize;  
    }  
  
    protected override void OnWriteBodyContents(XmlDictionaryWriter writer)  
    {  
        if (m_reader == null)  
            throw new ApplicationException("Reader cannot be null");  
  
        while (m_reader.Read())  
        {  
            switch (m_reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    writer.WriteStartElement(m_reader.LocalName, m_reader.NamespaceURI);  
                    break;  
                case XmlNodeType.Text:  
                    #region Streaming Code  
                    char[] tempBuffer = new char[m_chunkSize];  
                    int length = 0;  
                    while ((length = m_reader.ReadValueChunk(tempBuffer, 0, m_chunkSize)) > 0)  
                    {  
                        writer.WriteString(new String(tempBuffer, 0, length));  
                    }  
                    #endregion  
                    break;  
                case XmlNodeType.EndElement:  
                    writer.WriteEndElement();  
                    break;  
            }  
        }  
  
    }  
  
    #region IDisposable Members  
  
    public void Dispose()  
    {  
        if (m_reader != null)  
        {  
            m_reader.Close();  
            m_reader = null;  
        }  
    }  
  
    #endregion  
}  
```  
  
### <a name="creating-a-message-by-using-a-bodywriter"></a><span data-ttu-id="decfd-117">使用 BodyWriter 创建消息</span><span class="sxs-lookup"><span data-stu-id="decfd-117">Creating a Message by using a BodyWriter</span></span>  
 <span data-ttu-id="decfd-118">下面的示例演示如何创建 SendIdoc 请求消息使用**BodyWriter**在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="decfd-118">The following example shows how to create a SendIdoc request message using the **BodyWriter** in the preceding example.</span></span> <span data-ttu-id="decfd-119">从文件中读取消息数据。</span><span class="sxs-lookup"><span data-stu-id="decfd-119">The message data is read from a file.</span></span>  
  
```  
XmlReader readerIn = XmlReader.Create ("sendidoc.xml");  
// StreamingBodyWrtier class is responsible for streaming  
StreamingBodyWriter stBW = new StreamingBodyWriter(readerIn, chunkSize);  
  
Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.SAP/2007/03/Idoc/SendIdoc",   
    stBW);  
  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-adapter"></a><span data-ttu-id="decfd-120">从适配器的流式处理入站的平面文件 Idoc</span><span class="sxs-lookup"><span data-stu-id="decfd-120">Streaming Inbound Flat-File IDOCs from the Adapter</span></span>  
 <span data-ttu-id="decfd-121">入站 ReceiveIdoc 操作中接收平面文件 Idoc。</span><span class="sxs-lookup"><span data-stu-id="decfd-121">You receive a flat-file IDOCs in the inbound ReceiveIdoc operation.</span></span> <span data-ttu-id="decfd-122">适配器支持节点值 ReceiveIdoc 操作的请求消息流式处理。</span><span class="sxs-lookup"><span data-stu-id="decfd-122">The adapter supports node-value streaming on the request message for the ReceiveIdoc operation.</span></span>  
  
 <span data-ttu-id="decfd-123">若要支持节点值流式处理 ReceiveIdoc 操作以 WCF 通道模型，你必须：</span><span class="sxs-lookup"><span data-stu-id="decfd-123">To support node-value streaming on ReceiveIdoc operations in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="decfd-124">实现**System.Xml.XmlDictionaryWriter** ，它能够流式处理 （执行节点值的 IDOC 数据流式处理） 的 IDOC 数据。</span><span class="sxs-lookup"><span data-stu-id="decfd-124">Implement a **System.Xml.XmlDictionaryWriter** that is capable of streaming the IDOC data (performing node-value streaming on the IDOC data).</span></span>  
  
2.  <span data-ttu-id="decfd-125">使用**消息**通过调用其**WriteBodyContents**方法与此**XmlDictionaryWriter**。</span><span class="sxs-lookup"><span data-stu-id="decfd-125">Consume the **Message** by invoking its **WriteBodyContents** method with this **XmlDictionaryWriter**.</span></span>  
  
### <a name="implementing-an-xmldictionarywriter"></a><span data-ttu-id="decfd-126">实现 XmlDictionaryWriter</span><span class="sxs-lookup"><span data-stu-id="decfd-126">Implementing an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="decfd-127">下面的示例演示如何实现**XmlDictionaryWriter**执行节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="decfd-127">The following example shows an implementation of an **XmlDictionaryWriter** that performs node-value streaming.</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Text;  
  
class FileXmlWriter : XmlDictionaryWriter  
{  
    XmlTextWriter xts;  
  
    public FileXmlWriter(string file)  
    {  
        xts = new XmlTextWriter(file, Encoding.UTF8);  
    }  
  
    public override void WriteBase64(byte[] buffer, int index, int count)  
    {  
        xts.WriteBase64(buffer, index, count);  
    }  
  
    public override void WriteCData(string text)  
    {  
        xts.WriteCData(text);  
    }  
  
    public override void WriteCharEntity(char ch)  
    {  
        xts.WriteCharEntity(ch);  
    }  
  
    public override void WriteChars(char[] buffer, int index, int count)  
    {  
        xts.WriteChars(buffer, index, count);  
    }  
  
    public override void WriteComment(string text)  
    {  
        xts.WriteComment(text);  
    }  
  
    public override void WriteDocType(string name, string pubid, string sysid, string subset)  
    {  
        xts.WriteDocType(name, pubid, sysid, subset);  
    }  
  
    public override void WriteEndAttribute()  
    {  
        xts.WriteEndAttribute();  
    }  
  
    public override void WriteEndDocument()  
    {  
        xts.WriteEndDocument();  
    }  
  
    public override void WriteEndElement()  
    {  
        xts.WriteEndElement();  
    }  
  
    public override void WriteEntityRef(string name)  
    {  
        xts.WriteEntityRef(name);  
    }  
  
    public override void WriteFullEndElement()  
    {  
        xts.WriteFullEndElement();  
    }  
  
    public override void WriteProcessingInstruction(string name, string text)  
    {  
        xts.WriteProcessingInstruction(name, text);  
    }  
  
    public override void WriteRaw(string data)  
    {  
        xts.WriteRaw(data);  
    }  
  
    public override void WriteRaw(char[] buffer, int index, int count)  
    {  
        xts.WriteRaw(buffer, index, count);  
    }  
  
    public override void WriteStartAttribute(string prefix, string localName, string ns)  
    {  
        xts.WriteStartAttribute(prefix, localName, ns);  
    }  
  
    public override void WriteStartDocument(bool standalone)  
    {  
        xts.WriteStartDocument(standalone);  
    }  
  
    public override void WriteStartDocument()  
    {  
        xts.WriteStartDocument();  
    }  
  
    public override void WriteStartElement(string prefix, string localName, string ns)  
    {  
        xts.WriteStartElement(localName);  
    }  
  
    public override void WriteString(string text)  
    {  
        xts.WriteString(text);  
    }  
  
    public override void WriteSurrogateCharEntity(char lowChar, char highChar)  
    {  
        xts.WriteSurrogateCharEntity(lowChar, highChar);  
    }  
  
    public override void WriteWhitespace(string ws)  
    {  
        xts.WriteWhitespace(ws);  
    }  
  
    public override void Close()  
    {  
        xts.Close();  
    }  
  
    public override void Flush()  
    {  
        xts.Flush();  
    }  
  
    public override string LookupPrefix(string ns)  
    {  
        return xts.LookupPrefix(ns);  
    }  
  
    public override WriteState WriteState  
    {  
        get { return xts.WriteState; }  
    }  
  
}  
```  
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a><span data-ttu-id="decfd-128">通过使用 XmlDictionaryWriter 来使用一条消息</span><span class="sxs-lookup"><span data-stu-id="decfd-128">Consuming a Message by Using an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="decfd-129">下面的示例演示如何使用 ReceiveIdoc 请求消息使用**FileXmlWriter**实现在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="decfd-129">The following example shows how to consume a ReceiveIdoc request message using the **FileXmlWriter** implemented in the preceding example.</span></span> <span data-ttu-id="decfd-130">( **FileWriter**类由子类分类**XmlDictionaryWriter**。)该示例使用**IReplyChannel**通道接收 ReceiveIdoc 操作。</span><span class="sxs-lookup"><span data-stu-id="decfd-130">(The **FileWriter** class was created by sub-classing **XmlDictionaryWriter**.) The example uses an **IReplyChannel** channel to receive the ReceiveIdoc operation.</span></span> <span data-ttu-id="decfd-131">省略了创建频道的详细信息。</span><span class="sxs-lookup"><span data-stu-id="decfd-131">The details of the channel creation have been omitted.</span></span> <span data-ttu-id="decfd-132">ReceiveIdoc 请求消息写入到文件。</span><span class="sxs-lookup"><span data-stu-id="decfd-132">The ReceiveIdoc request message is written to a file.</span></span>  
  
```  
// Receive the ReceiveIdoc request message from the adapter.  
RequestContext rc = channel.ReceiveRequest();  
Message inputMsg = rc.RequestMessage;  
  
// Stream the request message to received_idoc.xml using the custom XmlDictionaryWriter.  
FileXmlWriter fileXmlWriter = new FileXmlWriter("received_idoc.xml");  
inputMsg.WriteBodyContents(fileXmlWriter);  
fileXmlWriter.Flush();  
fileXmlWriter.Close();  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="decfd-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="decfd-133">See Also</span></span>  
[<span data-ttu-id="decfd-134">使用 WCF 通道模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="decfd-134">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)