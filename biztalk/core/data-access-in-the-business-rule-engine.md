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
# <a name="data-access-in-the-business-rule-engine"></a><span data-ttu-id="7f7db-102">业务规则引擎中的数据访问</span><span class="sxs-lookup"><span data-stu-id="7f7db-102">Data Access in the Business Rule Engine</span></span>
<span data-ttu-id="7f7db-103">规则引擎本身只支持 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="7f7db-103">The rule engine supports only .NET objects natively.</span></span> <span data-ttu-id="7f7db-104">若要处理来自数据库的数据，则可直接使用 ADO.NET 对象，但该引擎还提供了某些助手类以简化根据规则使用数据库数据的过程。</span><span class="sxs-lookup"><span data-stu-id="7f7db-104">To handle data from a database, you can use the ADO.NET objects directly, but the engine provides some helper classes to simplify the use of database data from rules.</span></span> <span data-ttu-id="7f7db-105">规则引擎通过公开三个数据库相关的类型来扩展它的支持： **TypedDataRow**， **TypedDataTable**，和**该组**。</span><span class="sxs-lookup"><span data-stu-id="7f7db-105">The rule engine extends its support by exposing three database-related types: **TypedDataRow**, **TypedDataTable**, and **DataConnection**.</span></span> <span data-ttu-id="7f7db-106">本部分将介绍这些助手类，提供有关每种类型应在何时使用的建议，以及讨论在使用这些类时对性能所造成的影响。</span><span class="sxs-lookup"><span data-stu-id="7f7db-106">This section describes these helper classes, gives recommendations about when to use each type, and discusses some performance implications when using them.</span></span>  
  
 <span data-ttu-id="7f7db-107">助手类如下所示：</span><span class="sxs-lookup"><span data-stu-id="7f7db-107">The helper classes are as follows:</span></span>  
  
-   <span data-ttu-id="7f7db-108">**TypedDataRow。**</span><span class="sxs-lookup"><span data-stu-id="7f7db-108">**TypedDataRow.**</span></span> <span data-ttu-id="7f7db-109">通过使用 ADO.NET 的引用构造**DataRow**实例。</span><span class="sxs-lookup"><span data-stu-id="7f7db-109">Constructed by using a reference to an ADO.NET **DataRow** instance.</span></span> <span data-ttu-id="7f7db-110">**TypedDataRow**是从一个或少量的特定表中的行的数据以便仅处理的规则的一个明显选项。</span><span class="sxs-lookup"><span data-stu-id="7f7db-110">The **TypedDataRow** is an obvious choice for rules that only deal with data from one or a small number of rows from a particular table.</span></span>  
  
-   <span data-ttu-id="7f7db-111">**TypedDataTable。**</span><span class="sxs-lookup"><span data-stu-id="7f7db-111">**TypedDataTable.**</span></span> <span data-ttu-id="7f7db-112">按原义的集合**TypedDataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="7f7db-112">Literally a collection of **TypedDataRow** objects.</span></span> <span data-ttu-id="7f7db-113">数据库表中的每一行将包装为**TypedDataRow**和由规则引擎对声明到工作内存。</span><span class="sxs-lookup"><span data-stu-id="7f7db-113">Each row in the database table will be wrapped as a **TypedDataRow** and asserted into the working memory by the rule engine.</span></span>  
  
     <span data-ttu-id="7f7db-114">A **TypedDataTable**需要内存中 ADO.NET **DataTable**，可能是性能系统开销，如果此特定**DataTable**包含大量的行。</span><span class="sxs-lookup"><span data-stu-id="7f7db-114">A **TypedDataTable** requires an in-memory ADO.NET **DataTable**, which can be a performance overhead if this particular **DataTable** contains a very large number of rows.</span></span> <span data-ttu-id="7f7db-115">如果少量的数据库表中的行相关，且你可以确定之前调用的规则，使用这些行**DataTable**，否则使用**TypedDataRow**。假设条件是高 DataTable 中的行数是相关的规则。</span><span class="sxs-lookup"><span data-stu-id="7f7db-115">If a small number of rows in the database table is relevant and you can determine these rows prior to calling the rules, use a **DataTable**, otherwise use **TypedDataRow**.The assumption is that a high number of rows in the DataTable are relevant to the rules.</span></span>  
  
-   <span data-ttu-id="7f7db-116">**数据连接。**</span><span class="sxs-lookup"><span data-stu-id="7f7db-116">**DataConnection.**</span></span> <span data-ttu-id="7f7db-117">表示通过数据库连接访问的数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="7f7db-117">Represents a table in a database accessed through a database connection.</span></span> <span data-ttu-id="7f7db-118">之间的差异**该组**和**TypedDataTable**在于，除了数据集名称和表名**该组**需要一个可用数据库连接和 （可选） 数据库事务上下文。</span><span class="sxs-lookup"><span data-stu-id="7f7db-118">The difference between **DataConnection** and **TypedDataTable** is that in addition to the dataset name and table name, **DataConnection** requires a usable database connection and optionally a database transaction context.</span></span>  
  
     <span data-ttu-id="7f7db-119">使用规则中使用的某些或所有谓词**该组**将成为对数据库连接的查询约束的一部分。</span><span class="sxs-lookup"><span data-stu-id="7f7db-119">Some or all predicates used in rules with the **DataConnection** will become part of query constraints against the database connection.</span></span> <span data-ttu-id="7f7db-120">从数据库中检索只满足查询约束的行，并供引擎使用。</span><span class="sxs-lookup"><span data-stu-id="7f7db-120">Only rows that satisfy the query constraints will be retrieved from the database and used by the engine.</span></span> <span data-ttu-id="7f7db-121">此机制提供更好的性能和使用较少的内存比持有非常大**DataTable**在内存中。</span><span class="sxs-lookup"><span data-stu-id="7f7db-121">This mechanism provides better performance and consumes less memory than holding a very large **DataTable** in memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f7db-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="7f7db-122">In This Section</span></span>  
  
-   [<span data-ttu-id="7f7db-123">使用数据连接时的注意事项</span><span class="sxs-lookup"><span data-stu-id="7f7db-123">Considerations When Using DataConnection</span></span>](../core/considerations-when-using-dataconnection.md)  
  
-   [<span data-ttu-id="7f7db-124">使用数据连接和 TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="7f7db-124">Using DataConnection and TypedDataTable</span></span>](../core/using-dataconnection-and-typeddatatable.md)