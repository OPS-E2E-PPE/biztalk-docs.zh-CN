---
title: 指定 WCF 适配器的消息正文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, SOAP messages
- messages, WCF adapters
- WCF adapters, message bodies
- SOAP messages, WCF adapters
ms.assetid: b20364b7-0365-4636-b4d6-bde9c69b8dcb
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32e62da213c4fceaf54773c2fe44584f43de9155
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972136"
---
# <a name="specifying-the-message-body-for-the-wcf-adapters"></a><span data-ttu-id="32d27-102">指定 WCF 适配器的消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-102">Specifying the Message Body for the WCF Adapters</span></span>
<span data-ttu-id="32d27-103">可以使用**消息**选项卡中的 WCF 适配器以指定如何从传入 SOAP 消息提取 BizTalk 消息正文和 BizTalk 消息正文的方式放置在传出 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="32d27-103">You can use the **Messages** tab in the WCF adapters to specify how the BizTalk message body is extracted from an incoming SOAP message, and how the BizTalk message body is placed in an outgoing SOAP message.</span></span>  

## <a name="specifying-how-the-biztalk-message-body-is-extracted-from-an-incoming-soap-message"></a><span data-ttu-id="32d27-104">指定如何从传入 SOAP 消息提取 BizTalk 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-104">Specifying How the BizTalk Message Body Is Extracted from an Incoming SOAP Message</span></span>  
 <span data-ttu-id="32d27-105">可以控制如何从通过 WCF 适配器传入的 SOAP 消息创建入站 BizTalk 消息正文。</span><span class="sxs-lookup"><span data-stu-id="32d27-105">You can control how to create the inbound BizTalk message body from the SOAP messages incoming through the WCF adapters.</span></span> <span data-ttu-id="32d27-106">下图显示**消息**选项卡的 Wcf-netnamedpipe 接收适配器和发送适配器作为示例。</span><span class="sxs-lookup"><span data-stu-id="32d27-106">The following figures show the **Messages** tabs of the WCF-NetNamedPipe receive adapter and send adapter as examples.</span></span>  

 <span data-ttu-id="32d27-107">![消息选项卡中的 WCF 接收适配器](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")</span><span class="sxs-lookup"><span data-stu-id="32d27-107">![The Messages tab in the WCF receive adapters](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")</span></span>  

 <span data-ttu-id="32d27-108">![WCF 中的消息选项卡发送适配器](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")</span><span class="sxs-lookup"><span data-stu-id="32d27-108">![The Messages tab in the WCF send adapters](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")</span></span>  

 <span data-ttu-id="32d27-109">若要指定如何创建 BizTalk 消息正文，请选择中的下列选项之一**入站 BizTalk 消息正文**上面各图中的部分：</span><span class="sxs-lookup"><span data-stu-id="32d27-109">To specify how to create the BizTalk message body, select one of the following options in the **Inbound BizTalk message body** section in the preceding figures:</span></span>  

- <span data-ttu-id="32d27-110">**信封--整个\<soap: Envelope\>**。</span><span class="sxs-lookup"><span data-stu-id="32d27-110">**Envelope -- entire \<soap:Envelope\>**.</span></span> <span data-ttu-id="32d27-111">使用 SOAP**信封**传入消息创建 BizTalk 消息正文部分的元素。</span><span class="sxs-lookup"><span data-stu-id="32d27-111">Uses the SOAP **Envelope** element of an incoming message to create the BizTalk message body part.</span></span> <span data-ttu-id="32d27-112">整个传入消息将成为 BizTalk 消息正文。</span><span class="sxs-lookup"><span data-stu-id="32d27-112">The entire incoming message becomes the BizTalk message body.</span></span> <span data-ttu-id="32d27-113">使用此选项可以创建并入了所有标头的 BizTalk 消息正文。</span><span class="sxs-lookup"><span data-stu-id="32d27-113">Use this option to create the BizTalk message body incorporating all the headers.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="32d27-114">SOAP 标头放置在消息上下文中，但不会自动升级。</span><span class="sxs-lookup"><span data-stu-id="32d27-114">The SOAP headers are placed in the message context, but they are not promoted automatically.</span></span> <span data-ttu-id="32d27-115">可以在自定义管道组件中进行升级。</span><span class="sxs-lookup"><span data-stu-id="32d27-115">Promotion can be done in a custom pipeline component.</span></span>  

