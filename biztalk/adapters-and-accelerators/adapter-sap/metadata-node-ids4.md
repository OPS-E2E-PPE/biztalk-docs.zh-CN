---
title: 为 mySAP 适配器 BizTalk 适配器包中的元数据节点 Id |Microsoft 文档
description: 元数据，搜索、 检索节点类型和 mySAP 适配器-BizTalk 适配器包 (BAP) 中公开的 SAP 组件中使用的 Id
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46385060-f56a-4e06-9122-b75808776716
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 138e46b198df48348dcef35662589f6a3c2e317a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="node-types-and-ids-for-the-sap-adapter"></a>节点类型和 SAP 适配器 Id

## <a name="metadata-node-types-and-ids"></a>元数据节点类型和 Id
下表列出的节点类型和 SAP 项目的节点 ID，[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]图面。 节点 ID 是在中使用的节点的绝对路径**IMetadataRetrievalContractBrowse**，**搜索**，和**GetMetadata**方法。  
  
|项目显示名称|节点类型|节点 ID|  
|---------------------------|---------------|-------------|  
|RFC|类别|[VERSION] / RFCSECTION|  
|[RFC_APPL_GROUP_NAME]|类别|[VERSION]/RFCGROUP/[RFC_APPL_GROUP_ID]|  
|[RFC_NAME]|OPERATION|[VERSION]/Rfc/[RFC_NAME]|  
|RfcGetAttributes|OPERATION|[VERSION]/RfcApi/RfcGetAttributes|  
|TRFC|类别|[VERSION]/TRFCSECTION|  
|[TRFC_APPL_GROUP_NAME]|类别|[VERSION]/TRFCGROUP/[TRFC_APPL_GROUP_ID]|  
|[TRFC_NAME]|OPERATION|[VERSION]/TRfc/[TRFC_NAME]|  
|RfcConfirmTransID|OPERATION|[VERSION]/RfcApi/RfcConfirmTransID|  
|BAPI|类别|[VERSION]/BAPISECTION/000001|  
|[BAPI_APPL_GROUP_NAME]|类别|[VERSION]/BAPISECTION/[ BAPI_APPL_GROUP_NODE_ID]|  
|[BUSINESS_OBJECT_NAME]|类别|[VERSION]/BAPIOBJ/[BUSOBJ_TYPE]|  
|[BUSINESS_OBJECT_METHOD]|OPERATION|[VERSION]/BAPIOBJ/[BUSOBJ_TYPE]/[BUSOBJ_METHOD]/[FUNCTION_MODULE]|  
|IDOC|类别|[VERSION] / IDOCSECTION|  
|[IDOC_MSG_TYPE_NAME]|类别|[VERSION]/IDOCMESTYP/[IDOC_MSG_TYPE_NAME]|  
|([IDOC_TYPE_NAME]) ([IDOC_CIMTYPE])|类别|[VERSION]/IDOCCIMTYP/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[FIRST_IDOC_REL_NO]|  
|([IDOC_TYPE_NAME]。V[IDOC_VERSION]) ([IDOC_CIMTYPE]) ([IDOC_REL_NO])|类别|[VERSION]/IDOCCIMVER/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]|  
|Send|OPERATION|[VERSION]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/Send|  
|SendIdoc|OPERATION|[VERSION]/Idoc/SendIdoc|  
|Receive|OPERATION|[VERSION]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/Receive|  
|ReceiveIdoc|OPERATION|[VERSION]/Idoc/ReceiveIdoc|  
  
 [VERSION] = 版本字符串中;例如， http://Microsoft.LobServices.Sap/2007/03。  
  
 [RFC_APPL_GROUP_NAME] = 应用程序组; 的名称例如，销售。  
  
 [RFC_APPL_GROUP_ ID] = 与 SAP; 中的应用程序组相关联的 ID例如，V （针对销售）。  
  
 [RFC_NAME] = RFC; 的名称例如，RFC_GET_SYSTEM_INFO。  
  
 [TRFC_APPL_GROUP_NAME] = 应用程序组; 的名称例如，销售。 这是相同的应用程序组的 Rfc。  
  
 [TRFC_APPL_GROUP_ ID] = 与 SAP; 中的应用程序组相关联的 ID例如，V （针对销售）。 这是与 Rfc 的 ID 相同。  
  
 [TRFC_NAME] = tRFC; 的名称例如，RFC_GET_SYSTEM_INFO。 这是与 RFC 名称相同。  
  
 [BAPI_APPL_GROUP_NAME] = 如下所示在 SAP 中的 BAPI 资源管理器 BAPI 组的名称。 例如，销售和分发。  
  
 [BAPI_APPL_GROUP_NODE_ID] = 与 SAP; 中 BAPI 资源管理器树中的相应节点关联的 ID例如，3253 为销售和分发。 请注意可能是给定 BAPI 组节点下的更多组节点。 例如，销售和分发节点都有其名为销售 （节点 ID 3375） 下的另一个组节点。  
  
 [BUSINESS_OBJECT_NAME] = 业务对象; 的名称例如，销售订单。  
  
 [BUSOBJ_TYPE] = SAP; 中的业务对象类型例如 BUS2032 对于销售订单业务对象。  
  
 [BUSINESS_OBJECT_METHOD] = 业务对象方法; 的名称例如，GETLIST 对于销售订单业务对象。  
  
 [函数模块] = SAP 函数模块的业务对象方法;例如，BAPI_SALESORDER_GETLIST GETLIST 的销售订单业务对象的方法。  
  
 [IDOC_MSG_TYPE_NAME] = IDOC 消息类型的名称;例如，订单。  
  
 [IDOC_TYPE_NAME] = IDOC 类型中; 的名称例如，ORDERS05。  
  
 [IDOC_CIMTYPE] = IDOC CIM 类型 （扩展）;例如，Z1ORDERS。  
  
 [FIRST_IDOC_REL_NO] = 对特定的 IDOC 类型; 最小的 IDOC 发行版号例如，46A ORDERS05 为特定的 SAP 系统中。  
  
 [IDOC_VERSION] = IDOC 发行版本号;2 发行 2 IDOC 和 3 发行 3 IDOC...  
  
 [IDOC_REL_NO] = IDOC 发行版号;例如 46A、 46B 或 620。  
  
