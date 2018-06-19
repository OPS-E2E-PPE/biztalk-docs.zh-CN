---
title: 基本类型 1> |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, data types
- JD Edwards OneWorld adapters, business functions
- .NET Framework, mapping [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], data types
- adapters [JD Edwards OneWorld adapters], .NET Framework
- JD Edwards OneWorld adapters, .NET Framework
- adapters [JD Edwards OneWorld adapters], business functions
ms.assetid: d306ea1b-fb74-4fa3-9681-405252928df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90cda6259567adf5236d0c28e576900d8b25271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231853"
---
# <a name="basic-types"></a>基本类型
用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供仅到 JD Edwards OneWorld 业务函数的访问。 业务功能元数据使用业务功能接口读取，用于查找业务功能列表和相关联的数据结构。 对于所有业务功能方法，元数据都是强类型数据。  
  
 所有业务函数方法都有相同的调用约定： 是针对派生，整个系统的三个参数和指向的数据结构的指针。 下表显示了业务函数数据类型是如何表示的。  
  
 **业务函数数据类型**  
  
|JD Edwards OneWorld 数据类型|Description|WDSL 转换|  
|-----------------------------------|-----------------|---------------------|  
|char|字符的字符串。|xsd:string of 1|  
|int|短整数。|xsd:short|  
|long|长整型。|xsd:short|  
|字符串|请参阅[处理字符串值](../core/handling-string-values1.md)。|xsd:string|  
|JDEDATE|日期的特殊实现。|xsd:date|  
|MATH_NUMERIC|浮动点数的特殊实现，包括货币值。|32 个 xsd: string|  
|Byte|单个无符号字符。|xsd:string of 1|  
  
 下表包含 JD Edwards OneWorld 中的基本类型列表及其映射到 Microsoft .NET Framework 的方式。  
  
 **基本类型和它们如何映射到 Microsoft.NET Framework**  
  
|JD Edwards OneWorld XE|.NET Framework|  
|----------------------------|--------------------|  
|char|字符串|  
|int|Short|  
|long|Short|  
|字符串|字符串|  
|JDEDATE|System.DateTime|  
|MATH_NUMERIC|字符串|  
|Byte|字符串|  
  
> [!NOTE]
>  如果只有一个参数，且返回参数为 void，则占位符将替换为类，输出部分将成为返回值。 例如：  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 下面是一个方法签名示例：  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a>有限字符串  
 在 JD Edwards OneWorld 中，一些字符串是有字符限制的。 任何多余的字符将导致出错。 若要查看字符串中的字符限制，您可以使用 Microsoft 适配器向导。  
  
## <a name="see-also"></a>另请参阅  
 [使用 MATH_NUMERIC 类型](../core/using-the-math-numeric-type2.md)   
 [处理字符串值](../core/handling-string-values1.md)   
 [附录 a： 数据类型](../core/appendix-a-data-types.md)