---
title: 消息架构的记录类型 |Microsoft Docs
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
ms.openlocfilehash: 4405dfff4868cbe9632fcd71d2a151555e56e95c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376447"
---
# <a name="message-schemas-for-record-types"></a>记录类型的消息架构
Oracle 记录类型是结构化的 PL/SQL 数据类型组成的一个或更简单或结构化的数据库类型。 记录类型主要用于在 PL/SQL 存储过程和函数来发送和接收分层数据。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]按以下方式支持记录类型：  
  
- 记录类型显示为复杂类型。  
  
- 记录类型可以是嵌套 （记录在记录中的）。  
  
- 记录类型可以声明为表 %行类型参数在存储的过程和函数。  
  
- 记录类型可以声明为 PL/SQL 包; 中的类型的记录参数例如， `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`。  
  
  > [!NOTE]
  >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 BFILE 作为记录成员的类型。  
  
  存储的过程或函数中使用的记录类型参数时，将使用该操作的命名空间进行限定。 下面的 XML 演示在消息中的记录类型的结构：  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 [REC_PARAM_NAME] 是记录参数的名称。  
  
 [字段名] 是字段的记录类型中的名称。  
  
 [OPERATION_NAMESPACE] 是存储的过程或函数的记录参数在其中使用的命名空间。  
  
 以下 XML 显示了具有嵌套的记录类型字段的记录类型参数的结构：  
  
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
  
## <a name="see-also"></a>请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)