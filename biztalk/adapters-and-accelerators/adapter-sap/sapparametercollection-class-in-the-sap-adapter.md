---
title: SAP 适配器中的 SAPParameterCollection 类 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameterCollection, supported methods and classes
ms.assetid: fd09355b-95f4-4d49-a643-b13058e63d74
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924cb884c64f337cec0e628c804b5c5a8c6cf37b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218037"
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a>SAP 适配器中 SAPParameterCollection 类
以下部分列出的方法和属性**SAPParameterCollection**类。 该项派生自**System.Data.Common.DbParameterCollection**。  
  
## <a name="supported-properties"></a>受支持的属性  
  
|Name|Get/Set|Description|  
|----------|--------------|-----------------|  
|**Count**|获取|集合中的参数的数目。|  
|**IsFixedSize**|获取|不提供支持。 返回 false。|  
|**IsReadOnly**|获取|不提供支持。 返回 false。|  
|**IsSynchronized**|获取|不提供支持。 返回 false。|  
|**SyncRoot**|获取|返回的锁对象。|  
  
## <a name="supported-methods"></a>支持的方法  
  
|Name|Description|  
|----------|-----------------|  
|**Add(SAPParameter)**|参数不能属于多个 ParameterCollection。|  
|**Add(object)**|SAPParameter 类型应为对象。|  
|**AddRange(System.Array)**|将添加 SAPParameter 实例的数组。|  
|**Clear （)**|清除集合中的参数。|  
|**Contains(object)**|基于参数实例的检查。|  
|**Contains(string)**|检查基于参数名称。|  
|**CopyTo （SAPParameter []，int）**|到 SAPParameter 类型数组的副本参数列表。|  
|**CopyTo (System.Array，int)**|指向数组的副本参数列表。|  
|**GetEnumerator()**|集合中获取参数的枚举数。|  
|**IndexOf(object)**|基于 SAPParameter 实例的参数的索引。|  
|**IndexOf(string)**|基于 SAPParameter 名称的参数的索引。|  
|**Insert （int、 对象）**|将 SAPParameter 插入到集合。|  
|**Remove(object)**|删除 SAPParameter 到基于实例的集合。|  
|**RemoveAt(int)**|删除 SAPParameter 到给定索引处的集合。|  
|**RemoveAt(string)**|删除 SAPParameter 到基于名称的集合。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 SAP 适配器扩展 ADO.NET 接口](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)