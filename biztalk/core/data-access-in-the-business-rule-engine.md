---
title: 业务规则引擎中的数据访问 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, data access
- Business Rules Engine, helper classes
- data, data access
ms.assetid: 38da32af-1e0d-43fb-b946-fb49a11f1681
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c685f0af9bb1750e2507c41d51e11774ae457ce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390031"
---
# <a name="data-access-in-the-business-rule-engine"></a>业务规则引擎中的数据访问
规则引擎本身支持仅限.NET 对象。 若要处理数据库中的数据，可以使用 ADO.NET 对象直接，但引擎提供了一些帮助器类，以简化从规则的数据库数据的使用。 规则引擎通过公开三个与数据库相关的类型来扩展其支持：**TypedDataRow**， **TypedDataTable**，和**DataConnection**。 本部分介绍这些帮助器类，提供有关何时使用每种类型的建议并使用它们时讨论一些性能产生影响。  
  
 帮助程序类如下所示：  
  
-   **TypedDataRow.** 通过使用 ADO.NET 的引用构造**DataRow**实例。 **TypedDataRow**是显而易见的选择规则以便仅处理一个或少量的特定表中的行中的数据。  
  
-   **TypedDataTable.** 按原义的集合**TypedDataRow**对象。 数据库表中的每一行将包装成**TypedDataRow**和由规则引擎添加到工作内存。  
  
     一个**TypedDataTable**需要内存中 ADO.NET **DataTable**，可以是性能开销，如果此特定**DataTable**包含非常大量的行。 如果少量的数据库表中的行是相关，并且可以确定这些行在调用规则中，使用之前先**DataTable**，否则，请使用**TypedDataRow**。假设是大量的 DataTable 中的行不相关的规则。  
  
-   **DataConnection.** 表示通过数据库连接访问的数据库中的表。 之间的差异**DataConnection**并**TypedDataTable**是，除了数据集名称和表名称**DataConnection**需要一个可用数据库连接和 （可选） 在数据库事务上下文。  
  
     与规则中使用的部分或全部谓词**DataConnection**将成为针对数据库连接的查询约束的一部分。 将从数据库中检索并由引擎使用满足查询约束的行。 此机制提供了更好的性能，并且会占用较少的内存比持有极大型**DataTable**在内存中。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 DataConnection 的注意事项](../core/considerations-when-using-dataconnection.md)  
  
-   [使用 TypedDataTable 和 DataConnection](../core/using-dataconnection-and-typeddatatable.md)