---
title: 流式处理使用 WCF 通道模型的 Oracle 数据库 LOB 数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, Oracle LOB data types
- WCF channel model, streaming Oracle LOB data types
ms.assetid: 513a7cb8-495d-4019-bce1-b5babca3629f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d9c1ad3c50cf2383ad9b2d65af3d8c79f2c1862
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375982"
---
# <a name="streaming-oracle-database-lob-data-types-using-the-wcf-channel-model"></a><span data-ttu-id="f6ac3-102">使用 WCF 通道模型的流式处理 Oracle 数据库 LOB 数据类型</span><span class="sxs-lookup"><span data-stu-id="f6ac3-102">Streaming Oracle Database LOB Data Types Using the WCF Channel Model</span></span>
<span data-ttu-id="f6ac3-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]支持端到端的流式处理的 LOB 数据的某些操作。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports end-to-end streaming of LOB data for certain operations.</span></span> <span data-ttu-id="f6ac3-104">本主题中的部分介绍如何实现流式处理 LOB 数据时使用的 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-104">The sections in this topic describe how to implement streaming for LOB data when you use the WCF channel model.</span></span>  
  
 <span data-ttu-id="f6ac3-105">有关如何在适配器支持流式处理 LOB 数据类型的背景信息，请参阅[流式处理大型对象数据类型在 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-105">For background information about how the adapter supports streaming of LOB data types, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="f6ac3-106">您应阅读本主题继续操作之前。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-106">You should read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="f6ac3-107">LOB 数据进行流式处理演示的示例现已推出附带的 SDK 示例[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-107">A sample that demonstrates LOB data streaming is available in the SDK samples included with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="f6ac3-108">有关详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-108">For more information, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="streaming-outbound-messages-to-the-adapter"></a><span data-ttu-id="f6ac3-109">流式处理到适配器的出站消息</span><span class="sxs-lookup"><span data-stu-id="f6ac3-109">Streaming Outbound Messages to the Adapter</span></span>  
 <span data-ttu-id="f6ac3-110">该适配器支持 UpdateLOB 操作的请求消息流式处理的端到端 LOB 数据。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-110">The adapter supports end-to-end LOB data streaming for the request message for the UpdateLOB operation.</span></span>  
  
 <span data-ttu-id="f6ac3-111">若要支持端到端流式处理中的 WCF 通道模型 UpdateLOB 操作，必须：</span><span class="sxs-lookup"><span data-stu-id="f6ac3-111">To support end-to-end streaming on UpdateLOB operations in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="f6ac3-112">设置**UseAmbientTransaction**绑定属性为 true。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-112">Set the **UseAmbientTransaction** binding property to true.</span></span>  
  
2.  <span data-ttu-id="f6ac3-113">实现**System.ServiceModel.Channels.BodyWriter** ，它能够流式处理 LOB 数据 （执行流式处理 LOB 数据的节点的值）。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-113">Implement a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the LOB data (performing node-value streaming on the LOB data).</span></span>  
  
3.  <span data-ttu-id="f6ac3-114">执行 UpdateLOB 事务范围内的操作。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-114">Perform the UpdateLOB operation within a transaction scope.</span></span>  
  
4.  <span data-ttu-id="f6ac3-115">创建**System.ServiceModel.Message**用于通过提供与此消息正文中调用该操作**BodyWriter**使用的适当重载**Message.Create**方法。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-115">Create the **System.ServiceModel.Message** used to invoke the operation by supplying the message body with this **BodyWriter** using an appropriate overload of the **Message.Create** method.</span></span>  
  
### <a name="setting-the-useambienttransaction-binding-property"></a><span data-ttu-id="f6ac3-116">设置绑定属性 UseAmbientTransaction</span><span class="sxs-lookup"><span data-stu-id="f6ac3-116">Setting the UseAmbientTransaction Binding Property</span></span>  
 <span data-ttu-id="f6ac3-117">下面的示例演示如何为创建绑定[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]并设置**UseAmbientTransaction**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-117">The following example shows how to create a binding for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] and set the **UseAmbientTransaction** binding property.</span></span>  
  
```  
// Create binding  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
//set the binding property  
binding.UseAmbientTransaction = true;  
  
```  
  
### <a name="implementing-a-bodywriter"></a><span data-ttu-id="f6ac3-118">实现 BodyWriter</span><span class="sxs-lookup"><span data-stu-id="f6ac3-118">Implementing a BodyWriter</span></span>  
 <span data-ttu-id="f6ac3-119">下面的示例演示的实现**BodyWriter**执行节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-119">The following example shows an implementation of a **BodyWriter** that performs node-value streaming.</span></span>  
  
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
        if (chunkSize \<= 0)  
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
  
### <a name="perform-the-operations-within-a-transaction-scope"></a><span data-ttu-id="f6ac3-120">执行事务范围内的操作</span><span class="sxs-lookup"><span data-stu-id="f6ac3-120">Perform the Operations Within a Transaction Scope</span></span>  
 <span data-ttu-id="f6ac3-121">下面的示例演示如何在事务作用域中执行操作。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-121">The following example shows how to perform operations within a transaction scope.</span></span>  
  
```  
// Create a transaction scope  
using(TransactionScope tx = new TransactionScope())  
{  
  // perform operations within the transaction  
  // ...  
  // ...  
  
  //Complete the transaction  
  tx.Complete()  
}  
  
```  
  
### <a name="creating-a-message-by-using-a-bodywriter"></a><span data-ttu-id="f6ac3-122">使用 BodyWriter 创建消息</span><span class="sxs-lookup"><span data-stu-id="f6ac3-122">Creating a Message by using a BodyWriter</span></span>  
 <span data-ttu-id="f6ac3-123">下面的示例演示如何创建 UpdateLOB 请求消息使用**BodyWriter**在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-123">The following example shows how to create an UpdateLOB request message using the **BodyWriter** in the preceding example.</span></span> <span data-ttu-id="f6ac3-124">从文件中读取消息数据。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-124">The message data is read from a file.</span></span>  
  
```  
// Create a transaction scope  
using(TransactionScope tx = new TransactionScope())  
{  
    XmlReader readerIn = XmlReader.Create ("updatelob.xml");  
    // StreamingBodyWrtier class is responsible for streaming  
    StreamingBodyWriter stBW = new StreamingBodyWriter(readerIn, chunkSize);  
  
    Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/UpdateLOB",   
    stBW);  
  
    //Send the request message and get the output message  
    OutputMsg = channel.Request(InputMsg);  
  
    tx.Complete();  
}  
  
```  
  
## <a name="streaming-inbound-messages-from-the-adapter"></a><span data-ttu-id="f6ac3-125">流式处理来自适配器的入站的消息</span><span class="sxs-lookup"><span data-stu-id="f6ac3-125">Streaming Inbound Messages from the Adapter</span></span>  
 <span data-ttu-id="f6ac3-126">适配器支持以下入站消息的流式处理的端到端 LOB 数据：</span><span class="sxs-lookup"><span data-stu-id="f6ac3-126">The adapter supports end-to-end LOB data streaming for the following inbound messages:</span></span>  
  
- <span data-ttu-id="f6ac3-127">具有扩展的函数的响应消息或包含 LOB 数据在 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-127">Response message for functions with OUT or IN OUT parameters that contain LOB data.</span></span> <span data-ttu-id="f6ac3-128">请注意记录类型参数可包含 LOB 数据列。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-128">Note that RECORD TYPE parameters can contain LOB data columns.</span></span>  
  
- <span data-ttu-id="f6ac3-129">包含 LOB 数据带出 REF CURSOR 参数 （或返回值） 的函数的响应消息。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-129">Response message for functions with OUT REF CURSOR parameters (or return values) that contain LOB data.</span></span> <span data-ttu-id="f6ac3-130">这包括在 OUT REF CURSOR 参数在输出端。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-130">This includes the output side of IN OUT REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="f6ac3-131">用于过程以及在响应消息或包含 LOB 数据在 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-131">Response message for procedures with IN or IN OUT parameters that contain LOB data.</span></span> <span data-ttu-id="f6ac3-132">请注意记录类型参数可包含 LOB 数据列。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-132">Note that RECORD TYPE parameters can contain LOB data columns.</span></span>  
  
- <span data-ttu-id="f6ac3-133">带有 OUT REF CURSOR 参数包含 LOB 数据的过程的响应消息。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-133">Response message for procedures with OUT REF CURSOR parameters that contain LOB data.</span></span> <span data-ttu-id="f6ac3-134">这包括在 OUT REF CURSOR 参数在输出端</span><span class="sxs-lookup"><span data-stu-id="f6ac3-134">This includes the output side of IN OUT REF CURSOR parameters</span></span>  
  
- <span data-ttu-id="f6ac3-135">返回包含 LOB 数据的结果集的 SQLEXECUTE 操作的响应消息。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-135">Response message for SQLEXECUTE operations that return result sets that contain LOB data.</span></span>  
  
- <span data-ttu-id="f6ac3-136">设置表或视图返回结果中的 LOB 数据的 Select 操作的响应消息。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-136">Response message for Table or view Select operations that return LOB data in the result set.</span></span>  
  
- <span data-ttu-id="f6ac3-137">（入站） POLLINGSTMT 操作的请求消息</span><span class="sxs-lookup"><span data-stu-id="f6ac3-137">Request message for the (inbound) POLLINGSTMT operation</span></span>  
  
  <span data-ttu-id="f6ac3-138">若要支持端到端流式处理入站消息中的 WCF 通道模型上，您必须：</span><span class="sxs-lookup"><span data-stu-id="f6ac3-138">To support end-to-end streaming on an inbound message in the WCF channel model, you must:</span></span>  
  
1.  <span data-ttu-id="f6ac3-139">实现**System.Xml.XmlDictionaryWriter** ，它能够流式处理 LOB 数据 （执行流式处理 LOB 数据的节点的值）。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-139">Implement a **System.Xml.XmlDictionaryWriter** that is capable of streaming the LOB data (performing node-value streaming on the LOB data).</span></span>  
  
2.  <span data-ttu-id="f6ac3-140">占用**消息**通过调用**WriteBodyContents**方法与此**XmlDictionaryWriter**。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-140">Consume the **Message** by invoking **WriteBodyContents** method with this **XmlDictionaryWriter**.</span></span>  
  
### <a name="implementing-an-xmldictionarywriter"></a><span data-ttu-id="f6ac3-141">实现 XmlDictionaryWriter</span><span class="sxs-lookup"><span data-stu-id="f6ac3-141">Implementing an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="f6ac3-142">下面的示例演示的实现**XmlDictionaryWriter**执行节点值流式处理。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-142">The following example shows an implementation of an **XmlDictionaryWriter** that performs node-value streaming.</span></span>  
  
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
  
### <a name="consuming-a-message-by-using-an-xmldictionarywriter"></a><span data-ttu-id="f6ac3-143">通过使用 XmlDictionaryWriter 来使用一条消息</span><span class="sxs-lookup"><span data-stu-id="f6ac3-143">Consuming a Message by using an XmlDictionaryWriter</span></span>  
 <span data-ttu-id="f6ac3-144">下面的示例演示如何使用表选择响应消息使用**FileXmlWriter**在前面的示例中实现。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-144">The following example shows how to consume a table Select response message using the **FileXmlWriter** implemented in the preceding example.</span></span> <span data-ttu-id="f6ac3-145">( **FileWriter**类创建子类**XmlDictionaryWriter**。)该示例使用**IRequestChannel**通道来调用选择操作。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-145">(The **FileWriter** class was created by sub-classing **XmlDictionaryWriter**.) The example uses an **IRequestChannel** channel to invoke the Select operation.</span></span> <span data-ttu-id="f6ac3-146">省略了创建通道的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-146">The details of the channel creation have been omitted.</span></span> <span data-ttu-id="f6ac3-147">从文件读取选择请求消息，并选择响应消息写入到文件。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-147">The Select request message is read from a file and the Select response message is written to a file.</span></span>  
  
```  
// Read Select message body from a file  
XmlReader readerIn = XmlReader.Create("select.xml");  
Message InputMsg = Message.CreateMessage(MessageVersion.Default,  
    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER/Select", readerIn);  
  
Message OutputMsg = channel.Request(InputMsg);  
  
// Streaming response message to select_output.xml using the custom XmlDictionaryWriter;  
FileXmlWriter fileXmlWriter = new FileXmlWriter("select_output.xml");  
OutputMsg.WriteBodyContents(fileXmlWriter);  
fileXmlWriter.Flush();  
fileXmlWriter.Close();  
  
// Streaming complete close output message;  
OutputMsg.Close();  
```  
  
 <span data-ttu-id="f6ac3-148">以下 XML 显示在选择操作的请求消息 （select.xml 文件的内容）。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-148">The following XML shows the request message (contents of the select.xml file) for the Select operation.</span></span> <span data-ttu-id="f6ac3-149">CUSTOMER 表包含名为 PHOTO 的 BLOB 列。</span><span class="sxs-lookup"><span data-stu-id="f6ac3-149">The CUSTOMER table contains a BLOB column named PHOTO.</span></span>  
  
```  
<Select xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/CUSTOMER">  
  <COLUMN_NAMES>*</COLUMN_NAMES>  
  <FILTER>NAME='Kim Ralls'</FILTER>  
</Select>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6ac3-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6ac3-150">See Also</span></span>  
 [<span data-ttu-id="f6ac3-151">开发 Oracle 数据库应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="f6ac3-151">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)