---
title: 业务规则引擎中的数据访问 |Microsoft 文档
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
ms.openlocfilehash: 58de70c2befd13f4995ebd073ebd70a2e7d84ea7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238613"
---
# <a name="data-access-in-the-business-rule-engine"></a>业务规则引擎中的数据访问
规则引擎本身只支持 .NET 对象。 若要处理来自数据库的数据，则可直接使用 ADO.NET 对象，但该引擎还提供了某些助手类以简化根据规则使用数据库数据的过程。 规则引擎通过公开三个数据库相关的类型来扩展它的支持： **TypedDataRow**， **TypedDataTable**，和**该组**。 本部分将介绍这些助手类，提供有关每种类型应在何时使用的建议，以及讨论在使用这些类时对性能所造成的影响。  
  
 助手类如下所示：  
  
-   **TypedDataRow。** 通过使用 ADO.NET 的引用构造**DataRow**实例。 **TypedDataRow**是从一个或少量的特定表中的行的数据以便仅处理的规则的一个明显选项。  
  
-   **TypedDataTable。** 按原义的集合**TypedDataRow**对象。 数据库表中的每一行将包装为**TypedDataRow**和由规则引擎对声明到工作内存。  
  
     A **TypedDataTable**需要内存中 ADO.NET **DataTable**，可能是性能系统开销，如果此特定**DataTable**包含大量的行。 如果少量的数据库表中的行相关，且你可以确定之前调用的规则，使用这些行**DataTable**，否则使用**TypedDataRow**。假设条件是高 DataTable 中的行数是相关的规则。  
  
-   **数据连接。** 表示通过数据库连接访问的数据库中的表。 之间的差异**该组**和**TypedDataTable**在于，除了数据集名称和表名**该组**需要一个可用数据库连接和 （可选） 数据库事务上下文。  
  
     使用规则中使用的某些或所有谓词**该组**将成为对数据库连接的查询约束的一部分。 从数据库中检索只满足查询约束的行，并供引擎使用。 此机制提供更好的性能和使用较少的内存比持有非常大**DataTable**在内存中。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用数据连接时的注意事项](../core/considerations-when-using-dataconnection.md)  
  
-   [使用数据连接和 TypedDataTable](../core/using-dataconnection-and-typeddatatable.md)