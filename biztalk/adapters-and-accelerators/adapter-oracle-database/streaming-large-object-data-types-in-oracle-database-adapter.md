---
title: 流式处理 Oracle 数据库适配器中的大型对象数据类型 |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda4d99eb381321139e4ed493f119f9eaf21623e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="streaming-large-object-data-types-in-oracle-database-adapter"></a>Oracle 数据库适配器中的流式处理大型对象数据类型
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]支持流式处理 Oracle 大型对象 (LOB) 数据类型。 与[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]调用操作和通过交换 SOAP 消息返回响应。 SOAP 消息正文组成 XML 节点。  
  
 有适配器支持的两种类型的消息流处理：  
  
-   **节点流**。 在节点流式处理每个节点是发送到 Oracle 数据库前缓冲适配器 （或返回到客户端）。 这意味着，对于 LOB 数据类型，整个值读取到缓冲区。  
  
-   **节点值流式处理**。 在节点值流式处理节点的实际值可以进行流式处理 Oracle 数据库和客户端之间的小区块中。 节点值流式处理支持端到端流式处理的 LOB 适配器客户端和 Oracle 数据库之间的数据类型。  
  
 这两种流式处理模式依赖于支持流式处理的节点和节点值在 WCF 中的消息流式处理。 为此，流式处理 LOB 类型与密切如何创建和使用的适配器和客户端应用程序消息。 一个操作的结果是，支持流式处理 LOB 类型不相同跨所有的编程模型。  
  
 本主题中的部分提供：  
  
-   有关如何消息流式处理在 WCF 中支持和如何通过适配器实现的基本的背景信息。  
  
-   有关如何流式处理 LOB 数据类型时，支持你在每个编程模型中使用该适配器的信息。  
  
## <a name="streaming-fundamentals"></a>流式处理的基础知识  
 用于流式处理通过实现支持[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]是的组合：  
  
-   在 WCF 中的消息流式处理支持。  
  
-   Oracle 客户端库 (ODP.NET) 中的流式处理支持。  
  
-   创建和使用内部适配器的双向消息。  
  
### <a name="message-streaming-support-in-wcf"></a>在 WCF 中的消息流式处理支持  
 WCF 支持上一条消息流式处理的方式取决于消息的创建方式以及如何处理消息。  
  
-   WCF 消息创建使用静态**创建**方法**System.ServiceModel.Channels.Message**。 此方法具有好几个重载，支持将传递消息正文的不同方式。 可以通过传递消息的正文使用创建 WCF 消息：  
  
    -   A **System.Xml.XmlReader**，或  
  
    -   A **System.ServiceModel.Channels.BodyWriter**。  
  
-   可以使用使用 WCF 消息  
  
    -   An **XmlReader** by calling **Message.GetReaderAtBodyContents()**, or  
  
    -   **XmlDictionaryWriter**通过调用**Message.WriteBodyContents(XmlDictionaryWriter)**。  
  
 下表显示 WCF 的创建和使用的消息的不同组合的行为方式。  
  
|使用创建的消息|与使用的消息|WCF 行为|  
|--------------------------|---------------------------|------------------|  
|**XmlBodyWriter**|**XmlDictionaryWriter**|**节点值流式处理**支持。 WCF 通过管道传递两个编写器在一起，若要启用流。 这两个**XmlBodyWriter**和**XmlDictionaryWriter**必须支持节点值来进行这流式处理。|  
|**XmlBodyWriter**|**XmlReader**|**节点流**支持。 WCF 内部缓冲**XmlReader**。|  
|**XmlReader**|**XmlDictionaryWriter**|**节点流**支持。 WCF 内部缓冲**XmlReader**和回调到**XmlDictionaryWriter**。|  
|**XmlReader**|**XmlReader**|**节点流**支持。 WCF 内部缓冲**XmlReader**。|  
  
### <a name="streaming-support-in-the-oracle-client-library-odpnet"></a>Oracle 客户端库 (ODP.NET) 中的流式处理支持  
 ODP.NET 支持按以下方式流式处理：  
  
-   只能针对 Oracle LOB 数据类型支持流式传输。  
  
-   对于某些表 （和视图） 的操作，进行缓冲 LOB 数据类型。 因此，支持没有流式处理。  
  
### <a name="internal-message-handling-by-the-adapter"></a>内部消息处理由适配器  
 适配器支持按以下方式流式处理：  
  
