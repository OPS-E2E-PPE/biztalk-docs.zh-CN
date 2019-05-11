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
# <a name="using-dataconnection-and-typeddatatable"></a><span data-ttu-id="04054-102">使用 TypedDataTable 和 DataConnection</span><span class="sxs-lookup"><span data-stu-id="04054-102">Using DataConnection and TypedDataTable</span></span>
<span data-ttu-id="04054-103">在许多情况下，使用**DataConnection**提供了更好的性能和使用更少的内存比使用**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="04054-103">In many scenarios, using **DataConnection** provides better performance and consumes less memory than using **TypedDataTable**.</span></span> <span data-ttu-id="04054-104">但是， **TypedDataTable**可能要求在某些情况下，由于使用某些限制**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="04054-104">However, **TypedDataTable** may be required in some cases because of certain restrictions on using **DataConnection**.</span></span> <span data-ttu-id="04054-105">在某些其他情况下，使用**TypedDataTable**可能会产生更好的性能比使用**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="04054-105">In some other cases, using **TypedDataTable** may yield better performance than using **DataConnection**.</span></span> <span data-ttu-id="04054-106">本主题介绍的条件和选择正确的方法时应考虑的因素。</span><span class="sxs-lookup"><span data-stu-id="04054-106">This topic describes the criteria and factors that you should consider for choosing the right approach.</span></span>  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a><span data-ttu-id="04054-107">何时使用 TypedDataTable 而不是 DataConnection</span><span class="sxs-lookup"><span data-stu-id="04054-107">When to use TypedDataTable instead of DataConnection</span></span>  
 <span data-ttu-id="04054-108">在以下情况下，而不是 DataConnection 中使用 TypedDataTable:</span><span class="sxs-lookup"><span data-stu-id="04054-108">Use TypedDataTable instead of DataConnection in the following instances:</span></span>  
  
-   <span data-ttu-id="04054-109">不需要进行数据更改，但表没有主键。</span><span class="sxs-lookup"><span data-stu-id="04054-109">Data changes need to be made but the table does not have a primary key.</span></span> <span data-ttu-id="04054-110">若要使用做出数据更改**DataConnection**，主要密钥是必需的。</span><span class="sxs-lookup"><span data-stu-id="04054-110">To make data changes by using **DataConnection**, a primary key is required.</span></span> <span data-ttu-id="04054-111">因此，如果有没有主键，则**TypedDataTable**是唯一的可行方法。</span><span class="sxs-lookup"><span data-stu-id="04054-111">Therefore, if there is no primary key, **TypedDataTable** is the only viable approach.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04054-112">规则引擎只更新在内存中的值**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="04054-112">The rule engine only updates the values in memory for a **TypedDataTable**.</span></span> <span data-ttu-id="04054-113">负责调用方永久保存这些更改。</span><span class="sxs-lookup"><span data-stu-id="04054-113">It is up to the caller to make those changes permanent.</span></span>  
  
-   <span data-ttu-id="04054-114">选择性很高，这意味着大型的表中的行百分比将通过指定为规则条件的测试。</span><span class="sxs-lookup"><span data-stu-id="04054-114">Selectivity is high, which means that a large percentage of rows in the table will pass the tests specified as rule conditions.</span></span> <span data-ttu-id="04054-115">在这种情况下， **DataConnection**不提供很大的收益，其执行比**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="04054-115">In this case, **DataConnection** does not provide much benefit and it may perform worse than **TypedDataTable**.</span></span>  
  
-   <span data-ttu-id="04054-116">表非常小，通常情况下，包含少于 500 行的表。</span><span class="sxs-lookup"><span data-stu-id="04054-116">The table is small, typically, a table that contains fewer than 500 rows.</span></span> <span data-ttu-id="04054-117">请注意，此数目可更大或较小，具体取决于规则形状和可用于规则引擎的内存。</span><span class="sxs-lookup"><span data-stu-id="04054-117">Note that this number could be larger or smaller depending on the rule shape and the memory available to the rule engine.</span></span>  
  
