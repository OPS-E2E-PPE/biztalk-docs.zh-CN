---
title: "RFC 操作的消息架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RFC operations, message structure for
- RFC operations, message actions for
ms.assetid: 50cd9b28-2e66-4c76-9d19-f0da6e7b8e10
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef9d1dfe3ff3cef27269facfe89d3aea8f43cb10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-rfc-operations"></a>RFC 操作的消息架构
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为操作呈现 SAP 远程函数调用 (RFC)。 本主题包含有关消息架构和用于 RFC 操作的消息操作的信息。 消息结构是相同的入站和出站 RFC 操作。 适配器支持的 RFC 操作的概述，请参阅[操作中 SAP Rfc](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。  
  
 你也可以作为在适配器上的 RFC 操作调用 BAPIs。 此类调用的消息结构的示例包括在本主题中。  
  
## <a name="message-structure-for-rfc-operations"></a>RFC 操作的消息结构  
 下表显示 RFC 消息架构。 每个 RFC 操作由请求消息和答复 （响应） 消息组成。  
  
|消息|XML 消息结构|Description|  
|-------------|---------------------------|-----------------|  
|RFC<br /><br /> ([RFC_NAME])|`<[RFC_NAME] xmlns="[VERSION]/Rfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]>`|调用 RFC SAP 系统上。<br /><br /> -导入，更改，并支持表参数。<br /><br /> -导入和更改参数可以是 SAP 结构类型、 SAP 表类型或 SAP 简单数据类型。|  
|RFC 响应 （[RFC_NAME] 响应）|`<[RFC_NAME]Response xmlns="[VERSION]/Rfc/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME>     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]Response>`|RFC 返回。<br /><br /> -导出、 更改，并支持表参数。<br /><br /> **注意：**默认情况下，表参数不显示在响应消息中。 如果你需要在响应消息中的表参数，你必须在请求消息中传递空表参数。<br /><br /> -导入和更改参数可以是 SAP 结构类型、 SAP 表类型或 SAP 简单数据类型。|  
|RfcGetAttributes<br /><br /> (RfcGetAttributes)|`<RfcGetAttributes> </RfcGetAttributes>`|RfcGetAttributes 是通过显示的 RFC SDK API 操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 RfcGetAttributes 操作允许客户端程序来检索语言、 系统 ID，以及与 RFC 连接关联的合作伙伴代码页。|  
|RfcGetAttributes 响应<br /><br /> (RfcGetAttributesResponse)|`<RfcGetAttributesResponse>   <Language>lang</Language>   <SysId>id</SysId>   <PartnerCodePage>pnrcp</PartnerCodePage> </RfcGetAttributesResponse>`|RfcGetAttributes 操作的响应返回语言、 系统 ID，以及与 RFC 连接关联的合作伙伴代码页。|  
  
 [VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.SAP/2007/03。  
  
 [RFC_NAME] = RFC; 的名称例如，RFC_CUSTOMER_GET。  
  
 [IN_PARAM_NAME] = RFC 导入参数的名称。  
  
 [OUT_PARAM_NAME] = RFC 导出的参数的名称。  
  
 [INOUT_PARAM_NAME] = RFC 更改参数的名称。  
  
 [TABLE_PARAM_NAME] = RFC 表参数的名称。  
  
 [STRUCT_PARAM_NAME] = RFC 结构参数的名称。  
  
## <a name="message-actions-for-rfc-operations"></a>RFC 操作的消息操作  
 下表显示 RFC 操作的消息操作。  
  
|运算|消息操作|示例|  
|---------------|--------------------|-------------|  
|[RFC_NAME]|[VERSION] /Rfc/ [RFC_NAME]|http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET|  
|[RFC_NAME]响应|[VERSION] /Rfc/ [RFC_NAME] / 响应|http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET/response|  
|RfcGetAttributes|[VERSION] / RfcGetAttributes|http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes|  
|RfcGetAttributes 响应|版本 [/ RfcGetAttributes/响应|http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes/response|  
  
 [VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.Sap/2007/03。  
  
 [RFC_NAME] = RFC 要调用; 的名称例如，RFC_CUSTOMER_GET。  
  
## <a name="invoking-a-bapi-as-an-rfc-operation"></a>RFC 操作的形式调用 BAPI  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现 BAPIs RFC 操作，而且作为业务对象的方法。 作为 RFC 操作 BAPIs 会显示名称。 有关通过使用业务对象接口调用 BAPIs 的详细信息，请参阅[对 BAPIs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。  
  
 下面的 XML 显示的调用，将作为 RFC BAPI (BAPI_CUSTOMER_GETDETAIL2) 消息结构。 此操作的消息操作是： http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_CUSTOMER_GETDETAIL2。  
  
```  
<BAPI_CUSTOMER_GETDETAIL2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <COMPANYCODE>1001</COMPANYCODE>  
  <CUSTOMERNO>0000001001</CUSTOMERNO>  
  <CUSTOMERBANKDETAIL>  
    <BAPICUSTOMER_02 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <CUSTOMER />  
      <BANK_CTRY />  
      <BANK_KEY />  
      <BANK_ACCT />  
      <CTRL_KEY />  
      <PARTNER_BK />  
      <COLL_AUTH />  
      <BANK_REF />  
    </BAPICUSTOMER_02>  
  </CUSTOMERBANKDETAIL>  
</BAPI_CUSTOMER_GETDETAIL2>  
```  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)