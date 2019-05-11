---
title: 解决数据库错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases
- errors, databases
ms.assetid: d7b1cc9f-3f3e-464a-8249-1fd03b2b4d76
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 169dc680c4a49bd04dc61d0074d12d058b8d0a91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289925"
---
# <a name="resolving-database-errors"></a>解决数据库错误
HL7 组织发布的 HL7 Access 数据库中, Dataitem 和 TableValues 是由 table_id 和 hl7_version 链接的两个表。 以下数据库跨-查询显示了一些数据项，请参阅 table_id，它不具有表中列出的任何值：  
  
```  
select distinct d.table_id, d.hl7_version, t.table_item from DataElements as d left join TableValues as t on   
   d.table_id = t.table_id and d.hl7_version = t.hl7_version where d.table_id <>0 order by d.table_id  
```  
  
 如果 HL7 Access 数据库中有缺少枚举值，必须跨检查手动使用 HL7 规范的值，并在您的架构中使用这些值。 若要处理这种情况的一种方法是添加到架构的枚举列表。 若要执行此操作，请参阅[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)