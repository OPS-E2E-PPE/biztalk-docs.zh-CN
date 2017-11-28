---
title: "解决数据库错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases
- errors, databases
ms.assetid: d7b1cc9f-3f3e-464a-8249-1fd03b2b4d76
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47a22877cf06f03f875138208281420e56963da9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-database-errors"></a><span data-ttu-id="e0adb-102">解决数据库错误</span><span class="sxs-lookup"><span data-stu-id="e0adb-102">Resolving Database Errors</span></span>
<span data-ttu-id="e0adb-103">在 HL7 组织发布的 HL7 访问数据库，DataItems 和 TableValues 是由针对 table_id 所和 hl7_version 链接起来的两个表。</span><span class="sxs-lookup"><span data-stu-id="e0adb-103">In the HL7 Access database that the HL7 organization publishes, DataItems and TableValues are two tables linked by table_id and hl7_version.</span></span> <span data-ttu-id="e0adb-104">以下数据库跨-查询显示一些数据项，请参阅针对 table_id 所，它不具有任何表中列出的值：</span><span class="sxs-lookup"><span data-stu-id="e0adb-104">The following database cross-query shows that some data items refer to a table_id, which has no values listed in the table:</span></span>  
  
```  
select distinct d.table_id, d.hl7_version, t.table_item from DataElements as d left join TableValues as t on   
   d.table_id = t.table_id and d.hl7_version = t.hl7_version where d.table_id <>0 order by d.table_id  
```  
  
 <span data-ttu-id="e0adb-105">如果 HL7 Access 数据库具有缺少枚举值，你必须跨检查手动使用 HL7 规范的值并使用这些值在您的架构中。</span><span class="sxs-lookup"><span data-stu-id="e0adb-105">If the HL7 Access database has missing enumeration values, you must cross check the values manually with the HL7 specifications and use those values in your schema.</span></span> <span data-ttu-id="e0adb-106">处理此情形的一种方法是将枚举列表添加到架构。</span><span class="sxs-lookup"><span data-stu-id="e0adb-106">One way to deal with this situation is to add an enumeration list to the schema.</span></span> <span data-ttu-id="e0adb-107">若要执行此操作，请参阅[扩展枚举](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="e0adb-107">To do so, see [Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0adb-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0adb-108">See Also</span></span>  
 <span data-ttu-id="e0adb-109">[使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e0adb-109">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 [<span data-ttu-id="e0adb-110">扩展 HL7 2.X 架构具有 Z 对象</span><span class="sxs-lookup"><span data-stu-id="e0adb-110">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)