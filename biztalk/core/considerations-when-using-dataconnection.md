---
title: 使用数据连接时的注意事项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Business Rules Engine, DataConnection tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], DataConnection
ms.assetid: 1b4c8aa5-053f-43d7-9f5f-050383405fed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f99110daafa74cb16b6cc5b98e1382049bbb158
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22238949"
---
# <a name="considerations-when-using-dataconnection"></a>使用 DataConnection 的注意事项
对业务规则引擎使用 DataConnection 时，应考虑以下注意事项。  
  
## <a name="use-primary-keys"></a>使用主键  
 如果存在主键，则两行是否相等是由它们是否具有相同主键来确定的，而不是由对象比较确定。 如果确定两行相同，则内存中将只保留一个副本，另一行将被释放。 这样可以消耗较少的内存。  
  
 当 **该组** 声明规则引擎第一次，引擎将始终尝试找到其架构从其主密钥信息。 如果存在主键，则随后将检索该主键信息并在所有后续评估中使用该信息。  
  
> [!NOTE]
>  如果需要对数据库进行更改，则主键是必需的。  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a>在所有可能的情况下向 DataConnection 提供运行的事务  
 没有事务中，每个查询和更新上 **该组** 启动其自己的本地事务和不同的查询可能会返回不同会导致规则计算的不同部分。 如果底层数据库表中发生了更改，则用户可能会遇到不一致的情况。  
  
 尽管可以使用 **该组** 而无需在表不会随着时间的推移更改时提供事务，建议使用事务，即使 **该组** 只用于读取操作。  
  
 不过，在更新数据时应始终使用事务。  
  
## <a name="number-of-queries-may-grow-linearly"></a>查询数可能呈线性增长  
 为针对查询 **该组** 按其他联接的对象，对执行的查询数参数化 **该组** 直接对应的联接到达的对象数 **该组**。 因此，如果对象联接的数量达到 **该组** 对象呈线性增长，针对查询数 **该组** 将增加而呈线性增长以及。 目前尚没有适当的优化可用于减少查询数。  
  
 以下规则是此类情况的一个示例：  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 表示 **ObjectBinding**, ，DC 表示 **该组**, ，x 和 y 表示一个属性和 DC。  
  
 对于每个通过的测试的一个实例 (x = 7)，通过使用生成查询 **该组**。 如果存在多个匹配的实例，则会生成相同数量的查询。  
  
## <a name="use-or-conditions-with-caution"></a>谨慎使用 OR 条件  
 如果该规则使用仅联合 (**AND**) 条件、 测试和查询将执行尽早，因此将缩减通过传递的对象的实例。 因此，针对后续的查询数 **该组** 将按比例降低。 如果分离 (**或者**) 条件和 **该组** 在规则中，评估将推送到的最后一个查询的所有条件一起使用。 如果多个 **该组** 规则，但最后一个有效地将成为选择所有查询语句的所有查询中使用。  
  
 通常情况下，最好将任何带有 OR 条件的规则拆分为两个或多个离散的规则，因为与多个原子规则的定义相比，使用 OR 条件将会降低性能。 无论是否使用 DataConnections 都是如此。  
  
 你也可以考虑使用单独的规则仅组成的联合的条件，而不是具有一个规则 **或者** 条件。 与 **或者** 条件，查询的数量增加乘法的所有联接的对象实例的速度。 下面的示例说明了这一点。  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 在此示例中，一个表示 **ObjectBinding**;DC 表示 **该组**, ，和 x、 y 和 z 表示一个属性和 DC。 如果 A 具有 100 个实例，并且 x 为 1 中的第一个对象，在第二个对象中，通过在第 100 的对象中，100 2 100 查询具有对运行 **该组**。  
  
 最好通过将上述规则拆分为两个规则来对其进行重新编写。  
  
 **规则 1**  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 **规则 2**  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a>SQL 不支持某些谓词和函数  
 SQL 不支持规则引擎支持的某些谓词和函数。 如果规则条件中使用了这些不受支持的谓词和函数，则无法将该规则合并到查询中。 不能将以下术语作为 SQL 查询进行优化：  
  
-   某些引擎内置函数在 SQL 查询中没有任何等效项。 这些是 **Power**, ，**FindFirst**, ，和 **FindAll**。 使用 **该组** 列作为一个或多个其自变量不能优化查询的一部分; 例如，电源 (2，dc。Column1)。  
  
-   内置谓词使用的匹配 **该组** 作为其正则表达式自变量 （第一个参数） 的列。 例如，Match("abc*", dc1.Column2) 有效，但 Match(dc1.Column1, dc1.Column2) 无法进行翻译。  
  
-   使用具有的用户函数 **该组** 作为其参数之一的列。 例如，无法优化 c1.M(dc.Column1)，因为用户函数无法在数据库服务器上执行，但却必须由业务规则引擎执行。  
  
-   表示一组操作的用户函数 **该组**; 例如，dc。Column1(5)。  
  
-   函数使用 **ObjectReference** 到 **该组**; 例如，ObjecRef(dc)。  
  
-   如果函数的一个或多个参数无法进行翻译，则将无法翻译该函数调用，例如 Add(c1.M(dc.Column1), 5)。  
  
## <a name="see-also"></a>另请参阅  
 [业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md)