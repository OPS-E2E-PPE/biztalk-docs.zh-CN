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
# <a name="data-access-in-the-business-rule-engine"></a><span data-ttu-id="f7d63-102">业务规则引擎中的数据访问</span><span class="sxs-lookup"><span data-stu-id="f7d63-102">Data Access in the Business Rule Engine</span></span>
<span data-ttu-id="f7d63-103">规则引擎本身支持仅限.NET 对象。</span><span class="sxs-lookup"><span data-stu-id="f7d63-103">The rule engine supports only .NET objects natively.</span></span> <span data-ttu-id="f7d63-104">若要处理数据库中的数据，可以使用 ADO.NET 对象直接，但引擎提供了一些帮助器类，以简化从规则的数据库数据的使用。</span><span class="sxs-lookup"><span data-stu-id="f7d63-104">To handle data from a database, you can use the ADO.NET objects directly, but the engine provides some helper classes to simplify the use of database data from rules.</span></span> <span data-ttu-id="f7d63-105">规则引擎通过公开三个与数据库相关的类型来扩展其支持：**TypedDataRow**， **TypedDataTable**，和**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="f7d63-105">The rule engine extends its support by exposing three database-related types: **TypedDataRow**, **TypedDataTable**, and **DataConnection**.</span></span> <span data-ttu-id="f7d63-106">本部分介绍这些帮助器类，提供有关何时使用每种类型的建议并使用它们时讨论一些性能产生影响。</span><span class="sxs-lookup"><span data-stu-id="f7d63-106">This section describes these helper classes, gives recommendations about when to use each type, and discusses some performance implications when using them.</span></span>  
  
 <span data-ttu-id="f7d63-107">帮助程序类如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7d63-107">The helper classes are as follows:</span></span>  
  
-   <span data-ttu-id="f7d63-108">**TypedDataRow.**</span><span class="sxs-lookup"><span data-stu-id="f7d63-108">**TypedDataRow.**</span></span> <span data-ttu-id="f7d63-109">通过使用 ADO.NET 的引用构造**DataRow**实例。</span><span class="sxs-lookup"><span data-stu-id="f7d63-109">Constructed by using a reference to an ADO.NET **DataRow** instance.</span></span> <span data-ttu-id="f7d63-110">**TypedDataRow**是显而易见的选择规则以便仅处理一个或少量的特定表中的行中的数据。</span><span class="sxs-lookup"><span data-stu-id="f7d63-110">The **TypedDataRow** is an obvious choice for rules that only deal with data from one or a small number of rows from a particular table.</span></span>  
  
-   <span data-ttu-id="f7d63-111">**TypedDataTable.**</span><span class="sxs-lookup"><span data-stu-id="f7d63-111">**TypedDataTable.**</span></span> <span data-ttu-id="f7d63-112">按原义的集合**TypedDataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="f7d63-112">Literally a collection of **TypedDataRow** objects.</span></span> <span data-ttu-id="f7d63-113">数据库表中的每一行将包装成**TypedDataRow**和由规则引擎添加到工作内存。</span><span class="sxs-lookup"><span data-stu-id="f7d63-113">Each row in the database table will be wrapped as a **TypedDataRow** and asserted into the working memory by the rule engine.</span></span>  
  
     <span data-ttu-id="f7d63-114">一个**TypedDataTable**需要内存中 ADO.NET **DataTable**，可以是性能开销，如果此特定**DataTable**包含非常大量的行。</span><span class="sxs-lookup"><span data-stu-id="f7d63-114">A **TypedDataTable** requires an in-memory ADO.NET **DataTable**, which can be a performance overhead if this particular **DataTable** contains a very large number of rows.</span></span> <span data-ttu-id="f7d63-115">如果少量的数据库表中的行是相关，并且可以确定这些行在调用规则中，使用之前先**DataTable**，否则，请使用**TypedDataRow**。假设是大量的 DataTable 中的行不相关的规则。</span><span class="sxs-lookup"><span data-stu-id="f7d63-115">If a small number of rows in the database table is relevant and you can determine these rows prior to calling the rules, use a **DataTable**, otherwise use **TypedDataRow**.The assumption is that a high number of rows in the DataTable are relevant to the rules.</span></span>  
  
-   <span data-ttu-id="f7d63-116">**DataConnection.**</span><span class="sxs-lookup"><span data-stu-id="f7d63-116">**DataConnection.**</span></span> <span data-ttu-id="f7d63-117">表示通过数据库连接访问的数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="f7d63-117">Represents a table in a database accessed through a database connection.</span></span> <span data-ttu-id="f7d63-118">之间的差异**DataConnection**并**TypedDataTable**是，除了数据集名称和表名称**DataConnection**需要一个可用数据库连接和 （可选） 在数据库事务上下文。</span><span class="sxs-lookup"><span data-stu-id="f7d63-118">The difference between **DataConnection** and **TypedDataTable** is that in addition to the dataset name and table name, **DataConnection** requires a usable database connection and optionally a database transaction context.</span></span>  
  
     <span data-ttu-id="f7d63-119">与规则中使用的部分或全部谓词**DataConnection**将成为针对数据库连接的查询约束的一部分。</span><span class="sxs-lookup"><span data-stu-id="f7d63-119">Some or all predicates used in rules with the **DataConnection** will become part of query constraints against the database connection.</span></span> <span data-ttu-id="f7d63-120">将从数据库中检索并由引擎使用满足查询约束的行。</span><span class="sxs-lookup"><span data-stu-id="f7d63-120">Only rows that satisfy the query constraints will be retrieved from the database and used by the engine.</span></span> <span data-ttu-id="f7d63-121">此机制提供了更好的性能，并且会占用较少的内存比持有极大型**DataTable**在内存中。</span><span class="sxs-lookup"><span data-stu-id="f7d63-121">This mechanism provides better performance and consumes less memory than holding a very large **DataTable** in memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7d63-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="f7d63-122">In This Section</span></span>  
  
-   [<span data-ttu-id="f7d63-123">使用 DataConnection 的注意事项</span><span class="sxs-lookup"><span data-stu-id="f7d63-123">Considerations When Using DataConnection</span></span>](../core/considerations-when-using-dataconnection.md)  
  
-   [<span data-ttu-id="f7d63-124">使用 TypedDataTable 和 DataConnection</span><span class="sxs-lookup"><span data-stu-id="f7d63-124">Using DataConnection and TypedDataTable</span></span>](../core/using-dataconnection-and-typeddatatable.md)