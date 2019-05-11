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
# <a name="considerations-when-using-dataconnection"></a><span data-ttu-id="48c9a-102">使用 DataConnection 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="48c9a-102">Considerations When Using DataConnection</span></span>
<span data-ttu-id="48c9a-103">使用业务规则引擎使用 DataConnection 时，请考虑以下。</span><span class="sxs-lookup"><span data-stu-id="48c9a-103">Consider the following when using DataConnection with the Business Rule Engine.</span></span>  
  
## <a name="use-primary-keys"></a><span data-ttu-id="48c9a-104">使用主键</span><span class="sxs-lookup"><span data-stu-id="48c9a-104">Use primary keys</span></span>  
 <span data-ttu-id="48c9a-105">如果存在主键，是否具有相同的主键，而不是由对象比较由确定相等的两个行。</span><span class="sxs-lookup"><span data-stu-id="48c9a-105">When there is a primary key, the equality of two rows is determined by whether the rows have the same primary key, rather than by object comparison.</span></span> <span data-ttu-id="48c9a-106">如果行确定相同，只有一个副本保留在内存中，并且其他发布。</span><span class="sxs-lookup"><span data-stu-id="48c9a-106">If the rows are determined to be the same, only one copy is retained in memory, and the other is released.</span></span> <span data-ttu-id="48c9a-107">这会导致较少内存消耗。</span><span class="sxs-lookup"><span data-stu-id="48c9a-107">This results in less memory consumption.</span></span>  
  
 <span data-ttu-id="48c9a-108">当**DataConnection**将其添加到规则引擎第一次，该引擎始终尝试查找其主键信息从其架构。</span><span class="sxs-lookup"><span data-stu-id="48c9a-108">When a **DataConnection** is asserted into the rule engine for the first time, the engine always tries to locate its primary key information from its schema.</span></span> <span data-ttu-id="48c9a-109">如果存在主键，主键信息然后检索并在所有后续评估中使用。</span><span class="sxs-lookup"><span data-stu-id="48c9a-109">If a primary key exists, primary key information is then retrieved and used in all subsequent evaluations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48c9a-110">主键是必需的如果需要对数据库进行更改。</span><span class="sxs-lookup"><span data-stu-id="48c9a-110">A primary key is mandatory if changes need to be made to the database.</span></span>  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a><span data-ttu-id="48c9a-111">向 DataConnection 尽可能提供一个运行的事务</span><span class="sxs-lookup"><span data-stu-id="48c9a-111">Provide a running transaction to the DataConnection whenever possible</span></span>  
 <span data-ttu-id="48c9a-112">没有事务，每个查询和更新上**DataConnection**启动其自己的本地事务和不同的查询可能会返回不同结果的规则评估的不同部分中。</span><span class="sxs-lookup"><span data-stu-id="48c9a-112">Without a transaction, each query and update on the **DataConnection** initiates its own local transaction, and different queries might return different results in different parts of rule evaluations.</span></span> <span data-ttu-id="48c9a-113">如果基础数据库表中有更改，用户可能会遇到不一致的行为。</span><span class="sxs-lookup"><span data-stu-id="48c9a-113">Users may experience inconsistent behavior if there are changes in the underlying database table.</span></span>  
  
 <span data-ttu-id="48c9a-114">尽管可以使用**DataConnection**而无需提供事务表不会随着时间的推移更改时，建议使用事务，即使**DataConnection**仅正在用于读取操作。</span><span class="sxs-lookup"><span data-stu-id="48c9a-114">Although you can use a **DataConnection** without providing a transaction when the table does not change over time, it is recommended that a transaction be used even when the **DataConnection** is only being used for read operations.</span></span>  
  
 <span data-ttu-id="48c9a-115">但是，更新数据时应始终使用事务。</span><span class="sxs-lookup"><span data-stu-id="48c9a-115">However, a transaction should always be used when updating data.</span></span>  
  
