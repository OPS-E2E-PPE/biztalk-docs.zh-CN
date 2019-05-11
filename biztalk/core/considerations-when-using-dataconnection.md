---
title: 使用 DataConnection 的注意事项 |Microsoft Docs
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
ms.openlocfilehash: 3cf932f4082e36ed6704f848d38691326be5af66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354639"
---
# <a name="considerations-when-using-dataconnection"></a>使用 DataConnection 时的注意事项
使用业务规则引擎使用 DataConnection 时，请考虑以下。  
  
## <a name="use-primary-keys"></a>使用主键  
 如果存在主键，是否具有相同的主键，而不是由对象比较由确定相等的两个行。 如果行确定相同，只有一个副本保留在内存中，并且其他发布。 这会导致较少内存消耗。  
  
 当**DataConnection**将其添加到规则引擎第一次，该引擎始终尝试查找其主键信息从其架构。 如果存在主键，主键信息然后检索并在所有后续评估中使用。  
  
> [!NOTE]
>  主键是必需的如果需要对数据库进行更改。  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a>向 DataConnection 尽可能提供一个运行的事务  
 没有事务，每个查询和更新上**DataConnection**启动其自己的本地事务和不同的查询可能会返回不同结果的规则评估的不同部分中。 如果基础数据库表中有更改，用户可能会遇到不一致的行为。  
  
 尽管可以使用**DataConnection**而无需提供事务表不会随着时间的推移更改时，建议使用事务，即使**DataConnection**仅正在用于读取操作。  
  
 但是，更新数据时应始终使用事务。  
  
## <a name="number-of-queries-may-grow-linearly"></a>查询数可能呈线性增长  
 为针对查询**DataConnection**由其他联接的对象，针对执行的查询数量参数化**DataConnection**直接对应的联接对象数到达**DataConnection**。 因此，如果联接数对象到达**DataConnection**对象呈线性增长，针对的查询数量**DataConnection**将增长以线性方式以及。 目前，没有到位，以减少查询数进行优化。  
  
 此示例是规则：  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 表示**ObjectBinding**，DC 表示**DataConnection**，x 和 y 表示一个属性和 DC。  
  
 每个通过的测试的一个实例 (x = 7)，使用生成查询**DataConnection**。 如果有多个匹配的实例相同的查询结果数。  
  
## <a name="use-or-conditions-with-caution"></a>请谨慎使用 OR 条件  
 如果该规则使用仅合 (**AND**) 条件、 测试和查询将执行尽早，因此将减少通过传递的对象实例。 因此，针对后续的查询数量**DataConnection**也将相应减少。 如果析取范式 (**或者**) 的条件和一个**DataConnection**在规则中，所有条件评估将被推送至最终查询一起使用。 如果多个**DataConnection**规则，除了最后一个实际上都将变成 SELECT-ALL 查询语句的所有查询中使用。  
  
 一般情况下，它是更好的做法将任何带有 OR 条件的规则拆分为两个或多个离散的规则，因为使用 OR 条件将相比更多的原子规则定义的性能降低。 是否使用 DataConnections 都不是如此。  
  
 也可以考虑使用单独的规则，仅包含连接而不是使用一条规则的条件**或**条件。 与**或**条件，查询数增加实例全部连接对象的速度增长。 下面的示例说明了这一点。  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 在此示例中，一个代表**ObjectBinding**;DC 表示**DataConnection**，和 x、 y 和 z 表示一个属性和 DC。 如果 A 具有 100 个实例，并且 x 为 1，2 到 100 之间的第 100 对象中，在第二个对象中在第一个对象中需要根据运行 100 次查询**DataConnection**。  
  
 最好将其拆分为两个规则来重写前面的规则。  
  
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
 SQL 不支持某些谓词和规则引擎支持的函数。 如果在规则条件中使用这些不受支持的谓词和函数，它不能合并到查询中。 不能作为 SQL 查询优化了以下术语：  
  
-   某些引擎内置函数的 SQL 查询中有没有等效项。 这些是**电源**， **FindFirst**，并**FindAll**。 使用**DataConnection**列作为一个或多个其参数不能作为查询的一部分进行优化; 例如，Power (2，dc。Column1)。  
  
-   内置谓词使用的匹配**DataConnection**列作为其正则表达式参数 （第一个参数）。 例如，匹配 （"abc *"，dc1。Column2) 有效，但与匹配 (dc1。Column1，dc1。无法转换列 2)。  
  
-   使用具有的用户函数**DataConnection**列作为其参数之一。 例如，c1。M (dc。不能优化 Column1)，因为用户函数无法在数据库服务器上执行，但必须由业务规则引擎执行。  
  
-   表示在设置操作的用户函数**DataConnection**; 例如，dc。Column1(5)。  
  
-   函数使用**ObjectReference**到**DataConnection**; 例如，ObjecRef(dc)。  
  
-   如果一个或多个函数的自变量是进而，函数调用将成为则将无法翻译;例如，添加 (c1。M (dc。Column1)，5)。  
  
## <a name="see-also"></a>请参阅  
 [业务规则引擎中的数据访问](../core/data-access-in-the-business-rule-engine.md)