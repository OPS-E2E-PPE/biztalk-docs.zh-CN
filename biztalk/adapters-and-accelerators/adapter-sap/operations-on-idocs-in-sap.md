---
title: 在 SAP 中的 Idoc 的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOC, operations to receive an
- IDOCs
- IDOCs, operations on
- tRFC server
- IDOC, operations to send an
- RFC server
ms.assetid: 6abcc646-c7a3-48cf-a09e-01f516dcef97
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9c3bbf45074024b8745b845b3f9ca85f5ff814e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972222"
---
# <a name="operations-on-idocs-in-sap"></a>在 SAP 中的 Idoc 的操作
Idoc 是 SAP 支持用于以异步方式与 SAP 和非 SAP 系统进行通信的标准化类似于 EDI 的文档。 Idoc 用于发送和接收"business"文档，例如销售订单，例如，与贸易合作伙伴的 SAP 系统或外部程序。  
  
 虽然 SAP 系统支持多个发送和接收 Idoc 的端口类型 (如文件端口 CPIC 端口)，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持发送和接收 Idoc 通过 tRFC 端口。  
  
## <a name="operations-to-send-an-idoc"></a>操作以发送 IDOC  
 所有对 SAP 的 IDOC 调用在内部视为 tRFC 调用中的适配器可用作 tRFC 客户端，并在 SAP 发送 IDOC 中调用 RFC。 就像任何其他 tRFC 客户端调用，适配器客户端 （可选） 将 GUID 传递给适配器，这又将它与事务 ID (TID) 用于 SAP 系统上调用相关联。 （如果适配器客户端未通过一个 GUID，适配器生成其自己的 GUID。）向适配器客户端的响应消息中返回的 GUID。 适配器客户端可以使用此 GUID 来确认 TID SAP 系统上。 实际 tRFC 调用可以获取通过调用一种特殊的静态方法，在 SAP 绑定中，适配器使用的 SAP TID **ConvertGuidToTid**。 无实际 TID 可能可用于 SAP 系统上进行问题排查。  
  
 在调用后将发送完成 IDOC，TID 必须确认 SAP 系统上。 这使 SAP 系统从其数据库中删除 TID。 适配器客户端可以确认 SAP 系统上的 TID。  
  
- 显式，通过调用**RfcConfirmTransID**在适配器上的操作。 此操作采用一个 GUID （上面的响应消息中返回），并会导致适配器需要确认相关联的 TID SAP 系统上。  
  
- 隐式，通过设置**AutoConfirmSentIdocs**属性绑定。 如果此绑定属性为 true，则适配器将自动提交 TID 后它将 IDOC 发送到 SAP 系统。 请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)有关详细信息。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用以下 Rfc 以将 IDOC 发送：  
  
- INBOUND_IDOC_PROCESS。 使用此函数模块的 SAP 在 4.0 之前的版本。  
  
- IDOC_INBOUND_ASYNCHRONOUS。 此函数模块是使用 SAP 版 4.0 及更高版本。  
  
### <a name="sending-idocs-with-segment-data-across-multiple-lines"></a>使用跨多行数据分段发送 Idoc  
 Idoc 被构成的段。 IDOC 平面文件中的每个段条目包含段标头信息 （包含 DOCNUM 字段） 和数据分段。 某些 Idoc 中段数据可以拆分到多个行。 例如：  
  
```  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment data wrapped from the previous line  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
```  
  
 基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持将此类 Idoc 发送到 SAP 系统。 若要支持发送此类 Idoc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]确定每个段数据的上一个延续或者它是否是新段数据。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]决定这通过分析每个段标头，然后查找 DOCNUM 字段。 如果段数据拆分到两行，第二行不具有的段标头并因此导致[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不到 DOCNUM 字段。 因此，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以确定它是上一段数据的延续。  
  
 例如，在表示形式，如上所示的 IDOC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]找不到任何 DOCNUM 字段中的"`Segment data wrapped from the previous line`"并且能够确定行是上一段数据的延续。 考虑到的 IDOC 大小在生产环境中，为每个段数据执行此类检查平面文件可能会导致处理时间增加。  
  
> [!NOTE]
>  适配器使用 DOCNUM 字段而不是回车换行符 (CRLF) 来标识和提取每个段记录从 IDOC 数据。 如果中的控件和数据记录的 DOCNUM 字段无效或部分保留为空，则适配器将无法分析 IDOC。 因此，不到 SAP 系统发送 IDOC。  
  
### <a name="operations-to-send-an-idoc"></a>操作以发送 IDOC  
 用于将 Idoc 发送到 SAP 系统支持以下操作：  
  
