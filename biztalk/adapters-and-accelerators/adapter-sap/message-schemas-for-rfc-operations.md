---
title: RFC 操作的消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFC operations, message structure for
- RFC operations, message actions for
ms.assetid: 50cd9b28-2e66-4c76-9d19-f0da6e7b8e10
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 156b8e8c218c4ad23d49959323ed324b0c7cdfd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972846"
---
# <a name="message-schemas-for-rfc-operations"></a>RFC 操作的消息架构
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为操作的图面 SAP 远程函数调用 (RFC)。 本主题包含有关消息架构和使用 RFC 操作的消息操作的信息。 消息结构是相同的入站和出站 RFC 操作。 适配器支持 RFC 操作的概述，请参阅[Rfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。  

 此外可以在适配器上的 RFC 操作作为调用 Bapi。 本主题中包含此类调用的消息结构的示例。  

## <a name="message-structure-for-rfc-operations"></a>RFC 操作的消息结构  
 下表显示了 RFC 消息架构。 每个 RFC 操作包含请求消息和答复 （响应） 消息。  


|                             消息                              |                                                                                                                                                                                                                         XML 消息结构                                                                                                                                                                                                                          |                                                                                                                                                                                                     Description                                                                                                                                                                                                      |
|------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   RFC<br /><br /> ([RFC_NAME])                   | `<[RFC_NAME] xmlns="[VERSION]/Rfc/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]>` |                                                                                              调用上的 SAP 系统的 RFC。<br /><br /> -导入，更改，并支持表参数。<br /><br /> -导入并更改参数可以为 SAP 结构类型、 SAP 表类型或 SAP 简单数据类型。                                                                                              |
|                RFC 响应 （[RFC_NAME] 响应）                 |     `<[RFC_NAME]Response xmlns="[VERSION]/Rfc/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME>     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[RFC_NAME]Response>`      | RFC 返回。<br /><br /> -导出，更改，并支持表参数。<br /><br /> **注意：** 默认情况下，表参数不显示在响应消息。 如果您需要在响应消息中的表参数，您必须在请求消息中传递空表参数。<br /><br /> -导入并更改参数可以为 SAP 结构类型、 SAP 表类型或 SAP 简单数据类型。 |
|         RfcGetAttributes<br /><br /> (RfcGetAttributes)          |                                                                                                                                                                                                                `<RfcGetAttributes> </RfcGetAttributes>`                                                                                                                                                                                                                |                                                  RfcGetAttributes 是 RFC SDK API 操作显示的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 RfcGetAttributes 操作允许一个客户端程序来检索语言、 系统 ID 和与 RFC 连接相关联的合作伙伴代码页。                                                   |
| RfcGetAttributes 响应<br /><br /> (RfcGetAttributesResponse) |                                                                                                                                                          `<RfcGetAttributesResponse>   <Language>lang</Language>   <SysId>id</SysId>   <PartnerCodePage>pnrcp</PartnerCodePage> </RfcGetAttributesResponse>`                                                                                                                                                           |                                                                                                                              RfcGetAttributes 操作的响应返回的语言、 系统 ID 和与 RFC 连接相关联的合作伙伴代码页。                                                                                                                              |

 [VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.SAP/2007/03。  

 [RFC_NAME] = RFC; 的名称例如，RFC_CUSTOMER_GET。  

 [IN_PARAM_NAME] = RFC 导入参数的名称。  

 [OUT_PARAM_NAME] = RFC 导出参数的名称。  

 [INOUT_PARAM_NAME] = RFC 更改参数的名称。  

 [TABLE_PARAM_NAME] = RFC 表参数的名称。  

 [STRUCT_PARAM_NAME] = RFC 结构参数的名称。  

## <a name="message-actions-for-rfc-operations"></a>RFC 操作的消息操作  
 下表显示了 RFC 操作的消息操作。  


|         运算         |           消息操作           |                                示例                                 |
|---------------------------|------------------------------------|------------------------------------------------------------------------|
|        [RFC_NAME]         |      [VERSION]/Rfc/[RFC_NAME]      |     http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET      |
|    [RFC_NAME]响应    | [VERSION] /Rfc/ [RFC_NAME] / 响应  | http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET/response |
|     RfcGetAttributes      |     [VERSION] / RfcGetAttributes     |       http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes        |
| RfcGetAttributes 响应 | 版本 [/ RfcGetAttributes/响应 |   http://Microsoft.LobServices.Sap/2007/03/RfcGetAttributes/response   |

 [VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.Sap/2007/03。  

 [RFC_NAME] = RFC 调用; 的名称例如，RFC_CUSTOMER_GET。  

## <a name="invoking-a-bapi-as-an-rfc-operation"></a>RFC 操作的形式调用 BAPI  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示 Bapi 作为 RFC 操作和业务对象的方法。 作为 RFC 操作按名称显示 Bapi。 有关使用业务对象接口调用 Bapi 的详细信息，请参阅[sap Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。  

 以下 XML 显示了作为 RFC 调用 BAPI (BAPI_CUSTOMER_GETDETAIL2) 的消息结构。 此操作的消息操作是： http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_CUSTOMER_GETDETAIL2。  

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

## <a name="see-also"></a>请参阅  
 [消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)