- <span data-ttu-id="32d27-116">**--正文\<soap: Body\>元素**。</span><span class="sxs-lookup"><span data-stu-id="32d27-116">**Body -- contents of \<soap:Body\> element**.</span></span> <span data-ttu-id="32d27-117">使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。</span><span class="sxs-lookup"><span data-stu-id="32d27-117">Uses the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part.</span></span> <span data-ttu-id="32d27-118">如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="32d27-118">If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.</span></span>  

- <span data-ttu-id="32d27-119">**路径-按正文路径定位内容**。</span><span class="sxs-lookup"><span data-stu-id="32d27-119">**Path -- content located by body path**.</span></span> <span data-ttu-id="32d27-120">使用中的正文路径表达式**正文路径表达式**文本框中，用于创建 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="32d27-120">Uses the body path expression in the **Body path expression** text box to create the BizTalk message body part.</span></span> <span data-ttu-id="32d27-121">针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。</span><span class="sxs-lookup"><span data-stu-id="32d27-121">The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message.</span></span> <span data-ttu-id="32d27-122">当传入消息有二进制数据时，可以使用此选项让 BizTalk 消息正文仅包括二进制数据而没有任何标记。</span><span class="sxs-lookup"><span data-stu-id="32d27-122">When incoming messages have binary data, you can use this option for the BizTalk message body to include only the binary data without any tags.</span></span>  

  <span data-ttu-id="32d27-123">当**路径-按正文路径定位内容**选项，则**节点编码**属性可以配置为指定的正文路径表达式中指定的节点所需编码类型**正文路径表达式**文本框。</span><span class="sxs-lookup"><span data-stu-id="32d27-123">When the **Path -- content located by body path** option is selected, the **Node encoding** property can be configured to specify the expected encoding type for the node specified by the body path expression in the **Body path expression** text box.</span></span> <span data-ttu-id="32d27-124">如果正文路径表达式与多个元素匹配，则仅使用第一个匹配的元素。</span><span class="sxs-lookup"><span data-stu-id="32d27-124">If the body path expression matches more than one element, only the first matched element is used.</span></span>  

