---
title: 使用数据连接和 TypedDataTable |Microsoft 文档
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
ms.openlocfilehash: 2b5a0a490023d77676cc5d156ad5126ad5d7d6c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287541"
---
# <a name="using-dataconnection-and-typeddatatable"></a><span data-ttu-id="9636d-102">使用数据连接和 TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="9636d-102">Using DataConnection and TypedDataTable</span></span>
<span data-ttu-id="9636d-103">在许多情况下，使用**该组**提供更好的性能和使用较少的内存比使用**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="9636d-103">In many scenarios, using **DataConnection** provides better performance and consumes less memory than using **TypedDataTable**.</span></span> <span data-ttu-id="9636d-104">但是， **TypedDataTable**可能要求在某些情况下，由于某些限制使用**该组**。</span><span class="sxs-lookup"><span data-stu-id="9636d-104">However, **TypedDataTable** may be required in some cases because of certain restrictions on using **DataConnection**.</span></span> <span data-ttu-id="9636d-105">在某些其他情况下，使用**TypedDataTable**可能会产生更好的性能比使用**该组**。</span><span class="sxs-lookup"><span data-stu-id="9636d-105">In some other cases, using **TypedDataTable** may yield better performance than using **DataConnection**.</span></span> <span data-ttu-id="9636d-106">本主题介绍了在选择正确的方法时应考虑的条件和因素。</span><span class="sxs-lookup"><span data-stu-id="9636d-106">This topic describes the criteria and factors that you should consider for choosing the right approach.</span></span>  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a><span data-ttu-id="9636d-107">何时使用 TypedDataTable 而不是 DataConnection</span><span class="sxs-lookup"><span data-stu-id="9636d-107">When to use TypedDataTable instead of DataConnection</span></span>  
 <span data-ttu-id="9636d-108">在以下情况下使用 TypedDataTable 而不是 DataConnection：</span><span class="sxs-lookup"><span data-stu-id="9636d-108">Use TypedDataTable instead of DataConnection in the following instances:</span></span>  
  
-   <span data-ttu-id="9636d-109">需要更改数据，但表没有主键。</span><span class="sxs-lookup"><span data-stu-id="9636d-109">Data changes need to be made but the table does not have a primary key.</span></span> <span data-ttu-id="9636d-110">若要使用的数据更改**该组**，主密钥是必需的。</span><span class="sxs-lookup"><span data-stu-id="9636d-110">To make data changes by using **DataConnection**, a primary key is required.</span></span> <span data-ttu-id="9636d-111">因此，如果没有主键， **TypedDataTable**是唯一可行方法。</span><span class="sxs-lookup"><span data-stu-id="9636d-111">Therefore, if there is no primary key, **TypedDataTable** is the only viable approach.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9636d-112">规则引擎仅更新内存中的值**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="9636d-112">The rule engine only updates the values in memory for a **TypedDataTable**.</span></span> <span data-ttu-id="9636d-113">是否永久保存更改由调用方决定。</span><span class="sxs-lookup"><span data-stu-id="9636d-113">It is up to the caller to make those changes permanent.</span></span>  
  
-   <span data-ttu-id="9636d-114">选择性很高，这意味着，表中大部分行都将通过按规则条件指定的测试。</span><span class="sxs-lookup"><span data-stu-id="9636d-114">Selectivity is high, which means that a large percentage of rows in the table will pass the tests specified as rule conditions.</span></span> <span data-ttu-id="9636d-115">在这种情况下，**该组**不提供很大的收益，它可能执行不如**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="9636d-115">In this case, **DataConnection** does not provide much benefit and it may perform worse than **TypedDataTable**.</span></span>  
  
-   <span data-ttu-id="9636d-116">表非常小，通常包含的行数少于 500 行。</span><span class="sxs-lookup"><span data-stu-id="9636d-116">The table is small, typically, a table that contains fewer than 500 rows.</span></span> <span data-ttu-id="9636d-117">请注意，此数目可大可小，具体数值由规则形状和可用于规则引擎的内存来决定。</span><span class="sxs-lookup"><span data-stu-id="9636d-117">Note that this number could be larger or smaller depending on the rule shape and the memory available to the rule engine.</span></span>  
  
