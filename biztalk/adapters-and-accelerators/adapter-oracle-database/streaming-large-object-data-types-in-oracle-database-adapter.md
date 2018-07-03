---
title: 流式处理 Oracle 数据库适配器中的大型对象数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, support in the WCF service model
- streaming, support for
- streaming, support in BizTalk Server
- streaming, support in the WCF channel model
ms.assetid: c6cbe870-6794-4bf1-90c1-db65a242e8fe
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af0e81c5e2430dad50090637069713680c900d13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994110"
---
# <a name="streaming-large-object-data-types-in-oracle-database-adapter"></a>Oracle 数据库适配器中的流式处理大型对象数据类型
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]支持 Oracle 大型对象 (LOB) 数据类型的流式处理。 使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]调用操作和通过交换 SOAP 消息返回响应。 SOAP 消息正文组成的 XML 节点。  
  
 有两种类型的消息流处理的适配器支持：  
  
- **节点流**。 在节点流式处理的每个节点是缓冲的适配器，发送到 Oracle 数据库之前 （或返回到客户端）。 这意味着，对于 LOB 数据类型，整个值读取到缓冲区。  
  
- **节点值流式处理**。 在节点值流式处理节点的实际值可以进行流式处理 Oracle 数据库和客户端之间的块区中。 节点值流式处理支持端到端的流式处理的 Oracle 数据库适配器客户端之间的 LOB 数据类型。  
  
  这两种流式处理模式依赖于支持流式处理的节点和节点值在 WCF 中消息流处理。 出于此原因，LOB 类型的流式处理被密切关系到如何创建和使用适配器和客户端应用程序消息。 结果之一就是，流式处理 LOB 类型不支持相同跨所有编程模型。  
  
  本主题中的部分提供：  
  
- 有关如何流式处理的消息在 WCF 中支持和如何实现适配器的基本背景信息。  
  
- 有关如何流式处理 LOB 数据类型时，才支持每个编程模型中使用适配器的信息。  
  
## <a name="streaming-fundamentals"></a>流式处理的基础知识  
 流式处理由实现支持[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]组成：  
  
-   在 WCF 消息流式处理支持。  
  
-   Oracle 客户端库 (ODP.NET) 中的流式处理支持。  
  
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
  
### <a name="streaming-support-in-the-oracle-client-library-odpnet"></a>Oracle 客户端库 (ODP.NET) 中的流式处理支持  
 ODP.NET 支持流式处理按以下方式：  
  
-   仅在 Oracle LOB 数据类型支持流式处理。  
  
-   对于某些表 （和视图） 的操作，LOB 数据类型进行缓冲处理。 因此，支持任何流式处理。  
  
### <a name="internal-message-handling-by-the-adapter"></a>内部消息处理由适配器  
 适配器支持流式处理按以下方式：  
  
-   该适配器扩展了**消息**若要实现自定义消息类**Microsoft.Adapters.AdapterUtilities.AdapterMessage**。 它会创建**AdapterMessage**对于所有 WCF 都消息提供给适配器客户端; 这包括所有出站操作的响应都消息和 POLLINGSTMT 操作的请求消息。 这使得适配器可以支持节点值为 ReadLOB 操作流式处理，从而**XmlReader**支持**ReadValueChunk**到适配器客户端。  
  
-   适配器使用的所有使用的自定义实现从客户端接收的消息**XmlDictionaryWriter**。  
  
-   适配器创建发送到客户端使用的自定义实现的所有消息**XmlBodyWriter**，ReadLOB 响应消息除外。 （这包括所有出站操作的响应消息和 POLLINGSTMT 操作的请求消息。）  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>WCF 通道模型中的流式处理支持  
 下表提供了有关如何流式处理中的 WCF 通道模型支持的详细的信息。  
  