-   <span data-ttu-id="04054-118">在规则集中需要规则链接行为。</span><span class="sxs-lookup"><span data-stu-id="04054-118">Rule-chaining behavior is expected in a rule set.</span></span> <span data-ttu-id="04054-119">调用**更新**函数**DataConnection**不受支持，但你可以调用**DataConnection.Update**在规则中使用的帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="04054-119">Calling the **Update** function on a **DataConnection** is not supported, but you could invoke **DataConnection.Update** in a rule using a helper method.</span></span> <span data-ttu-id="04054-120">必需的规则链接时**TypedDataTable**是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="04054-120">When rule chaining is required, **TypedDataTable** is a better choice.</span></span>  
  
-   <span data-ttu-id="04054-121">表中的一个或多个列包含非常大量的数据不是必需的规则。</span><span class="sxs-lookup"><span data-stu-id="04054-121">One or more columns in the table hold a very large amount of data that is not required by the rules.</span></span> <span data-ttu-id="04054-122">一个示例是一个图像数据库中，各列包含图像 （大量的数据）、 名称、 日期和等等。</span><span class="sxs-lookup"><span data-stu-id="04054-122">An example is an image database, where the columns hold the image (large amount of data), name, date, and so on.</span></span> <span data-ttu-id="04054-123">如果不需要图像，则可能会更好的做法选择仅规则所需的列。</span><span class="sxs-lookup"><span data-stu-id="04054-123">If the image is not required, it may be better to select only the columns needed by the rules.</span></span> <span data-ttu-id="04054-124">例如，发出"SELECT Name，Date from TABLE"之类的查询可能比使用更高效**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="04054-124">For example, issuing a query such as "SELECT Name, Date from TABLE" can be more efficient than using **DataConnection**.</span></span>  
  
-   <span data-ttu-id="04054-125">如果许多规则需要更新同一数据库行，使用**TypedDataTable**，该行处于共享状态之间的所有规则，并且如果条件为相同 (例如 Table.Column = = 5)，可以优化条件评估。</span><span class="sxs-lookup"><span data-stu-id="04054-125">If many rules need or update the same database row, using a **TypedDataTable**, the row is shared between all rules, and if the condition is the same (for example, Table.Column == 5), the condition evaluation can be optimized.</span></span> <span data-ttu-id="04054-126">与**DataConnection**，一般情况下，查询生成的每个规则，以使用**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="04054-126">With a **DataConnection**, in general, a query is generated for each rule that uses the **DataConnection**.</span></span> <span data-ttu-id="04054-127">虽然 （如果表具有主键），行重复使用，可以生成多个查询以获取每次的相同的数据。</span><span class="sxs-lookup"><span data-stu-id="04054-127">Although the rows are reused (if the table has a primary key), multiple queries could be generated to get the same data each time.</span></span>  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a><span data-ttu-id="04054-128">何时使用 DataConnection 而不是 TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="04054-128">When to use DataConnection instead of TypedDataTable</span></span>  
 <span data-ttu-id="04054-129">在以下情况下，而不是 TypedDataTable 使用 DataConnection:</span><span class="sxs-lookup"><span data-stu-id="04054-129">Use DataConnection instead of TypedDataTable in the following instances:</span></span>  
  
-   <span data-ttu-id="04054-130">表中包含大量行，但选择性很低 — 仅少数行满足规则条件。</span><span class="sxs-lookup"><span data-stu-id="04054-130">The table contains a large number of rows, but selectivity is low—only a small percentage of rows will satisfy the rule conditions.</span></span>  
  
-   <span data-ttu-id="04054-131">只有一个数据库表很大;在规则中使用的所有其他对象都有较多的实例。</span><span class="sxs-lookup"><span data-stu-id="04054-131">Only one database table is large; all other objects used in the rule have a small number of instances.</span></span> <span data-ttu-id="04054-132">在最坏的情况下，对数据库执行的查询数等于在规则中使用的所有其他实例的产品。</span><span class="sxs-lookup"><span data-stu-id="04054-132">In the worst case, the number of queries executed against the database is equal to the product of all the other instances used in the rule.</span></span>  
  
-   <span data-ttu-id="04054-133">规则以独占方式包含连接条件，并且这些规则中使用对象，而非数据库表。</span><span class="sxs-lookup"><span data-stu-id="04054-133">Rules consist exclusively of conjunctive conditions and objects other than database table are used in these rules.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04054-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="04054-134">See Also</span></span>  
 [<span data-ttu-id="04054-135">业务规则引擎中的数据访问</span><span class="sxs-lookup"><span data-stu-id="04054-135">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)