## <a name="number-of-queries-may-grow-linearly"></a><span data-ttu-id="48c9a-116">查询数可能呈线性增长</span><span class="sxs-lookup"><span data-stu-id="48c9a-116">Number of queries may grow linearly</span></span>  
 <span data-ttu-id="48c9a-117">为针对查询**DataConnection**由其他联接的对象，针对执行的查询数量参数化**DataConnection**直接对应的联接对象数到达**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="48c9a-117">As queries against the **DataConnection** are parameterized by other joined objects, the number of queries executed against the **DataConnection** corresponds directly to the number of joining objects reaching the **DataConnection**.</span></span> <span data-ttu-id="48c9a-118">因此，如果联接数对象到达**DataConnection**对象呈线性增长，针对的查询数量**DataConnection**将增长以线性方式以及。</span><span class="sxs-lookup"><span data-stu-id="48c9a-118">Therefore, if the number of joining objects reaching the **DataConnection** object grows linearly, the number of queries against the **DataConnection** will grow linearly as well.</span></span> <span data-ttu-id="48c9a-119">目前，没有到位，以减少查询数进行优化。</span><span class="sxs-lookup"><span data-stu-id="48c9a-119">Currently, there is no optimization in place to reduce the number of queries.</span></span>  
  
 <span data-ttu-id="48c9a-120">此示例是规则：</span><span class="sxs-lookup"><span data-stu-id="48c9a-120">An example of this is the rule:</span></span>  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 <span data-ttu-id="48c9a-121">表示**ObjectBinding**，DC 表示**DataConnection**，x 和 y 表示一个属性和 DC。</span><span class="sxs-lookup"><span data-stu-id="48c9a-121">A represents an **ObjectBinding**, DC represents a **DataConnection**, and x and y represent attributes of A and DC.</span></span>  
  
 <span data-ttu-id="48c9a-122">每个通过的测试的一个实例 (x = 7)，使用生成查询**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="48c9a-122">For every instance of A that passes the test (x = 7), a query is generated by using the **DataConnection**.</span></span> <span data-ttu-id="48c9a-123">如果有多个匹配的实例相同的查询结果数。</span><span class="sxs-lookup"><span data-stu-id="48c9a-123">If there are many matching instances, the same number of queries results.</span></span>  
  
## <a name="use-or-conditions-with-caution"></a><span data-ttu-id="48c9a-124">请谨慎使用 OR 条件</span><span class="sxs-lookup"><span data-stu-id="48c9a-124">Use OR conditions with caution</span></span>  
 <span data-ttu-id="48c9a-125">如果该规则使用仅合 (**AND**) 条件、 测试和查询将执行尽早，因此将减少通过传递的对象实例。</span><span class="sxs-lookup"><span data-stu-id="48c9a-125">If the rule uses only conjunctive (**AND**) conditions, tests and queries will be executed as early as possible, so instances of objects passing through will be reduced.</span></span> <span data-ttu-id="48c9a-126">因此，针对后续的查询数量**DataConnection**也将相应减少。</span><span class="sxs-lookup"><span data-stu-id="48c9a-126">As a result, the number of queries against the subsequent **DataConnection** will be reduced proportionally.</span></span> <span data-ttu-id="48c9a-127">如果析取范式 (**或者**) 的条件和一个**DataConnection**在规则中，所有条件评估将被推送至最终查询一起使用。</span><span class="sxs-lookup"><span data-stu-id="48c9a-127">If disjunctive (**OR**) conditions and a **DataConnection** are used together in a rule, all condition evaluations will be pushed to the final query.</span></span> <span data-ttu-id="48c9a-128">如果多个**DataConnection**规则，除了最后一个实际上都将变成 SELECT-ALL 查询语句的所有查询中使用。</span><span class="sxs-lookup"><span data-stu-id="48c9a-128">If more than one **DataConnection** is used in a rule, all queries except the last one will effectively become a Select-ALL query statement.</span></span>  
  
 <span data-ttu-id="48c9a-129">一般情况下，它是更好的做法将任何带有 OR 条件的规则拆分为两个或多个离散的规则，因为使用 OR 条件将相比更多的原子规则定义的性能降低。</span><span class="sxs-lookup"><span data-stu-id="48c9a-129">In general, it is better to split any rule with an OR condition into two or more discrete rules, because the use of OR conditions will decrease performance compared to the definition of more atomic rules.</span></span> <span data-ttu-id="48c9a-130">是否使用 DataConnections 都不是如此。</span><span class="sxs-lookup"><span data-stu-id="48c9a-130">This is true whether DataConnections are used or not.</span></span>  
  
 <span data-ttu-id="48c9a-131">也可以考虑使用单独的规则，仅包含连接而不是使用一条规则的条件**或**条件。</span><span class="sxs-lookup"><span data-stu-id="48c9a-131">You may also consider using separate rules that consist only of conjunctive conditions instead of one rule with **OR** conditions.</span></span> <span data-ttu-id="48c9a-132">与**或**条件，查询数增加实例全部连接对象的速度增长。</span><span class="sxs-lookup"><span data-stu-id="48c9a-132">With **OR** conditions, the number of queries grows at the speed of multiplication of instances of all joining objects.</span></span> <span data-ttu-id="48c9a-133">下面的示例说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="48c9a-133">This is shown in the following example.</span></span>  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="48c9a-134">在此示例中，一个代表**ObjectBinding**;DC 表示**DataConnection**，和 x、 y 和 z 表示一个属性和 DC。</span><span class="sxs-lookup"><span data-stu-id="48c9a-134">In this example, A represents an **ObjectBinding**; DC represents a **DataConnection**, and x, y, and z represent attributes of A and DC.</span></span> <span data-ttu-id="48c9a-135">如果 A 具有 100 个实例，并且 x 为 1，2 到 100 之间的第 100 对象中，在第二个对象中在第一个对象中需要根据运行 100 次查询**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="48c9a-135">If A has 100 instances, and x is 1 in the first object, 2 in the second object, through 100 in the 100th object, 100 queries have to run against the **DataConnection**.</span></span>  
  
 <span data-ttu-id="48c9a-136">最好将其拆分为两个规则来重写前面的规则。</span><span class="sxs-lookup"><span data-stu-id="48c9a-136">It is better to rewrite the preceding rule by splitting it in to two rules.</span></span>  
  
 <span data-ttu-id="48c9a-137">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="48c9a-137">**Rule 1**</span></span>  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 <span data-ttu-id="48c9a-138">**规则 2**</span><span class="sxs-lookup"><span data-stu-id="48c9a-138">**Rule 2**</span></span>  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a><span data-ttu-id="48c9a-139">SQL 不支持某些谓词和函数</span><span class="sxs-lookup"><span data-stu-id="48c9a-139">SQL does not support some predicates and functions</span></span>  
 <span data-ttu-id="48c9a-140">SQL 不支持某些谓词和规则引擎支持的函数。</span><span class="sxs-lookup"><span data-stu-id="48c9a-140">Some predicates and functions that the rule engine supports are not supported by SQL.</span></span> <span data-ttu-id="48c9a-141">如果在规则条件中使用这些不受支持的谓词和函数，它不能合并到查询中。</span><span class="sxs-lookup"><span data-stu-id="48c9a-141">If these unsupported predicates and functions are used in the rule conditions, it cannot be incorporated into the query.</span></span> <span data-ttu-id="48c9a-142">不能作为 SQL 查询优化了以下术语：</span><span class="sxs-lookup"><span data-stu-id="48c9a-142">The following terms cannot be optimized as an SQL query:</span></span>  
  
