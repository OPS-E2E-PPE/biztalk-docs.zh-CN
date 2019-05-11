---
title: Stream 中使用 WCF 通道模型的 SAP 的平面文件 Idoc |Microsoft Docs
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
ms.openlocfilehash: bf0b2c0cd8fe401e8d410c8827d2d3ed7547edab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372777"
---
# <a name="stream-flat-file-idocs-in-sap-using-the-wcf-channel-model"></a>在 SAP 中使用 WCF 通道模型 Stream 平面文件 Idoc
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持节点值对于 SendIdoc 和 ReceiveIdoc 操作流式处理。 这些操作用于发送和接收平面文件 （字符串） Idoc 与该适配器。 在这两种操作，整个 IDOC 的数据包含在下一个节点字符串 (\<idocData\>)。 对于大型 Idoc，流式传输适配器与你的代码之间的 IDOC 数据可能会节省大量内存资源。  
  
 有关如何在适配器支持的流式处理的背景信息，请参阅[流式处理和 SAP 适配器](../../adapters-and-accelerators/adapter-sap/streaming-and-the-sap-adapter.md)。 您应阅读本主题继续操作之前。  
  
 本主题中的部分介绍如何实现节点值时使用的 WCF 通道模型对于 SendIdoc 和 ReceiveIdoc 操作流式处理。  
  
## <a name="streaming-outbound-flat-file-idocs-to-the-adapter"></a>流式处理到适配器的出站平面文件 Idoc  
 该适配器支持节点值 SendIdoc 操作的请求消息流处理。  
  
 若要支持节点值中的 WCF 通道模型 SendIdoc 操作的流式处理，必须：  
  
1.  实现**System.ServiceModel.Channels.BodyWriter** ，它能够流式传输 （执行节点值流处理的 IDOC 数据） IDOC 的数据。  
  
2.  创建**System.ServiceModel.Message**用于通过提供与此消息正文中调用该操作**BodyWriter**使用的适当重载**Message.Create**方法。  
  
### <a name="implementing-a-bodywriter"></a>实现 BodyWriter  
 下面的示例演示的实现**BodyWriter**执行节点值流式处理。  
  
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
  
### <a name="creating-a-message-by-using-a-bodywriter"></a>使用 BodyWriter 创建消息  
 下面的示例演示如何创建 SendIdoc 请求消息使用**BodyWriter**在前面的示例。 从文件中读取消息数据。  
  
```  
XmlReader readerIn = XmlReader.Create ("sendidoc.xml");  
// StreamingBodyWrtier class is responsible for streaming  
StreamingBodyWriter stBW = new StreamingBodyWriter(readerIn, chunkSize);  
  
Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.SAP/2007/03/Idoc/SendIdoc",   
    stBW);  
  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-adapter"></a>流式处理来自适配器的入站的平面文件 Idoc  
 在入站 ReceiveIdoc 操作中接收平面文件 Idoc。 该适配器支持节点值 ReceiveIdoc 操作的请求消息流处理。  
  
 若要支持节点值中的 WCF 通道模型 ReceiveIdoc 操作的流式处理，必须：  
  
1.  实现**System.Xml.XmlDictionaryWriter** ，它能够流式传输 （执行节点值流处理的 IDOC 数据） IDOC 的数据。  
  
2.  占用**消息**通过调用其**WriteBodyContents**方法与此**XmlDictionaryWriter**。  
  
### <a name="implementing-an-xmldictionarywriter"></a>实现 XmlDictionaryWriter  
 下面的示例演示的实现**XmlDictionaryWriter**执行节点值流式处理。  
  
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
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a>通过使用 XmlDictionaryWriter 来使用一条消息  
 下面的示例演示如何使用 ReceiveIdoc 请求消息使用**FileXmlWriter**在前面的示例中实现。 ( **FileWriter**类创建子类**XmlDictionaryWriter**。)该示例使用**IReplyChannel**频道接收 ReceiveIdoc 操作。 省略了创建通道的详细信息。 ReceiveIdoc 请求消息写入到文件。  
  
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
  
## <a name="see-also"></a>请参阅  
[使用 WCF 通道模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)