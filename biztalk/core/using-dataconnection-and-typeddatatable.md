---
title: 使用 DataConnection 和 TypedDataTable |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9decd3a849aa21e0e769e006c8dfe29ca5b7315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401615"
---
# <a name="using-dataconnection-and-typeddatatable"></a>使用 TypedDataTable 和 DataConnection
在许多情况下，使用**DataConnection**提供了更好的性能和使用更少的内存比使用**TypedDataTable**。 但是， **TypedDataTable**可能要求在某些情况下，由于使用某些限制**DataConnection**。 在某些其他情况下，使用**TypedDataTable**可能会产生更好的性能比使用**DataConnection**。 本主题介绍的条件和选择正确的方法时应考虑的因素。  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a>何时使用 TypedDataTable 而不是 DataConnection  
 在以下情况下，而不是 DataConnection 中使用 TypedDataTable:  
  
-   不需要进行数据更改，但表没有主键。 若要使用做出数据更改**DataConnection**，主要密钥是必需的。 因此，如果有没有主键，则**TypedDataTable**是唯一的可行方法。  
  
    > [!NOTE]
    >  规则引擎只更新在内存中的值**TypedDataTable**。 负责调用方永久保存这些更改。  
  
-   选择性很高，这意味着大型的表中的行百分比将通过指定为规则条件的测试。 在这种情况下， **DataConnection**不提供很大的收益，其执行比**TypedDataTable**。  
  
-   表非常小，通常情况下，包含少于 500 行的表。 请注意，此数目可更大或较小，具体取决于规则形状和可用于规则引擎的内存。  
  
-   在规则集中需要规则链接行为。 调用**更新**函数**DataConnection**不受支持，但你可以调用**DataConnection.Update**在规则中使用的帮助器方法。 必需的规则链接时**TypedDataTable**是更好的选择。  
  
-   表中的一个或多个列包含非常大量的数据不是必需的规则。 一个示例是一个图像数据库中，各列包含图像 （大量的数据）、 名称、 日期和等等。 如果不需要图像，则可能会更好的做法选择仅规则所需的列。 例如，发出"SELECT Name，Date from TABLE"之类的查询可能比使用更高效**DataConnection**。  
  
-   如果许多规则需要更新同一数据库行，使用**TypedDataTable**，该行处于共享状态之间的所有规则，并且如果条件为相同 (例如 Table.Column = = 5)，可以优化条件评估。 与**DataConnection**，一般情况下，查询生成的每个规则，以使用**DataConnection**。 虽然 （如果表具有主键），行重复使用，可以生成多个查询以获取每次的相同的数据。  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a>何时使用 DataConnection 而不是 TypedDataTable  
 在以下情况下，而不是 TypedDataTable 使用 DataConnection:  
  
-   表中包含大量行，但选择性很低 — 仅少数行满足规则条件。  
  
-   只有一个数据库表很大;在规则中使用的所有其他对象都有较多的实例。 在最坏的情况下，对数据库执行的查询数等于在规则中使用的所有其他实例的产品。  
  
-   规则以独占方式包含连接条件，并且这些规则中使用对象，而非数据库表。  
  
## <a name="see-also"></a>请参阅  
 [业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md)