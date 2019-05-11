---
title: 基本类型 1> |Microsoft Docs
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
ms.openlocfilehash: 1c1cfd31eacd56c19e5b1daf2288be098d9448c3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529140"
---
# <a name="basic-types"></a>基本类型
用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供仅到 JD Edwards OneWorld 业务功能的访问。 业务功能元数据使用业务功能接口读取和用于查找业务功能的列表和关联数据结构。 在所有情况下，对于所有业务功能方法为强类型元数据。  
  
 所有业务功能方法都具有相同的调用约定： 系统派生的三个参数和数据结构的指针。 下表显示了业务函数数据类型的表示方式。  
  
 **业务函数数据类型**  
  
|JD Edwards OneWorld Data Type|Description|WDSL 转换|  
|-----------------------------------|-----------------|---------------------|  
|char|字符的字符串。|xsd: string 的 1|  
|ssNoversion|短整数。|xsd:short|  
|long|长整型。|xsd:short|  
|String|请参阅[处理字符串值](../core/handling-string-values1.md)。|xsd:string|  
|JDEDATE|数据的特殊实现。|xsd:date|  
|MATH_NUMERIC|浮点数字，其中包括货币值的特殊实现。|32 个 xsd: string|  
|Byte|单个无符号的字符。|xsd: string 的 1|  
  
 下表包含 JD Edwards OneWorld 以及它们如何映射到 Microsoft.NET Framework 中的基本类型的列表。  
  
 **基本类型以及它们如何映射到 Microsoft.NET Framework**  
  
|JD Edwards OneWorld XE|.NET Framework|  
|----------------------------|--------------------|  
|char|String|  
|ssNoversion|Short|  
|long|Short|  
|String|String|  
|JDEDATE|System.DateTime|  
|MATH_NUMERIC|String|  
|Byte|String|  
  
> [!NOTE]
>  如果只有一个参数，且返回参数为 void，占位符将替换为类，并输出部分将成为返回值。 例如：  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 以下是方法签名的示例：  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a>有限字符串  
 在 JD Edwards OneWorld 中一些字符串是有字符限制。 任何多余的字符将导致错误。 若要查看字符串中的字符的限制，可以使用 Microsoft 适配器向导。  
  
## <a name="see-also"></a>请参阅  
 [使用 MATH_NUMERIC 类型](../core/using-the-math-numeric-type2.md)   
 [处理字符串值](../core/handling-string-values1.md)   
 [附录 a:数据类型](../core/appendix-a-data-types.md)