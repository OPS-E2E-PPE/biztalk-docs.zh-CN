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
# <a name="considerations-when-using-dataconnection"></a><span data-ttu-id="b1543-102">使用 DataConnection 的注意事项</span><span class="sxs-lookup"><span data-stu-id="b1543-102">Considerations When Using DataConnection</span></span>
<span data-ttu-id="b1543-103">对业务规则引擎使用 DataConnection 时，应考虑以下注意事项。</span><span class="sxs-lookup"><span data-stu-id="b1543-103">Consider the following when using DataConnection with the Business Rule Engine.</span></span>  
  
## <a name="use-primary-keys"></a><span data-ttu-id="b1543-104">使用主键</span><span class="sxs-lookup"><span data-stu-id="b1543-104">Use primary keys</span></span>  
 <span data-ttu-id="b1543-105">如果存在主键，则两行是否相等是由它们是否具有相同主键来确定的，而不是由对象比较确定。</span><span class="sxs-lookup"><span data-stu-id="b1543-105">When there is a primary key, the equality of two rows is determined by whether the rows have the same primary key, rather than by object comparison.</span></span> <span data-ttu-id="b1543-106">如果确定两行相同，则内存中将只保留一个副本，另一行将被释放。</span><span class="sxs-lookup"><span data-stu-id="b1543-106">If the rows are determined to be the same, only one copy is retained in memory, and the other is released.</span></span> <span data-ttu-id="b1543-107">这样可以消耗较少的内存。</span><span class="sxs-lookup"><span data-stu-id="b1543-107">This results in less memory consumption.</span></span>  
  
 <span data-ttu-id="b1543-108">当 **该组** 声明规则引擎第一次，引擎将始终尝试找到其架构从其主密钥信息。</span><span class="sxs-lookup"><span data-stu-id="b1543-108">When a **DataConnection** is asserted into the rule engine for the first time, the engine always tries to locate its primary key information from its schema.</span></span> <span data-ttu-id="b1543-109">如果存在主键，则随后将检索该主键信息并在所有后续评估中使用该信息。</span><span class="sxs-lookup"><span data-stu-id="b1543-109">If a primary key exists, primary key information is then retrieved and used in all subsequent evaluations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1543-110">如果需要对数据库进行更改，则主键是必需的。</span><span class="sxs-lookup"><span data-stu-id="b1543-110">A primary key is mandatory if changes need to be made to the database.</span></span>  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a><span data-ttu-id="b1543-111">在所有可能的情况下向 DataConnection 提供运行的事务</span><span class="sxs-lookup"><span data-stu-id="b1543-111">Provide a running transaction to the DataConnection whenever possible</span></span>  
 <span data-ttu-id="b1543-112">没有事务中，每个查询和更新上 **该组** 启动其自己的本地事务和不同的查询可能会返回不同会导致规则计算的不同部分。</span><span class="sxs-lookup"><span data-stu-id="b1543-112">Without a transaction, each query and update on the **DataConnection** initiates its own local transaction, and different queries might return different results in different parts of rule evaluations.</span></span> <span data-ttu-id="b1543-113">如果底层数据库表中发生了更改，则用户可能会遇到不一致的情况。</span><span class="sxs-lookup"><span data-stu-id="b1543-113">Users may experience inconsistent behavior if there are changes in the underlying database table.</span></span>  
  
 <span data-ttu-id="b1543-114">尽管可以使用 **该组** 而无需在表不会随着时间的推移更改时提供事务，建议使用事务，即使 **该组** 只用于读取操作。</span><span class="sxs-lookup"><span data-stu-id="b1543-114">Although you can use a **DataConnection** without providing a transaction when the table does not change over time, it is recommended that a transaction be used even when the **DataConnection** is only being used for read operations.</span></span>  
  
 <span data-ttu-id="b1543-115">不过，在更新数据时应始终使用事务。</span><span class="sxs-lookup"><span data-stu-id="b1543-115">However, a transaction should always be used when updating data.</span></span>  
  
