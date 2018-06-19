---
title: SAP 适配器中的 SAPDataReader 类 |Microsoft 文档
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
ms.openlocfilehash: 70fe658058b6d00b4a22b333ef5683a285b9cab3
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22217309"
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a>SAP 适配器中 SAPDataReader 类
以下部分列出的方法和属性**SAPDataReader**类。 该项派生自**System.Data.Common.DbDataReader**。  
  
## <a name="supported-properties"></a>受支持的属性  
  
|名称|Get/Set|Description|  
|----------|--------------|-----------------|  
|**深度**|获取|不提供支持。 返回 0。|  
|**FieldCount**|获取|中的当前记录集的字段数|  
|**关闭**|获取|返回数据读取器的状态|  
|**RecordsAffected**|获取|不提供支持。 将返回-1|  
  
## <a name="supported-methods"></a>支持的方法  
  
|名称|Description|  
|----------|-----------------|  
|**Close()**|关闭 DataReader|  
|**获取 [方法]** <sup>*</sup><br /><br /> 其中 [方法] 是预期的数据类型。 例如 GetInt32(int)|获取列的值基于期望的数据类型|  
|**IsDBNull(int)**|不提供支持。 返回 false。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 SAP 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)