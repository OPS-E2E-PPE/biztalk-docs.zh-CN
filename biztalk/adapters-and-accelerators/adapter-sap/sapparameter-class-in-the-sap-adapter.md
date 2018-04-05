---
title: SAP 适配器中的 SAPParameter 类 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ff43c344cc14adb3deef226c270adc3ca94f2a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sapparameter-class-in-the-sap-adapter"></a>SAP 适配器中 SAPParameter 类
以下部分列出的方法和属性**SAPParameter**类。 该项派生自**System.Data.Common.DbParameter**。  
  
## <a name="supported-properties"></a>受支持的属性  
  
|Name|Get/Set|Description|  
|----------|--------------|-----------------|  
|**DbType**|获取|如果返回参数的 DbType。 无法设置。|  
|**方向**|获取和设置|不支持的 ParameterDirection.ReturnValue。|  
|**IsNullable**|-|不提供支持。|  
|**参数名称**|获取和设置|参数的名称。|  
|**Size**|-|不提供支持。|  
|**SourceColumn**|-|不提供支持。|  
|**SourceColumnNullMapping**|-|不提供支持。|  
|**源版本**|-|不提供支持。|  
|**值**|获取和设置|参数值|  
  
## <a name="supported-methods"></a>支持的方法  
  
|Name|Description|  
|----------|-----------------|  
|**ResetDbType()**|不提供支持。|  
  
## <a name="supported-constructors"></a>支持的构造函数  
  
|Name|Description|  
|----------|-----------------|  
|**SAPParameter()**|SAP 参数实例。|  
|**SAPParameter(string)**|SAP 使用 SAP 参数名称的参数。|  
|**SAPParameter (string，DbType)**|SAP 参数名称和 DbType SAP 参数。|  
|**SAPParameter （字符串、 对象）**|SAP SAP 参数名称和值的参数。 复杂类型有类型 DataTable 的值和 XML 字符串。|  
|**SAPParameter (string，ParameterDirection)**|与 SAP 参数名称和参数方向的 SAP 参数。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 SAP 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)