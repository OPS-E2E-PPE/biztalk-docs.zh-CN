---
title: "使用数据连接和 TypedDataTable |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Assert function [Business Rules Engine], TypedData table
- Business Rules Engine, DataConnection tips
- TypedData table
- Business Rules Engine, TypedData table tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], DataConnection
ms.assetid: e825803e-6626-4ddd-a77e-75a3ba2b74a4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b5a0a490023d77676cc5d156ad5126ad5d7d6c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-dataconnection-and-typeddatatable"></a>使用数据连接和 TypedDataTable
在许多情况下，使用**该组**提供更好的性能和使用较少的内存比使用**TypedDataTable**。 但是， **TypedDataTable**可能要求在某些情况下，由于某些限制使用**该组**。 在某些其他情况下，使用**TypedDataTable**可能会产生更好的性能比使用**该组**。 本主题介绍了在选择正确的方法时应考虑的条件和因素。  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a>何时使用 TypedDataTable 而不是 DataConnection  
 在以下情况下使用 TypedDataTable 而不是 DataConnection：  
  
-   需要更改数据，但表没有主键。 若要使用的数据更改**该组**，主密钥是必需的。 因此，如果没有主键， **TypedDataTable**是唯一可行方法。  
  
    > [!NOTE]
    >  规则引擎仅更新内存中的值**TypedDataTable**。 是否永久保存更改由调用方决定。  
  
-   选择性很高，这意味着，表中大部分行都将通过按规则条件指定的测试。 在这种情况下，**该组**不提供很大的收益，它可能执行不如**TypedDataTable**。  
  
-   表非常小，通常包含的行数少于 500 行。 请注意，此数目可大可小，具体数值由规则形状和可用于规则引擎的内存来决定。  
  
-   在规则集中预计存在规则链接行为。 调用**更新**函数上**该组**不受支持，但你无法调用**DataConnection.Update**规则使用一个帮助器方法中。 当规则链接是必需的**TypedDataTable**是更好的选择。  
  
-   表中一个或多个列包含大量规则不需要的数据。 例如，图像数据库。图像数据库中的各列包含图像（大量数据）、名称、日期等信息。 如果不需要图像，则最好只选择规则所需的列。 例如，例如"选择名称、 日期表"将查询可以是比使用效率更高**该组**。  
  
-   如果多个规则需要或更新相同的数据库行，使用**TypedDataTable**，该行处于共享状态之间的所有规则，以及条件是否相同 (例如，Table.Column = = 5)，可以优化条件求值。 与**该组**，一般情况下，为每个规则，以使用生成查询**该组**。 尽管行是重复使用的（如果表具有主键），但仍需要生成多个查询，每次都获取相同的数据。  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a>何时使用 DataConnection 而不是 TypedDataTable  
 在以下情况下使用 DataConnection 而不是 TypedDataTable：  
  
-   表中包含大量行，但选择性很低；也就是说，只有少数行满足规则条件。  
  
-   只有一个数据库表很大；在规则中使用的其他所有对象都具有数量很少的实例。 在最差的情况下，对数据库执行的查询数等于在规则中使用的其他所有实例的乘积。  
  
-   规则仅由连接条件构成，并且在这些规则中使用非数据库表的对象。  
  
## <a name="see-also"></a>另请参阅  
 [业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md)