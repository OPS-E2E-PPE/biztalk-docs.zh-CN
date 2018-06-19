---
title: 自动换行字符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7268f46-9bf6-4c76-9b3a-b4ee0e8db997
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f95ed10811232b15762c31bfc435ac7772a53b3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290029"
---
# <a name="wrap-characters"></a>自动换行字符

## <a name="overview"></a>概述
环绕符是单个字符，用于环绕字段中的数据字符，以便取消这些数据字符原本具有的特殊意义。 例如，如果您将某个平面文件记录定义为具有以下特性：  
  
-   名称 = Record1  
  
-   带分隔符  
  
-   子分隔符 = 逗号字符 (,)  
  
-   子顺序 = 中缀  
  
-   转义符 = 反斜杠字符 (\\)  
  
-   标记 = RECORD1  
  
-   名为 Field1、Field2 和 Field3 的三个字段均定义为使用数字符号字符 (#) 作为其环绕符。  
  
 则以下平面文件数据适用于记录：  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 数据分解到 XML 的以下片段中。  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 请注意，环绕粗体数据字符 field1、field2 和 field3 的环绕符 (#) 已删除。  
  
 当平面文件汇编器执行反向操作，将 XML 版本的记录转换为其等效的平面文件记录时之前, 和之后的每个字段，以生成的原始序列的数据字符的则都会插入换行字符平面文件的字符。  
  
 定义的转义符可与定义的环绕符一起使用。 例如，假定按如下所示更改 Field1 的值（以粗体显示）：  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 当使用所提供记录和字段定义组装此 XML 片断时，将生成以下平面文件字符的序列（以粗体显示转义的数字符号字符序列）：  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 在创建使用 BizTalk 编辑器的平面文件架构，你可以定义整个架构使用的默认换行字符**默认换行字符**和**默认换行字符类型**的属性**架构**节点。 然后，你可以配置要使用此默认换行字符或自定义的、 特定于字段的换行字符使用的架构中的每个单独的字段**换行字符**和**换行字符类型**属性的**Field 元素**或**字段特性**平面文件架构中的节点。
  
## <a name="see-also"></a>另请参阅  
- [如何解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- 自动换行字符属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    -  默认换行字符的平面文件架构 （节点属性
    -  默认换行字符类型的平面文件架构 （节点属性
    -  自动换行字符的平面文件架构 （节点属性  
    -  自动换行字符类型的平面文件架构 （节点属性