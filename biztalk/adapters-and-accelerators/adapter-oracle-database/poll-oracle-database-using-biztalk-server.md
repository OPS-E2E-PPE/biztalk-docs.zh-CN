---
title: 使用 BizTalk Server 轮询 Oracle 数据库 |Microsoft Docs
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
ms.openlocfilehash: 31a4a7d7afe372c6334219ec8cdf84a3e43aef65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376271"
---
# <a name="poll-oracle-database-using-biztalk-server"></a><span data-ttu-id="de9b5-102">使用 BizTalk Server 轮询 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="de9b5-102">Poll Oracle Database using BizTalk Server</span></span>
<span data-ttu-id="de9b5-103">你可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]从 Oracle 数据库接收基于轮询的消息。</span><span class="sxs-lookup"><span data-stu-id="de9b5-103">You can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive polling-based messages from Oracle database.</span></span> <span data-ttu-id="de9b5-104">适配器提供轮询 Oracle 数据库的两种的方法：</span><span class="sxs-lookup"><span data-stu-id="de9b5-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
- <span data-ttu-id="de9b5-105">**使用 SELECT 语句**。</span><span class="sxs-lookup"><span data-stu-id="de9b5-105">**Using SELECT statements**.</span></span> <span data-ttu-id="de9b5-106">可以指定一个简单的 SELECT 语句来轮询的表和 Oracle 数据库中的视图。</span><span class="sxs-lookup"><span data-stu-id="de9b5-106">You can specify a simple SELECT statement to poll the tables and views in the Oracle database.</span></span> <span data-ttu-id="de9b5-107">适配器执行 SELECT 语句指定的时间间隔，并将结果返回到适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="de9b5-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
- <span data-ttu-id="de9b5-108">**使用存储的过程、 函数或过程或函数的包中**。</span><span class="sxs-lookup"><span data-stu-id="de9b5-108">**Using stored procedures, functions, or procedures or functions within a package**.</span></span> <span data-ttu-id="de9b5-109">您可以指定存储的过程、 函数或过程或函数来轮询 Oracle 数据库的包中。</span><span class="sxs-lookup"><span data-stu-id="de9b5-109">You can specify a stored procedure, function, or procedure or function within a package to poll the Oracle database.</span></span> <span data-ttu-id="de9b5-110">适配器在指定的时间间隔执行的请求消息并将结果返回到适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="de9b5-110">The adapter executes the request message at specified intervals and returns the result to the adapter clients.</span></span>  
  
  <span data-ttu-id="de9b5-111">中的两种方法的主要区别是方式适配器客户端指定用于轮询 Oracle 数据库适配器的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="de9b5-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="de9b5-112">简单的 SELECT 语句的轮询语句的第一种方法时，另一种方法的轮询语句是执行存储的过程、 函数或过程或函数的包中的请求消息。</span><span class="sxs-lookup"><span data-stu-id="de9b5-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the other approach is a request message that executes the stored procedure, function, or procedure or function within a package.</span></span> <span data-ttu-id="de9b5-113">适配器客户端在指定的轮询语句，这两种方法， **PollingStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="de9b5-113">Adapter clients specify the polling statement, for either approach, in the **PollingStatement** binding property.</span></span> <span data-ttu-id="de9b5-114">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="de9b5-114">For more information about the binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
  <span data-ttu-id="de9b5-115">在本部分中的主题说明了如何轮询使用 SELECT 语句和存储的过程、 函数或过程或函数的包中。</span><span class="sxs-lookup"><span data-stu-id="de9b5-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure, function, or procedure or function within a package.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de9b5-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="de9b5-116">In This Section</span></span>  
  
-   [<span data-ttu-id="de9b5-117">使用 SELECT 语句轮询 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="de9b5-117">Poll Oracle Database using the SELECT statement</span></span>](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [<span data-ttu-id="de9b5-118">使用存储的过程、 函数或封装的过程和函数的轮询 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="de9b5-118">Poll Oracle Database Using Stored Procedures, Functions, or Packaged Procedures and Functions</span></span>](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a><span data-ttu-id="de9b5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="de9b5-119">See Also</span></span>  
[<span data-ttu-id="de9b5-120">开发 BizTalk 应用程序使用 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="de9b5-120">Develop BizTalk applications using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)