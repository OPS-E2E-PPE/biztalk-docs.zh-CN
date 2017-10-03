---
title: "步骤 7： 为 Echo 适配器实现同步的出站处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4da4d987-03c4-4817-850b-4c5ca2ba7e62
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e1ccddee7bb7b08ec363fabd9b7e061cd41357d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter"></a><span data-ttu-id="0a128-102">步骤 7： 为 Echo 适配器实现同步的出站处理程序</span><span class="sxs-lookup"><span data-stu-id="0a128-102">Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter</span></span>
<span data-ttu-id="0a128-103">![9 的第 7 步](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")</span><span class="sxs-lookup"><span data-stu-id="0a128-103">![Step 7 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")</span></span>  
  
 <span data-ttu-id="0a128-104">**完成时间：** 30 分钟</span><span class="sxs-lookup"><span data-stu-id="0a128-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="0a128-105">在此步骤中，你可以实现 Echo 适配器出站的同步功能。</span><span class="sxs-lookup"><span data-stu-id="0a128-105">In this step, you implement the synchronous outbound capability of the Echo adapter.</span></span> <span data-ttu-id="0a128-106">根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，来支持同步的出站功能，则必须实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`接口。</span><span class="sxs-lookup"><span data-stu-id="0a128-106">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support the synchronous outbound capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` interface.</span></span> <span data-ttu-id="0a128-107">为 Echo 适配器[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成一个调用 EchoAdapterOutboundHandler 的派生的类。</span><span class="sxs-lookup"><span data-stu-id="0a128-107">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates one derived class called EchoAdapterOutboundHandler.</span></span>  
  
 <span data-ttu-id="0a128-108">在以下部分中，你将更新 EchoAdapterOutboundHandler 类，以获取更好地了解如何实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`、 如何分析传入的 WCF 请求消息，以及如何生成传出的 WCF 响应消息。</span><span class="sxs-lookup"><span data-stu-id="0a128-108">In the following sections, you update the EchoAdapterOutboundHandler class to get a better understanding of how to implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`, how to parse the incoming WCF request message, and how to generate outgoing WCF response messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a128-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="0a128-109">Prerequisites</span></span>  
 <span data-ttu-id="0a128-110">在开始此步骤之前，你必须已成功完成[步骤 6： 为 Echo 适配器实现的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0a128-110">Before you begin this step, you must have successfully completed [Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="0a128-111">基本熟悉`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`也是有帮助。</span><span class="sxs-lookup"><span data-stu-id="0a128-111">A basic familiarity with `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` is also helpful.</span></span>  
  
## <a name="the-ioutboundhandler-interface"></a><span data-ttu-id="0a128-112">IOutboundHandler 接口</span><span class="sxs-lookup"><span data-stu-id="0a128-112">The IOutboundHandler Interface</span></span>  
 <span data-ttu-id="0a128-113">`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`定义为：</span><span class="sxs-lookup"><span data-stu-id="0a128-113">The `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` is defined as:</span></span>  
  
```  
public interface IOutboundHandler : IConnectionHandler, IDisposable  
{  
    Message Execute(Message message, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="0a128-114">`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`方法的调用，目标系统上的相应方法来执行传入的 WCF 请求消息，然后返回一个传出的 WCF 响应消息。</span><span class="sxs-lookup"><span data-stu-id="0a128-114">The `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method executes the incoming WCF request message by invoking the corresponding method on the target system and then returns an outgoing WCF response message.</span></span> <span data-ttu-id="0a128-115">下表中列出了其参数的定义：</span><span class="sxs-lookup"><span data-stu-id="0a128-115">The definitions of its parameters are listed in the following table:</span></span>  
  
|<span data-ttu-id="0a128-116">**参数**</span><span class="sxs-lookup"><span data-stu-id="0a128-116">**Parameter**</span></span>|<span data-ttu-id="0a128-117">**定义**</span><span class="sxs-lookup"><span data-stu-id="0a128-117">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="0a128-118">message</span><span class="sxs-lookup"><span data-stu-id="0a128-118">message</span></span>|<span data-ttu-id="0a128-119">传入的 WCF 请求消息。</span><span class="sxs-lookup"><span data-stu-id="0a128-119">Incoming WCF request message.</span></span>|  
|<span data-ttu-id="0a128-120">timeout</span><span class="sxs-lookup"><span data-stu-id="0a128-120">timeout</span></span>|<span data-ttu-id="0a128-121">应在其中完成此操作的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0a128-121">Time interval within which this operation should be completed.</span></span> <span data-ttu-id="0a128-122">此操作应引发`System.TimeoutException`如果在操作完成前超出指定的超时。</span><span class="sxs-lookup"><span data-stu-id="0a128-122">The operation should throw a `System.TimeoutException` if the specified timeout is exceeded before the operation is completed.</span></span>|  
  
 <span data-ttu-id="0a128-123">如果你的适配器正在执行 （没有任何你适配器所需的响应消息） 单向发送，此方法应返回 null。</span><span class="sxs-lookup"><span data-stu-id="0a128-123">If your adapter is performing a one-way send (there is no response message expected by your adapter), this method should return null.</span></span> <span data-ttu-id="0a128-124">如果你的适配器正在执行的双向操作`Microsoft.ServiceModel.Channels.Common.OperationResult`等于`Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`，此方法返回包含正文为空的 WCF 响应消息。</span><span class="sxs-lookup"><span data-stu-id="0a128-124">If your adapter is performing a two-way operation with `Microsoft.ServiceModel.Channels.Common.OperationResult` equal to `Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`, this method returns a WCF response message with an empty body.</span></span> <span data-ttu-id="0a128-125">否则，它应返回的 WCF 响应消息的正文包含中的值`Microsoft.ServiceModel.Channels.Common.OperationResult`对象。</span><span class="sxs-lookup"><span data-stu-id="0a128-125">Otherwise, it should return the WCF response message with a body that contains the values in the `Microsoft.ServiceModel.Channels.Common.OperationResult` object.</span></span> <span data-ttu-id="0a128-126">若要构造响应操作字符串，使用`Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`。</span><span class="sxs-lookup"><span data-stu-id="0a128-126">To construct the response action string, use `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`.</span></span>  
  
## <a name="echo-adapter-synchronous-outbound"></a><span data-ttu-id="0a128-127">回显适配器同步出站</span><span class="sxs-lookup"><span data-stu-id="0a128-127">Echo Adapter Synchronous Outbound</span></span>  
 <span data-ttu-id="0a128-128">根据目标系统的操作，有很多种实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`方法。</span><span class="sxs-lookup"><span data-stu-id="0a128-128">Depending on your target system's operations, there are many ways to implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method.</span></span> <span data-ttu-id="0a128-129">对于 Echo 适配器中，有三个出站操作，并且其分配的节点 Id 和显示名称是：</span><span class="sxs-lookup"><span data-stu-id="0a128-129">For the Echo adapter, there are three outbound operations, and their assigned node IDs and display names are:</span></span>  
  
-   <span data-ttu-id="0a128-130">字符串 [] EchoStrings （字符串数据），节点 ID = Echo/EchoString，显示名称 = EchoString</span><span class="sxs-lookup"><span data-stu-id="0a128-130">string[] EchoStrings(string data), node ID = Echo/EchoString, display name=EchoString</span></span>  
  
-   <span data-ttu-id="0a128-131">问候语 [] EchoGreetings(Greeting greeting)，节点 ID = Echo/EchoGreetings，显示名称 = EchoGreetings</span><span class="sxs-lookup"><span data-stu-id="0a128-131">Greeting[] EchoGreetings(Greeting greeting), node ID=Echo/EchoGreetings, display name=EchoGreetings</span></span>  
  
-   <span data-ttu-id="0a128-132">CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath)，nodeID = Echo/EchoCustomGreetingFromFile，显示名称 = EchoGreetings</span><span class="sxs-lookup"><span data-stu-id="0a128-132">CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath), nodeID=Echo/EchoCustomGreetingFromFile, display name=EchoGreetings</span></span>  
  
 <span data-ttu-id="0a128-133">若要正确分析传入的 WCF 请求消息并生成传出的 WCF 响应消息，你必须熟悉使用 SOAP 消息中的以下元素[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0a128-133">To correctly parse the incoming WCF request message and generate the outgoing WCF response message, you must be familiar with the following elements within the SOAP message used by the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:</span></span>  
  
 <span data-ttu-id="0a128-134">传入的 WCF 请求消息：</span><span class="sxs-lookup"><span data-stu-id="0a128-134">For the incoming WCF request message:</span></span>  
  
-   <span data-ttu-id="0a128-135">WCF 输入消息操作 = 操作的节点 ID</span><span class="sxs-lookup"><span data-stu-id="0a128-135">The WCF input message action = operation's node ID</span></span>  
  
-   <span data-ttu-id="0a128-136">传入的消息正文 = 开始正文的元素是\<displayname >\<参数名称 > {数据}\</parameter 名称 >\</displayname ></span><span class="sxs-lookup"><span data-stu-id="0a128-136">Incoming message body = The start element of the body is \<displayname>\<parameter name>{data}\</parameter name>\</displayname></span></span>  
  
 <span data-ttu-id="0a128-137">传出的 WCF 响应消息：</span><span class="sxs-lookup"><span data-stu-id="0a128-137">For the outgoing WCF response message:</span></span>  
  
-   <span data-ttu-id="0a128-138">WCF 输出消息操作 = 操作的节点 ID +"/ 响应"</span><span class="sxs-lookup"><span data-stu-id="0a128-138">The WCF output message action = operation's node ID + "/response"</span></span>  
  
-   <span data-ttu-id="0a128-139">传出消息正文 = 开始正文的元素是\<displayname +"响应"> 后, 跟\<displayname +"结果">，并且后跟\<数据类型 > 数据\</datatype >\</displayname +"结果 >\</displayname +"响应"></span><span class="sxs-lookup"><span data-stu-id="0a128-139">Outgoing message body = The start element of the body is \<displayname + "Response">, followed by \<displayname + "Result">, and followed by the \<datatype>data\</datatype>\</displayname+"Result>\</displayname + "Response"></span></span>  
  
 <span data-ttu-id="0a128-140">例如，操作**string [] EchoStrings （字符串数据）**，节点 ID = Echo/EchoStrings，并显示名称 = EchoStrings:</span><span class="sxs-lookup"><span data-stu-id="0a128-140">For example, operation **string[] EchoStrings(string data)**, node ID = Echo/EchoStrings, and display name= EchoStrings:</span></span>  
  
 <span data-ttu-id="0a128-141">WCF 输入消息操作 ="Echo/EchoStrings";和输入的正文如下所示，因为参数名称为`data`。</span><span class="sxs-lookup"><span data-stu-id="0a128-141">The WCF input message action = "Echo/EchoStrings"; and the input body looks as follows, since the parameter name is `data`.</span></span>  
  
```  
<EchoStrings>  
<data>{data}  
</data>  
</EchoStrings>  
```  
  
 <span data-ttu-id="0a128-142">WCF 输出消息操作 ="EchoStrings/回显/响应";和输出正文如下所示，由于数据类型为**字符串**。</span><span class="sxs-lookup"><span data-stu-id="0a128-142">The WCF output message action = "Echo/EchoStrings/response"; and the output body looks as follows, since the data type is **string**.</span></span>  
  
```  
<EchoStringsResponse>  
<EchoStringsResult>  
<string>{data}</string>  
</EchoStringsResult>  
</EchoStringsResponse>  
```  
  
 <span data-ttu-id="0a128-143">在分析传入的 WCF 请求消息时，你可以使用`System.Xml.XmlDictionaryReader`要检索 WCF 消息中; 中的内容，在撰写 WCF 响应消息时，您可以使用`System.Xml.XmlWriter`若要这样做。</span><span class="sxs-lookup"><span data-stu-id="0a128-143">When parsing the incoming WCF request message, you can use the `System.Xml.XmlDictionaryReader` to retrieve content within the WCF message; when composing the WCF response message, you can use the `System.Xml.XmlWriter` to do so.</span></span>  
  
## <a name="implementing-the-ioutboundhandler"></a><span data-ttu-id="0a128-144">实现 IOutboundHandler</span><span class="sxs-lookup"><span data-stu-id="0a128-144">Implementing the IOutboundHandler</span></span>  
 <span data-ttu-id="0a128-145">实现的 Execute 方法`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`。</span><span class="sxs-lookup"><span data-stu-id="0a128-145">You implement the Execute method of the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`.</span></span> <span data-ttu-id="0a128-146">首先，获取`Microsoft.ServiceModel.Channels.Common.OperationMetadata`对象基于输入的消息的操作。</span><span class="sxs-lookup"><span data-stu-id="0a128-146">First, gets a `Microsoft.ServiceModel.Channels.Common.OperationMetadata` object based on the input message action.</span></span> <span data-ttu-id="0a128-147">然后，分析传入的 WCF 消息并执行基于每个操作的关联的 echo 功能。</span><span class="sxs-lookup"><span data-stu-id="0a128-147">Then, parses the incoming WCF message and executes the associated echo functionality based on each operation.</span></span> <span data-ttu-id="0a128-148">最后，通过使用传出的消息正文的格式创建传出的 WCF 响应消息。</span><span class="sxs-lookup"><span data-stu-id="0a128-148">Finally, creates an outgoing WCF response message by using the format of outgoing message body.</span></span>  
  
#### <a name="to-implement-the-execute-method-of-the-echoadapteroutboundhandler-class"></a><span data-ttu-id="0a128-149">若要实现 EchoAdapterOutboundHandler 类的 Execute 方法</span><span class="sxs-lookup"><span data-stu-id="0a128-149">To implement the Execute method of the EchoAdapterOutboundHandler class</span></span>  
  
1.  <span data-ttu-id="0a128-150">在解决方案资源管理器中，双击**EchoAdapterOutboundHandler.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="0a128-150">In Solution Explorer, double-click the **EchoAdapterOutboundHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="0a128-151">在 Visual Studio 编辑器中，添加以下两个使用到现有的 using 指令集的指令。</span><span class="sxs-lookup"><span data-stu-id="0a128-151">In the Visual Studio editor, add the following two using directives to the existing set of using directives.</span></span>  
  
    ```csharp  
    using System.Xml;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="0a128-152">内部**执行**方法，用以下代码替换现有的逻辑：</span><span class="sxs-lookup"><span data-stu-id="0a128-152">Inside the **Execute** method, replace the existing logic with the following:</span></span>  
  
    1.  <span data-ttu-id="0a128-153">此逻辑验证请求的操作。</span><span class="sxs-lookup"><span data-stu-id="0a128-153">This logic verifies the requested operation.</span></span>  
  
    2.  <span data-ttu-id="0a128-154">它获取`Microsoft.ServiceModel.Channels.Common.OperationMetadata`对象基于 SOAP 的输入的消息操作。</span><span class="sxs-lookup"><span data-stu-id="0a128-154">It gets the `Microsoft.ServiceModel.Channels.Common.OperationMetadata` object based on the SOAP input message action.</span></span>  
  
    3.  <span data-ttu-id="0a128-155">它根据操作类型，分析 WCF 请求消息并调用适当的操作。</span><span class="sxs-lookup"><span data-stu-id="0a128-155">Based on the action type, it parses the WCF request message and invokes the appropriate operation.</span></span>  
  
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
  
4.  <span data-ttu-id="0a128-156">现在添加**ExecuteEchoStrings**方法以处理字符串 [] EchoStrings （字符串数据） 操作。</span><span class="sxs-lookup"><span data-stu-id="0a128-156">Now add the **ExecuteEchoStrings** method to handle the string[] EchoStrings(string data) operation.</span></span> <span data-ttu-id="0a128-157">此帮助器函数将读取 WCF 请求消息，检查以 echoInUpperCase URI 元素是否已设置为 true;如果是这样，它将输入的字符串转换为大写形式计数变量指示多次。</span><span class="sxs-lookup"><span data-stu-id="0a128-157">This helper function reads the WCF request message, checks to see if the echoInUpperCase URI element is set to true; if so, it converts the input string to upper case as many times as the count variable indicates.</span></span> <span data-ttu-id="0a128-158">然后，它将生成 WCF 响应消息的格式： \<EchoStringsResponse >\<EchoStringResult >\<字符串 > {数据}\</字符串 >\</EchoStringResult >\</EchoStringsResponse >。</span><span class="sxs-lookup"><span data-stu-id="0a128-158">Then, it generates the WCF response message in the format of: \<EchoStringsResponse>\<EchoStringResult>\<string>{data}\</string>\</EchoStringResult>\</EchoStringsResponse>.</span></span>  
  
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
  
5.  <span data-ttu-id="0a128-159">继续通过添加**ExecuteEchoGreetings**方法以处理 EchoGreetings 操作。</span><span class="sxs-lookup"><span data-stu-id="0a128-159">Continue by adding the **ExecuteEchoGreetings** method to handle the EchoGreetings operation.</span></span> <span data-ttu-id="0a128-160">此帮助器函数将读取 WCF 请求消息、 操作以及类型解析`ResolveOperationMetadata`和`ResolveTypeMetadata`方法`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`接口，，然后生成 WCF 响应消息使用的格式： \<EchoGreetingsResponse >\<EchoGreetingsResult >...消息...\</EchoGreetingsResult >\</EchoGreetingsResponse >。</span><span class="sxs-lookup"><span data-stu-id="0a128-160">This helper function reads the WCF request message, resolves operation and type by the `ResolveOperationMetadata` and `ResolveTypeMetadata` methods of the `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` interface, and then generates the WCF response message using the format of: \<EchoGreetingsResponse>\<EchoGreetingsResult>…message…\</EchoGreetingsResult>\</EchoGreetingsResponse>.</span></span>  
  
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
  
6.  <span data-ttu-id="0a128-161">现在添加**ExecuteEchoCustomGreetingFromFile**方法以处理 EchoCustomGreetingFromFile 操作。</span><span class="sxs-lookup"><span data-stu-id="0a128-161">Now add the **ExecuteEchoCustomGreetingFromFile** method to handle the EchoCustomGreetingFromFile operation.</span></span> <span data-ttu-id="0a128-162">此帮助器函数将读取 WCF 请求消息中，从指定的文件中，读取该消息，然后生成 WCF 响应消息使用的格式： \<EchoGreetingsFromFileResponse >\<EchoGreetingsFromFileResult>...消息...\</EchoGreetingsFromFileResult >\</EchoGreetingsFromFileResponse >。</span><span class="sxs-lookup"><span data-stu-id="0a128-162">This helper function reads the WCF request message, reads the message from the specified file, and then generates the  WCF response message using the format of: \<EchoGreetingsFromFileResponse>\<EchoGreetingsFromFileResult>…message…\</EchoGreetingsFromFileResult>\</EchoGreetingsFromFileResponse>.</span></span>  
  
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
  
7.  <span data-ttu-id="0a128-163">在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="0a128-163">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
8.  <span data-ttu-id="0a128-164">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="0a128-164">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="0a128-165">它应编译错误。</span><span class="sxs-lookup"><span data-stu-id="0a128-165">It should compile without errors.</span></span> <span data-ttu-id="0a128-166">如果没有，请确保您已按照上述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="0a128-166">If not, ensure that you have followed every step above.</span></span> <span data-ttu-id="0a128-167">现在，你可以安全地关闭 Visual Studio 或继续[步骤 8： 为 Echo 适配器实现同步入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0a128-167">Now, you can safely close Visual Studio or continue on to [Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="0a128-168">未我只需做什么？</span><span class="sxs-lookup"><span data-stu-id="0a128-168">What Did I Just Do?</span></span>  
 <span data-ttu-id="0a128-169">在此步骤中，您学习了如何实现同步 Echo 适配器的出站消息传送功能。</span><span class="sxs-lookup"><span data-stu-id="0a128-169">In this step, you learned how to implement the synchronous outbound messaging functionality of the Echo adapter.</span></span> <span data-ttu-id="0a128-170">为此，你可以实现`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`方法`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`。</span><span class="sxs-lookup"><span data-stu-id="0a128-170">To do so, you implemented the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method of the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`.</span></span> <span data-ttu-id="0a128-171">此方法分析传入的 WCF 请求消息，执行必要的操作，然后生成传出的 WCF 响应消息。</span><span class="sxs-lookup"><span data-stu-id="0a128-171">This method parsed the incoming WCF request message, performed the necessary actions, and then generated the outgoing WCF response message.</span></span>  
  
 <span data-ttu-id="0a128-172">具体而言，对于传入的 WCF 请求消息，使用 WCF`System.ServiceModel.Channels.Message.Headers.Action%2A`检索的输入的消息操作的进一步了解传入的消息正文的基本结构。</span><span class="sxs-lookup"><span data-stu-id="0a128-172">Specifically, for the incoming WCF request message, you used WCF `System.ServiceModel.Channels.Message.Headers.Action%2A` to retrieve the input message action by further understanding the basic structure of the incoming message body.</span></span> <span data-ttu-id="0a128-173">对于传出的 WCF 响应消息，你使用`Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`检索输出消息操作的进一步了解传出的消息正文的基本结构。</span><span class="sxs-lookup"><span data-stu-id="0a128-173">For the outgoing WCF response message, you used `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A` to retrieve the output message action by further understanding the basic structure of the outgoing message body.</span></span> <span data-ttu-id="0a128-174">分析和编写 WCF 消息，当你使用`System.Xml.XmlDictionaryReader`到读取传入的 WCF 请求消息和使用`System.Xml.XmlWriter`将传出的 WCF 响应消息写入。</span><span class="sxs-lookup"><span data-stu-id="0a128-174">When parsing and composing WCF messages, you used `System.Xml.XmlDictionaryReader` to read the incoming WCF request message and used `System.Xml.XmlWriter` to write an outgoing WCF response message.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0a128-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0a128-175">Next Steps</span></span>  
<span data-ttu-id="0a128-176">生成和部署 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="0a128-176">Build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a128-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a128-177">See Also</span></span>  
 <span data-ttu-id="0a128-178">[步骤 6： 为 Echo 适配器实现的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0a128-178">[Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="0a128-179">步骤 8： 为 Echo 适配器实现同步的入站处理程序</span><span class="sxs-lookup"><span data-stu-id="0a128-179">Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)