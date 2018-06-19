---
title: 流式处理和 SAP 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, support in WCF service model
- streaming, node-value
- streaming, node
- streaming, support in BizTalk Server
- streaming, and the SAP adapter
- streaming, support in WCF channel model
ms.assetid: 9fa1788b-f21b-4dec-be14-27dd8080a9d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48b97b0349822dcca1ae6486e4a0b515778b4d4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218245"
---
# <a name="streaming-and-the-sap-adapter"></a>流式处理和 SAP 适配器
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持消息本身和客户端应用程序之间流式处理。 与[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]调用操作和通过交换 SOAP 消息返回响应。 SOAP 消息正文组成 XML 节点。  
  
 有适配器支持的两种类型的消息流处理：  
  
-   **节点流**。 在节点流中，一条消息可以进行流式处理节点客户端和适配器之间的一次。 这意味着，一个节点的整个值读入缓冲区以及然后发送到接收方。  
  
-   **节点值流式处理**。 在节点值流式处理节点的实际值可以进行流式处理客户端和适配器之间的小区块中。 节点值流式处理可用于发送或接收使用 SendIdoc 或 ReceiveIdoc 操作的大 Idoc。 这是因为整个 IDOC 包含在单个节点。 （而不是强类型发送或接收的 IDOC 数据分为多个节点的操作）。  
  
> [!IMPORTANT]
>  之间的适配器和客户端应用程序仅支持节点值流式处理。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持使用 SAP 系统流式处理的端到端节点的值。 这是因为 SAP 客户端库不支持此功能。  
  
 这两种流式处理模式依赖于支持流式处理的节点和节点值在 WCF 中的消息流式处理。 为此，流式处理与密切如何创建和使用的适配器和客户端应用程序消息。 一个操作的结果是，对消息流式处理的支持并不相同跨所有的编程模型。  
  
 本主题中的部分提供：  
  
-   有关如何消息流式处理在 WCF 中支持和如何通过适配器实现的基本的背景信息。  
  
-   有关如何消息流式处理时，支持你在每个编程模型中使用该适配器的信息。  
  
## <a name="streaming-fundamentals"></a>流式处理的基础知识  
 用于流式处理通过实现支持[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是的组合：  
  
-   在 WCF 中的消息流式处理支持。  
  
-   SAP 客户端库中的流式处理支持。  
  
-   创建和使用内部适配器的双向消息。  
  
### <a name="message-streaming-support-in-wcf"></a>在 WCF 中的消息流式处理支持  
 WCF 支持上一条消息流式处理的方式取决于消息的创建方式以及如何处理消息。  
  
-   WCF 消息创建使用静态**创建**方法**System.ServiceModel.Channels.Message**。 此方法具有好几个重载，支持将传递消息正文的不同方式。 可以通过传递消息的正文使用创建 WCF 消息：  
  
    -   A **System.Xml.XmlReader**，或  
  
    -   A **System.ServiceModel.Channels.BodyWriter**。  
  
-   可以使用使用 WCF 消息  
  
    -   **XmlReader**通过调用**Message.GetReaderAtBodyContents()**，或  
  
    -   **XmlDictionaryWriter**通过调用**Message.WriteBodyContents(XmlDictionaryWriter)**。  
  
 下表显示 WCF 的创建和使用的消息的不同组合的行为方式。  
  
|使用创建的消息|与使用的消息|WCF 行为|  
|--------------------------|---------------------------|------------------|  
|**XmlBodyWriter**|**XmlDictionaryWriter**|**节点值流式处理**支持。 WCF 通过管道传递两个编写器在一起，若要启用流。 这两个**XmlBodyWriter**和**XmlDictionaryWriter**必须支持节点值来进行这流式处理。|  
|**XmlBodyWriter**|**XmlReader**|**节点流**支持。 WCF 内部缓冲**XmlReader**。|  
|**XmlReader**|**XmlDictionaryWriter**|**节点流**支持。 WCF 内部缓冲**XmlReader**和回调到**XmlDictionaryWriter**。|  
|**XmlReader**|**XmlReader**|**节点流**支持。 WCF 内部缓冲**XmlReader**。|  
  
### <a name="streaming-support-in-the-sap-client-library"></a>SAP 客户端库中的流式处理支持  
 SAP 客户端库不支持流式处理。 因此流式处理端到端节点的值不支持通过[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="internal-message-handling-by-the-adapter"></a>内部消息处理由适配器  
 适配器支持按以下方式流式处理：  
  
-   适配器使用接收从客户端使用的自定义实现的 SendIdDoc 请求消息**XmlDictionaryWriter**。 它会使用从客户端收到的所有其他消息**XmlReader**。  
  
-   适配器创建 ReceiveIdoc 请求消息发送到客户端使用的自定义实现**XmlBodyWriter**。 它将创建它发送到客户端使用的所有其他消息**XmlReader**。  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>WCF 通道模型中的流式处理支持  
 下表提供了有关如何流式处理支持 WCF 通道模型的详细的信息。  
  
|运算|流式处理的节点|节点值流式处理|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|（从适配器到客户端） 的出站 RFC 和 BAPI 操作|不支持|不支持||  
|（从适配器到客户端） 的出站 tRFC 操作|不支持|不支持||  
|IDOC 发送操作 （强类型）|不支持|不支持||  
|IDOC 接收操作 （强类型）|是否支持|不支持||  
|SendIdoc 操作 （字符串）|是否支持|是否支持|适配器使用**XmlDictionaryWriter**使用请求消息。 如果客户端创建的消息的**BodyWriter**，会出现节点值从客户端流式传输到适配器。|  
|ReceiveIdoc 操作 （字符串）|是否支持|是否支持|适配器使用**BodyWriter**创建请求消息。 如果客户端使用消息使用**XmlDictionaryWriter**，会出现节点值从适配器流式传输到客户端。|  
|入站的 RFC 操作|不支持|不支持||  
|入站的 tRFC 操作|不支持|不支持||  
  
 有关如何实现节点值的代码来发送和接收平面文件 （字符串） Idoc 使用 SendIdoc 和 ReceiveIdoc 操作流式处理的信息，请参阅[SAP 使用 WCF 通道模型中的流平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>WCF 服务模型中的流式处理支持  
 序列化和反序列化的 XML 表示形式一条消息的该消息的托管的代码对象的表示形式之间需要写入和读取到内存的整个消息。 因此，节点流式处理和流式处理的节点的值都不支持从 WCF 服务模型。  
  
## <a name="streaming-support-in-biztalk-server"></a>BizTalk Server 中的流式处理支持  
 下表提供了有关如何流式处理在 BizTalk Server 中支持的详细的信息。  
  
|运算|流式处理的节点|节点值流式处理|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|（从适配器到客户端） 的 RFC 和 BAPI 操作|不支持|不支持||  
|tRFC 操作 （从适配器到客户端）|不支持|不支持||  
|IDOC 发送操作 （强类型）|不支持|不支持||  
|IDOC 接收操作 （强类型）|是否支持|不支持||  
|SendIdoc 操作 （字符串）|是否支持|是否支持|WCF 自定义适配器使用**BodyWriter**创建请求消息中，因此节点值流式处理支持。|  
|ReceiveIdoc 操作 （字符串）|是否支持|是否支持|WCF 自定义适配器使用**XmlDictionaryWriter**使用请求消息中，因此节点值流式处理支持。|  
|入站的 RFC 操作|不支持|不支持||  
|入站的 tRFC 操作|不支持|不支持||  
  
## <a name="see-also"></a>另请参阅  
[开发您的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)