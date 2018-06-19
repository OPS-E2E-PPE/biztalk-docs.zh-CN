---
title: 记录类型的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, message schemas for
- RECORD types, support for
ms.assetid: 637c42f2-eed0-4941-a6cd-7e03d01088b8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9022274041e06ad8ccc3f5243715d44d2b64282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214133"
---
# <a name="message-schemas-for-record-types"></a>记录类型的消息架构
Oracle 记录类型为结构化的 PL/SQL 数据类型组成的一个或更简单或结构化的数据库类型。 记录类型主要用于 PL/SQL 存储过程或函数中来发送和接收层次结构数据。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]按以下方式支持记录类型：  
  
-   为复杂类型中加以表示记录类型。  
  
-   记录类型可以嵌套 （记录在记录中的）。  
  
-   记录类型可声明为表中存储的过程和函数的 %rowtype 参数。  
  
-   记录类型可声明为 PL/SQL 包; 中的类型的记录参数例如， `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`。  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持作为记录成员 BFILE 类型。  
  
 当在存储的过程或函数中使用的记录类型参数时，将使用该操作的命名空间进行限定。 下面的 XML 演示在消息中的记录类型的结构：  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 [REC_PARAM_NAME] 是记录参数的名称。  
  
 [字段名] 是字段的中的记录类型的名称。  
  
 [OPERATION_NAMESPACE] 是存储的过程或在其中使用的记录参数的函数的命名空间。  
  
 下面的 XML 显示嵌套的记录类型字段的记录类型参数的结构：  
  
```  
<[REC_PARAM_NAME]>    
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  <[REC_PARAM_NAME2]>  
    <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
    <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME2]>  
    …  
  </[REC_PARAM_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)