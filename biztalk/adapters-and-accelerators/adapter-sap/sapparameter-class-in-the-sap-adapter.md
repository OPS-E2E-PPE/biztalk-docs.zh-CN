---
title: SAP 适配器 SAPParameter 类 |Microsoft Docs
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
ms.openlocfilehash: 67f87932d7add9723d67e0af822a8d6f389b59fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372945"
---
# <a name="sapparameter-class-in-the-sap-adapter"></a>SAP 适配器 SAPParameter 类
以下部分列出的方法和属性**SAPParameter**类。 这派生自**System.Data.Common.DbParameter**。  
  
## <a name="supported-properties"></a>支持的属性  
  
|“属性”|获取/设置|Description|  
|----------|--------------|-----------------|  
|**DbType**|获取|如果返回参数的 DbType。 无法设置。|  
|**方向**|获取和设置|ParameterDirection.ReturnValue 不受支持。|  
|**IsNullable**|-|不提供支持。|  
|**ParameterName**|获取和设置|参数的名称。|  
|**大小**|-|不提供支持。|  
|**SourceColumn**|-|不提供支持。|  
|**SourceColumnNullMapping**|-|不提供支持。|  
|**SourceVersion**|-|不提供支持。|  
|**ReplTest1**|获取和设置|参数的值|  
  
## <a name="supported-methods"></a>受支持的方法  
  
|“属性”|Description|  
|----------|-----------------|  
|**ResetDbType()**|不提供支持。|  
  
## <a name="supported-constructors"></a>受支持的构造函数  
  
|“属性”|Description|  
|----------|-----------------|  
|**SAPParameter()**|参数的 SAP 实例。|  
|**SAPParameter(string)**|SAP 与 SAP 的参数名的参数。|  
|**SAPParameter(string, DbType)**|使用 SAP 参数名称和 DbType SAP 参数。|  
|**SAPParameter(string, object)**|SAP 使用 SAP 参数名称和值的参数。 复杂类型具有 DataTable 类型的值和 XML 字符串。|  
|**SAPParameter(string, ParameterDirection)**|SAP 具有 SAP 参数名称和参数方向的参数。|  
  
## <a name="see-also"></a>请参阅  
 [扩展 ADO.NET 接口，与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)