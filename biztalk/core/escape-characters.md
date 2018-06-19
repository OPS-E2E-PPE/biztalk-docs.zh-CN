---
title: 转义字符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af800b9-d31b-487a-9a06-6eda47d1574e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e961a205b77a9944a497d6e6cbed0df71f63e03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246125"
---
# <a name="escape-characters"></a>转义字符

## <a name="overview"></a>概述
：转义符是取消其后紧跟字符的任何特殊意义的单个字符。 例如，如果您将某个平面文件记录定义为具有以下特性：  
  
-   名称 = Record1  
  
-   带分隔符  
  
-   子分隔符 = 逗号字符 (,)  
  
-   子顺序 = 前缀  
  
-   转义符 = 反斜杠字符 (\\)  
  
-   标记 = RECORD1  
  
-   名为 Field1 和 Field2 的两个字段  
  
 则以下平面文件数据适用于记录：  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 数据将被拆装为以下 XML 片断：  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 请注意，转义的字符序列`\,`指示行的下平面文件记录，已转换为一个逗号字符不在数据中的转义字符的情况下为 Field1 等效 XML 记录中。 此外，该逗号字符未像其他两个逗号一样被解释为字段分隔符。  
  
 当平面文件组装器执行反向操作（将记录的 XML 版本转换为其等效平面文件记录）时，转义符将插入到 Field1 中间逗号的前面，以表示它应被解释为数据而不是字段分隔符。  
  
 在创建使用 BizTalk 编辑器的平面文件架构，你可以定义整个架构使用的默认转义字符**默认转义字符**和**默认转义字符类型**属性**架构**节点。 然后，你可以配置为使用此默认转义字符或自定义的、 特定记录的转义字符使用架构中的每个单独的记录**转义符]** 和**转义字符类型**属性**记录**节点。  
  
## <a name="see-also"></a>另请参阅  
- [如何解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- 转义字符属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - 默认转义字符 （的平面文件架构的节点属性）
    - 默认转义字符类型 （平面文件架构的节点属性）
    - 转义字符 （的平面文件架构的节点属性）  
    - 转义字符类型 （平面文件架构的节点属性）