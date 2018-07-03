---
title: IDOC 操作的消息架构在 BizTalk 中的我 SAP 适配器 |Microsoft Docs
description: 消息操作、 结构和操作来发送和接收 Idoc 使用 mySAP 适配器的 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 601aa9f9-e42f-47aa-b020-7a1eed4f0780
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ef2f5de5a9e7e13eb2fb53918cb1208a0aeeee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980022"
---
# <a name="message-schemas-for-idoc-operations"></a>IDOC 操作的消息架构
中间文档 (IDOC) 是用于以异步方式与 SAP 和非 SAP 系统进行通信的 SAP 支持的标准化类似于 EDI 的文档。 IDOC 用于发送和接收业务文档，如销售订单与贸易合作伙伴的 SAP 系统或外部程序。  

 虽然 SAP 系统支持多个端口类型来发送和接收 IDOC （例如，file 端口或 CPIC 端口），但[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持发送和接收 IDOC 使用 tRFC 端口。  

- 对于出站 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]充当 tRFC 客户端并调用以将 IDOC 发送到 SAP RFC。  

- 对于入站 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]充当 tRFC 服务器并接受来自 SAP 的 tRFC 客户端调用，用于接收 IDOC。  

  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示可用于发送和接收与 SAP 系统的 IDOC 的 IDOC 节点下的四个操作。  

- **SendIdoc**。 字符串数据作为将 IDOC 发送到适配器。 直接在 IDOC 根节点下显示此操作。 相同的操作用于所有 Idoc。  

- **发送**。 强类型化数据作为将 IDOC 发送到适配器。 此操作在特定的节点下显示为每个 IDOC。  

- **ReceiveIdoc**。 作为字符串数据从适配器接收 IDOC。 直接在 IDOC 根节点下显示此操作。 相同的操作用于所有 Idoc。  

- **接收**。 从适配器接收 IDOC 作为强类型化数据。 此操作在特定的节点下显示为每个 IDOC。  

> [!NOTE]
>  这些四个操作提供程序之间交换 Idoc 的不同的方式和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 适配器始终使用 RFC （如在下一节中所述） 来发送或接收与 SAP 系统的 Idoc。  

 除了使用四个 IDOC 操作之一，还可以发送或接收 IDOC，通过在内部使用的 Rfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]交换与 SAP 系统的 Idoc。 有关如何概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 Idoc，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。  

 本主题包含有关消息架构和用于 IDOC 操作的消息操作的信息。  

## <a name="rfcs-used-by-the-sap-adapter-to-send-and-receive-idocs"></a>SAP 适配器用于发送和接收 Idoc 的 Rfc  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在内部使用以下远程函数调用 (Rfc) 来交换与 SAP 系统的 IDOC。 在出站端 （到 SAP 系统的适配器），适配器可充当 tRFC 客户端以调用 RFC。 在入站端 (SAP 到适配器)，SAP 调用适配器，充当 tRFC 服务器上的 RFC。  

|RFC|Description|  
|---------|-----------------|  
|IDOC_INBOUND_ASYNCHRONOUS|从版本 4.0 及更高版本使用此函数模块。 在记录类型有效的 4.x 版本中，它处理 IDOC。 这可确保支持较长的 IDOC 段名称。<br /><br /> 此 rfc 参数包括：<br /><br /> -idoc_control_rec_40 （SAP 结构是 EDI_DC40）<br /><br /> -idoc_data_rec_40 （SAP 结构是 EDI_DD40）<br /><br /> IDOC 控制记录包含以下字段：<br /><br /> - **Mestyp**。 逻辑消息类型。 传达消息的业务含义。 此字段是必需字段。<br /><br /> - **Idoctyp**。 IDOC 的基本结构。 此字段标识使用此消息布局设置。 此字段是必需字段。<br /><br /> -                      **Cimtyp**。 客户扩展的结构。 如果 SAP 基础结构已扩展，客户必须为扩展插件的结构提供名称。 如果客户已增强功能; 这是必填字段否则为初始。<br /><br /> - **合作伙伴字段**。 这是发送端，接收方合作伙伴参数，如合作伙伴类型、 合作伙伴数量合作伙伴函数。<br /><br /> IDOC 数据记录包含以下字段：<br /><br /> - **标头字段**。 分段标头字段，例如表名称、 段数量的段类型。 这些是必填字段。<br /><br /> -                      **Sdata**。 1000 字节字符所使用的 IDOC 数据字段。这是必填字段。|  
|INBOUND_IDOC_PROCESS|此函数模块用于 4.0 的版本。 在记录类型有效的 3.x 版本中，它处理 IDOC。 还有可能要在 4.x 中使用此函数模块。<br /><br /> 此 rfc 参数包括：<br /><br /> -idoc_control （SAP 结构是 EDI_DC）<br /><br /> -idoc_data （SAP 结构是 EDI_DD）|  