## <a name="number-of-queries-may-grow-linearly"></a><span data-ttu-id="b1543-116">查询数可能呈线性增长</span><span class="sxs-lookup"><span data-stu-id="b1543-116">Number of queries may grow linearly</span></span>  
 <span data-ttu-id="b1543-117">为针对查询 **该组** 按其他联接的对象，对执行的查询数参数化 **该组** 直接对应的联接到达的对象数 **该组**。</span><span class="sxs-lookup"><span data-stu-id="b1543-117">As queries against the **DataConnection** are parameterized by other joined objects, the number of queries executed against the **DataConnection** corresponds directly to the number of joining objects reaching the **DataConnection**.</span></span> <span data-ttu-id="b1543-118">因此，如果对象联接的数量达到 **该组** 对象呈线性增长，针对查询数 **该组** 将增加而呈线性增长以及。</span><span class="sxs-lookup"><span data-stu-id="b1543-118">Therefore, if the number of joining objects reaching the **DataConnection** object grows linearly, the number of queries against the **DataConnection** will grow linearly as well.</span></span> <span data-ttu-id="b1543-119">目前尚没有适当的优化可用于减少查询数。</span><span class="sxs-lookup"><span data-stu-id="b1543-119">Currently, there is no optimization in place to reduce the number of queries.</span></span>  
  
 <span data-ttu-id="b1543-120">以下规则是此类情况的一个示例：</span><span class="sxs-lookup"><span data-stu-id="b1543-120">An example of this is the rule:</span></span>  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 <span data-ttu-id="b1543-121">表示 **ObjectBinding**, ，DC 表示 **该组**, ，x 和 y 表示一个属性和 DC。</span><span class="sxs-lookup"><span data-stu-id="b1543-121">A represents an **ObjectBinding**, DC represents a **DataConnection**, and x and y represent attributes of A and DC.</span></span>  
  
 <span data-ttu-id="b1543-122">对于每个通过的测试的一个实例 (x = 7)，通过使用生成查询 **该组**。</span><span class="sxs-lookup"><span data-stu-id="b1543-122">For every instance of A that passes the test (x = 7), a query is generated by using the **DataConnection**.</span></span> <span data-ttu-id="b1543-123">如果存在多个匹配的实例，则会生成相同数量的查询。</span><span class="sxs-lookup"><span data-stu-id="b1543-123">If there are many matching instances, the same number of queries results.</span></span>  
  
## <a name="use-or-conditions-with-caution"></a><span data-ttu-id="b1543-124">谨慎使用 OR 条件</span><span class="sxs-lookup"><span data-stu-id="b1543-124">Use OR conditions with caution</span></span>  
 <span data-ttu-id="b1543-125">如果该规则使用仅联合 (**AND**) 条件、 测试和查询将执行尽早，因此将缩减通过传递的对象的实例。</span><span class="sxs-lookup"><span data-stu-id="b1543-125">If the rule uses only conjunctive (**AND**) conditions, tests and queries will be executed as early as possible, so instances of objects passing through will be reduced.</span></span> <span data-ttu-id="b1543-126">因此，针对后续的查询数 **该组** 将按比例降低。</span><span class="sxs-lookup"><span data-stu-id="b1543-126">As a result, the number of queries against the subsequent **DataConnection** will be reduced proportionally.</span></span> <span data-ttu-id="b1543-127">如果分离 (**或者**) 条件和 **该组** 在规则中，评估将推送到的最后一个查询的所有条件一起使用。</span><span class="sxs-lookup"><span data-stu-id="b1543-127">If disjunctive (**OR**) conditions and a **DataConnection** are used together in a rule, all condition evaluations will be pushed to the final query.</span></span> <span data-ttu-id="b1543-128">如果多个 **该组** 规则，但最后一个有效地将成为选择所有查询语句的所有查询中使用。</span><span class="sxs-lookup"><span data-stu-id="b1543-128">If more than one **DataConnection** is used in a rule, all queries except the last one will effectively become a Select-ALL query statement.</span></span>  
  
 <span data-ttu-id="b1543-129">通常情况下，最好将任何带有 OR 条件的规则拆分为两个或多个离散的规则，因为与多个原子规则的定义相比，使用 OR 条件将会降低性能。</span><span class="sxs-lookup"><span data-stu-id="b1543-129">In general, it is better to split any rule with an OR condition into two or more discrete rules, because the use of OR conditions will decrease performance compared to the definition of more atomic rules.</span></span> <span data-ttu-id="b1543-130">无论是否使用 DataConnections 都是如此。</span><span class="sxs-lookup"><span data-stu-id="b1543-130">This is true whether DataConnections are used or not.</span></span>  
  
 <span data-ttu-id="b1543-131">你也可以考虑使用单独的规则仅组成的联合的条件，而不是具有一个规则 **或者** 条件。</span><span class="sxs-lookup"><span data-stu-id="b1543-131">You may also consider using separate rules that consist only of conjunctive conditions instead of one rule with **OR** conditions.</span></span> <span data-ttu-id="b1543-132">与 **或者** 条件，查询的数量增加乘法的所有联接的对象实例的速度。</span><span class="sxs-lookup"><span data-stu-id="b1543-132">With **OR** conditions, the number of queries grows at the speed of multiplication of instances of all joining objects.</span></span> <span data-ttu-id="b1543-133">下面的示例说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="b1543-133">This is shown in the following example.</span></span>  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="b1543-134">在此示例中，一个表示 **ObjectBinding**;DC 表示 **该组**, ，和 x、 y 和 z 表示一个属性和 DC。</span><span class="sxs-lookup"><span data-stu-id="b1543-134">In this example, A represents an **ObjectBinding**; DC represents a **DataConnection**, and x, y, and z represent attributes of A and DC.</span></span> <span data-ttu-id="b1543-135">如果 A 具有 100 个实例，并且 x 为 1 中的第一个对象，在第二个对象中，通过在第 100 的对象中，100 2 100 查询具有对运行 **该组**。</span><span class="sxs-lookup"><span data-stu-id="b1543-135">If A has 100 instances, and x is 1 in the first object, 2 in the second object, through 100 in the 100th object, 100 queries have to run against the **DataConnection**.</span></span>  
  
 <span data-ttu-id="b1543-136">最好通过将上述规则拆分为两个规则来对其进行重新编写。</span><span class="sxs-lookup"><span data-stu-id="b1543-136">It is better to rewrite the preceding rule by splitting it in to two rules.</span></span>  
  
 <span data-ttu-id="b1543-137">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="b1543-137">**Rule 1**</span></span>  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="b1543-138">**规则 2**</span><span class="sxs-lookup"><span data-stu-id="b1543-138">**Rule 2**</span></span>  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a><span data-ttu-id="b1543-139">SQL 不支持某些谓词和函数</span><span class="sxs-lookup"><span data-stu-id="b1543-139">SQL does not support some predicates and functions</span></span>  
 <span data-ttu-id="b1543-140">SQL 不支持规则引擎支持的某些谓词和函数。</span><span class="sxs-lookup"><span data-stu-id="b1543-140">Some predicates and functions that the rule engine supports are not supported by SQL.</span></span> <span data-ttu-id="b1543-141">如果规则条件中使用了这些不受支持的谓词和函数，则无法将该规则合并到查询中。</span><span class="sxs-lookup"><span data-stu-id="b1543-141">If these unsupported predicates and functions are used in the rule conditions, it cannot be incorporated into the query.</span></span> <span data-ttu-id="b1543-142">不能将以下术语作为 SQL 查询进行优化：</span><span class="sxs-lookup"><span data-stu-id="b1543-142">The following terms cannot be optimized as an SQL query:</span></span>  
  
