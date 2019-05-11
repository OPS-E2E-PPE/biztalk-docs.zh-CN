---
title: SAP 适配器 SAPDataReader 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f05550dea2c42d8227e0c135759eea24238c0e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372959"
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a>SAP 适配器 SAPDataReader 类
以下部分列出的方法和属性**SAPDataReader**类。 这派生自**System.Data.Common.DbDataReader**。  
  
## <a name="supported-properties"></a>支持的属性  
  
|“属性”|获取/设置|Description|  
|----------|--------------|-----------------|  
|**深度**|获取|不提供支持。 返回 0。|  
|**FieldCount**|获取|中的当前记录集的字段数|  
|**IsClosed**|获取|返回数据读取器的状态|  
|**RecordsAffected**|获取|不提供支持。 返回-1|  
  
## <a name="supported-methods"></a>受支持的方法  
  
|“属性”|Description|  
|----------|-----------------|  
|**Close()**|关闭 DataReader|  
|**获取 [方法]** <sup>*</sup><br /><br /> 其中 [方法] 是预期的数据类型。 例如 GetInt32(int)|获取列的值根据预期的数据类型|  
|**IsDBNull(int)**|不提供支持。 返回 false。|  
  
## <a name="see-also"></a>请参阅  
 [扩展 ADO.NET 接口，与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)