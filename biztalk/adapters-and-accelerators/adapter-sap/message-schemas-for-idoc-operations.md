---
title: "为 IDOC 操作消息架构中 BizTalk 我 SAP 适配器 |Microsoft 文档"
description: "消息操作、 结构和操作发送和接收到的 Idoc 使用 mySAP 适配器-BizTalk 适配器包 (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 601aa9f9-e42f-47aa-b020-7a1eed4f0780
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d6cc5a7c8c651bcd9fcc6198b7069180c511bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-idoc-operations"></a>IDOC 操作的消息架构
中间文档 (IDOC) 是用于以异步方式与 SAP 和非 SAP 系统进行通信的 SAP 支持的标准化的 EDI 类似文档。 IDOC 用于发送和接收到或从贸易合作伙伴的 SAP 系统或外部程序的销售订单类似的商业文档。  
  
 虽然 SAP 系统支持多个端口类型来发送和接收 IDOC （例如，文件端口或 CPIC 端口），但[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持发送和接收到的 IDOC 通过 tRFC 端口。  
  
-   为出站 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]充当 tRFC 客户端并调用以将 IDOC 发送到 SAP RFC。  
  
-   为入站 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]充当 tRFC 服务器并接受来自 SAP 的 tRFC 客户端调用，以接收 IDOC。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现在可用来发送和接收到的 IDOC 与 SAP 系统的 IDOC 节点下的四个操作。  
  
-   **SendIdoc**。 将 IDOC 发送到适配器中，作为字符串数据。 直接在 IDOC 根节点下显示此操作。 同一操作适用于所有 Idoc。  
  
-   **发送**。 将 IDOC 发送到适配器中，作为强类型数据。 此操作在特定节点下显示为每个 IDOC。  
  
-   **ReceiveIdoc**。 作为字符串数据从适配器接收 IDOC。 直接在 IDOC 根节点下显示此操作。 同一操作适用于所有 Idoc。  
  
-   **接收**。 从适配器接收 IDOC，作为强类型数据。 此操作在特定节点下显示为每个 IDOC。  
  