- **发送**。 使用此操作以将 IDOC 发送到 SAP 系统使用强类型化的架构。 此操作的架构公开控件记录字段和数据记录的字段，包括段标头和段字段。 发送操作是特定于 IDocType + CimType + ReleaseNumber + 版本组合。  
  
   此操作显示每个 idoc，并位于中的特定 IDOC 节点下[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
  > [!NOTE]
  >  若要能够成功执行**发送**操作，你必须在 SAP 系统中有相关的授权。 有关详细信息，  
  
- **SendIdoc**。 使用此操作以将 IDOC 发送到 SAP 系统使用弱类型的架构。 此操作的架构公开包含控制记录和数据记录的单个字符串字段为 Idoc。 SendIdoc 操作将 IDOC 字符串和一个 GUID 作为参数。  
  
   这是一次性显示所有 Idoc 公开的 SAP 系统，可在根目录下**IDOC**中的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
  有关详细信息：  
  
- 将 IDOC 发送到 SAP 系统使用 BizTalk Server，请参阅[发送到通过使用 BizTalk Server 的 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)。  
  
- 将 IDOC 发送到 SAP 系统使用 WCF 服务模型，请参阅[向使用 WCF 服务模型的 SAP 发送 Idoc](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)。  
  
- 消息结构和 SOAP 操作以发送 IDOC，请参见[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  
  
## <a name="operations-to-receive-an-idoc"></a>若要接收 IDOC 的操作  
 若要接收 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为 tRFC 服务器或 RFC 服务器行为：  
  
- 为使适配器为 tRFC 服务器，绑定属性的行为**TidDatabaseConnectionString**必须设置为您的计算机上的 TID 数据库的连接字符串。 TRFC 服务器方案中，对于适配器接受从 SAP 系统的 tRFC 客户端调用，用于接收 IDOC。  
  
- 适配器为 RFC 服务器行为**TidDatabaseConnectionString**应为 null （默认值）。 RFC 服务器方案，该适配器接受从 SAP 系统的 RFC 客户端调用，用于接收 IDOC。  
  
  以下 Rfc 用于发送和接收 Idoc;将发送 Idoc，适配器将使用这些 Rfc，而 SAP 系统接收 IDOC 时, 使用它们。  
  
- INBOUND_IDOC_PROCESS。 使用此函数模块的 SAP 在 4.0 之前的版本。  
  
- IDOC_INBOUND_ASYNCHRONOUS。 此函数模块是使用 SAP 版 4.0 及更高版本。  
  
  用于从 SAP 系统接收 Idoc 支持以下操作：  
  
- **接收**。 此操作用于从使用强类型架构的 SAP 系统接收 IDOC。 此操作的架构公开控件记录字段和数据包括段标头和段字段的记录字段。  
  
   此操作显示每个 idoc，并位于中的特定 IDOC 节点下[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
  > [!NOTE]
  >  若要能够成功执行**接收**操作，你必须在 SAP 系统中有相关的授权。 有关详细信息，  
  
  > [!NOTE]
  >  使用**接收**操作，也可能会收到多个 Idoc。  
  
- **ReceiveIdoc**。 此操作用于从 SAP 系统使用弱类型架构接收 IDOC。 此操作的架构公开为控制记录和数据记录组成的单个字符串字段的 Idoc。 此操作在下一条 XML 消息中字符串形式接收 Idoc \<idocData\>标记。  
  
   这是一次性显示所有 Idoc 公开的 SAP 系统，可在根目录下**IDOC**中的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
  在接收 Idoc 时,[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持不同的消息格式，可以指定为绑定属性的值， **ReceiveIDocFormat**公开[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 如果设置为"类型化"，XML 架构强类型化为特定所收到的 IDOC。 （从接收操作，就可以查看此消息的架构。 请注意，架构是不同的 idoc 不同）。 这会生成 XML IDOC。  
  
- 如果设置为"String"，传入的 IDOC 数据返回为字符串值。 （此消息的架构，可以查看从 ReceiveIdoc 操作）。 这将生成的 XML 消息\<idocData\>标记。  
  
- 如果设置为"Rfc"，消息架构匹配的 RFC 操作 IDOC_INBOUND_ASYNCHRONOUS 或 INBOUND_IDOC_PROCESS，具体取决于传入的 IDOC 版本的 RFC （或 tRFC） 架构。 如果指定此绑定的属性应使用 IDOC_INBOUND_ASYNCHRONOUS 或 INBOUND_IDOC_PROCESS RFC 接收 IDOC。 在前两个选项中，则适配器将在内部使用此 RFC。 在此选项中，您显式使用此 RFC 接收 IDOC。  
  
  用于接收 IDOC 的操作必须与匹配适配器发出的 IDOC 数据的格式。 下表提供了在其中你可以从 SAP 接收 IDOC 的不同组合的摘要。  
  
|若要接收 IDOC 使用|设置绑定属性 ReceiveIDOCFormat 到|  
|------------------------------|---------------------------------------------------|  
|**接收**操作|类型化|  
|**ReciveIdoc**操作|String|  
|IDOC_INBOUND_ASYNCHRONOUS RFC|Rfc|  
|INBOUND_IDOC_PROCESS RFC|Rfc|  
  
 另一个绑定属性**PadReceivedIdocsWithSpaces**为可选字段时填充空格与收到的 IDOC 接收所需格式为"String"。 这样，与使用以前版本的适配器接收 IDOC 数据格式的兼容性。  
  
 有关绑定属性的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
 有关详细信息：  
  
-   请参阅使用 BizTalk Server 中，某个 SAP 系统从接收 IDOC[从通过使用 BizTalk Server 的 SAP 接收 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)。  
  
-   从事务性上下文中使用 BizTalk Server 中的 SAP 系统接收 IDOC，请参阅[接收来自事务性上下文中使用 BizTalk server 中的 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)。  
  
-   消息结构和用于接收 IDOC 的 SOAP 操作，请参见[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  
  
##  <a name="BKMK_Authorize"></a> SAP 授权的使用发送或接收操作  
 当你使用**发送**或**接收**操作发送或接收 Idoc 使用强类型化的架构，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在内部调用 IDOCTYPE_READ_COMPLETE RFC，若要检索的元数据IDOC。 调用此 RFC 需要在 SAP 中的以下授权：  
  
```  
Authorisation object S_IDOCDEFT, Fields:  
EDI_TCD, value 'WE30'  
ACTVT, value - 03 (display)  
EDI_DOC, value  *  
EDI_CIM, value *  
```  
  
 您可以使用 sap SU01 事务添加授权对象。 有关事务的详细信息，请联系您的 SAP 管理员或，请参阅 SAP 文档。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)