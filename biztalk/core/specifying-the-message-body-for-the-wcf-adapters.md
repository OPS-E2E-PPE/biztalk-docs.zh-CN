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
ms.openlocfilehash: c68a6d7b3da82bac90f98f79b67affc700ec75c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243126"
---
# <a name="specifying-the-message-body-for-the-wcf-adapters"></a>指定 WCF 适配器的消息正文
可以使用**消息**选项卡中的 WCF 适配器以指定如何从传入 SOAP 消息提取 BizTalk 消息正文和 BizTalk 消息正文的方式放置在传出 SOAP 消息中。  

## <a name="specifying-how-the-biztalk-message-body-is-extracted-from-an-incoming-soap-message"></a>指定如何从传入 SOAP 消息提取 BizTalk 消息正文  
 您可以控制如何通过 WCF 适配器传入的 SOAP 消息创建入站的 BizTalk 消息正文。 下图显示**消息**选项卡的 Wcf-netnamedpipe 接收适配器和发送适配器作为示例。  

 ![消息选项卡中的 WCF 接收适配器](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")  

 ![WCF 中的消息选项卡发送适配器](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")  

 若要指定如何创建 BizTalk 消息正文，请选择中的下列选项之一**入站 BizTalk 消息正文**上面各图中的部分：  

- **信封--整个\<soap: Envelope\>** 。 使用 SOAP**信封**传入消息创建 BizTalk 消息正文部分的元素。 整个传入消息将成为 BizTalk 消息正文。 此选项用于创建 BizTalk 消息正文将合并所有标头。  

  > [!NOTE]
  >  SOAP 标头都将置于消息上下文，但它们不会自动升级。 自定义管道组件可进行升级。  

- **--正文\<soap: Body\>元素**。 使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。  

- **路径-按正文路径定位内容**。 使用中的正文路径表达式**正文路径表达式**文本框中，用于创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 当传入消息有二进制数据时，可以使用此选项用于 BizTalk 消息正文以仅包括二进制数据而没有任何标记。  

  当**路径-按正文路径定位内容**选项，则**节点编码**属性可以配置为指定的正文路径表达式中指定的节点所需编码类型**正文路径表达式**文本框。 如果正文路径表达式匹配多个元素，则使用的第一个匹配的元素。  

> [!NOTE]
>  有关**正文路径表达式**属性，仅支持 XML 的适用于只进处理的表达式的 XPath。 有关可用于此属性的 XPath 表达式的详细信息，请参阅"的这两个优势：将 XPath 与 XmlReader"处[ http://go.microsoft.com/fwlink/?LinkID=75701 ](http://go.microsoft.com/fwlink/?LinkID=75701)。  

 如果**路径-按正文路径定位内容**选择选项和**节点编码**属性设置为**字符串**，则 WCF 适配器期望匹配的节点具有 utf-8编码的字符数据。 如果传入消息包含转义字符数据的 XML 特殊字符，如\<和\>，创建 BizTalk 消息正文部分时，WCF 适配器会还原转义的字符数据。 例如，如果匹配的节点已转义字符数据，如 **&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** WCF 适配器会创建 **\<FirstName\>CONTOSO\</FirstName\>** 在入站 BizTalk 消息正文。  

 如果**路径-按正文路径定位内容**选择选项和**节点编码**属性设置为**十六进制**或者**Base64**、匹配的节点可以有一个有效**BinHex**或**Base64**序列。 如果匹配的节点具有无效的序列，WCF 客户端将接收**FaultException**、 在您的 BizTalk Server 计算机上的事件日志中记录一条错误消息和不挂起任何消息。  

 如果**路径-按正文路径定位内容**选择选项和**节点编码**属性设置为**XML**，WCF 适配器会创建与 BizTalk 消息正文中的正文路径表达式所选择的节点的外部 XML**正文路径表达式**文本框。  

 如果匹配的节点不具有作为编码数据中指定**节点编码**属性，创建一个空的入站的 BizTalk 消息正文。  

 例如，假定 WCF 发送适配器从 WCF 客户端接收以下 SOAP 消息：  

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

 如果你配置**入站 BizTalk 消息正文**部分下的表中，前面的传入 SOAP 消息中所示将成为入站的 BizTalk 消息正文部分。  

|入站的 BizTalk 消息正文|正文路径表达式|节点编码|  
|----------------------------------|--------------------------|-------------------|  
|**信封--整个\<soap: Envelope\>**|不可用|不可用|  

 如果你配置**BizTalk 消息正文**部分下表中所示，WCF 适配器会创建入站的 BizTalk 消息正文部分以仅包含**顺序**中的上一个元素传入的 SOAP 消息。  

|入站的 BizTalk 消息正文|正文路径表达式|节点编码|  
|----------------------------------|--------------------------|-------------------|  
|**--正文\<soap: Body\>元素**|不可用|不可用|  

 如果你配置**BizTalk 消息正文**部分下表中所示，则 WCF 适配器期望正文路径表达式匹配的传入节点将具有 utf-8 编码字符数据。  

|入站的 BizTalk 消息正文|正文路径表达式|节点编码|  
|----------------------------------|--------------------------|-------------------|  
|**路径-按正文路径定位内容**|/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']|**String**|  

 在前面的传入 SOAP 消息，WCF 适配器使用的字符数据， **CONTOSO**的**CustomerID**元素来创建入站的 BizTalk 消息正文部分。  

> [!NOTE]
>  不能使用 XPath，缩简的语法 **/Order/OrderDetail/CustomerID**，在前面的传入 SOAP 消息。 这是因为 XPath 缩简的语法返回未声明的命名空间的节点和**CustomerID**前面的 SOAP 消息中的元素中声明 **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess** 命名空间默认命名空间。  

 如果你配置**BizTalk 消息正文**部分下表中所示**CustomID**前面的传入 SOAP 消息中的元素应具有一个有效**BinHex**或**Base64**序列。  

|入站的 BizTalk 消息正文|正文路径表达式|节点编码|  
|----------------------------------|--------------------------|-------------------|  
|**路径-按正文路径定位内容**|/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']|**十六进制**或**Base64**|  

 如果你配置**BizTalk 消息正文**部分下表中所示，WCF 适配器创建前面的传入 SOAP 消息的入站的 BizTalk 消息正文，如表后，在代码中所示。  

|入站的 BizTalk 消息正文|正文路径表达式|节点编码|  
|----------------------------------|--------------------------|-------------------|  
|**路径-按正文路径定位内容**|/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']|**XML**|  

```  
<CustomerID xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">CONTOSO</CustomerID>   
```  

## <a name="specifying-the-source-of-the-outbound-wcf-message-body"></a>指定出站 WCF 消息正文的源  
 您可以控制如何创建从 BizTalk 消息正文，以便通过 WCF 适配器发送的出站 WCF 消息正文。 若要指定出站 WCF 消息正文中放置 BizTalk 消息正文的方式，可以使用中的下列选项之一**出站 WCF 消息正文**部分**消息**选项卡中所示上一节中的图形：  

- **正文--BizTalk 响应消息正文**。 使用 BizTalk 消息正文部分创建的 soap 内容**正文**为传出消息的元素。 传出 BizTalk 消息正文将成为出站 SOAP 消息的正文。  

- **模板-由模板指定的内容**。 使用中提供的模板**XML**文本框中，若要创建的 soap 内容**正文**为传出消息的元素。 使用 WCF 适配器**正文--BizTalk 响应消息正文**（默认值） 选项不允许发送字符数据和位图图像等非 XML 消息。 可以使用**模板-由模板指定的内容**WCF 适配器能够发送非 XML 消息编码中的选项**base64**，**十六进制**，或**字符串**.  

  当**模板-由模板指定的内容**选择选项，则必须提供中的任意模板 XML 元素**出站 WCF 消息正文-XML**文本框。 模板 XML 元素必须包含以下**bts 消息正文**元素一次且只有一次除非模板 XML 元素留空：  

```  
<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2010" encoding="[base64|hex|string|xml]"/>  
```  

 WCF 适配器对根据 BizTalk 消息正文进行编码**编码**属性在 XML 模板，然后将**bts 消息正文**使用编码的 BizTalk 消息正文时创建的元素出站 WCF 消息。 如果**出站 WCF 消息正文-XML**文本框留空，则 WCF 适配器编码的 BizTalk 消息正文**Base64**，然后将放**Base64**序列中出站 SOAP 消息正文。  

 如果**编码**XML 模板中的属性设置为**字符串**，WCF 适配器将 BizTalk 消息正文部分编码为 utf-8 编码字符数据，在其中的 XML 特殊字符。 例如\<和\>进行转义。  

 如果**编码**XML 模板中的属性设置为**base64**或**十六进制**，则 WCF 适配器编码 BizTalk 消息正文部分作为**BinHex**或**Base64**序列。  

 如果**编码**XML 模板中的属性设置为**xml**，WCF 适配器替换**bts 消息正文**具有出站 BizTalk 消息正文，以便创建元素传出 WCF 消息。  

 例如，假定 WCF 适配器需要将以下 BizTalk 消息正文部分发送到 WCF 客户端：  

```  
<ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
```  

 如果你配置**出站 WCF 消息正文**部分下表中所示，WCF 适配器创建出站 WCF 消息，如表后，在代码中所示。  

|出站 WCF 消息正文|XML|  
|-------------------------------|---------|  
|**正文--BizTalk 响应消息正文**|不可用|  

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

 如果你配置**出站 WCF 消息正文**部分下表中所示，WCF 适配器创建出站 WCF 消息，如表后，在代码中所示。  


|         出站 WCF 消息正文         |                                                                    XML                                                                    |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| **正文--BizTalk 响应消息正文** | \<Book\><br /><br /> \<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**string**"/\><br /><br /> \</Book\> |

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

 如果你配置**出站 WCF 消息正文**部分下表中所示，WCF 适配器创建出站 WCF 消息，如表后，在代码中所示。  


|         出站 WCF 消息正文         |                                                                    XML                                                                    |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| **正文--BizTalk 响应消息正文** | \<Book\><br /><br /> \<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**base64**"/\><br /><br /> \</Book\> |

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

 如果你配置**出站 WCF 消息正文**部分下表中所示，WCF 适配器创建出站 WCF 消息，如表后，在代码中所示。  


|         出站 WCF 消息正文         |                                                                  XML                                                                   |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **正文--BizTalk 响应消息正文** | \<Book\><br /><br /> \<**bts-msg-body** xmlns="<http://www.microsoft.com/schemas/bts2010>" encoding="**xml**"/\><br /><br /> \</Book\> |

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