-   <span data-ttu-id="48c9a-143">某些引擎内置函数的 SQL 查询中有没有等效项。</span><span class="sxs-lookup"><span data-stu-id="48c9a-143">Some of the engine built-in functions have no equivalent in an SQL query.</span></span> <span data-ttu-id="48c9a-144">这些是**电源**， **FindFirst**，并**FindAll**。</span><span class="sxs-lookup"><span data-stu-id="48c9a-144">These are **Power**, **FindFirst**, and **FindAll**.</span></span> <span data-ttu-id="48c9a-145">使用**DataConnection**列作为一个或多个其参数不能作为查询的一部分进行优化; 例如，Power (2，dc。Column1)。</span><span class="sxs-lookup"><span data-stu-id="48c9a-145">Using a **DataConnection** column as one or more of their arguments cannot be optimized as part of a query; for example, Power( 2, dc.Column1).</span></span>  
  
-   <span data-ttu-id="48c9a-146">内置谓词使用的匹配**DataConnection**列作为其正则表达式参数 （第一个参数）。</span><span class="sxs-lookup"><span data-stu-id="48c9a-146">Built-in predicate Match that uses a **DataConnection** column as its regular expression argument (the first argument).</span></span> <span data-ttu-id="48c9a-147">例如，匹配 （"abc \*"，dc1。Column2) 有效，但与匹配 (dc1。Column1，dc1。无法转换列 2)。</span><span class="sxs-lookup"><span data-stu-id="48c9a-147">For example, Match("abc\*", dc1.Column2) is valid, but Match(dc1.Column1, dc1.Column2) cannot be translated.</span></span>  
  
-   <span data-ttu-id="48c9a-148">使用具有的用户函数**DataConnection**列作为其参数之一。</span><span class="sxs-lookup"><span data-stu-id="48c9a-148">Using a user function that has a **DataConnection** column as one of its parameters.</span></span> <span data-ttu-id="48c9a-149">例如，c1。M (dc。不能优化 Column1)，因为用户函数无法在数据库服务器上执行，但必须由业务规则引擎执行。</span><span class="sxs-lookup"><span data-stu-id="48c9a-149">For example, c1.M(dc.Column1) cannot be optimized because the user function cannot execute on the database server, but must be executed by the Business Rule Engine.</span></span>  
  
-   <span data-ttu-id="48c9a-150">表示在设置操作的用户函数**DataConnection**; 例如，dc。Column1(5)。</span><span class="sxs-lookup"><span data-stu-id="48c9a-150">User functions that represent set operations on the **DataConnection**; for example, dc.Column1(5).</span></span>  
  
-   <span data-ttu-id="48c9a-151">函数使用**ObjectReference**到**DataConnection**; 例如，ObjecRef(dc)。</span><span class="sxs-lookup"><span data-stu-id="48c9a-151">Functions that use an **ObjectReference** to the **DataConnection**; for example, ObjecRef(dc).</span></span>  
  
-   <span data-ttu-id="48c9a-152">如果一个或多个函数的自变量是进而，函数调用将成为则将无法翻译;例如，添加 (c1。M (dc。Column1)，5)。</span><span class="sxs-lookup"><span data-stu-id="48c9a-152">If one or more of a function's arguments is untranslatable, the function call becomes untranslatable; for example, Add(c1.M(dc.Column1), 5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c9a-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="48c9a-153">See Also</span></span>  
 [<span data-ttu-id="48c9a-154">业务规则引擎中的数据访问</span><span class="sxs-lookup"><span data-stu-id="48c9a-154">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)