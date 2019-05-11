---
title: SAP 适配器 SAPParameterCollection 类 |Microsoft Docs
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
ms.openlocfilehash: c94dc7e8219a2439d58fbfea78fc7fe9c42b64bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372920"
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a>SAP 适配器 SAPParameterCollection 类
以下部分列出的方法和属性**SAPParameterCollection**类。 这派生自**System.Data.Common.DbParameterCollection**。  
  
## <a name="supported-properties"></a>支持的属性  
  
|“属性”|获取/设置|Description|  
|----------|--------------|-----------------|  
|**Count**|获取|集合中的参数数目。|  
|**IsFixedSize**|获取|不提供支持。 返回 false。|  
|**IsReadOnly**|获取|不提供支持。 返回 false。|  
|**IsSynchronized**|获取|不提供支持。 返回 false。|  
|**SyncRoot**|获取|返回的锁对象。|  
  
## <a name="supported-methods"></a>受支持的方法  
  
|“属性”|Description|  
|----------|-----------------|  
|**Add(SAPParameter)**|参数不能属于多个 ParameterCollection。|  
|**Add(object)**|SAPParameter 类型应为对象。|  
|**AddRange(System.Array)**|将添加 SAPParameter 实例的数组。|  
|**Clear()**|清除集合中的参数。|  
|**Contains(object)**|基于参数实例的检查。|  
|**Contains(string)**|检查基于参数名称。|  
|**CopyTo(SAPParameter[], int)**|副本到 SAPParameter 类型的数组的参数列表。|  
|**CopyTo(System.Array, int)**|复制到一个数组的参数列表。|  
|**GetEnumerator()**|获取一个枚举器的参数集合中。|  
|**IndexOf(object)**|基于 SAPParameter 实例的参数的索引。|  
|**IndexOf(string)**|基于 SAPParameter 名称的参数的索引。|  
|**Insert(int, object)**|将 SAPParameter 插入到集合。|  
|**Remove(object)**|为基于实例的集合中移除 SAPParameter。|  
|**RemoveAt(int)**|集合中给定索引处移除 SAPParameter。|  
|**RemoveAt(string)**|删除 SAPParameter 到基于名称的集合。|  
  
## <a name="see-also"></a>请参阅  
 [扩展 ADO.NET 接口，与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)