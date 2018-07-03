---
title: 使用 SAP 适配器的 WCF 通道模型概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
- WCF channel model, creating messages for the SAP adapter
ms.assetid: 6192d637-efac-4580-8880-b5bae9d16f31
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81eba8c28b3bf11eea38624e0a017d8bca9eb9a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013182"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sap-adapter"></a>使用 SAP 适配器的 WCF 通道模型概述
若要在 SAP 系统中，调用 Rfc、 Trfc 或 Bapi 或 IDOC 发送到 SAP 系统，你的代码可作为 WCF 客户端，将向适配器发送出站操作。 在 WCF 通道模型中，你的代码的通道上发送请求消息来调用在适配器上的操作。  
  
 充当 tRFC 或 RFC 服务器到 SAP 系统，你的代码的行为作为 WCF 服务。 也就是说，适配器调用你的代码上的入站的操作 — 例如，RFC 或 ReceiveIdoc 操作 （用于接收来自 SAP 系统的字符串格式的 IDOC）。 在此方案中，你的代码通过适配器从通道接收请求消息，该操作。  
  
 在本部分中的主题提供使用概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 WCF 通道模型。  
  
## <a name="wcf-channel-model-overview"></a>WCF 通道模型概述  
 通过交换 SOAP 消息，客户端和服务进行通信。 WCF 通道模型是此消息交换的低级别抽象。 它提供了接口和类型，您可以发送和接收消息，通过使用分层的协议堆栈，称为通道堆栈。 堆栈中的每个层组成的一个通道，并且从 WCF 绑定创建的每个通道。 在最低层是传输通道。 传输通道可实现服务和客户端之间的基础传输机制并显示每条消息到较高的层 （和最终使用方应用程序），并且**System.ServiceModel.Message**。 WCF**消息**类是抽象的 SOAP 消息。 WCF 提供了多个通道接口，名为的基本 SOAP 消息交换模式进行建模，例如请求-答复或单向通道形状。 WCF 传输绑定提供的实现的一个或更高版本层的详细通道形状可用于发送和接收消息。 有关 WCF 通道模型的详细信息，请参阅[通道模型概述](https://msdn.microsoft.com/library/ms729840.aspx)。
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是公开为 WCF 服务将 SAP 系统的 WCF 自定义传输绑定。  
  
## <a name="supported-channel-shapes-for-the-sap-adapter"></a>SAP 适配器支持通道形状  
 适配器实现以下 WCF 通道形状：  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**接口实现请求-答复消息交换的客户端。 可以使用**IRequestChannel**执行你想要使用的响应，例如若要调用返回数据的 SAP 系统上的 RFC 的操作。  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 此形状实现单向消息交换的客户端。 可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如若要调用不返回任何数据的 SAP 系统上的 RFC。  
  
- **IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**)。 此形状实现请求-答复消息交换在服务端。 可以使用**IReplyChannel** ，实现 RFC 或 tRFC 服务器，或用于从 SAP 系统接收 Idoc。  
  
  像任何 WCF 绑定，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用工厂模式来提供到应用程序代码的通道。 您使用**Microsoft.Adapters.SAPBinding**对象创建的实例：  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>** 提供**IRequestChannel**通道可用来调用在适配器上的请求-响应操作。  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>** 提供**IOutputChannel**通道可用来调用在适配器上的单向操作。  
  
- **System.ServiceModel.IChannelListener\<IReplyChannel\>** 提供**IReplyChannel**通道可用于从适配器接收请求-响应操作。  
  
## <a name="creating-messages-for-the-sap-adapter-in-the-wcf-channel-model"></a>正在创建 WCF 通道模型中的 SAP 适配器的消息  
 在 WCF **System.ServiceModel.Channels.Message**类提供了内存中 SOAP 消息的表示形式。 您创建**消息**实例通过调用静态**Message.Create**方法。  
  
 有两个重要构造时必须指定的 SOAP 消息部分**消息**实例将发送到[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 消息操作是一个字符串，是 SOAP 消息标头的一部分。 消息操作标识的操作应在调用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 下面的示例演示指定要调用 SD_RFC_CUSTOMER_GET RFC，SAP 系统上的消息操作： `http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`。  
  
- 消息正文包含操作的参数数据。 消息正文组成对应于所需的消息架构的格式正确的 XML[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]对请求的操作。 以下消息正文包含 SAP 系统上 SD_RFC_CUSTOMER_GET rfc 的参数。  
  
  ```  
  <SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>  
  ```  
  
  璝惠[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]消息架构和消息操作的操作，请参见[消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。  
  
  **Message.Create**方法被重载并提供许多不同的提供消息正文选项。 下面的代码演示如何创建**消息**通过使用实例**System.Xml.XmlReader**提供消息正文。 在此代码中，从一个字符串常量中读取消息正文。  
  
```  
//create an XML message to send to the SAP system  
//We are invoking the SD_RFC_CUSTOMER_GET RFC.  
//The XML below specifies that we want to search for customers with names starting with "AB"  
string inputXml = "<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
//create an XML reader from the input XML  
XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
//create a WCF message from the XML reader  
Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
```  
  
> [!IMPORTANT]
>  必须提供中的消息操作，你**消息**实例。 这通常是何时**消息**创建实例。  
  
## <a name="streaming-support-on-the-sap-adapter-in-the-wcf-channel-model"></a>WCF 通道模型中的 SAP 适配器上的流式处理支持  
 如何创建和使用 SAP 适配器与交换的消息确定如何对消息流式处理你的代码和适配器之间。  
  
### <a name="node-streaming"></a>流式处理的节点  
 节点流式处理是流式处理支持除了 SendIdoc 和 ReceiveIdoc 操作之外的所有操作的唯一级别。  
  
 若要执行节点的流式处理的消息，则：  
  
-   创建出站消息使用**XmlReader**提供消息正文。  
  
-   使用入站的消息使用**XmlReader**。 通过调用获取的读取器**GetReaderAtBodyContents**方法在入站**消息**。  
  
### <a name="node-value-streaming"></a>节点值流式处理  
 因为 SendIdoc 和 ReceiveIdoc 操作包含在单个 XML 节点的字符串中的 IDOC 数据 (\<idocData\>)、 适配器支持节点的值流处理这些操作。  
  
 若要执行这些操作的流式处理的节点的值，你可以：  
  
- 创建 SendIdoc 请求消息 （出站） 使用**BodyWriter**实现节点值的流式处理以提供消息正文。  
  
- 使用 ReceiveIdoc 请求消息 （传入） 通过调用**WriteBodyContents**上的消息的方法**XmlDictionaryWriter**实现节点值流式处理。  
  
  有关流式处理平面文件 （字符串） Idoc 使用 WCF 通道模型的详细信息，请参阅[流式处理中使用 WCF 通道模型的 SAP 的平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 通道模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)