-   <span data-ttu-id="b1543-143">某些引擎内置函数在 SQL 查询中没有任何等效项。</span><span class="sxs-lookup"><span data-stu-id="b1543-143">Some of the engine built-in functions have no equivalent in an SQL query.</span></span> <span data-ttu-id="b1543-144">这些是 **Power**, ，**FindFirst**, ，和 **FindAll**。</span><span class="sxs-lookup"><span data-stu-id="b1543-144">These are **Power**, **FindFirst**, and **FindAll**.</span></span> <span data-ttu-id="b1543-145">使用 **该组** 列作为一个或多个其自变量不能优化查询的一部分; 例如，电源 (2，dc。Column1)。</span><span class="sxs-lookup"><span data-stu-id="b1543-145">Using a **DataConnection** column as one or more of their arguments cannot be optimized as part of a query; for example, Power( 2, dc.Column1).</span></span>  
  
-   <span data-ttu-id="b1543-146">内置谓词使用的匹配 **该组** 作为其正则表达式自变量 （第一个参数） 的列。</span><span class="sxs-lookup"><span data-stu-id="b1543-146">Built-in predicate Match that uses a **DataConnection** column as its regular expression argument (the first argument).</span></span> <span data-ttu-id="b1543-147">例如，Match("abc\*", dc1.Column2) 有效，但 Match(dc1.Column1, dc1.Column2) 无法进行翻译。</span><span class="sxs-lookup"><span data-stu-id="b1543-147">For example, Match("abc\*", dc1.Column2) is valid, but Match(dc1.Column1, dc1.Column2) cannot be translated.</span></span>  
  
-   <span data-ttu-id="b1543-148">使用具有的用户函数 **该组** 作为其参数之一的列。</span><span class="sxs-lookup"><span data-stu-id="b1543-148">Using a user function that has a **DataConnection** column as one of its parameters.</span></span> <span data-ttu-id="b1543-149">例如，无法优化 c1.M(dc.Column1)，因为用户函数无法在数据库服务器上执行，但却必须由业务规则引擎执行。</span><span class="sxs-lookup"><span data-stu-id="b1543-149">For example, c1.M(dc.Column1) cannot be optimized because the user function cannot execute on the database server, but must be executed by the Business Rule Engine.</span></span>  
  
-   <span data-ttu-id="b1543-150">表示一组操作的用户函数 **该组**; 例如，dc。Column1(5)。</span><span class="sxs-lookup"><span data-stu-id="b1543-150">User functions that represent set operations on the **DataConnection**; for example, dc.Column1(5).</span></span>  
  
-   <span data-ttu-id="b1543-151">函数使用 **ObjectReference** 到 **该组**; 例如，ObjecRef(dc)。</span><span class="sxs-lookup"><span data-stu-id="b1543-151">Functions that use an **ObjectReference** to the **DataConnection**; for example, ObjecRef(dc).</span></span>  
  
-   <span data-ttu-id="b1543-152">如果函数的一个或多个参数无法进行翻译，则将无法翻译该函数调用，例如 Add(c1.M(dc.Column1), 5)。</span><span class="sxs-lookup"><span data-stu-id="b1543-152">If one or more of a function's arguments is untranslatable, the function call becomes untranslatable; for example, Add(c1.M(dc.Column1), 5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1543-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1543-153">See Also</span></span>  
 [<span data-ttu-id="b1543-154">业务规则引擎中的数据访问</span><span class="sxs-lookup"><span data-stu-id="b1543-154">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)