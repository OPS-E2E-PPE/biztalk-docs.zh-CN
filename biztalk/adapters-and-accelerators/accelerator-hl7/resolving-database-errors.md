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
# <a name="resolving-database-errors"></a><span data-ttu-id="b74e9-102">解决数据库错误</span><span class="sxs-lookup"><span data-stu-id="b74e9-102">Resolving Database Errors</span></span>
<span data-ttu-id="b74e9-103">HL7 组织发布的 HL7 Access 数据库中, Dataitem 和 TableValues 是由 table_id 和 hl7_version 链接的两个表。</span><span class="sxs-lookup"><span data-stu-id="b74e9-103">In the HL7 Access database that the HL7 organization publishes, DataItems and TableValues are two tables linked by table_id and hl7_version.</span></span> <span data-ttu-id="b74e9-104">以下数据库跨-查询显示了一些数据项，请参阅 table_id，它不具有表中列出的任何值：</span><span class="sxs-lookup"><span data-stu-id="b74e9-104">The following database cross-query shows that some data items refer to a table_id, which has no values listed in the table:</span></span>  
  
```  
select distinct d.table_id, d.hl7_version, t.table_item from DataElements as d left join TableValues as t on   
   d.table_id = t.table_id and d.hl7_version = t.hl7_version where d.table_id <>0 order by d.table_id  
```  
  
 <span data-ttu-id="b74e9-105">如果 HL7 Access 数据库中有缺少枚举值，必须跨检查手动使用 HL7 规范的值，并在您的架构中使用这些值。</span><span class="sxs-lookup"><span data-stu-id="b74e9-105">If the HL7 Access database has missing enumeration values, you must cross check the values manually with the HL7 specifications and use those values in your schema.</span></span> <span data-ttu-id="b74e9-106">若要处理这种情况的一种方法是添加到架构的枚举列表。</span><span class="sxs-lookup"><span data-stu-id="b74e9-106">One way to deal with this situation is to add an enumeration list to the schema.</span></span> <span data-ttu-id="b74e9-107">若要执行此操作，请参阅[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="b74e9-107">To do so, see [Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74e9-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b74e9-108">See Also</span></span>  
 <span data-ttu-id="b74e9-109">[使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="b74e9-109">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 [<span data-ttu-id="b74e9-110">使用 Z 对象扩展 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="b74e9-110">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)