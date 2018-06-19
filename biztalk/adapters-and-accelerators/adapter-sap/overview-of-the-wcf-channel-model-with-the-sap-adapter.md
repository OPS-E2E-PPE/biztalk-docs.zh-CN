---
title: 与 SAP 适配器的 WCF 通道模型概述 |Microsoft 文档
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
ms.openlocfilehash: 51b5469681f7acce2ebb0b55fe63e285d25192e0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967243"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sap-adapter"></a>与 SAP 适配器的 WCF 通道模型概述
若要在 SAP 系统中，调用 Rfc、 tRFCs 或 BAPIs 或将 IDOC 发送到 SAP 系统，你的代码将充当 WCF 客户端，并将出站操作发送到适配器。 在 WCF 通道模型中，你的代码时，将调用在适配器上的操作通过在通道上发送请求消息。  
  
 若要充当 tRFC 或 RFC 到 SAP 系统的服务器，你的代码的行为作为 WCF 服务。 适配器，即你的代码上的入站的操作时，将调用 — 例如，RFC 或 ReceiveIdoc 操作 （以接收从 SAP 系统的字符串格式的 IDOC）。 在此方案中，你的代码通过从适配器通道接收到针对该操作的请求消息。  
  
 本部分中的主题提供使用的概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 WCF 通道模型。  
  
## <a name="wcf-channel-model-overview"></a>WCF 通道模型概述  
 通过交换 SOAP 消息，客户端和服务进行通信。 WCF 通道模型是此消息交换的低级别抽象。 它提供接口和使您能够发送和接收消息，通过使用调用的通道堆栈的分层的协议堆栈的类型。 堆栈的每个层组成一个通道，并且每个通道创建从 WCF 绑定。 在最低层是传输通道。 传输通道可实现服务和客户端之间的底层传输机制并显示到较高层 （和最终使用方应用程序） 的每条消息，并且**System.ServiceModel.Message**。 WCF**消息**类是 SOAP 消息的抽象。 WCF 提供了多个通道接口，调用的基本 SOAP 消息交换模式进行建模，如请求-答复或单向通道形状。 WCF 传输绑定提供的实现的一个或多个更高版本上层的通道形状可以用于发送和接收消息。 有关 WCF 通道模型的详细信息，请参阅[通道模型概述](https://msdn.microsoft.com/library/ms729840.aspx)。
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是公开的 SAP 系统作为 WCF 服务的 WCF 自定义传输绑定。  
  
## <a name="supported-channel-shapes-for-the-sap-adapter"></a>SAP 适配器支持通道形状  
 适配器实现以下的 WCF 通道形状：  
  
-   **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**接口实现请求-答复消息交换的客户端。 你可以使用**IRequestChannel**执行你想要使用的响应，例如调用 RFC 返回数据的 SAP 系统上的操作。  
  
-   **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 此形状实现单向消息交换的客户端。 你可以使用**IOutputChannel**来调用的操作不需要为其使用的响应，例如，若要调用不返回任何数据的 SAP 系统上的 RFC。  
  
-   **IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**)。 此形状实现请求-答复消息交换的服务端。 你可以使用**IReplyChannel**实现的 RFC 或 tRFC 服务器或从 SAP 系统接收到的 Idoc。  
  
 如任何 WCF 绑定，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用工厂模式提供到应用程序代码的通道。 你使用**Microsoft.Adapters.SAPBinding**对象创建的实例：  
  
-   **System.ServiceModel.ChannelFactory\<IRequestChannel\>** 提供**IRequestChannel**通道可用于调用在适配器上的请求-响应操作。  
  
-   **System.ServiceModel.ChannelFactory\<IOutputChannel\>** 提供**IOutputChannel**通道可用于调用在适配器上的单向操作。  
  
-   **System.ServiceModel.IChannelListener\<IReplyChannel\>** 提供**IReplyChannel**通道可用于从适配器接收请求-响应操作。  
  
## <a name="creating-messages-for-the-sap-adapter-in-the-wcf-channel-model"></a>正在创建的 WCF 通道模型中的 SAP 适配器消息  
 在 WCF 中**System.ServiceModel.Channels.Message**类提供内存中的 SOAP 消息的表示形式。 你创建**消息**实例通过调用静态**Message.Create**方法。  
  
 有两个重要构造时必须指定的 SOAP 消息部分**消息**实例将发送到[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   消息操作是一个字符串，它的 SOAP 消息标头的一部分。 消息操作标识应在调用操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 下面的示例演示了指定用于调用 SD_RFC_CUSTOMER_GET RFC SAP 系统上的消息操作： `http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`。  
  
-   消息正文包含操作的参数数据。 消息正文组成对应于预期的消息架构的格式正确的 XML[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]请求的操作。 以下的消息正文的 SAP 系统上 SD_RFC_CUSTOMER_GET RFC 中包含的参数。  
  
    ```  
    <SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>  
    ```  
  
 璝惠[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]消息架构和消息操作的操作，请参阅[消息和消息架构用于 mySAP Business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。  
  
 **Message.Create**方法重载方法，提供了多种不同的选项，用于提供消息正文。 下面的代码演示如何创建**消息**实例使用**System.Xml.XmlReader**提供消息正文。 在此代码中，从字符串常量读取消息正文。  
  
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
>  必须提供中的消息操作你**消息**实例。 这通常完成时**消息**创建实例。  
  
## <a name="streaming-support-on-the-sap-adapter-in-the-wcf-channel-model"></a>在 WCF 通道模型中的 SAP 适配器上的流式处理支持  
 如何创建和使用与 SAP 适配器交换的消息确定如何对消息流式处理你的代码和适配器之间。  
  
### <a name="node-streaming"></a>流式处理的节点  
 节点流是流式处理支持除 SendIdoc 和 ReceiveIdoc 操作的所有操作的唯一级别。  
  
 若要执行节点流式处理的消息，你：  
  
-   创建出站消息使用**XmlReader**提供消息正文。  
  
-   使用入站的消息使用**XmlReader**。 通过调用获取读取器**GetReaderAtBodyContents**方法在入站**消息**。  
  
### <a name="node-value-streaming"></a>节点值流式处理  
 因为 SendIdoc 和 ReceiveIdoc 操作包含在单个 XML 节点的字符串中的 IDOC 数据 (\<idocData\>) 的适配器支持节点的值流式处理这些操作。  
  
 若要执行这些操作流式处理节点的值，你可以：  
  
-   创建 SendIdoc 请求消息 （出站） 使用**BodyWriter**实现流提供消息正文的节点的值。  
  
-   使用 ReceiveIdoc 请求消息 （入站） 通过调用**WriteBodyContents**方法对于消息**XmlDictionaryWriter**实现节点值流式处理。  
  
 有关流式处理平面文件 （字符串） Idoc 使用 WCF 通道模型的详细信息，请参阅[SAP 使用 WCF 通道模型中流式处理平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。  
  
## <a name="see-also"></a>另请参阅  
[使用 WCF 通道模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)