## <a name="metadata-search-node-ids"></a>元数据搜索的节点 Id  
 元数据搜索是一款强大功能[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]作为的一部分的图面其**IMetadataRetrievalContract**接口。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用此功能以便支持搜索以下 SAP 项目。  
  
|项目显示名称|节点 ID|Description|  
|---------------------------|-------------|-----------------|  
|/RFC|[VERSION] / RFCSECTION|返回与搜索表达式匹配的所有 RFC 操作。|  
|/RFC/[RFC_APPL_GROUP_NAME]|[VERSION]/RFCGROUP/[RFC_APPL_GROUP_NAME]|返回与搜索表达式匹配的应用程序组中的 RFC 操作。|  
|/TRFC|[VERSION]/TRFCSECTION|返回与搜索表达式匹配的所有 RFC 操作。|  
|/TRFC/[TRFC_APPL_GROUP_NAME]|[VERSION]/TRFCGROUP/[TRFC_APPL_GROUP_NAME]|返回与搜索表达式匹配的应用程序组中的 RFC 操作。|  
|/BAPI|[VERSION] / BAPISECTION|返回与搜索表达式匹配的所有 BAPIs。|  
|/IDOC|[VERSION] / IDOCSECTION|返回与搜索表达式匹配的所有 Idoc。|  
  
 下表列出通配符[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在搜索表达式中支持。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|加号 （+）|完全匹配一个字符。<br /><br /> 例如，A + 匹配 AB、 AC、 AD 中，依次类推。|  
|星号 （*）|匹配零个或多个字符;例如，"A *"匹配"A"、"AB"，"ABC"等。|  
  
## <a name="metadata-retrieval-node-ids"></a>元数据检索的节点 Id  
 下表总结了返回的元数据特征[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
|项目|元数据特征|  
|--------------|------------------------------|  
|RFC|-   RFC name.<br />RFC 导入、 导出、 更改和表参数。<br />RFC 参数数据类型。<br />映射到方面 maxLength 的 RFC 参数字段长度<br />RFC 必选参数映射到方面 minOccurs = 1<br />RFC 可选参数映射到方面 minOccurs = 0<br />RFC 参数为空的约束映射到方面 isNillable = true。 这意味着到 SAP 系统的适配器应通过此参数。<br />-RFC 本身是该操作。|  
|TRFC|除 RFC 相同<br /><br /> RFC 导入参数将不显示中。 因为 tRFC 是异步的将不显示任何输出参数。|  
|BAPI|-业务对象的名称<br />-业务对象方法名称<br />-与相同 RFC 特征|  
|IDOC|IDOC 类型<br /><br /> CIMType<br /><br /> IDOC 发行版号<br /><br /> IDOC 版本<br /><br /> IDOC 控制记录字段映射到 EDI_DC 复杂类型<br /><br /> IDOC 数据记录段和段字段映射到 EDI_DD 复杂类型<br /><br /> 段父-子关系<br /><br /> IDOC 段必选参数映射到 minOccurs = 1<br /><br /> IDOC 段可选参数映射到 minOccurs = 0<br /><br /> IDOC 段标头字段名称<br /><br /> IDOC 段标头字段数据类型<br /><br /> IDOC 段字段名称<br /><br /> IDOC 段字段数据类型<br /><br /> IDOC 段字段值枚举<br /><br /> IDOC 段字段最小值、 最大值 （范围）**注意：**时 IDOC 段字段包含的最小值列表，呈现为枚举。 如果 IDOC 段字段包含最小值和最大值，则将它呈现为而无需任何枚举类型或范围构造的字符串。|  
  
 有关格式的元数据的详细信息，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开特定项目和操作在 SAP 系统上，请参阅[消息和消息架构用于 mySAP Business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。  
  
