---
title: "SAP 中的 Idoc 上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDOC, operations to receive an
- IDOCs
- IDOCs, operations on
- tRFC server
- IDOC, operations to send an
- RFC server
ms.assetid: 6abcc646-c7a3-48cf-a09e-01f516dcef97
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6a70e6bc4062a6c2865c9adb8f76d68a078e965
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-idocs-in-sap"></a>SAP 中的 Idoc 上的操作
Idoc 是 SAP 支持用于以异步方式与 SAP 和非 SAP 系统进行通信的标准化的 EDI 类似文档。 Idoc 用于发送和接收到或从贸易合作伙伴的 SAP 系统或外部程序的销售订单，例如，如"business"文档。  
  
 尽管 SAP 系统支持大量的发送和接收到的 Idoc 的端口类型 (如文件端口 CPIC 端口)，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持发送和接收到的 Idoc 通过 tRFC 端口。  
  
## <a name="operations-to-send-an-idoc"></a>操作以将 IDOC 发送  
 对 SAP 的所有 IDOC 调用内部都视为 tRFC 调用其中适配器充当 tRFC 客户端，以将 IDOC 发送的 SAP 中调用 RFC。 就像任何其他 tRFC 客户端调用，适配器客户端 （可选） 将 GUID 传递给适配器，这反过来将它与事务 ID (TID) 用于 SAP 系统上调用相关联。 （如果适配器客户端未通过 GUID，该适配器将生成其自己的 GUID。）向适配器客户端的响应消息中返回的 GUID。 适配器客户端可以使用此 GUID 以确认 TID SAP 系统上。 可以通过调用一种特殊的静态方法，在 SAP 绑定中，获得 tRFC 调用用于适配器实际 SAP TID **ConvertGuidToTid**。 具有实际 TID 可能有助于故障排除 SAP 系统上的问题。  
  
 在调用后将发送完成 IDOC，TID 必须确认 SAP 系统上。 这使得 SAP 系统从其数据库中删除 TID。 适配器客户端可以确认 TID SAP 系统上。  
  
-   显式，通过调用**RfcConfirmTransID**适配器上的操作。 此操作采用 （上面的响应消息中返回） 的 GUID，并会导致确认关联的 TID SAP 系统上的适配器。  
  
-   隐式，通过设置**AutoConfirmSentIdocs**绑定属性。 如果此绑定属性为 true，该适配器将自动提交 TID 后它将 IDOC 发送到 SAP 系统。 请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)有关详细信息。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用了以下 Rfc 将 IDOC 发送：  
  
-   INBOUND_IDOC_PROCESS。 使用此函数的模块有关 SAP 4.0 之前的版本。  
  
-   IDOC_INBOUND_ASYNCHRONOUS。 此函数模块是用于 SAP 版本 4.0 及更高版本。  
  
### <a name="sending-idocs-with-segment-data-across-multiple-lines"></a>与跨多行数据分段发送到的 Idoc  
 Idoc 被构成的段。 IDOC 平面文件中的每个段条目包含 （包含 DOCNUM 字段） 的段标头信息和数据分段。 在某些 Idoc，可以跨多行拆分数据分段。 例如：  
  
```  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment data wrapped from the previous line  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
```  
  
 基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持将此类 Idoc 发送到 SAP 系统。 若要支持发送此类 Idoc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]确定每个段数据是否是上一个，延续或者它是否是新的段数据。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]决定此分析每个段标头，查找 DOCNUM 字段。 如果对段数据已拆分到两行，第二行没有段标头和因此[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]未找到 DOCNUM 字段。 因此，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以确定它是否是上一段数据的延续。  
  
 例如，在的表示形式，如上所示的 IDOC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]未找到任何 DOCNUM 字段"`Segment data wrapped from the previous line`"并且能够决定行是上一段数据的延续。 考虑到的 IDOC 的大小在生产环境中，为每个段数据执行此类检查的平面文件可能会导致处理时间增加。  
  
> [!NOTE]
>  适配器使用的 DOCNUM 字段而不是回车换行符 (CRLF) 标识和提取每个段记录从 IDOC 数据。 如果控制和数据记录中的 DOCNUM 字段无效或部分为空，该适配器无法分析 IDOC。 因此，IDOC 不会发送到 SAP 系统。  
  
### <a name="operations-to-send-an-idoc"></a>操作以将 IDOC 发送  
 将 Idoc 发送到 SAP 系统支持以下操作：  
  
