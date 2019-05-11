---
title: 对字符进行转义 |Microsoft Docs
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
ms.openlocfilehash: 21bc0c175303f7ccfd64a896dd713bf4651b6dcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346208"
---
# <a name="escape-characters"></a>转义字符

## <a name="overview"></a>概述
转义符是字符的取消其后的任何特殊含义的单个字符。 例如，如果平面文件记录定义为具有以下特征：  
  
- 名称 = Record1  
  
- 带分隔符  
  
- 子分隔符 = 逗号字符 （，）  
  
- 子顺序 = 前缀  
  
- 转义符 = 反斜杠字符 (\\)  
  
- 标记 = RECORD1  
  
- 名为 Field1 和 Field2 的两个字段  
  
  然后以下平面文件数据适用于该记录。  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 数据将拆装成以下 XML 片断。  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 请注意转义字符序列`\,`指示后的平面文件记录的行上，已转换为不带转义字符数据中的单个逗号字符 Field1 的等效 XML 记录中。 此外，该逗号字符是未解释为像其他两个逗号是字段分隔符。  
  
 当平面文件组装器执行反向操作，将记录的 XML 版本转换为其等效的平面文件记录时，从而指示应将解释 Field1，中间逗号的前面插入转义符为数据而不是字段分隔符。  
  
 在创建时使用 BizTalk 编辑器的平面文件架构，可以定义的整个架构使用默认转义符**默认转义符**并**默认转义符类型**属性**架构**节点。 然后，可以配置每个记录中要使用此默认转义符或自定义的特定于记录的转义字符使用的架构**转义符]** 和**转义符类型**的属性**记录**节点。  
  
## <a name="see-also"></a>请参阅  
- [将特殊字符作为字段值的一部分进行解释的方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- 转义字符属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - 默认的转义符 （平面文件架构的节点属性）
    - 默认转义符类型 （平面文件架构的节点属性）
    - 转义符 （平面文件架构的节点属性）  
    - 转义符类型 （平面文件架构的节点属性）