-   适配器扩展**消息**以实现一个自定义消息的类， **Microsoft.Adapters.AdapterUtilities.AdapterMessage**。 它将创建**AdapterMessage**对于所有 WCF 都消息，它提供了到适配器客户端; 这包括所有出站操作的响应都消息和 POLLINGSTMT 操作的请求消息。 这使支持节点值 ReadLOB 操作用于通过提供的流式处理的适配器**XmlReader**支持**ReadValueChunk**到适配器客户端。  
  
-   适配器使用通过使用的自定义实现从客户端接收的所有消息**XmlDictionaryWriter**。  
  
-   适配器会创建它将发送到客户端使用的自定义实现的所有消息**XmlBodyWriter**，ReadLOB 响应消息除外。 （这包括所有出站操作的响应消息和 POLLINGSTMT 操作的请求消息。）  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>WCF 通道模型中的流式处理支持  
 下表提供了有关如何流式处理支持 WCF 通道模型的详细的信息。  
  
|运算|流式处理的节点|节点值流式处理|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|表插入操作|支持*|不支持之间的适配器和 Oracle 数据库。 支持客户端和适配器之间|不支持流式处理的端到端节点的值，因为 LOB 列的值进行缓冲通过 ODP.NET，，然后执行插入。 但是，节点值流式处理客户端和适配器之间有可能 LOB 列，如果客户端创建的消息的**BodyWriter**。|  
|表选择操作|Supported|Supported|适配器使用**BodyWriter**创建响应消息。 如果客户端使用消息使用**XmlDictionaryWriter**，节点值流式处理 LOB 列时发生。|  
|表更新操作|Supported|不支持之间的适配器和 Oracle 数据库。 支持客户端和适配器之间。|不支持流式处理的端到端节点的值，因为 LOB 列的值进行缓冲通过 ODP.NET，，然后执行更新。 如果客户端创建的消息的节点值流式处理客户端和适配器之间但是，有可能 LOB 列**BodyWriter**。|  
|表删除操作|Supported|不支持之间的适配器和 Oracle 数据库。 支持客户端和适配器之间。|不支持流式处理的端到端节点的值，因为 LOB 列的值进行缓冲 ODP.NET 通过，然后执行删除操作。 如果客户端创建的消息的节点值流式处理客户端和适配器之间但是，有可能 LOB 列**BodyWriter**。|  
|表 ReadLOB 操作|Supported|Supported|ReadLOB 操作主要设计为 WCF 服务模型中的流 LOB 数据列。 在 WCF 通道模型中，如果客户端使用消息使用**XmlReader** (通过调用**GetReaderAtBodyContents**的响应消息的方法)，流式处理端到端节点值时发生。 这是因为该适配器返回**XmlReader**支持**ReadValueChunk**调用 ReadLOB 响应消息。 但是，建议不使用 WCF 通道模型 ReadLOB 操作。 可以改为使用选择的操作或 SQLEXECUTE 操作。|  
|表 UpdateLOB 操作|Supported|Supported|适配器使用**XmlDictionaryWriter**使用请求消息。 如果客户端使用**BodyWriter**若要创建请求消息，流式处理 LOB 数据的端到端节点的值在发生。|  
|SQLEXECUTE 操作|Supported|Supported|适配器使用**BodyWriter**创建响应消息。<br /><br /> 如果客户端使用**XmlDictionaryWriter**若要使用响应消息，流式处理 LOB 数据的端到端节点的值在发生。<br /><br /> 不支持请求消息流式处理的端到端节点的值，因为它可以调用 Oracle 数据库的操作之前，适配器必须缓冲的所有操作数。|  
|存储的过程和函数的操作|Supported|Supported|适配器使用**BodyWriter**创建响应消息。<br /><br /> 如果客户端使用**XmlDictionaryWriter**若要使用响应消息，流式处理 LOB 数据的端到端节点的值在发生。 (这意味着，对于扩展支持流式处理和 IN 出过程和函数参数的响应消息中。)<br /><br /> 不支持请求消息流式处理的端到端节点的值，因为它可以调用 Oracle 数据库的操作之前，适配器必须缓冲的所有操作数。|  
|POLLINGSTMT 操作|Supported|Supported|适配器使用**BodyWriter**创建 POLLINGSTMT 请求消息。 如果客户端使用消息使用**XmlDictionaryWriter**，则会出现节点值流式处理 LOB 列。|  
  
 有关如何实现流在代码中，当使用 WCF 通道模型的 LOB 数据的信息，请参阅[流式处理 Oracle 数据库 LOB 数据类型使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)。  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>WCF 服务模型中的流式处理支持  
 序列化和反序列化的 XML 表示形式一条消息的该消息的托管的代码对象的表示形式之间需要写入和读取到内存的整个消息。 因此，节点流式处理和流式处理的节点的值都不支持针对大多数操作。  
  
 唯一的例外是 ReadLOB 操作。 实现此操作是专门为了支持端到端流用于读取 WCF 服务模型中的表和视图 LOB 列。  
  