-   <span data-ttu-id="9636d-118">在规则集中预计存在规则链接行为。</span><span class="sxs-lookup"><span data-stu-id="9636d-118">Rule-chaining behavior is expected in a rule set.</span></span> <span data-ttu-id="9636d-119">调用**更新**函数上**该组**不受支持，但你无法调用**DataConnection.Update**规则使用一个帮助器方法中。</span><span class="sxs-lookup"><span data-stu-id="9636d-119">Calling the **Update** function on a **DataConnection** is not supported, but you could invoke **DataConnection.Update** in a rule using a helper method.</span></span> <span data-ttu-id="9636d-120">当规则链接是必需的**TypedDataTable**是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="9636d-120">When rule chaining is required, **TypedDataTable** is a better choice.</span></span>  
  
-   <span data-ttu-id="9636d-121">表中一个或多个列包含大量规则不需要的数据。</span><span class="sxs-lookup"><span data-stu-id="9636d-121">One or more columns in the table hold a very large amount of data that is not required by the rules.</span></span> <span data-ttu-id="9636d-122">例如，图像数据库。图像数据库中的各列包含图像（大量数据）、名称、日期等信息。</span><span class="sxs-lookup"><span data-stu-id="9636d-122">An example is an image database, where the columns hold the image (large amount of data), name, date, and so on.</span></span> <span data-ttu-id="9636d-123">如果不需要图像，则最好只选择规则所需的列。</span><span class="sxs-lookup"><span data-stu-id="9636d-123">If the image is not required, it may be better to select only the columns needed by the rules.</span></span> <span data-ttu-id="9636d-124">例如，例如"选择名称、 日期表"将查询可以是比使用效率更高**该组**。</span><span class="sxs-lookup"><span data-stu-id="9636d-124">For example, issuing a query such as "SELECT Name, Date from TABLE" can be more efficient than using **DataConnection**.</span></span>  
  
-   <span data-ttu-id="9636d-125">如果多个规则需要或更新相同的数据库行，使用**TypedDataTable**，该行处于共享状态之间的所有规则，以及条件是否相同 (例如，Table.Column = = 5)，可以优化条件求值。</span><span class="sxs-lookup"><span data-stu-id="9636d-125">If many rules need or update the same database row, using a **TypedDataTable**, the row is shared between all rules, and if the condition is the same (for example, Table.Column == 5), the condition evaluation can be optimized.</span></span> <span data-ttu-id="9636d-126">与**该组**，一般情况下，为每个规则，以使用生成查询**该组**。</span><span class="sxs-lookup"><span data-stu-id="9636d-126">With a **DataConnection**, in general, a query is generated for each rule that uses the **DataConnection**.</span></span> <span data-ttu-id="9636d-127">尽管行是重复使用的（如果表具有主键），但仍需要生成多个查询，每次都获取相同的数据。</span><span class="sxs-lookup"><span data-stu-id="9636d-127">Although the rows are reused (if the table has a primary key), multiple queries could be generated to get the same data each time.</span></span>  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a><span data-ttu-id="9636d-128">何时使用 DataConnection 而不是 TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="9636d-128">When to use DataConnection instead of TypedDataTable</span></span>  
 <span data-ttu-id="9636d-129">在以下情况下使用 DataConnection 而不是 TypedDataTable：</span><span class="sxs-lookup"><span data-stu-id="9636d-129">Use DataConnection instead of TypedDataTable in the following instances:</span></span>  
  
-   <span data-ttu-id="9636d-130">表中包含大量行，但选择性很低；也就是说，只有少数行满足规则条件。</span><span class="sxs-lookup"><span data-stu-id="9636d-130">The table contains a large number of rows, but selectivity is low—only a small percentage of rows will satisfy the rule conditions.</span></span>  
  
-   <span data-ttu-id="9636d-131">只有一个数据库表很大；在规则中使用的其他所有对象都具有数量很少的实例。</span><span class="sxs-lookup"><span data-stu-id="9636d-131">Only one database table is large; all other objects used in the rule have a small number of instances.</span></span> <span data-ttu-id="9636d-132">在最差的情况下，对数据库执行的查询数等于在规则中使用的其他所有实例的乘积。</span><span class="sxs-lookup"><span data-stu-id="9636d-132">In the worst case, the number of queries executed against the database is equal to the product of all the other instances used in the rule.</span></span>  
  
-   <span data-ttu-id="9636d-133">规则仅由连接条件构成，并且在这些规则中使用非数据库表的对象。</span><span class="sxs-lookup"><span data-stu-id="9636d-133">Rules consist exclusively of conjunctive conditions and objects other than database table are used in these rules.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9636d-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9636d-134">See Also</span></span>  
 [<span data-ttu-id="9636d-135">业务规则引擎中的数据访问</span><span class="sxs-lookup"><span data-stu-id="9636d-135">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)