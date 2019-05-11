---
title: 流式处理和 SAP 适配器 |Microsoft Docs
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
ms.openlocfilehash: 59ede457ffd415d3ac7cae9a15ebe61cf46a1138
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372766"
---
# <a name="streaming-and-the-sap-adapter"></a>流式处理和 SAP 适配器
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持流式处理本身和客户端应用程序之间的消息。 使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]调用操作和通过交换 SOAP 消息返回响应。 SOAP 消息正文组成的 XML 节点。  
  
 有两种类型的消息流处理的适配器支持：  
  
-   **节点流**。 在节点流中，一条消息可以进行流式处理节点在客户端和适配器之间的时间。 这意味着，整个节点的值是读取到缓冲区，然后发送给接收方。  
  
-   **节点值流式处理**。 在节点值流式处理节点的实际值可以进行流式处理客户端和适配器之间的块区中。 节点值流式处理可用于发送或接收大型 Idoc 使用 SendIdoc 或 ReceiveIdoc 操作。 这是因为单个节点中包含整个 IDOC。 （而不是强类型发送或接收 IDOC 数据分成多个节点的操作）。  
  
> [!IMPORTANT]
>  在适配器和客户端应用程序之间仅支持节点值流处理。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持流式处理与 SAP 系统的端到端节点的值。 这是因为 SAP 客户端库不支持此功能。  
  
 这两种流式处理模式依赖于支持流式处理的节点和节点值在 WCF 中消息流处理。 出于此原因，流式处理被密切关系到如何创建和使用适配器和客户端应用程序消息。 结果之一就是，消息流式处理不支持相同跨所有编程模型。  
  
 本主题中的部分提供：  
  
-   有关如何流式处理的消息在 WCF 中支持和如何实现适配器的基本背景信息。  
  
-   有关如何流式处理消息时，才支持每个编程模型中使用适配器的信息。  
  
## <a name="streaming-fundamentals"></a>流式处理的基础知识  
 流式处理由实现支持[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]组成：  
  
-   在 WCF 消息流式处理支持。  
  
-   SAP 客户端库中的流式处理支持。  
  
-   双向消息创建，并在内部使用的适配器。  
  
### <a name="message-streaming-support-in-wcf"></a>WCF 中的消息流支持  
 WCF 如何支持流式处理的消息取决于如何创建的消息和消息的使用方式。  
  
- WCF 消息创建使用静态**创建**方法**System.ServiceModel.Channels.Message**。 此方法有若干重载，支持不同的方法来传递消息正文。 可以通过传递消息的正文使用创建 WCF 消息：  
  
  -   一个**System.Xml.XmlReader**，或  
  
  -   一个**System.ServiceModel.Channels.BodyWriter**。  
  
- 可以使用已使用 WCF 消息  
  
  -   **XmlReader**通过调用**Message.GetReaderAtBodyContents()**，或  
  
  -   **XmlDictionaryWriter**通过调用**Message.WriteBodyContents(XmlDictionaryWriter)**。  
  
  下表显示了 WCF 创建和使用消息的不同组合的行为方式。  
  
|使用创建的消息|使用的消息|WCF 行为|  
|--------------------------|---------------------------|------------------|  
|**XmlBodyWriter**|**XmlDictionaryWriter**|**节点值流式处理**支持。 WCF 通过管道传递两个编写器组合起来以实现流式处理。 这两个**XmlBodyWriter**并**XmlDictionaryWriter**必须支持节点值为其发生流式处理。|  
|**XmlBodyWriter**|**XmlReader**|**节点流**支持。 WCF 在内部缓冲**XmlReader**。|  
|**XmlReader**|**XmlDictionaryWriter**|**节点流**支持。 WCF 在内部缓冲**XmlReader** ，并返回到调用**XmlDictionaryWriter**。|  
|**XmlReader**|**XmlReader**|**节点流**支持。 WCF 在内部缓冲**XmlReader**。|  
  
### <a name="streaming-support-in-the-sap-client-library"></a>SAP 客户端库中的流式处理支持  
 SAP 客户端库不支持流式处理。 因此流式处理端到端节点的值不受[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="internal-message-handling-by-the-adapter"></a>内部消息处理由适配器  
 适配器支持流式处理按以下方式：  
  
-   该适配器将使用 SendIdDoc 请求消息使用的自定义实现从客户端接收**XmlDictionaryWriter**。 它会使用从客户端接收的所有其他消息**XmlReader**。  
  
-   适配器创建 ReceiveIdoc 请求消息发送到客户端使用的自定义实现**XmlBodyWriter**。 它将创建它发送到客户端使用的其他所有消息**XmlReader**。  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>WCF 通道模型中的流式处理支持  
 下表提供了有关如何流式处理中的 WCF 通道模型支持的详细的信息。  
  
|操作|流式处理的节点|节点值流式处理|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|（从适配器到客户端） 的出站 RFC 和 BAPI 操作|不支持|不支持||  
|出站 tRFC 操作 （从适配器到客户端）|不支持|不支持||  
|发送 IDOC 的操作 （强类型）|不支持|不支持||  
|接收 IDOC 的操作 （强类型）|支持|不支持||  
|SendIdoc 操作 （字符串）|支持|支持|该适配器将使用**XmlDictionaryWriter**来使用请求消息。 如果客户端创建的消息**BodyWriter**，会出现节点值从客户端流式传输到适配器。|  
|ReceiveIdoc 操作 （字符串）|支持|支持|该适配器将使用**BodyWriter**创建请求消息。 如果客户端使用消息使用**XmlDictionaryWriter**，会出现节点值从适配器流式传输到客户端。|  
|RFC 的入站的操作|不支持|不支持||  
|入站 tRFC 操作|不支持|不支持||  
  
 有关如何实现节点值流式处理来发送和接收平面文件 （字符串） Idoc 使用 SendIdoc 和 ReceiveIdoc 操作在代码中的信息，请参阅[Stream SAP 使用 WCF 通道模型中的平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)。  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>WCF 服务模型中的流式处理支持  
 序列化和反序列化消息的 XML 表示形式和该消息的托管的代码对象表示形式之间需要写入和读取到内存中的整个消息。 出于此原因，流式处理的节点和节点值流式传输都不支持从 WCF 服务模型。  
  
## <a name="streaming-support-in-biztalk-server"></a>BizTalk Server 中的流式处理支持  
 下表提供了有关如何流式处理 BizTalk Server 中支持的详细的信息。  
  
|操作|流式处理的节点|节点值流式处理|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|（从适配器到客户端） 的 RFC 和 BAPI 操作|不支持|不支持||  
|tRFC 操作 （从适配器到客户端）|不支持|不支持||  
|发送 IDOC 的操作 （强类型）|不支持|不支持||  
|接收 IDOC 的操作 （强类型）|支持|不支持||  
|SendIdoc 操作 （字符串）|支持|支持|WCF 自定义适配器将使用**BodyWriter**创建请求消息，因此节点值流式处理支持。|  
|ReceiveIdoc 操作 （字符串）|支持|支持|WCF 自定义适配器将使用**XmlDictionaryWriter**来使用请求消息，因此节点值流式处理支持。|  
|RFC 的入站的操作|不支持|不支持||  
|入站 tRFC 操作|不支持|不支持||  
  
## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)