> [!NOTE]
>  这些四个操作提供程序之间交换 Idoc 不同的方法和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 适配器始终使用 RFC （如在下一节中讨论） 发送或接收到的 Idoc 与 SAP 系统。  
  
 除了使用四个 IDOC 操作之一，你可以还发送或接收 IDOC 通过内部使用的 Rfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 SAP 系统交换 Idoc。 有关如何概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 Idoc，请参阅[SAP 中的 Idoc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。  
  
 本主题包含有关消息架构和用于 IDOC 操作的消息操作的信息。  
  
## <a name="rfcs-used-by-the-sap-adapter-to-send-and-receive-idocs"></a>Rfc SAP 适配器用于发送和接收到的 Idoc  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用以下远程函数调用 (文档 Rfc) 内部与 SAP 系统交换 IDOC。 在出站端 （到 SAP 系统的适配器），该适配器充当 tRFC 客户端调用 RFC。 在入站端 (SAP 到适配器)，SAP 调用适配器，它将充当 tRFC 服务器上的 RFC。  
  
|RFC|Description|  
|---------|-----------------|  
|IDOC_INBOUND_ASYNCHRONOUS|从版本 4.0 及更高版本使用此函数模块。 在对 4.x 版本有效的记录类型，它处理 IDOC。 这可确保，支持较长的 IDOC 段名称。<br /><br /> 此 RFC 的参数包括：<br /><br /> -idoc_control_rec_40 （SAP 结构是 EDI_DC40）<br /><br /> -idoc_data_rec_40 （SAP 结构是 EDI_DD40）<br /><br /> IDOC 控制记录包含以下字段：<br /><br /> - **Mestyp**。 逻辑消息类型。 业务表达消息。 此字段是必需字段。<br /><br /> - **Idoctyp**。 IDOC 基本结构。 此字段标识的此消息的布局集。 此字段是必需字段。<br /><br /> -                      **Cimtyp**。 客户扩展的结构。 如果 SAP 基本结构进行扩展，客户必须为指定名称，该扩展的结构。 如果客户已进行一项增强功能; 这是必填字段否则为初始。<br /><br /> - **合作伙伴字段**。 这些是发送方和接收端合作伙伴参数，如合作伙伴类型、 伙伴号、 合作伙伴函数。<br /><br /> IDOC 数据记录包含以下字段：<br /><br /> - **标头字段**。 分段标头字段，如表名称、 段号、 的段类型。 这些是必填字段。<br /><br /> -                      **Sdata**。 使用 IDOC 的数据的 1000年字节字符字段。这是必填字段。|  
|INBOUND_IDOC_PROCESS|此函数模块用于最多 4.0 版本。 在对 3.x 版本有效的记录类型，它处理 IDOC。 还有可能要在 4.x 中使用此函数模块。<br /><br /> 此 RFC 的参数包括：<br /><br /> -idoc_control （SAP 结构是 EDI_DC）<br /><br /> -idoc_data （SAP 结构是 EDI_DD）|  
  
## <a name="operations-to-send-idocs"></a>操作发送到的 Idoc  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开客户端将 Idoc 发送到 SAP 系统的发送和 SendIdoc 操作。 对于发送操作中，IDOC 表示为强类型数据;对于 SendIdoc 操作中，IDOC 表示为字符串数据。 这些操作确定 IDOC 数据适配器和你的应用程序之间的表示方式。 适配器始终使用将发送到的 Idoc 给 SAP IDOC_INBOUND_ASYNCHRONOUS 或 IDOC_INBOUND_PROCESS (t) RFC。 若要将 IDOC 发送到 SAP 系统，你可以使用发送或 SendIdoc 操作中，或您可直接调用适当的 RFC。  
  
### <a name="message-structures-for-idoc-client-operations"></a>IDOC 客户端操作的消息结构  
 下表显示发送和 SendIdoc 操作的消息结构。  
  
|运算|XML 结构|Description|  
|---------------|-------------------|-----------------|  
|Send|`<Send xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                    [CIMTYP]/[RELNO]/Send">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData>   <guid>guid</guid> </Send>`|将强类型的 IDOC 发送到 SAP<br /><br /> -IDOC 架构是强类型。<br /><br /> -公开控制记录的字段。<br /><br /> -公开包括段标头和段字段的数据记录字段。<br /><br /> [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将 GUID 与 SAP 事务 ID (TID)，并用于将 IDOC 发送相关联。 你可以选择是否在请求消息中指定的 GUID。 如果在请求消息中，不包含 GUID[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]生成一个密钥。 在响应消息中返回的 GUID。|  
|发送响应|`<SendResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/         [IDOCTYP]/[CIMTYP]/[RELNO]/Send">   <guid>guid</guid> </SendResponse>`|指示 IDOC，已发送到 SAP 系统。<br /><br /> 如果**AutoConfirmSentIdocs**绑定属性是**true**、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]自动确定事务在 SAP 系统上的，你可以忽略响应中返回的 GUID。 如果**AutoConfirmSentIdocs**绑定属性是**false**，必须调用**RfcConfirmTransID**具有 GUID 的操作返回[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到完成事务在 SAP 系统上。<br /><br /> 你可以调用**SapAdapterUtilities.ConvertGuidToTid**方法来获取 TID 与的工作 (LUW) 的逻辑单元关联。|  
|SendIdoc|`<SendIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData>   <guid>guid</guid> </SendIdoc>`|将弱类型 IDOC 发送到 SAP。<br /><br /> -IDOC 架构是弱类型。<br /><br /> -作为单个字符串字段组成的控制记录和数据记录公开 IDOC。<br /><br /> [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将 GUID 与它使用以将 IDOC 发送 SAP TID 相关联。 你可以选择是否在请求消息中指定的 GUID。 如果在请求消息中，不包含 GUID[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将生成一个构造函数。 在响应消息中返回的 GUID|  
|SendIdoc 响应|`<SendIdocResponse xmlns="[MSG_VERSION]/Idoc">   <guid>guid</guid> </SendIdocResponse>`|指示 IDOC，已发送到 SAP 系统。<br /><br /> 如果**AutoConfirmSentIdocs**绑定属性是**true**、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]自动确定事务在 SAP 系统上的，你可以忽略响应中返回的 GUID。 如果**AutoConfirmSentIdocs**绑定属性是**false**，必须调用**RfcConfirmTransID**具有 GUID 的操作返回[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到完成事务在 SAP 系统上。<br /><br /> 你可以调用**SapAdapterUtilities.ConvertGuidToTid** LUW 与关联的方法来获取 TID。|  
  
 [MSG_VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.Sap/2007/03。  
  
 [VERSION] = IDOC 发行版 （2 或 3）。  
  
 [IDOCTYP] = IDOC 类型;例如，ORDERS05。  
  
 [CIMTYP] = Cimtype 的自定义的 IDOC。  
  
 [RELNO] = 发行版号;例如，620。  
  
 [EDI_DC40/EDI_DC] = EDI_DC40 版本发布的版本 3 Idoc 和为 EDI_DC version2 Idoc。  
  
 [EDIDC_FIELD] = 构成 EDI_DC40/EDI_DC 控件记录结构的字段。  
  
 [SEGMENT_DEFN] = 段定义名称 （不段类型名称）;例如，E2EDK01005。 请注意，段定义节点无法还显示在某个段组节点下, 基于的 idoc 的结构。  
  
 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = 每个段都有一组标准的跟段数据的标头字段组成的段标题。 段数据的所有段字段和数据组成。 此节点表示段标头字段;例如，DATAHEADERCOLUMN_SEGNAM。  
  
 [SEG_FIELD] = 构成特定段定义 [SEGMENT_DEFN] 段字段名称。  
  
 [guid] = GUID 参数。  
  
### <a name="message-actions-for-idoc-client-operations"></a>IDOC 客户端操作的消息操作  
 下表显示发送和 SendIdoc 操作的消息操作。  
  
|运算|操作|示例|  
|---------------|------------|-------------|  
|Send|[MESSAGE_VERSION] /Idoc/ [VERSION] / [IDOCTYP] / [CIMTYP] / [RELNO] / 发送|http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send|  
|发送响应|[MESSAGE_VERSION] /Idoc/ [VERSION] / [IDOCTYP] / [CIMTYP] / [RELNO] / 发送/响应|http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send/response|  
|SendIdoc|[MESSAGE_VERSION] / Idoc/SendIdoc|http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc|  
|SendIdoc 响应|[MESSAGE_VERSION] / Idoc/SendIdoc/响应|http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc/response|  
  
 [MESSAGE_VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.Sap/2007/03。  
  
 [VERSION] = IDOC 发行版 （2 或 3）。  
  
 [IDOCTYP] = IDOC 类型;例如，ORDERS05。  
  
 [CIMTYP] = Cimtype 的自定义的 IDOC。  
  
 [RELNO] = 发行版号;例如，620。  
  
## <a name="operations-to-receive-idocs"></a>操作接收到的 Idoc  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开应用程序从某个 SAP 系统接收到的 Idoc 的接收和 ReceiveIdoc 操作。 接收操作的 IDOC 表示为强类型数据;对于 ReceiveIdoc 操作中，IDOC 表示为字符串数据。  
  
 这些操作确定如何 IDOC 数据发出的适配器到你的应用程序。 适配器始终会从 SAP 系统的 Idoc 作为 IDOC_INBOUND_ASYNCHRONOUS 或 IDOC_INBOUND_PROCESS tRFC 接收。 你可以使用接收或 ReceiveIdoc 操作中，也可以在 RFC 格式接收 IDOC 数据。 你设置**ReceiveIdocFormat**绑定属性，以指定在其中适配器发出到你的应用程序的 IDOC 数据的格式。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
### <a name="message-structures-for-idoc-receive-operations"></a>消息结构的 IDOC 接收操作  
 下表显示在接收和 ReceiveIdoc 操作的消息结构。  
  
|运算|XML 结构|Description|  
|---------------|-------------------|-----------------|  
|Receive|`<Receive xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                 [CIMTYP]/[RELNO]/Receive">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData> </Receive>`|从 SAP 接收强类型的 IDOC<br /><br /> -IDOC 架构是强类型。<br /><br /> -公开控制记录的字段。<br /><br /> -公开包括段标头和段字段的数据记录字段。|  
|接收响应|`<ReceiveResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/         [CIMTYP]/[RELNO]/Receive"> </ReceiveResponse>`|指示已从 SAP 系统接收了 IDOC。|  
|ReceiveIdoc|`<ReceiveIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData> </ReceiveIdoc>`|从 SAP 接收弱类型 IDOC。<br /><br /> -IDOC 架构是弱类型。<br /><br /> -作为单个字符串字段组成的控制记录和数据记录公开 IDOC。|  
|ReceiveIdoc 响应|`<ReceiveIdocResponse xmlns="[MSG_VERSION]/Idoc"> </ReceiveIdocResponse>`|指示已从 SAP 系统接收了 IDOC。|  
  
 [MSG_VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.Sap/2007/03。  
  
 [VERSION] = IDOC 发行版 （2 或 3）。  
  
 [IDOCTYP] = IDOC 类型;例如，ORDERS05。  
  
 [CIMTYP] = Cimtype 的自定义的 IDOC。  
  
 [RELNO] = 发行版号;例如，620。  
  
 [EDI_DC40/EDI_DC] = EDI_DC40 版本发布的版本 3 Idoc 和 EDI_DC 为版本 2 Idoc。  
  
 [EDIDC_FIELD] = 构成 EDI_DC40/EDI_DC 控件记录结构的字段。  
  
 [SEGMENT_DEFN] = 段定义名称 （不段类型名称）;例如，E2EDK01005。 段定义节点也可以显示在基于的 idoc 结构段组节点下。  
  
 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = 每个段都有一组标准的跟段数据的标头字段组成的段标题。 段数据的所有段字段和数据组成。 此节点表示段标头字段;例如，DATAHEADERCOLUMN_SEGNAM。  
  
 [SEG_FIELD] = 构成特定段定义 [SEGMENT_DEFN] 段字段名称。  
  
#### <a name="receiving-an-idoc-in-rfc-format"></a>RFC 格式接收 IDOC  
 也可以在 RFC 格式接收到的 Idoc。 用于从 SAP 接收到的 Idoc 的 Rfc 是：  
  
-   版本 3 Idoc 的 IDOC_INBOUND_ASYNCHRONOUS。  
  
-   版本 2 Idoc 的 INBOUND_IDOC_PROCESS。  
  
 下面的代码演示 IDOC_INBOUND_ASYNCHRONOUS 操作的形式收到的 IDOC 的结构。  
  
```  
<IDOC_INBOUND_ASYNCHRONOUS xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <IDOC_CONTROL_REC_40>  
    <EDI_DC40 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <EDIDC_FIELD1>field1</EDIDC_FIELD1>  
      <EDIDC_FIELD2>field2</EDIDC_FIELD2>  
      …  
    </EDI_DC40>  
  <IDOC_DATA_REC_40>  
    <EDI_DD40 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      \<[SEG_HEADER_FIELD1]>value1\</[SEG_HEADER_FIELD1]>  
      \<[SEG_HEADER_FIELD2]>value2\</[SEG_HEADER_FIELD2]>  
      …  
      <SDATA>segment value</SDATA>  
    </EDI_DD40>  
    …  
  </IDOC_DATA_REC_40>  
</IDOC_INBOUND_ASYNCHRONOUS>  
```  
  
 [EDIDC_FIELD] = 构成 EDI_DC40/EDI_DC 控件记录结构的字段  
  
 [SEG_HEADER_FIELD] = 每个段都有一组标准的跟段数据的标头字段组成的段标题。 段数据的所有段字段和数据组成。 此节点表示段标头字段;例如，SEGNAM、 MANDT 和 DOCNUM。  
  
 有关格式 tRFC 操作的详细信息，请参阅[trfc 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  
  
### <a name="message-actions-for-idoc-receive-operations"></a>IDOC 的消息操作接收操作  
 下表显示在接收和 ReceiveIdoc 操作的消息操作。  
  
|运算|操作|示例|  
|---------------|------------|-------------|  
|Receive|[MESSAGE_VERSION] /Idoc/ [VERSION] / [IDOCTYP] / [CIMTYP] / [RELNO] / 接收|http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive|  
|接收响应|[MESSAGE_VERSION] /Idoc/ [VERSION] / [IDOCTYP] / [CIMTYP] / [RELNO] / 接收/响应|http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive/response|  
|ReceiveIdoc|[MESSAGE_VERSION] / Idoc/ReceiveIdoc|http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc|  
|ReceiveIdoc 响应|[MESSAGE_VERSION] / Idoc/ReceiveIdoc/响应|http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc/response|  
  
