---
title: 步骤 7：实现 Echo 适配器的同步出站处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da4d987-03c4-4817-850b-4c5ca2ba7e62
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 591b30f97fdfbe4c014f67b0be4b6ef1182765b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363158"
---
# <a name="step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter"></a>步骤 7：实现 Echo 适配器的同步出站处理程序
![步骤 7 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")  
  
 **若要完成的时间：** 30 分钟  
  
 在此步骤中，将实现 Echo 适配器的同步出站功能。 根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，以支持同步的出站功能，必须实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`接口。 Echo 适配器[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成一个名为 EchoAdapterOutboundHandler 的派生的类。  
  
 在以下部分中，你将更新 EchoAdapterOutboundHandler 类，以获取更好地了解如何实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`、 如何分析传入的 WCF 请求消息，以及如何生成传出的 WCF 响应消息。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，你必须已成功完成[步骤 6:实现 Echo 适配器的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)。 基本熟悉`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`也会有所帮助。  
  
## <a name="the-ioutboundhandler-interface"></a>IOutboundHandler 接口  
 `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`定义为：  
  
```  
public interface IOutboundHandler : IConnectionHandler, IDisposable  
{  
    Message Execute(Message message, TimeSpan timeout);  
}  
```  
  
 `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`方法通过调用相应方法在目标系统上的执行传入 WCF 请求消息，然后返回一个传出的 WCF 响应消息。 下表列出了它的参数的定义：  
  
|**参数**|**定义**|  
|-------------------|--------------------|  
|message|传入的 WCF 请求消息。|  
|timeout|应在其中完成此操作的时间间隔。 此操作应引发`System.TimeoutException`如果在操作完成之前超出指定的超时时间。|  
  
 如果您的适配器执行的一个单向发送 （没有任何响应消息所需的适配器），此方法应返回 null。 如果您的适配器执行的与双向操作`Microsoft.ServiceModel.Channels.Common.OperationResult`等于`Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`，此方法返回包含空正文的 WCF 响应消息。 否则，它应返回 WCF 响应消息正文包含中的值与`Microsoft.ServiceModel.Channels.Common.OperationResult`对象。 若要构造响应的操作字符串，请使用`Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`。  
  
## <a name="echo-adapter-synchronous-outbound"></a>回显适配器同步出站  
 根据目标系统的操作，有许多方法来实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`方法。 Echo 适配器有三个出站操作和其分配的节点 Id 和显示名称：  
  
- string [] EchoStrings （字符串数据）、 节点 ID = Echo/EchoString，显示名称 = EchoString  
  
- 问候语 [] EchoGreetings(Greeting greeting)，节点 ID = Echo/EchoGreetings，显示名称 = EchoGreetings  
  
- CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath)，nodeID = Echo/EchoCustomGreetingFromFile，显示名称 = EchoGreetings  
  
  若要正确分析传入的 WCF 请求消息和生成传出的 WCF 响应消息，您必须熟悉使用的 SOAP 消息中的以下元素[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
  传入的 WCF 请求消息：  
  
- WCF 输入消息操作 = 操作的节点 ID  
  
- 传入消息正文 = 开始正文的元素是\<displayname\>\<参数名称\>{数据}\</parameter 名称\>\</displayname\>  
  
  为传出 WCF 响应消息：  
  
- WCF 输出消息操作 = 操作的节点 ID +"/ 响应"  
  
- 传出消息正文 = 开始正文的元素是\<displayname"响应"+\>后, 跟\<displayname +"结果"\>，并后跟\<数据类型\>数据\</datatype\>\</displayname+"结果\>\</displayname +"响应"\>  
  
  例如，操作**string [] EchoStrings （字符串数据）**，节点 ID = Echo/EchoStrings 和显示名称 = EchoStrings:  
  
  WCF 输入消息操作 ="回送/EchoStrings";输入的正文如下所示，因为参数名称为和`data`。  
  
```  
<EchoStrings>  
<data>{data}  
</data>  
</EchoStrings>  
```  
  
 WCF 输出消息操作 ="回送/EchoStrings/响应";和输出正文如下所示，因为数据类型为**字符串**。  
  
```  
<EchoStringsResponse>  
<EchoStringsResult>  
<string>{data}</string>  
</EchoStringsResult>  
</EchoStringsResponse>  
```  
  
 当解析传入的 WCF 请求消息，可以使用`System.Xml.XmlDictionaryReader`若要检索 WCF 消息中; 中的内容，在撰写 WCF 响应消息时，可以使用`System.Xml.XmlWriter`若要执行此操作。  
  
## <a name="implementing-the-ioutboundhandler"></a>实现 IOutboundHandler  
 实现的 Execute 方法`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`。 首先，获取`Microsoft.ServiceModel.Channels.Common.OperationMetadata`对象根据输入的消息操作。 然后，分析传入 WCF 消息并执行基于每个操作的关联回送功能。 最后，使用传出的消息正文的格式创建传出 WCF 响应消息。  
  
#### <a name="to-implement-the-execute-method-of-the-echoadapteroutboundhandler-class"></a>若要实现 EchoAdapterOutboundHandler 类的 Execute 方法  
  
1.  在解决方案资源管理器中双击**EchoAdapterOutboundHandler.cs**文件。  
  
2.  在 Visual Studio 编辑器中，添加以下两个使用对现有的 using 指令集的指令。  
  
    ```csharp  
    using System.Xml;  
    using System.IO;  
    ```  
  
3.  内部**Execute**方法，用以下代码替换现有的逻辑：  
  
    1.  此逻辑将验证请求的操作。  
  
    2.  它获取`Microsoft.ServiceModel.Channels.Common.OperationMetadata`对象基于 SOAP 的输入的消息操作。  
  
    3.  它根据操作类型，分析 WCF 请求消息并调用相应的操作。  
  
    ```csharp  
    // Trace input message  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Verbose, "http://Microsoft.Adapters.Samples.Sql/TraceCode/InputWcfMessage", "Input WCF Message", this, new MessageTraceRecord(message));  
    // Timeout is not supported in this sample  
    OperationMetadata om = this.MetadataLookup.GetOperationDefinitionFromInputMessageAction(message.Headers.Action, timeout);  
    if (om == null)  
    {  
        throw new AdapterException("Invalid operation metadata for " + message.Headers.Action);  
    }  
    if (timeout.Equals(TimeSpan.Zero))  
    {  
        throw new AdapterException("time out is zero");  
    }  
  
    switch (message.Headers.Action)  
    {  
        case "Echo/EchoStrings":  
            return ExecuteEchoStrings(om as ParameterizedOperationMetadata, message, timeout);  
  
        case "Echo/EchoGreetings":  
            return ExecuteEchoGreetings(om as ParameterizedOperationMetadata, message, timeout);  
  
        case "Echo/EchoCustomGreetingFromFile":  
            return ExecuteEchoCustomGreetingFromFile(om, message, timeout);  
    }  
    return null;              
    ```  
  
4.  现在，添加**ExecuteEchoStrings**方法以处理字符串 [] EchoStrings （字符串数据） 操作。 此帮助器函数读取 WCF 请求消息，检查，以查看 echoInUpperCase URI 元素是否已设置为 true;如果是这样，它会将输入的字符串转换为大写无数次，指示计数变量中。 然后，它生成 WCF 响应消息的格式为：\<EchoStringsResponse\>\<EchoStringResult\>\<字符串\>{数据}\</字符串\>\</EchoStringResult\> \</EchoStringsResponse\>。  
  
    ```csharp  
    private Message ExecuteEchoStrings(ParameterizedOperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // ** Read the WCF request  
        // ** <EchoStrings><name>{text}</name></EchoStrings>  
        XmlDictionaryReader inputReader = message.GetReaderAtBodyContents();  
        while (inputReader.Read())  
        {  
            if ((String.IsNullOrEmpty(inputReader.Prefix) && inputReader.Name.Equals("data"))  
                || inputReader.Name.Equals(inputReader.Prefix + ":" + "data")) break;  
        }  
        inputReader.Read();  
        // if the connection property "echoInUpperCase" is set to true, it echoes the data in upper case  
        bool echoInUpperCase = this.Connection.ConnectionFactory.ConnectionUri.EchoInUpperCase;  
        string inputValue = echoInUpperCase ? inputReader.Value.ToUpper() : inputReader.Value;  
        int arrayCount = this.Connection.ConnectionFactory.Adapter.Count;  
  
        // ** Generate the WCF response  
        // ** <EchoStringsResponse><EchoStringResult>{Name}</EchoStringResult></EchoStringsResponse >  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        if (om.OperationResult.IsArray)  
        {  
            for (int count = 0; count < arrayCount; count++)  
            {  
                replywriter.WriteElementString("string", "http://schemas.microsoft.com/2003/10/Serialization/Arrays", inputValue);  
            }  
        }  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
5.  继续通过添加**ExecuteEchoGreetings**方法以处理 EchoGreetings 操作。 此帮助器函数读取 WCF 请求消息时，解析操作并通过键入`ResolveOperationMetadata`并`ResolveTypeMetadata`方法的`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`接口，并生成 WCF 响应消息使用的格式：\<EchoGreetingsResponse\>\<EchoGreetingsResult\>...消息。\</EchoGreetingsResult\>\</EchoGreetingsResponse\>。  
  
    ```csharp  
    private Message ExecuteEchoGreetings(ParameterizedOperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // NOTE this method doesn't return response in upper case based on   
        // connection property echoInUpperCase  
  
        // ** Read the WCF request  
        String inputValue = String.Empty;  
        using (XmlDictionaryReader inputReader = message.GetReaderAtBodyContents())  
        {  
  
            bool foundGreeting = inputReader.ReadToDescendant("greeting");  
            if (foundGreeting)  
            {  
                inputValue = inputReader.ReadInnerXml();  
            }  
        }  
  
        int arrayCount = this.Connection.ConnectionFactory.Adapter.Count;  
  
        // ** Generate the WCF response  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        for(int i = 0; i < arrayCount; i++ )  
        {  
            ComplexQualifiedType cqtResult = om.OperationResult.QualifiedType as ComplexQualifiedType;  
            StructuredTypeMetadata tmResult = MetadataLookup.GetTypeDefinition(cqtResult.TypeId, timeout) as StructuredTypeMetadata;  
            replywriter.WriteStartElement(tmResult.TypeName, tmResult.TypeNamespace);  
            replywriter.WriteRaw(inputValue);  
            replywriter.WriteEndElement();  
        }  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
6.  现在，添加**ExecuteEchoCustomGreetingFromFile**方法以处理 EchoCustomGreetingFromFile 操作。 此帮助器函数读取 WCF 请求消息，从指定的文件，读取消息，然后生成 WCF 响应消息使用的格式：\<EchoGreetingsFromFileResponse\>\<EchoGreetingsFromFileResult\>...消息。\</EchoGreetingsFromFileResult\>\</EchoGreetingsFromFileResponse\>。  
  
    ```csharp  
    private Message ExecuteEchoCustomGreetingFromFile(OperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // NOTE this method doesn't return response in upper case based on   
        // connection property echoInUpperCase  
  
        // ** Read the WCF request  
        Uri path;  
        using (XmlDictionaryReader inputReader = message.GetReaderAtBodyContents())  
        {  
            inputReader.MoveToContent();  
            inputReader.ReadStartElement(om.DisplayName);  
            inputReader.MoveToContent();  
            // The path contains the location of the XML file that contains the instance of Greeting object to read   
            path = new Uri(inputReader.ReadElementContentAsString());  
            inputReader.ReadEndElement();  
        }  
  
        // ** Generate the WCF response  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        // Read the XML file and set it to the reply writer here  
        FileStream stream = new FileStream(path.AbsolutePath, FileMode.Open);  
        XmlDictionaryReader xdr = XmlDictionaryReader.CreateTextReader(stream, new XmlDictionaryReaderQuotas());  
        xdr.MoveToContent();  
        string rawGreeting = xdr.ReadInnerXml();  
        replywriter.WriteRaw(rawGreeting);  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
7.  在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。  
  
8.  在“生成”  菜单上，单击“生成解决方案” 。 它应编译错误。 如果没有，请确保您已按照上述每个步骤。 现在，可以安全地关闭 Visual Studio，或继续[步骤 8:实现 Echo 适配器的同步入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您学习了如何实现 Echo 适配器的同步出站消息传递功能。 若要执行此操作，应实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`方法的`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`。 此方法分析传入的 WCF 请求消息，执行必要的操作，然后生成传出的 WCF 响应消息。  
  
 具体而言，对于传入 WCF 请求消息，使用 WCF`System.ServiceModel.Channels.Message.Headers.Action%2A`通过进一步理解传入的消息正文的基本结构检索输入的消息操作。 对于传出的 WCF 响应消息，则使用`Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`通过进一步理解传出的消息正文的基本结构检索输出消息操作。 分析和编写 WCF 消息，当您使用`System.Xml.XmlDictionaryReader`到读取传入的 WCF 请求消息并使用`System.Xml.XmlWriter`写入传出 WCF 响应消息。  
  
## <a name="next-steps"></a>后续步骤  
生成并部署 Echo 适配器。  
  
## <a name="see-also"></a>请参阅  
 [步骤 6：实现 Echo 适配器的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)   
 [步骤 8：实现 Echo 适配器的同步入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)