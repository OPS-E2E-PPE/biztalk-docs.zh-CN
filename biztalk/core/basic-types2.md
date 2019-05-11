---
title: 基本 Types2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51caed0e57b6b1869fb5e921b5a660293d71840d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530497"
---
# <a name="basic-types"></a>基本类型
用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器提供仅到 JD Edwards EnterpriseOne 业务功能的访问。 业务功能元数据使用业务功能接口读取和用于查找业务功能的列表和关联数据结构。 在所有情况下，对于所有业务功能方法为强类型元数据。  
  
 所有业务功能方法都具有相同的调用约定： 系统派生的三个参数和数据结构的指针。 下表显示了业务函数数据类型的表示方式。  
  
|JD Edwards EnterpriseOne Data Type|Description|WDSL 转换|  
|----------------------------------------|-----------------|---------------------|  
|char|字符的字符串。|xsd: string 的 1|  
|ssNoversion|短整数。|xsd:short|  
|long|长整型。|xsd:short|  
|String|请参阅[处理字符串值](../core/handling-string-values2.md)。|xsd:string|  
|JDEDATE|数据的特殊实现。|xsd:date|  
|MATH_NUMERIC|浮点数字，其中包括货币值的特殊实现。|32 个 xsd: string|  
|Byte|单个无符号的字符。|xsd: string 的 1|  
|JDEUTIME|包括日期和时间组件。<br /><br /> 数据类型存储的所有日期/时间和执行以协调世界时 (UTC) 的所有日期/时间计算。|xsd:dateTime|  
  
## <a name="see-also"></a>请参阅  
 [使用 MATH_NUMERIC 类型](../core/using-the-math-numeric-type1.md)   
 [处理字符串值](../core/handling-string-values2.md)   
 [附录 b:数据类型](../core/appendix-b-data-types.md)