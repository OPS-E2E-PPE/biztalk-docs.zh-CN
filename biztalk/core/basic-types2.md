---
title: "基本 Types2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e5c47d8760e9743ec11a62598581d9d20b3e53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="basic-types"></a>基本类型
用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器仅提供了对 JD Edwards EnterpriseOne 业务功能的访问。 业务功能元数据使用业务功能接口读取，用于查找业务功能列表和相关联的数据结构。 对于所有业务功能方法，元数据都是强类型数据。  
  
 所有业务函数方法都有相同的调用约定： 是针对派生，整个系统的三个参数和指向的数据结构的指针。 下表显示了业务功能数据类型的表示方式。  
  
|JD Edwards EnterpriseOne 数据类型|Description|WDSL 转换|  
|----------------------------------------|-----------------|---------------------|  
|char|字符的字符串。|xsd:string of 1|  
|int|短整数。|xsd:short|  
|long|长整型。|xsd:short|  
|字符串|请参阅[处理字符串值](../core/handling-string-values2.md)。|xsd:string|  
|JDEDATE|日期的特殊实现。|xsd:date|  
|MATH_NUMERIC|浮动点数的特殊实现，包括货币值。|32 个 xsd: string|  
|Byte|单个无符号字符。|xsd:string of 1|  
|JDEUTIME|包括日期和时间的组件。<br /><br /> 数据类型存储的所有日期/时间并执行以协调世界时 (UTC) 的所有日期/时间计算。|xsd:dateTime|  
  
## <a name="see-also"></a>另请参阅  
 [使用 MATH_NUMERIC 类型](../core/using-the-math-numeric-type1.md)   
 [处理字符串值](../core/handling-string-values2.md)   
 [附录 b： 数据类型](../core/appendix-b-data-types.md)