-   **发送**。 使用此操作以将 IDOC 发送到使用强类型的架构的 SAP 系统。 此操作的架构公开控件记录字段和数据记录字段，包括段标头和段字段。 发送操作是特定于 IDocType + CimType + ReleaseNumber + 版本组合。  
  
     此操作会显示每个 idoc 并位于中的特定 IDOC 节点下[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
    > [!NOTE]
    >  若要能够成功执行**发送**操作，你必须在 SAP 系统中有相关的授权。 有关详细信息，  
  
-   **SendIdoc**。 使用此操作以将 IDOC 发送到使用弱类型的架构的 SAP 系统。 此操作的架构将作为单个字符串字段组成的控制记录和数据记录公开 Idoc。 SendIdoc 操作将作为参数的 IDOC 字符串和一个 GUID。  
  
     这是为公开的 SAP 系统的所有 Idoc 中加以表示单个操作，可以在根目录下**IDOC**中的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
 有关详细信息：  
  
-   将 IDOC 发送到使用 BizTalk Server SAP 系统，请参阅[将 Idoc 发送到 SAP 使用 BizTalk server](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)。  
  
-   将 IDOC 发送到使用 WCF 服务模型 SAP 系统，请参阅[将 Idoc 发送到使用 WCF 服务模型的 SAP](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)。  
  
-   消息结构和用于发送 IDOC 的 SOAP 操作，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  
  
## <a name="operations-to-receive-an-idoc"></a>操作接收 IDOC  
 若要接收 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以具有作为 tRFC 服务器或 RFC 服务器的行为：  
  
-   为使适配器为 tRFC 服务器，绑定属性的行为**TidDatabaseConnectionString**必须设置为你计算机上的 TID 数据库的连接字符串。 对于 tRFC 服务器方案，该适配器接受从 SAP 系统的 tRFC 客户端调用，以接收 IDOC。  
  
-   为使适配器充当 RFC 服务器，行为**TidDatabaseConnectionString**应为 null （默认值）。 有关 RFC 服务器方案，该适配器接受从 SAP 系统的 RFC 客户端调用，以接收 IDOC。  
  
 以下 Rfc 用于发送和接收到的 Idoc;发送到的 Idoc 时, 适配器将使用这些 Rfc，而当接收到的 IDOC，SAP 系统使用它们。  
  
-   INBOUND_IDOC_PROCESS。 使用此函数的模块有关 SAP 4.0 之前的版本。  
  
-   IDOC_INBOUND_ASYNCHRONOUS。 此函数模块是用于 SAP 版本 4.0 及更高版本。  
  
 用于从 SAP 系统接收到的 Idoc 支持以下操作：  
  
-   **接收**。 使用此操作使用强类型的架构的 SAP 系统从接收 IDOC。 此操作的架构公开控件记录字段和数据包括段标头和段字段的记录字段。  
  
     此操作会显示每个 idoc 并位于中的特定 IDOC 节点下[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
    > [!NOTE]
    >  若要能够成功执行**接收**操作，你必须在 SAP 系统中有相关的授权。 有关详细信息，  
  
    > [!NOTE]
    >  使用**接收**操作，也可以接收多个 Idoc。  
  
-   **ReceiveIdoc**。 使用此操作使用弱类型的架构的 SAP 系统从接收 IDOC。 此操作的架构将作为单个字符串字段组成的控制记录和数据记录公开 Idoc。 此操作作为字符串下一条 XML 消息中接收到的 Idoc \<idocData > 标记。  
  
     这是为公开的 SAP 系统的所有 Idoc 中加以表示单个操作，可以在根目录下**IDOC**中的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
 当接收到的 Idoc，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持不同的消息格式，可以指定为绑定属性的值， **ReceiveIDocFormat**公开[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   如果设置为"类型"，XML 架构强类型化为特定所收到的 IDOC。 （从接收操作，就可以看到此消息的架构。 请注意，架构是不同的不同 Idoc）。 这会生成 XML IDOC。  
  
-   如果设置为"String"，传入的 IDOC 数据返回为字符串值。 （此消息的架构，可以查看从 ReceiveIdoc 操作）。 这将生成的 XML 消息\<idocData > 标记。  
  
-   如果设置为"Rfc"，消息架构匹配的 RFC 操作 IDOC_INBOUND_ASYNCHRONOUS 或 INBOUND_IDOC_PROCESS，具体取决于传入的 IDOC 版本的 RFC （或 tRFC） 架构。 如果指定此绑定属性，你应使用 IDOC_INBOUND_ASYNCHRONOUS 或 INBOUND_IDOC_PROCESS RFC 接收 IDOC。 在前两个选项中，适配器在内部使用此 RFC。 在此选项，则显式使用此 RFC 来接收 IDOC。  
  
 用于接收 IDOC 操作必须与匹配适配器发出的 IDOC 数据的格式。 下表提供了在其中您可以从 SAP 接收 IDOC 的不同组合的摘要。  
  
|若要接收 IDOC 使用|设置绑定属性 ReceiveIDOCFormat 到|  
|------------------------------|---------------------------------------------------|  
|**接收**操作|类型化|  
|**ReciveIdoc**操作|字符串|  
|IDOC_INBOUND_ASYNCHRONOUS RFC|Rfc|  
|INBOUND_IDOC_PROCESS RFC|Rfc|  
  
 另一个绑定属性**PadReceivedIdocsWithSpaces**可选字段时将填充以空格收到的 IDOC 接收的预期格式为"字符串"。 这使与接收到使用以前的版本的适配器的 IDOC 数据格式的兼容性。  
  
 有关绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
 有关详细信息：  
  
-   使用 BizTalk Server 中，某个 SAP 系统从接收 IDOC 请参阅[从 SAP 使用 BizTalk server 接收 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)。  
  
-   从 SAP 系统中使用 BizTalk Server 的事务上下文中接收 IDOC，请参阅[接收从通过使用 BizTalk Server 事务上下文中的 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)。  
  
-   消息结构和用于接收 IDOC 的 SOAP 操作，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  
  
##  <a name="BKMK_Authorize"></a>SAP 授权使用发送或接收操作  
 当你使用**发送**或**接收**操作发送或接收到的 Idoc 使用强类型的架构，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]内部调用 IDOCTYPE_READ_COMPLETE RFC 若要检索的元数据IDOC。 调用此 RFC 需要在 SAP 中的以下授权：  
  
```  
Authorisation object S_IDOCDEFT, Fields:  
EDI_TCD, value 'WE30'  
ACTVT, value - 03 (display)  
EDI_DOC, value  *  
EDI_CIM, value *  
```  
  
 可以使用在 SAP 中 SU01 事务可以添加的授权对象。 有关事务的详细信息，请与您的 SAP 管理员，或请参阅 SAP 文档。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)