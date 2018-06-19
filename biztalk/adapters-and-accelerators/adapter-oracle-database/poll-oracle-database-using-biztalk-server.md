---
title: 使用 BizTalk Server 轮询 Oracle 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c3aef30-956d-4585-b2de-7eebb919fab5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2578d00518a9f1632e690e84db04426575619109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214173"
---
# <a name="poll-oracle-database-using-biztalk-server"></a><span data-ttu-id="325e5-102">使用 BizTalk Server 轮询 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="325e5-102">Poll Oracle Database using BizTalk Server</span></span>
<span data-ttu-id="325e5-103">你可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]从 Oracle 数据库接收基于轮询的消息。</span><span class="sxs-lookup"><span data-stu-id="325e5-103">You can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive polling-based messages from Oracle database.</span></span> <span data-ttu-id="325e5-104">适配器提供轮询 Oracle 数据库的两种的方法：</span><span class="sxs-lookup"><span data-stu-id="325e5-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
-   <span data-ttu-id="325e5-105">**使用 SELECT 语句**。</span><span class="sxs-lookup"><span data-stu-id="325e5-105">**Using SELECT statements**.</span></span> <span data-ttu-id="325e5-106">你可以指定要轮询的表和视图的 Oracle 数据库中的简单 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="325e5-106">You can specify a simple SELECT statement to poll the tables and views in the Oracle database.</span></span> <span data-ttu-id="325e5-107">适配器执行 SELECT 语句指定时间间隔，并将结果返回给适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="325e5-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
-   <span data-ttu-id="325e5-108">**使用存储的过程、 函数或过程或函数在一个包内的**。</span><span class="sxs-lookup"><span data-stu-id="325e5-108">**Using stored procedures, functions, or procedures or functions within a package**.</span></span> <span data-ttu-id="325e5-109">你可以指定存储的过程、 函数或过程或函数在包轮询 Oracle 数据库中。</span><span class="sxs-lookup"><span data-stu-id="325e5-109">You can specify a stored procedure, function, or procedure or function within a package to poll the Oracle database.</span></span> <span data-ttu-id="325e5-110">适配器在指定的时间间隔执行的请求消息，并将结果返回给适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="325e5-110">The adapter executes the request message at specified intervals and returns the result to the adapter clients.</span></span>  
  
 <span data-ttu-id="325e5-111">在两个方法中的关键区别是方式适配器客户端指定适配器使用来轮询 Oracle 数据库的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="325e5-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="325e5-112">第一种方法的轮询语句时简单的 SELECT 语句，另一种方法的轮询语句将是执行存储的过程、 函数或过程或函数在一个包内的请求消息。</span><span class="sxs-lookup"><span data-stu-id="325e5-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the other approach is a request message that executes the stored procedure, function, or procedure or function within a package.</span></span> <span data-ttu-id="325e5-113">适配器客户端在指定的轮询语句，这两种方法， **PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="325e5-113">Adapter clients specify the polling statement, for either approach, in the **PollingStatement** binding property.</span></span> <span data-ttu-id="325e5-114">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="325e5-114">For more information about the binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
 <span data-ttu-id="325e5-115">此部分中的主题提供有关如何轮询使用 SELECT 语句和存储的过程、 函数或过程的说明或函数在一个包内。</span><span class="sxs-lookup"><span data-stu-id="325e5-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure, function, or procedure or function within a package.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="325e5-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="325e5-116">In This Section</span></span>  
  
-   [<span data-ttu-id="325e5-117">使用 SELECT 语句的轮询 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="325e5-117">Poll Oracle Database using the SELECT statement</span></span>](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [<span data-ttu-id="325e5-118">使用存储的过程、 函数或打包的过程和函数的轮询 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="325e5-118">Poll Oracle Database Using Stored Procedures, Functions, or Packaged Procedures and Functions</span></span>](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a><span data-ttu-id="325e5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="325e5-119">See Also</span></span>  
[<span data-ttu-id="325e5-120">开发使用 Oracle 数据库适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="325e5-120">Develop BizTalk applications using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)