---
title: 为 mySAP 适配器在 BizTalk 适配器包中的元数据节点 Id |Microsoft Docs
description: 元数据，搜索、 检索节点类型和 mySAP 适配器的 BizTalk 适配器包 (BAP) 中公开的 SAP 组件中使用的 Id
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46385060-f56a-4e06-9122-b75808776716
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9efcb2a3fd48f1a92d27314c73dfe684e87b37aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373202"
---
# <a name="node-types-and-ids-for-the-sap-adapter"></a>节点类型和 SAP 适配器的 Id

## <a name="metadata-node-types-and-ids"></a>元数据节点类型和 Id
下表列出的节点类型和 SAP 项目的节点 ID 的[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]图面。 节点 ID 是在中使用的节点的绝对路径**IMetadataRetrievalContractBrowse**，**搜索**，并**GetMetadata**方法。  
  
|项目显示名称|节点类型|节点 ID|  
|---------------------------|---------------|-------------|  
|RFC|类别|[VERSION]/RFCSECTION|  
|[RFC_APPL_GROUP_NAME]|类别|[VERSION]/RFCGROUP/[RFC_APPL_GROUP_ID]|  
|[RFC_NAME]|OPERATION|[VERSION]/Rfc/[RFC_NAME]|  
|RfcGetAttributes|OPERATION|[VERSION]/RfcApi/RfcGetAttributes|  
|TRFC|类别|[VERSION]/TRFCSECTION|  
|[TRFC_APPL_GROUP_NAME]|类别|[VERSION]/TRFCGROUP/[TRFC_APPL_GROUP_ID]|  
|[TRFC_NAME]|OPERATION|[VERSION]/TRfc/[TRFC_NAME]|  
|RfcConfirmTransID|OPERATION|[VERSION]/RfcApi/RfcConfirmTransID|  
|BAPI|类别|[VERSION]/BAPISECTION/000001|  
|[BAPI_APPL_GROUP_NAME]|类别|[VERSION]/BAPISECTION/[ BAPI_APPL_GROUP_NODE_ID]|  
|[BUSINESS_OBJECT_NAME]|类别|[VERSION] /BAPIOBJ/ [BUSOBJ_TYPE]|  
|[BUSINESS_OBJECT_METHOD]|OPERATION|[VERSION]/BAPIOBJ/[BUSOBJ_TYPE]/[BUSOBJ_METHOD]/[FUNCTION_MODULE]|  
|IDOC|类别|[VERSION]/IDOCSECTION|  
|[IDOC_MSG_TYPE_NAME]|类别|[VERSION]/IDOCMESTYP/[IDOC_MSG_TYPE_NAME]|  
|([IDOC_TYPE_NAME]) ([IDOC_CIMTYPE])|类别|[VERSION]/IDOCCIMTYP/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[FIRST_IDOC_REL_NO]|  
|([IDOC_TYPE_NAME].V[IDOC_VERSION]) ([IDOC_CIMTYPE]) ([IDOC_REL_NO])|类别|[VERSION]/IDOCCIMVER/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]|  
|Send|OPERATION|[VERSION]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/Send|  
|SendIdoc|OPERATION|[VERSION]/Idoc/SendIdoc|  
|Receive|OPERATION|[VERSION]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/Receive|  
|ReceiveIdoc|OPERATION|[VERSION]/Idoc/ReceiveIdoc|  
  
 [VERSION] =; 在版本字符串例如， http://Microsoft.LobServices.Sap/2007/03。  
  
 [RFC_APPL_GROUP_NAME] = 应用程序组; 的名称例如，销售。  
  
 [RFC_APPL_GROUP_ ID] = 与 SAP; 中的应用程序组关联的 ID例如，V （针对销售）。  
  
 [RFC_NAME] = RFC; 的名称例如，RFC_GET_SYSTEM_INFO。  
  
 [TRFC_APPL_GROUP_NAME] = 应用程序组; 的名称例如，销售。 这是 Rfc 的应用程序组相同的。  
  
 [TRFC_APPL_GROUP_ ID] = 与 SAP; 中的应用程序组关联的 ID例如，V （针对销售）。 这是与 Rfc 的 ID 相同。  
  
 [TRFC_NAME] = tRFC; 的名称例如，RFC_GET_SYSTEM_INFO。 这是与 RFC 名称相同。  
  
 [BAPI_APPL_GROUP_NAME] = 如下所示的 BAPI 资源管理器在 SAP 中的 BAPI 组的名称。 例如，销售和分发。  
  
 [BAPI_APPL_GROUP_NODE_ID] = SAP; 中的 BAPI 资源管理器树中的相应节点与相关联的 ID例如，3253 销售和分发。 请注意，则可能会在给定的 BAPI 组节点的更多组节点。 例如，销售和分发节点具有名为 Sales （节点 ID 3375） 下的另一个组节点。  
  
 [BUSINESS_OBJECT_NAME] = 业务对象; 的名称例如，销售订单。  
  
 [BUSOBJ_TYPE] = SAP; 中的业务对象类型例如 BUS2032 销售订单的业务对象。  
  
 [BUSINESS_OBJECT_METHOD] = 业务对象方法; 的名称例如，GETLIST 销售订单的业务对象。  
  
 [函数模块] = SAP 函数模块的业务对象方法;例如，BAPI_SALESORDER_GETLIST GETLIST 方法的销售订单业务对象。  
  
 [IDOC_MSG_TYPE_NAME] = IDOC 消息类型; 的名称例如，订单。  
  
 [IDOC_TYPE_NAME] = IDOC 类型; 的名称例如，ORDERS05。  
  
 [IDOC_CIMTYPE] = IDOC CIM 类型 （扩展名）;例如，Z1ORDERS。  
  
 [FIRST_IDOC_REL_NO] = 特定 IDOC 类型; 最小的 IDOC 发行版号例如，对于 ORDERS05 46A 中特定 SAP 系统。  
  
 [IDOC_VERSION] = IDOC 发行版本号;2 表示发布 2 个 IDOC 和 3 的发布 3 个 IDOC...  
  
 [IDOC_REL_NO] = IDOC 发行版号;例如 46A、 46B 或 620。  
  