## <a name="operations-to-send-idocs"></a>操作以发送 Idoc  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开客户端将 Idoc 发送到 SAP 系统的发送和 SendIdoc 操作。 发送操作 IDOC 表示为强类型化数据;SendIdoc 操作 IDOC 表示为字符串数据。 这些操作确定 IDOC 数据适配器与你的应用程序之间的表示方式。 适配器始终会向 SAP 的 Idoc 使用 IDOC_INBOUND_ASYNCHRONOUS 或 IDOC_INBOUND_PROCESS (t) RFC 发送。 若要将 IDOC 发送到 SAP 系统，您可以使用发送或 SendIdoc 操作，也可直接调用相应的 RFC。  

### <a name="message-structures-for-idoc-client-operations"></a>IDOC 客户端操作的消息结构  
 下表显示了发送和 SendIdoc 操作的消息结构。  


|     运算     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   XML 结构                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                   Description                                                                                                                                                                                                                                                                                                                                                                   |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Send        | `<Send xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                    [CIMTYP]/[RELNO]/Send">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData>   <guid>guid</guid> </Send>` |                                               将强类型化的 IDOC 发送到 SAP<br /><br /> -IDOC 架构是强类型化。<br /><br /> -公开控制记录字段。<br /><br /> -公开包括段标头和段字段的数据记录字段。<br /><br /> [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将 GUID 与 SAP 事务 ID (TID)，它使用以将 IDOC 发送相关联。 您可以选择是否要在请求消息中指定的 GUID。 如果请求消息中不包含 GUID[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]生成一个密钥。 响应消息中返回的 GUID。                                                |
|   发送响应   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         `<SendResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/         [IDOCTYP]/[CIMTYP]/[RELNO]/Send">   <guid>guid</guid> </SendResponse>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | 指示具有已对 IDOC 发送到 SAP 系统。<br /><br /> 如果**AutoConfirmSentIdocs**绑定属性是**true**，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]自动确认 SAP 系统上的事务，可以忽略响应中返回的 GUID。 如果**AutoConfirmSentIdocs**绑定属性是**false**，必须调用**RfcConfirmTransID**具有 GUID 的操作返回的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到完成 SAP 系统上的事务。<br /><br /> 可以调用**SapAdapterUtilities.ConvertGuidToTid**与工作 (LUW) 的逻辑单元关联的方法来获取 TID。 |
|     SendIdoc      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    `<SendIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData>   <guid>guid</guid> </SendIdoc>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                   向 SAP 发送弱类型的 IDOC。<br /><br /> -IDOC 架构是弱类型。<br /><br /> -公开为控制记录和数据记录组成的单个字符串字段的 IDOC。<br /><br /> [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将 GUID 与 SAP TID，它使用以将 IDOC 发送相关联。 您可以选择是否要在请求消息中指定的 GUID。 如果请求消息中不包含 GUID[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将生成一个。 响应消息中返回的 GUID                                                                    |
| SendIdoc 响应 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              `<SendIdocResponse xmlns="[MSG_VERSION]/Idoc">   <guid>guid</guid> </SendIdocResponse>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |             指示具有已对 IDOC 发送到 SAP 系统。<br /><br /> 如果**AutoConfirmSentIdocs**绑定属性是**true**，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]自动确认 SAP 系统上的事务，可以忽略响应中返回的 GUID。 如果**AutoConfirmSentIdocs**绑定属性是**false**，必须调用**RfcConfirmTransID**具有 GUID 的操作返回的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到完成 SAP 系统上的事务。<br /><br /> 可以调用**SapAdapterUtilities.ConvertGuidToTid** LUW 与关联的方法来获取 TID。             |

 [MSG_VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.Sap/2007/03。  

 [VERSION] = （2 或 3） 的 IDOC 版本。  

 [IDOCTYP] = IDOC 类型;例如，ORDERS05。  

 [CIMTYP] = Cimtype 的自定义 IDOC。  

 [RELNO] = 发行版号;例如，620。  

 [EDI_DC40/EDI_DC] = EDI_DC40 版发布的版本 3 Idoc 和为 EDI_DC version2 Idoc。  

 [EDIDC_FIELD] = 构成 EDI_DC40/EDI_DC 控制记录结构的字段。  

 [SEGMENT_DEFN] = 段定义名称 （不段类型名称）;例如，E2EDK01005。 请注意，也可能会段定义节点显示下一个段组节点中，基于的 IDOC 的结构。  

 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = 每个段具有包含一组标准的跟段数据的标头字段的段标头。 段数据包含的所有段字段和数据。 此节点表示的段标头字段;例如，DATAHEADERCOLUMN_SEGNAM。  

 [SEG_FIELD] = 构成特定段定义 [SEGMENT_DEFN] 段字段名称。  

 [guid] = GUID 参数。  

### <a name="message-actions-for-idoc-client-operations"></a>IDOC 客户端操作的消息操作  
 下表显示了发送和 SendIdoc 操作的消息操作。  


|     运算     |                                   操作                                   |                                   示例                                   |
|-------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------|
|       Send        |     [MESSAGE_VERSION]/Idoc/[VERSION] /[IDOCTYP]/[CIMTYP]/[RELNO]/Send      |     http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send      |
|   发送响应   | [MESSAGE_VERSION]/Idoc/[VERSION] /[IDOCTYP]/[CIMTYP]/[RELNO]/Send/response | http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send/response |
|     SendIdoc      |                      [MESSAGE_VERSION]/Idoc/SendIdoc                       |           http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc            |
| SendIdoc 响应 |                  [MESSAGE_VERSION]/Idoc/SendIdoc/response                  |       http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc/response       |

 [MESSAGE_VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.Sap/2007/03。  

 [VERSION] = （2 或 3） 的 IDOC 版本。  

 [IDOCTYP] = IDOC 类型;例如，ORDERS05。  

 [CIMTYP] = Cimtype 的自定义 IDOC。  

 [RELNO] = 发行版号;例如，620。  

## <a name="operations-to-receive-idocs"></a>用于接收 Idoc 的操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开应用程序用于从 SAP 系统接收 Idoc 的接收和 ReceiveIdoc 操作。 对于接收操作，IDOC 表示为强类型化数据;ReceiveIdoc 操作 IDOC 表示为字符串数据。  

 这些操作确定如何将适配器添加到你的应用程序发出的 IDOC 数据。 适配器始终会从 SAP 系统的 Idoc 的 IDOC_INBOUND_ASYNCHRONOUS 或 IDOC_INBOUND_PROCESS tRFC 作为接收。 您可以使用 Receive 或 ReceiveIdoc 操作，也可以采用 RFC 格式接收 IDOC 数据。 您设置**ReceiveIdocFormat**绑定属性来指定在其中适配器发出到你的应用程序的 IDOC 数据的格式。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  

### <a name="message-structures-for-idoc-receive-operations"></a>IDOC 的消息结构接收操作  
 下表显示了接收和 ReceiveIdoc 操作的消息结构。  

|运算|XML 结构|Description|  
|---------------|-------------------|-----------------|  
|Receive|`<Receive xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                 [CIMTYP]/[RELNO]/Receive">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData> </Receive>`|从 SAP 接收强类型化的 IDOC<br /><br /> -IDOC 架构是强类型化。<br /><br /> -公开控制记录字段。<br /><br /> -公开包括段标头和段字段的数据记录字段。|  
|接收响应|`<ReceiveResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/         [CIMTYP]/[RELNO]/Receive"> </ReceiveResponse>`|指示已从 SAP 系统接收了 IDOC。|  
|ReceiveIdoc|`<ReceiveIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData> </ReceiveIdoc>`|从 SAP 接收弱类型的 IDOC。<br /><br /> -IDOC 架构是弱类型。<br /><br /> -公开为控制记录和数据记录组成的单个字符串字段的 IDOC。|  
|ReceiveIdoc 响应|`<ReceiveIdocResponse xmlns="[MSG_VERSION]/Idoc"> </ReceiveIdocResponse>`|指示已从 SAP 系统接收了 IDOC。|  

 [MSG_VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.Sap/2007/03。  

 [VERSION] = （2 或 3） 的 IDOC 版本。  

 [IDOCTYP] = IDOC 类型;例如，ORDERS05。  

 [CIMTYP] = Cimtype 的自定义 IDOC。  

 [RELNO] = 发行版号;例如，620。  

 [EDI_DC40/EDI_DC] = EDI_DC40 版发布的版本 3 Idoc 和 EDI_DC 为版本 2 Idoc。  

 [EDIDC_FIELD] = 构成 EDI_DC40/EDI_DC 控制记录结构的字段。  

 [SEGMENT_DEFN] = 段定义名称 （不段类型名称）;例如，E2EDK01005。 段定义节点也可以基于该结构的 IDOC 的段组节点下显示。  

 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = 每个段具有包含一组标准的跟段数据的标头字段的段标头。 段数据包含的所有段字段和数据。 此节点表示的段标头字段;例如，DATAHEADERCOLUMN_SEGNAM。  

 [SEG_FIELD] = 构成特定段定义 [SEGMENT_DEFN] 段字段名称。  

#### <a name="receiving-an-idoc-in-rfc-format"></a>RFC 格式接收 IDOC  
 此外可以在 RFC 格式接收 Idoc。 用于从 SAP 接收 Idoc 的 Rfc 是：  

- 版本 3 idoc IDOC_INBOUND_ASYNCHRONOUS。  

- 版本 2 idoc INBOUND_IDOC_PROCESS。  

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
      <[SEG_HEADER_FIELD1]>value1</[SEG_HEADER_FIELD1]>  
      <[SEG_HEADER_FIELD2]>value2</[SEG_HEADER_FIELD2]>  
      …  
      <SDATA>segment value</SDATA>  
    </EDI_DD40>  
    …  
  </IDOC_DATA_REC_40>  
</IDOC_INBOUND_ASYNCHRONOUS>  
```  

 [EDIDC_FIELD] = 字段构成 EDI_DC40/EDI_DC 控制记录结构  

 [SEG_HEADER_FIELD] = 每个段具有包含一组标准的跟段数据的标头字段的段标头。 段数据包含的所有段字段和数据。 此节点表示的段标头字段;例如，SEGNAM、 MANDT 和 DOCNUM。  

 TRFC 操作的格式的详细信息，请参阅[tRFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)。  

### <a name="message-actions-for-idoc-receive-operations"></a>IDOC 的消息操作接收操作  
 下表显示了接收和 ReceiveIdoc 操作的消息操作。  


|      运算       |                                    操作                                     |                                    示例                                     |
|----------------------|-------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
|       Receive        |     [MESSAGE_VERSION]/Idoc/[VERSION] /[IDOCTYP]/[CIMTYP]/[RELNO]/Receive      |     http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive      |
|   接收响应   | [MESSAGE_VERSION]/Idoc/[VERSION] /[IDOCTYP]/[CIMTYP]/[RELNO]/Receive/response | http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive/response |
|     ReceiveIdoc      |                      [MESSAGE_VERSION]/Idoc/ReceiveIdoc                       |           http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc            |
| ReceiveIdoc 响应 |                  [MESSAGE_VERSION]/Idoc/ReceiveIdoc/response                  |       http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc/response       |

