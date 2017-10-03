---
title: "TRFC 操作的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC operations, message structure for
- tRFC operations, message schemas for
- tRFC operations, message actions for
ms.assetid: 0e269555-f0a1-40ae-a1b5-d8c4981e730f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb64ba0d14fe2b3f2d551ab851537cd16d1b7940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-trfc-operations"></a>Trfc 操作的消息架构
Transactiostructnal 远程函数调用 (tRFCs) 用于执行的工作 (LUW) 逻辑单元 RFC 调用。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持多个 tRFCs 每 LUW 的入站的 tRFC 调用。 对于出站 （客户端） tRFC 调用，该适配器可以支持仅单个 tRFC 中 LUW;它因此对于创建 LUW 在 SAP 上为每个客户端 tRFC 调用。 有关详细信息，如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 tRFC 操作，请参阅[对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。 本部分介绍的消息架构和 tRFC 操作的操作。  
  
## <a name="message-structure-for-trfc-operations"></a>Trfc 操作的消息结构  
 每个 tRFC 操作由请求消息和答复 （响应） 消息组成。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将 GUID 与 SAP 系统事务 ID (TID) 标识 SAP 系统上的 LUW 相关联。 此 GUID 可出现在这两个 tRFC 请求和响应消息中\<TransactionalRfcOperationIdentifier > 元素。  
  
-   对于出站 tRFC 调用，你可以将一个 GUID 传递到 tRFC 请求消息中的适配器。 如果未提供一个 GUID，适配器将生成一个用于你。 适配器始终 tRFC 响应消息中返回的 GUID。 要确认 TID SAP 系统上的 RfcConfirmTransID 操作中传递此 GUID。  
  
-   对于入站的 tRFC 调用，该适配器将传递它生成并映射到 SAP TID tRFC 请求消息中的 GUID。 （可选） 可以在响应消息中返回此 GUID。  
  
> [!IMPORTANT]
>  在某些情况下，例如，若要解决的问题在 SAP 系统上，你可能需要标识 SAP 系统上的 tRFC 的 SAP TID 的实际值。 你可以获取的 SAP TID 通过调用与 GUID 的值**ConvertGuidToTid**方法。 有关详细信息**ConvertGuidToTid**，请参阅[特殊操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)。  
  
 下表显示使用 tRFC 操作和克 RfcConfirmTransID 操作的消息架构。 这样就能确认客户端 tRFC 调用中的 SAP TID，将适配器显示 RfcConfirmTransID 操作。  
  
|运算|XML 结构|Description|  
|---------------|-------------------|-----------------|  
|tRFC<br /><br /> ([RFC_NAME])|`<[RFC_NAME] xmlns="[VERSION]/Trfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Trfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   …   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]>`|调用 tRFC SAP 系统上。<br /><br /> -导入，更改，并支持表参数。<br /><br /> -导入和更改参数可以是 SAP 结构类型、 SAP 表类型或 SAP 简单数据类型。<br /><br /> -tRFC 客户端调用没有输出端中返回的值。 SAP 以异步方式执行这些与仅端输入的值。<br /><br /> \<TransactionalRfcOperationIdentifier > 元素：<br /><br /> -对于出站 tRFC 调用，你可以选择指定应映射到 SAP TID 中此元素的适配器的 GUID。 如果未指定一个 GUID，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]生成一个密钥并将其映射到 tRFC SAP TID。<br /><br /> -对于入站的 tRFC 调用该适配器传递映射到此元素中的 SAP TID 的 GUID。|  
|tRFC 响应<br /><br /> （[RFC_NAME] 响应）|`<[RFC_NAME]Response xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </[RFC_NAME]Response>`|指示 RFC，已发送到 SAP 系统。<br /><br /> -tRFC 客户端调用没有输出端中返回的值。 SAP 以异步方式执行这些与仅端输入的值。<br /><br /> \<TransactionalRfcOperationIdentifier > 元素：<br /><br /> -对于出站 tRFC 调用该适配器将发送此元素中 tRFC SAP TID 与关联的 GUID。<br /><br /> -对于入站的 tRFC 调用可以选择性地返回请求消息中的适配器发送的 GUID。|  
|RfcConfirmTransID<br /><br /> (RfcConfirmTransID)|`<RfcConfirmTransID xmlns="[VERSION]/Trfc/">   <TransactionalRfcOperationIdentifier>GUID   </TransactionalRfcOperationIdentifier> </RfcConfirmTransID>`|RfcConfirmTransID 操作确认 TID SAP 系统上的出站 tRFC 操作中使用。<br /><br /> \<TransactionalRfcOperationIdentifier > 元素包含映射到 TID 与出站 tRFC 调用关联的 GUID。 你应设置为适配器 tRFC 响应消息中返回的 GUID 的值。<br /><br /> 有关 RfcConfirmTransID 操作的详细信息，请参阅[特殊操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)。|  
|RfcConfirmTransIDResponse<br /><br /> (RfcConfirmTransIDResponse)|`<RfcConfirmTransIDResponse xmlns="[VERSION]/Trfc/"> </RfcConfirmTransIDResponse>`|指示[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]已经确认 TID SAP 系统上的。|  
  
 [VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.Sap/2007/03。  
  
 [RFC_NAME] = RFC; 的名称例如，RFC_CUSTOMER_GET。  
  
 [IN_PARAM_NAME] = RFC 导入参数的名称。  
  
 [INOUT_PARAM_NAME] = RFC 更改参数的名称。  
  
 [TABLE_PARAM_NAME] = RFC 表参数的名称。  
  
 [STRUCT_PARAM_NAME] = RFC 结构参数的名称。  
  
 GUID = 标识 SAP TID tRFC 与关联的 GUID。  
  
## <a name="message-actions-for-trfc-operations"></a>Trfc 操作的消息操作  
 下表显示用于 tRFC 操作的消息操作。  
  
|运算|消息操作|示例|  
|---------------|--------------------|-------------|  
|[RFC_NAME]|[VERSION] /Trfc/ [RFC_NAME]|http://Microsoft.LobServices.Sap/2007/03/Trfc/RFC_CUSTOMER_GET|  
|[RFC_NAME]响应|[VERSION] /Trfc/ [RFC_NAME] / 响应|http://Microsoft.LobServices.Sap/2007/03/Trfc/RFC_CUSTOMER_GET/response|  
|RfcConfirmTransID|[VERSION] / Trfc/RfcConfirmTransID|http://Microsoft.LobServices.Sap/2007/03/Trfc/RfcConfirmTransID|  
|RfcConfirmTransID 响应|[版本/Trfc/RfcConfirmTransID/响应|http://Microsoft.LobServices.Sap/2007/03/Trfc/RfcConfirmTransID/response|  
  
 [VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.Sap/2007/03。  
  
 [RFC_NAME] = RFC 要调用; 的名称例如，RFC_CUSTOMER_GET。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)