## <a name="metadata-search-node-ids"></a>元数据搜索节点 Id  
 元数据搜索是一项强大功能[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]图面作为的一部分其**IMetadataRetrievalContract**接口。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用此功能来支持搜索以下 SAP 项目。  
  
|项目显示名称|节点 ID|Description|  
|---------------------------|-------------|-----------------|  
|/RFC|[VERSION]/RFCSECTION|返回与搜索表达式匹配的所有 RFC 操作。|  
|/RFC/[RFC_APPL_GROUP_NAME]|[VERSION]/RFCGROUP/[RFC_APPL_GROUP_NAME]|返回与搜索表达式匹配的应用程序组中的 RFC 操作。|  
|/TRFC|[VERSION]/TRFCSECTION|返回与搜索表达式匹配的所有 RFC 操作。|  
|/TRFC/[TRFC_APPL_GROUP_NAME]|[VERSION]/TRFCGROUP/[TRFC_APPL_GROUP_NAME]|返回与搜索表达式匹配的应用程序组中的 RFC 操作。|  
|/BAPI|[VERSION] / BAPISECTION|返回与搜索表达式匹配的所有 Bapi。|  
|/IDOC|[VERSION]/IDOCSECTION|返回与搜索表达式匹配的所有 Idoc。|  
  
 下表列出了通配符[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持搜索表达式中。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|加号 （+）|匹配一个字符。<br /><br /> 例如，A + 匹配 AB、 交流、 AD 中，依次类推。|  
|星号 （*）|匹配零个或多个字符;例如，"A *"匹配"A"、"AB"，"ABC"等。|  
  
## <a name="metadata-retrieval-node-ids"></a>元数据检索节点 Id  
 下表总结了返回的元数据特征[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
|项目|元数据特征|  
|--------------|------------------------------|  
|RFC|的 RFC 名称。<br />-RFC 导入、 导出、 更改和表参数。<br />RFC 参数数据类型。<br />的映射到 facet maxLength RFC 参数字段长度<br />RFC 必需参数映射到 facet minOccurs = 1<br />RFC 可选参数映射到 facet minOccurs = 0<br />RFC 参数为 NULL 约束映射到 facet isNillable = true。 这意味着适配器到 SAP 系统应不传递此参数。<br />-在 RFC 本身是该操作。|  
|TRFC|除 RFC 相同<br /><br /> 的不显示 RFC 导入参数。 因为 tRFC 是异步的会不显示任何输出参数。|  
|BAPI|-业务对象的名称<br />-业务对象方法的名称<br />-与相同 RFC 特征|  
|IDOC|IDOC 类型<br /><br /> CIMType<br /><br /> IDOC 发行版号<br /><br /> IDOC 版本<br /><br /> IDOC 控制记录字段映射到 EDI_DC 复杂类型<br /><br /> IDOC 数据记录段和段字段映射到 EDI_DD 复杂类型<br /><br /> 段父-子关系<br /><br /> IDOC 段必需的参数映射到 minOccurs = 1<br /><br /> IDOC 段映射到 minOccurs 的可选参数 = 0<br /><br /> IDOC 段标头字段名称<br /><br /> IDOC 段标头字段数据类型<br /><br /> IDOC 段字段名称<br /><br /> IDOC 段字段数据类型<br /><br /> IDOC 段字段值枚举<br /><br /> IDOC 段字段最小值、 最大值 （范围）**注意：** 当一个 IDOC 段字段包含最小值的列表时，则将它显示为枚举。 如果 IDOC 段字段包含最小值和最大值，则将它显示为一个不带任何枚举或范围构造字符串。|  
  
 有关格式的元数据的详细信息，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开的特定项目上和操作 SAP 系统，请参阅[消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。  
  