> [!NOTE]
>  <span data-ttu-id="32d27-125">有关**正文路径表达式**属性，仅支持 XML 的适用于只进处理的表达式的 XPath。</span><span class="sxs-lookup"><span data-stu-id="32d27-125">For the **body path expression** property, only the XPath expressions suitable for forward-only processing of XML are supported.</span></span> <span data-ttu-id="32d27-126">有关可用于此属性的 XPath 表达式的详细信息，请参阅"最佳的两个领域:: 组合 XPath 与 XmlReader"网址[ http://go.microsoft.com/fwlink/?LinkID=75701 ](http://go.microsoft.com/fwlink/?LinkID=75701)。</span><span class="sxs-lookup"><span data-stu-id="32d27-126">For more information about the XPath expressions available for this property, see "The Best of Both Worlds: Combining XPath with the XmlReader" at [http://go.microsoft.com/fwlink/?LinkID=75701](http://go.microsoft.com/fwlink/?LinkID=75701).</span></span>  

 <span data-ttu-id="32d27-127">如果**路径-按正文路径定位内容**选择选项和**节点编码**属性设置为**字符串**，则 WCF 适配器期望匹配的节点具有 utf-8编码的字符数据。</span><span class="sxs-lookup"><span data-stu-id="32d27-127">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **String**, the WCF adapters expect that the matched node has UTF-8 encoded character data.</span></span> <span data-ttu-id="32d27-128">如果传入消息包含转义字符数据的 XML 特殊字符，如\<和\>，创建 BizTalk 消息正文部分时，WCF 适配器会还原转义的字符数据。</span><span class="sxs-lookup"><span data-stu-id="32d27-128">If the incoming messages include escaped character data for the XML special characters such as \< and \>, the WCF adapters restore the escaped character data when creating the BizTalk message body part.</span></span> <span data-ttu-id="32d27-129">例如，如果匹配的节点已转义字符数据，如**&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** WCF 适配器会创建**\<FirstName\>CONTOSO\</FirstName\>** 在入站 BizTalk 消息正文。</span><span class="sxs-lookup"><span data-stu-id="32d27-129">For example, if the matched node has escaped character data such as **&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** the WCF adapters create **\<FirstName\>CONTOSO\</FirstName\>** in the inbound BizTalk message body.</span></span>  

 <span data-ttu-id="32d27-130">如果**路径-按正文路径定位内容**选择选项和**节点编码**属性设置为**十六进制**或者**Base64**、匹配的节点可以有一个有效**BinHex**或**Base64**序列。</span><span class="sxs-lookup"><span data-stu-id="32d27-130">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **Hex** or **Base64**, the matched node can have a valid **BinHex** or **Base64** sequence.</span></span> <span data-ttu-id="32d27-131">如果匹配的节点具有无效的序列，WCF 客户端将接收**FaultException**、 在您的 BizTalk Server 计算机上的事件日志中记录一条错误消息和不挂起任何消息。</span><span class="sxs-lookup"><span data-stu-id="32d27-131">If the matched node has an invalid sequence, the WCF client receives **FaultException**, an error message is logged in the event log on your BizTalk Server computer, and no message is suspended.</span></span>  

 <span data-ttu-id="32d27-132">如果**路径-按正文路径定位内容**选择选项和**节点编码**属性设置为**XML**，WCF 适配器会创建与 BizTalk 消息正文中的正文路径表达式所选择的节点的外部 XML**正文路径表达式**文本框。</span><span class="sxs-lookup"><span data-stu-id="32d27-132">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **XML**, the WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in the **Body path expression** text box.</span></span>  

 <span data-ttu-id="32d27-133">如果匹配的节点不具有作为编码数据中指定**节点编码**属性，创建一个空的入站的 BizTalk 消息正文。</span><span class="sxs-lookup"><span data-stu-id="32d27-133">If the matched node does not have data encoded as specified in the **Node encoding** property, an empty inbound BizTalk message body is created.</span></span>  

 <span data-ttu-id="32d27-134">例如，假定 WCF 发送适配器从 WCF 客户端接收以下 SOAP 消息：</span><span class="sxs-lookup"><span data-stu-id="32d27-134">For example, suppose the WCF send adapters receive the following SOAP message from WCF clients:</span></span>  

```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/OrderRefresh</a:Action>   
    <a:MessageID>urn:uuid:59e74507-66d0-4d50-be70-c3ec248b6f78</a:MessageID>   
    <a:ReplyTo>  
       <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>   
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>   
  </s:Header>  
  <s:Body>  
    <Order xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
     <OrderDetail>  
       <CustomerID>CONTOSO</CustomerID>   
       <OrderID>00000000</OrderID>   
     </OrderDetail>  
    </Order>  
  </s:Body>  
</s:Envelope>  
```  

 <span data-ttu-id="32d27-135">如果你配置**入站 BizTalk 消息正文**部分下的表中，前面的传入 SOAP 消息中所示将成为入站的 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="32d27-135">If you configure the **Inbound BizTalk message body** section as shown in the following table, the previous incoming SOAP message becomes the inbound BizTalk message body part.</span></span>  

|<span data-ttu-id="32d27-136">入站 BizTalk 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-136">Inbound BizTalk message body</span></span>|<span data-ttu-id="32d27-137">正文路径表达式</span><span class="sxs-lookup"><span data-stu-id="32d27-137">Body path expression</span></span>|<span data-ttu-id="32d27-138">节点编码</span><span class="sxs-lookup"><span data-stu-id="32d27-138">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="32d27-139">**信封--整个\<soap: Envelope\>**</span><span class="sxs-lookup"><span data-stu-id="32d27-139">**Envelope -- entire \<soap:Envelope\>**</span></span>|<span data-ttu-id="32d27-140">N/A</span><span class="sxs-lookup"><span data-stu-id="32d27-140">N/A</span></span>|<span data-ttu-id="32d27-141">N/A</span><span class="sxs-lookup"><span data-stu-id="32d27-141">N/A</span></span>|  

 <span data-ttu-id="32d27-142">如果你配置**BizTalk 消息正文**部分下表中所示，WCF 适配器会创建入站的 BizTalk 消息正文部分以仅包含**顺序**中的上一个元素传入的 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="32d27-142">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters create the inbound BizTalk message body part to contain only the **Order** element in the previous incoming SOAP message.</span></span>  

|<span data-ttu-id="32d27-143">入站 BizTalk 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-143">Inbound BizTalk message body</span></span>|<span data-ttu-id="32d27-144">正文路径表达式</span><span class="sxs-lookup"><span data-stu-id="32d27-144">Body path expression</span></span>|<span data-ttu-id="32d27-145">节点编码</span><span class="sxs-lookup"><span data-stu-id="32d27-145">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="32d27-146">**--正文\<soap: Body\>元素**</span><span class="sxs-lookup"><span data-stu-id="32d27-146">**Body -- contents of \<soap:Body\> element**</span></span>|<span data-ttu-id="32d27-147">N/A</span><span class="sxs-lookup"><span data-stu-id="32d27-147">N/A</span></span>|<span data-ttu-id="32d27-148">N/A</span><span class="sxs-lookup"><span data-stu-id="32d27-148">N/A</span></span>|  

 <span data-ttu-id="32d27-149">如果你配置**BizTalk 消息正文**部分下表中所示，则 WCF 适配器期望正文路径表达式匹配的传入节点将具有 utf-8 编码字符数据。</span><span class="sxs-lookup"><span data-stu-id="32d27-149">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters expect that the incoming node that the body path expression matches will have UTF-8 encoded character data.</span></span>  

|<span data-ttu-id="32d27-150">入站 BizTalk 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-150">Inbound BizTalk message body</span></span>|<span data-ttu-id="32d27-151">正文路径表达式</span><span class="sxs-lookup"><span data-stu-id="32d27-151">Body path expression</span></span>|<span data-ttu-id="32d27-152">节点编码</span><span class="sxs-lookup"><span data-stu-id="32d27-152">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="32d27-153">**路径-按正文路径定位内容**</span><span class="sxs-lookup"><span data-stu-id="32d27-153">**Path -- content located by body path**</span></span>|<span data-ttu-id="32d27-154">/ \* [local-name = Order] /\*[本地名称 （) = OrderDetail] /\*[本地名称 （) = CustomerID]</span><span class="sxs-lookup"><span data-stu-id="32d27-154">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="32d27-155">**String**</span><span class="sxs-lookup"><span data-stu-id="32d27-155">**String**</span></span>|  

 <span data-ttu-id="32d27-156">在前面的传入 SOAP 消息，WCF 适配器使用的字符数据， **CONTOSO**的**CustomerID**元素来创建入站的 BizTalk 消息正文部分。</span><span class="sxs-lookup"><span data-stu-id="32d27-156">For the previous incoming SOAP message, the WCF adapters use the character data, **CONTOSO**, of the **CustomerID** element to create the inbound BizTalk message body part.</span></span>  

> [!NOTE]
>  <span data-ttu-id="32d27-157">不能使用 XPath，缩简的语法 **/Order/OrderDetail/CustomerID**，在前面的传入 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="32d27-157">You cannot use the abbreviated syntax of XPath, **/Order/OrderDetail/CustomerID**, for the previous incoming SOAP message.</span></span> <span data-ttu-id="32d27-158">这是因为 XPath 缩简的语法返回未声明的命名空间的节点和**CustomerID**前面的 SOAP 消息中的元素中声明**http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess**命名空间默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="32d27-158">This is because the abbreviated syntax of XPath returns the node not declared in a namespace, and the **CustomerID** element in the previous SOAP message is declared in the **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess** namespace by default namespaces.</span></span>  

 <span data-ttu-id="32d27-159">如果你配置**BizTalk 消息正文**部分下表中所示**CustomID**前面的传入 SOAP 消息中的元素应具有一个有效**BinHex**或**Base64**序列。</span><span class="sxs-lookup"><span data-stu-id="32d27-159">If you configure the **BizTalk message body** section as shown in the following table, the **CustomID** element in the previous incoming SOAP message should have a valid **BinHex** or **Base64** sequence.</span></span>  

|<span data-ttu-id="32d27-160">入站 BizTalk 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-160">Inbound BizTalk message body</span></span>|<span data-ttu-id="32d27-161">正文路径表达式</span><span class="sxs-lookup"><span data-stu-id="32d27-161">Body path expression</span></span>|<span data-ttu-id="32d27-162">节点编码</span><span class="sxs-lookup"><span data-stu-id="32d27-162">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="32d27-163">**路径-按正文路径定位内容**</span><span class="sxs-lookup"><span data-stu-id="32d27-163">**Path -- content located by body path**</span></span>|<span data-ttu-id="32d27-164">/ \* [local-name = Order] /\*[本地名称 （) = OrderDetail] /\*[本地名称 （) = CustomerID]</span><span class="sxs-lookup"><span data-stu-id="32d27-164">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="32d27-165">**十六进制**或**Base64**</span><span class="sxs-lookup"><span data-stu-id="32d27-165">**Hex** or **Base64**</span></span>|  

 <span data-ttu-id="32d27-166">如果你配置**BizTalk 消息正文**部分下表中所示，WCF 适配器创建前面的传入 SOAP 消息的入站的 BizTalk 消息正文，如表后，在代码中所示。</span><span class="sxs-lookup"><span data-stu-id="32d27-166">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters create the inbound BizTalk message body for the previous incoming SOAP message as shown in the code after the table.</span></span>  

|<span data-ttu-id="32d27-167">入站 BizTalk 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-167">Inbound BizTalk message body</span></span>|<span data-ttu-id="32d27-168">正文路径表达式</span><span class="sxs-lookup"><span data-stu-id="32d27-168">Body path expression</span></span>|<span data-ttu-id="32d27-169">节点编码</span><span class="sxs-lookup"><span data-stu-id="32d27-169">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="32d27-170">**路径-按正文路径定位内容**</span><span class="sxs-lookup"><span data-stu-id="32d27-170">**Path -- content located by body path**</span></span>|<span data-ttu-id="32d27-171">/ \* [local-name = Order] /\*[本地名称 （) = OrderDetail] /\*[本地名称 （) = CustomerID]</span><span class="sxs-lookup"><span data-stu-id="32d27-171">/\*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="32d27-172">**XML**</span><span class="sxs-lookup"><span data-stu-id="32d27-172">**XML**</span></span>|  

```  
<CustomerID xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">CONTOSO</CustomerID>   
```  

## <a name="specifying-the-source-of-the-outbound-wcf-message-body"></a><span data-ttu-id="32d27-173">指定出站 WCF 消息正文的源</span><span class="sxs-lookup"><span data-stu-id="32d27-173">Specifying the Source of the Outbound WCF Message Body</span></span>  
 <span data-ttu-id="32d27-174">可以控制如何从 BizTalk 消息正文创建出站 WCF 消息正文以通过 WCF 适配器发送。</span><span class="sxs-lookup"><span data-stu-id="32d27-174">You can control how to create the outbound WCF message body from a BizTalk message body to send through the WCF adapters.</span></span> <span data-ttu-id="32d27-175">若要指定出站 WCF 消息正文中放置 BizTalk 消息正文的方式，可以使用中的下列选项之一**出站 WCF 消息正文**部分**消息**选项卡中所示上一节中的图形：</span><span class="sxs-lookup"><span data-stu-id="32d27-175">To specify how the BizTalk message body is placed in the outbound WCF message body, you can use one of the following options in the **Outbound WCF message body** section on the **Messages** tab as shown in the figures in the previous section:</span></span>  

- <span data-ttu-id="32d27-176">**正文--BizTalk 响应消息正文**。</span><span class="sxs-lookup"><span data-stu-id="32d27-176">**Body -- BizTalk response message body**.</span></span> <span data-ttu-id="32d27-177">使用 BizTalk 消息正文部分创建的 soap 内容**正文**为传出消息的元素。</span><span class="sxs-lookup"><span data-stu-id="32d27-177">Uses the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message.</span></span> <span data-ttu-id="32d27-178">传出 BizTalk 消息正文将成为出站 SOAP 消息的正文。</span><span class="sxs-lookup"><span data-stu-id="32d27-178">The outgoing BizTalk message body becomes the body of the outbound SOAP message.</span></span>  

- <span data-ttu-id="32d27-179">**模板-由模板指定的内容**。</span><span class="sxs-lookup"><span data-stu-id="32d27-179">**Template -- content specified by template**.</span></span> <span data-ttu-id="32d27-180">使用中提供的模板**XML**文本框中，若要创建的 soap 内容**正文**为传出消息的元素。</span><span class="sxs-lookup"><span data-stu-id="32d27-180">Uses the template supplied in the **XML** text box to create the content of the SOAP **Body** element for an outgoing message.</span></span> <span data-ttu-id="32d27-181">使用 WCF 适配器**正文--BizTalk 响应消息正文**（默认值） 选项不允许发送字符数据和位图图像等非 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="32d27-181">The WCF adapters with **Body -- BizTalk response message body** (the default value) option do not allow sending non-XML message such as character data and bitmap images.</span></span> <span data-ttu-id="32d27-182">可以使用**模板-由模板指定的内容**WCF 适配器能够发送非 XML 消息编码中的选项**base64**，**十六进制**，或**字符串**.</span><span class="sxs-lookup"><span data-stu-id="32d27-182">You can use the **Template -- content specified by template** option for the WCF adapters to send non-XML messages encoded in **base64**, **hex**, or **string**.</span></span>  

  <span data-ttu-id="32d27-183">当**模板-由模板指定的内容**选择选项，则必须提供中的任意模板 XML 元素**出站 WCF 消息正文-XML**文本框。</span><span class="sxs-lookup"><span data-stu-id="32d27-183">When the **Template -- content specified by template** option is selected, you must provide an arbitrary template XML element in the **Outbound WCF message body - XML** text box.</span></span> <span data-ttu-id="32d27-184">模板 XML 元素必须包含以下**bts 消息正文**元素一次且只有一次除非模板 XML 元素留空：</span><span class="sxs-lookup"><span data-stu-id="32d27-184">The template XML element must contain the following **bts-msg-body** element once and only once unless the template XML element is left empty:</span></span>  

```  
<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2010" encoding="[base64|hex|string|xml]"/>  
```  

 <span data-ttu-id="32d27-185">WCF 适配器对根据 BizTalk 消息正文进行编码**编码**属性在 XML 模板，然后将**bts 消息正文**使用编码的 BizTalk 消息正文时创建的元素出站 WCF 消息。</span><span class="sxs-lookup"><span data-stu-id="32d27-185">The WCF adapters encode the BizTalk message body according to the **encoding** attribute in the XML template, and then replace the **bts-msg-body** element with the encoded BizTalk message body when creating outbound WCF messages.</span></span> <span data-ttu-id="32d27-186">如果**出站 WCF 消息正文-XML**文本框留空，则 WCF 适配器编码的 BizTalk 消息正文**Base64**，然后将放**Base64**序列中出站 SOAP 消息正文。</span><span class="sxs-lookup"><span data-stu-id="32d27-186">If the **Outbound WCF message body - XML** text box is left empty, the WCF adapters encode the BizTalk message body in **Base64**, and then place the **Base64** sequence in the outbound SOAP message body.</span></span>  

 <span data-ttu-id="32d27-187">如果**编码**XML 模板中的属性设置为**字符串**，WCF 适配器将 BizTalk 消息正文部分编码为 utf-8 编码字符数据，在其中的 XML 特殊字符。 例如\<和\>进行转义。</span><span class="sxs-lookup"><span data-stu-id="32d27-187">If the **encoding** attribute in the XML template is set to **string**, the WCF adapters encode the BizTalk message body part as UTF-8 encoded character data, in which the XML special characters such as \< and \> are escaped.</span></span>  

 <span data-ttu-id="32d27-188">如果**编码**XML 模板中的属性设置为**base64**或**十六进制**，则 WCF 适配器编码 BizTalk 消息正文部分作为**BinHex**或**Base64**序列。</span><span class="sxs-lookup"><span data-stu-id="32d27-188">If the **encoding** attribute in the XML template is set to **base64** or **hex**, the WCF adapters encode the BizTalk message body part as a **BinHex** or **Base64** sequence.</span></span>  

 <span data-ttu-id="32d27-189">如果**编码**XML 模板中的属性设置为**xml**，WCF 适配器替换**bts 消息正文**具有出站 BizTalk 消息正文，以便创建元素传出 WCF 消息。</span><span class="sxs-lookup"><span data-stu-id="32d27-189">If the **encoding** attribute in the XML template is set to **xml**, the WCF adapters replace the **bts-msg-body** element with the outbound BizTalk message body to create the outgoing WCF message.</span></span>  

 <span data-ttu-id="32d27-190">例如，假定 WCF 适配器需要将以下 BizTalk 消息正文部分发送到 WCF 客户端：</span><span class="sxs-lookup"><span data-stu-id="32d27-190">For example, suppose the WCF adapters need to send the following BizTalk message body part to WCF clients:</span></span>  

```  
<ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
```  

 <span data-ttu-id="32d27-191">如果你配置**出站 WCF 消息正文**部分下表中所示，WCF 适配器创建出站 WCF 消息，如表后，在代码中所示。</span><span class="sxs-lookup"><span data-stu-id="32d27-191">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  

|<span data-ttu-id="32d27-192">出站 WCF 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-192">Outbound WCF message body</span></span>|<span data-ttu-id="32d27-193">XML</span><span class="sxs-lookup"><span data-stu-id="32d27-193">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="32d27-194">**正文--BizTalk 响应消息正文**</span><span class="sxs-lookup"><span data-stu-id="32d27-194">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="32d27-195">N/A</span><span class="sxs-lookup"><span data-stu-id="32d27-195">N/A</span></span>|  

```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:6a706a54-c4f5-4767-909d-a992c7c26dba</a:MessageID>  
    <a:ReplyTo>  
<a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
  </s:Body>  
</s:Envelope>  
```  

 <span data-ttu-id="32d27-196">如果你配置**出站 WCF 消息正文**部分下表中所示，WCF 适配器创建出站 WCF 消息，如表后，在代码中所示。</span><span class="sxs-lookup"><span data-stu-id="32d27-196">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  


|         <span data-ttu-id="32d27-197">出站 WCF 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-197">Outbound WCF message body</span></span>         |                                                                    <span data-ttu-id="32d27-198">XML</span><span class="sxs-lookup"><span data-stu-id="32d27-198">XML</span></span>                                                                    |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="32d27-199">**正文--BizTalk 响应消息正文**</span><span class="sxs-lookup"><span data-stu-id="32d27-199">**Body -- BizTalk response message body**</span></span> | <span data-ttu-id="32d27-200">\<通讯簿\></span><span class="sxs-lookup"><span data-stu-id="32d27-200">\<Book\></span></span><br /><br /> <span data-ttu-id="32d27-201">\<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**string**"/\></span><span class="sxs-lookup"><span data-stu-id="32d27-201">\<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**string**"/\></span></span><br /><br /> <span data-ttu-id="32d27-202">\</Book\></span><span class="sxs-lookup"><span data-stu-id="32d27-202">\</Book\></span></span> |

```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:05dde292-eedd-467e-b0d2-f1b8f0757410</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <Book><ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  <ns0:OrderDetail>    <ns0:CustomerID>CONTOSO</ns0:CustomerID>    <ns0:OrderID> 01A2c</ns0:OrderID>  </ns0:OrderDetail></ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```  

 <span data-ttu-id="32d27-203">如果你配置**出站 WCF 消息正文**部分下表中所示，WCF 适配器创建出站 WCF 消息，如表后，在代码中所示。</span><span class="sxs-lookup"><span data-stu-id="32d27-203">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  


|         <span data-ttu-id="32d27-204">出站 WCF 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-204">Outbound WCF message body</span></span>         |                                                                    <span data-ttu-id="32d27-205">XML</span><span class="sxs-lookup"><span data-stu-id="32d27-205">XML</span></span>                                                                    |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="32d27-206">**正文--BizTalk 响应消息正文**</span><span class="sxs-lookup"><span data-stu-id="32d27-206">**Body -- BizTalk response message body**</span></span> | <span data-ttu-id="32d27-207">\<通讯簿\></span><span class="sxs-lookup"><span data-stu-id="32d27-207">\<Book\></span></span><br /><br /> <span data-ttu-id="32d27-208">\<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**base64**"/\></span><span class="sxs-lookup"><span data-stu-id="32d27-208">\<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**base64**"/\></span></span><br /><br /> <span data-ttu-id="32d27-209">\</Book\></span><span class="sxs-lookup"><span data-stu-id="32d27-209">\</Book\></span></span> |

```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://ww  
w.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe  
/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:cb3cac6d-a542-4a90-bad8-cdbfa8251112</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessSer  
vice</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>77u/PG5zMDpPcmRlciB4bWxuczpuczA9Imh0dHA6Ly9NaWNyb3NvZnQuU2FtcGxlcy5CaX  
pUYWxrLk5ldE5hbWVkUGlwZS9PcmRlclByb2Nlc3MiPg0KICA8bnMwOk9yZGVyRGV0YWlsPg0KICAgID  
xuczA6Q3VzdG9tZXJJRD5DT05UT1NPPC9uczA6Q3VzdG9tZXJJRD4NCiAgICA8bnMwOk9yZGVySUQ+MD  
FBMmM8L25zMDpPcmRlcklEPg0KICA8L25zMDpPcmRlckRldGFpbD4NCjwvbnMwOk9yZGVyPg==</Book  
>  
  </s:Body>  
</s:Envelope>  
```  

 <span data-ttu-id="32d27-210">如果你配置**出站 WCF 消息正文**部分下表中所示，WCF 适配器创建出站 WCF 消息，如表后，在代码中所示。</span><span class="sxs-lookup"><span data-stu-id="32d27-210">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  


|         <span data-ttu-id="32d27-211">出站 WCF 消息正文</span><span class="sxs-lookup"><span data-stu-id="32d27-211">Outbound WCF message body</span></span>         |                                                                  <span data-ttu-id="32d27-212">XML</span><span class="sxs-lookup"><span data-stu-id="32d27-212">XML</span></span>                                                                   |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="32d27-213">**正文--BizTalk 响应消息正文**</span><span class="sxs-lookup"><span data-stu-id="32d27-213">**Body -- BizTalk response message body**</span></span> | <span data-ttu-id="32d27-214">\<通讯簿\></span><span class="sxs-lookup"><span data-stu-id="32d27-214">\<Book\></span></span><br /><br /> <span data-ttu-id="32d27-215">\<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**xml**"/\></span><span class="sxs-lookup"><span data-stu-id="32d27-215">\<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**xml**"/\></span></span><br /><br /> <span data-ttu-id="32d27-216">\</Book\></span><span class="sxs-lookup"><span data-stu-id="32d27-216">\</Book\></span></span> |

```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:A  
ction>  
    <a:MessageID>{513C123C-0600-4A1C-BEE2-EF83E0EFEB15}</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>  
      <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CustomerID_0</ns0:CustomerID>  
    <ns0:OrderID>OrderID_0</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```