## <a name="streaming-support-in-biztalk-server"></a>BizTalk Server 中的流式处理支持  
 下表提供了有关如何流式处理在 BizTalk Server 中支持的详细的信息。 (对"适配器"的所有引用都指[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; WCF 自定义适配器始终由所引用它在此表中的完整名称。)  
  
|运算|流式处理的节点|节点值流式处理|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|表插入操作|支持*|之间的适配器和 Oracle 数据库中; 不支持但是，BizTalk Server 和适配器之间进行流式处理数据。|不支持流式处理的端到端节点的值，因为 LOB 列的值进行缓冲 ODP.NET 通过，然后执行插入。 但是，节点的值之间 BizTalk Server 和适配器流式处理支持 LOB 数据类型因为 WCF 自定义适配器创建的消息的**BodyWriter**。|  
|表选择操作|Supported|Supported|WCF 自定义适配器使用**XmlDictionaryWriter**来使用响应消息中，因此支持 LOB 类型流式处理的端到端节点的值。|  
|表更新操作|Supported|之间的适配器和 Oracle 数据库中; 不支持但是，BizTalk Server 和适配器之间进行流式处理数据。|不支持流式处理的端到端节点的值，因为 LOB 列的值进行缓冲 ODP.NET 通过，然后执行更新。 但是，节点的值之间 BizTalk Server 和适配器流式处理支持 LOB 数据类型因为 WCF 自定义适配器创建的消息的**BodyWriter**。|  
|表删除操作|Supported|之间的适配器和 Oracle 数据库中; 不支持但是，BizTalk Server 和适配器之间进行流式处理数据。|不支持流式处理的端到端节点的值，因为 LOB 列的值进行缓冲 ODP.NET 通过，然后执行删除操作。 但是，节点的值之间 BizTalk Server 和适配器流式处理支持 LOB 数据类型因为 WCF 自定义适配器创建的消息的**BodyWriter**。|  
|表 ReadLOB 操作|ReadLOB 操作不可用于 BizTalk Server。|ReadLOB 操作不可用于 BizTalk Server。|ReadLOB 操作不可用于 BizTalk Server。 改为使用选择的操作或 SQLEXECUTE 操作。|  
|表 UpdateLOB 操作|Supported|Supported|WCF 自定义适配器使用**BodyWriter**创建请求消息中，因此支持流式处理 LOB 数据类型的端到端节点的值。|  
|SQLEXECUTE 操作|Supported|Supported|WCF 自定义适配器使用**XmlDictionaryWriter**来使用响应消息中，因此支持流式处理响应消息中的 LOB 数据类型的端到端节点的值。<br /><br /> 不支持请求消息流式处理的端到端节点的值，因为它可以调用 Oracle 数据库的操作之前，适配器必须缓冲的所有操作数。|  
|存储的过程和函数的操作|Supported|Supported|WCF 自定义适配器使用**XmlDictionaryWriter**来使用响应消息中，因此支持流式处理响应消息中的 LOB 数据类型的端到端节点的值。 (这意味着，对于扩展支持流式处理和 IN 出过程和函数参数的响应消息中。)<br /><br /> 不支持请求消息流式处理的端到端节点的值，因为它可以调用 Oracle 数据库的操作之前，适配器必须缓冲的所有操作数。|  
|POLLINGSTMT 操作|Supported|Supported|WCF 自定义适配器使用**XmlDictionaryWriter**来使用 （入站） 请求消息，因此支持流式处理 LOB 数据类型的端到端节点的值。|  
  
## <a name="see-also"></a>另请参阅  
[开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)