|运算|流式处理的节点|节点值流式处理|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|表插入操作|支持*|不支持在适配器和 Oracle 数据库之间。 支持客户端和适配器之间|不支持流式处理的端到端节点的值，因为将 LOB 列的值由 ODP.NET，进行缓冲，则执行插入。 但是，节点值流式处理客户端和适配器之间有可能 LOB 列，如果客户端创建的消息**BodyWriter**。|  
|表选择操作|是否支持|是否支持|该适配器将使用**BodyWriter**创建响应消息。 如果客户端使用消息使用**XmlDictionaryWriter**，节点值流式处理 LOB 列时发生。|  
|表更新操作|是否支持|不支持在适配器和 Oracle 数据库之间。 支持客户端和适配器之间。|不支持流式处理的端到端节点的值，因为将 LOB 列的值进行缓冲通过 ODP.NET，，然后执行更新。 但是，节点值流式处理客户端和适配器之间有 LOB 列可能的如果客户端创建的消息**BodyWriter**。|  
|表删除操作|是否支持|不支持在适配器和 Oracle 数据库之间。 支持客户端和适配器之间。|不支持流式处理的端到端节点的值，因为通过 ODP.NET 进行缓冲 LOB 列的值，然后执行删除操作。 但是，节点值流式处理客户端和适配器之间有 LOB 列可能的如果客户端创建的消息**BodyWriter**。|  
|表 ReadLOB 操作|是否支持|是否支持|ReadLOB 操作主要设计到流的 WCF 服务模型中的 LOB 数据列。 在 WCF 通道模型中，如果客户端使用消息使用**XmlReader** (通过调用**GetReaderAtBodyContents**在响应消息的方法)，会发生流式处理端到端节点的值。 这是因为该适配器返回**XmlReader**支持**ReadValueChunk**调用 ReadLOB 响应消息。 但是，建议不要使用 WCF 通道模型从 ReadLOB 操作。 可以改为使用选择操作或 SQLEXECUTE 操作。|  
|表 UpdateLOB 操作|是否支持|是否支持|该适配器将使用**XmlDictionaryWriter**来使用请求消息。 如果客户端使用**BodyWriter**若要创建请求消息，流式处理 LOB 数据的端到端节点的值时发生。|  
|SQLEXECUTE 操作|是否支持|是否支持|该适配器将使用**BodyWriter**创建响应消息。<br /><br /> 如果客户端使用**XmlDictionaryWriter**若要使用的响应消息，流式处理 LOB 数据的端到端节点的值时发生。<br /><br /> 请求消息不支持流式处理的端到端节点的值，因为它可以调用 Oracle 数据库上的操作之前，适配器必须缓冲所有操作数。|  
|存储的过程和函数操作|是否支持|是否支持|该适配器将使用**BodyWriter**创建响应消息。<br /><br /> 如果客户端使用**XmlDictionaryWriter**若要使用的响应消息，流式处理 LOB 数据的端到端节点的值时发生。 (这意味着，对于扩展支持流式处理和 IN 出过程和函数参数的响应消息中。)<br /><br /> 请求消息不支持流式处理的端到端节点的值，因为它可以调用 Oracle 数据库上的操作之前，适配器必须缓冲所有操作数。|  
|POLLINGSTMT 操作|是否支持|是否支持|该适配器将使用**BodyWriter**创建 POLLINGSTMT 请求消息。 如果客户端使用消息使用**XmlDictionaryWriter**，就会发生流式处理 LOB 列的节点的值。|  
  
 有关如何实现使用 WCF 通道模型时在代码中流式处理 LOB 数据的信息，请参阅[流式处理 Oracle 数据库 LOB 数据类型使用的 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)。  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>WCF 服务模型中的流式处理支持  
 序列化和反序列化消息的 XML 表示形式和该消息的托管的代码对象表示形式之间需要写入和读取到内存中的整个消息。 出于此原因，流式处理的节点和节点值流式传输都不支持针对大多数操作。  
  
 唯一的例外是 ReadLOB 操作。 实现此操作是专门为支持端到端流式处理读取的 WCF 服务模型中的表和视图 LOB 列。  
  
## <a name="streaming-support-in-biztalk-server"></a>BizTalk Server 中的流式处理支持  
 下表提供了有关如何流式处理 BizTalk Server 中支持的详细的信息。 ("适配器"的所有引用是否都引用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; Wcf-custom 适配器始终引用此表中其完整名称。)  
  
|运算|流式处理的节点|节点值流式处理|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|表插入操作|支持*|不支持之间的适配器和 Oracle 数据库中;但是，BizTalk Server 和适配器之间传输数据。|不支持流式处理的端到端节点的值，因为将 LOB 列的值由 ODP.NET 进行缓冲，则执行插入。 但是，节点值流式处理 BizTalk Server 和适配器之间的支持，LOB 数据类型因为 WCF 自定义适配器创建的消息**BodyWriter**。|  
|表选择操作|是否支持|是否支持|WCF 自定义适配器将使用**XmlDictionaryWriter**来使用响应消息，因此支持 LOB 类型的流式处理的端到端节点的值。|  
|表更新操作|是否支持|不支持之间的适配器和 Oracle 数据库中;但是，BizTalk Server 和适配器之间传输数据。|不支持流式处理的端到端节点的值，因为通过 ODP.NET 进行缓冲 LOB 列的值，然后执行更新。 但是，节点值流式处理 BizTalk Server 和适配器之间的支持，LOB 数据类型因为 WCF 自定义适配器创建的消息**BodyWriter**。|  
|表删除操作|是否支持|不支持之间的适配器和 Oracle 数据库中;但是，BizTalk Server 和适配器之间传输数据。|不支持流式处理的端到端节点的值，因为通过 ODP.NET 进行缓冲 LOB 列的值，然后执行删除操作。 但是，节点值流式处理 BizTalk Server 和适配器之间的支持，LOB 数据类型因为 WCF 自定义适配器创建的消息**BodyWriter**。|  
|表 ReadLOB 操作|为 BizTalk Server 不支持 ReadLOB 操作。|为 BizTalk Server 不支持 ReadLOB 操作。|为 BizTalk Server 不支持 ReadLOB 操作。 改为使用选择的操作或 SQLEXECUTE 操作。|  
|表 UpdateLOB 操作|是否支持|是否支持|WCF 自定义适配器将使用**BodyWriter**创建请求消息，因此支持 LOB 数据类型的流式处理的端到端节点的值。|  
|SQLEXECUTE 操作|是否支持|是否支持|WCF 自定义适配器将使用**XmlDictionaryWriter**来使用响应消息，因此支持端到端节点的值在响应消息中的 LOB 数据类型的流式处理。<br /><br /> 请求消息不支持流式处理的端到端节点的值，因为它可以调用 Oracle 数据库上的操作之前，适配器必须缓冲所有操作数。|  
|存储的过程和函数操作|是否支持|是否支持|WCF 自定义适配器将使用**XmlDictionaryWriter**来使用响应消息，因此支持端到端节点的值在响应消息中的 LOB 数据类型的流式处理。 (这意味着，对于扩展支持流式处理和 IN 出过程和函数参数的响应消息中。)<br /><br /> 请求消息不支持流式处理的端到端节点的值，因为它可以调用 Oracle 数据库上的操作之前，适配器必须缓冲所有操作数。|  
|POLLINGSTMT 操作|是否支持|是否支持|WCF 自定义适配器将使用**XmlDictionaryWriter**使用 （入站） 的请求消息，因此支持 LOB 数据类型的流式处理的端到端节点的值。|  
  
## <a name="see-also"></a>请参阅  
[开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)