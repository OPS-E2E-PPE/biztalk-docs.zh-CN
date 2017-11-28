---
title: "轮询 SQL Server 与 BizTalk Server 中使用 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eef9a4b4-552d-4552-b318-1deab506bad9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e631a966ffee632e6c866a962c4fe47b2f1025
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a><span data-ttu-id="9e9a2-102">与 BizTalk Server 中使用 SQL 适配器的轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e9a2-102">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>
<span data-ttu-id="9e9a2-103">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收基于轮询的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive polling-based data-changed messages from SQL Server.</span></span> <span data-ttu-id="9e9a2-104">你可以指定适配器执行轮询数据库轮询语句。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="9e9a2-105">轮询语句可以是 SELECT 语句或存储的过程返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="9e9a2-106">基于收到的轮询消息类型，该适配器将公开轮询的三种不同的方式：</span><span class="sxs-lookup"><span data-stu-id="9e9a2-106">Based on the type of polling message received, the adapter exposes three different ways of polling:</span></span>  
  
-   <span data-ttu-id="9e9a2-107">**轮询**。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-107">**Polling**.</span></span> <span data-ttu-id="9e9a2-108">此操作将返回数据集作为轮询消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-108">This operation returns a data set as part of the polling message.</span></span> <span data-ttu-id="9e9a2-109">在设计时，轮询的数据库对象的架构不可用。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-109">At design time, the schema of the database object being polled is not available.</span></span> <span data-ttu-id="9e9a2-110">相反，架构是可用在运行时的轮询消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-110">Instead, the schema is available as part of the polling message during run time.</span></span>  
  
-   <span data-ttu-id="9e9a2-111">**TypedPolling**。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-111">**TypedPolling**.</span></span> <span data-ttu-id="9e9a2-112">此操作将返回强类型的轮询消息。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-112">This operation returns a strongly-typed polling message.</span></span> <span data-ttu-id="9e9a2-113">在设计时，数据库对象的架构也会提供。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-113">At design time, the schema of the database object is also available.</span></span> <span data-ttu-id="9e9a2-114">你必须使用此操作对于轮询如果你想要映射到另一个架构，可能是用于另一操作中的轮询消息的某些元素。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-114">You must use this operation for polling if you want to map certain elements from the polling message to another schema, which could be for another operation.</span></span>  
  
-   <span data-ttu-id="9e9a2-115">**XmlPolling**。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-115">**XmlPolling**.</span></span> <span data-ttu-id="9e9a2-116">此操作返回作为 XML 消息的轮询消息。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-116">This operation returns the polling message as an XML message.</span></span> <span data-ttu-id="9e9a2-117">如果你想要使用的 SELECT 语句或使用 FOR XML 子句以 XML 消息形式返回数据的存储的过程，你必须使用此操作。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-117">You must use this operation if you want to use SELECT statements or stored procedures that use the FOR XML clause to return data as XML messages.</span></span> <span data-ttu-id="9e9a2-118">有关 FOR XML 子句的详细信息，请参阅[FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-118">For more information about the FOR XML clause, see [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx).</span></span> 
  
 <span data-ttu-id="9e9a2-119">有关这些轮询操作的详细信息，请参阅[进行轮询的支持](https://msdn.microsoft.com/library/dd788416.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-119">For more information about these polling operations, see [Support for Polling](https://msdn.microsoft.com/library/dd788416.aspx).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e9a2-120">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器的客户端需要具有相同的数据库或表的多个轮询或 TypedPolling 操作的单个 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-120">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to have a single BizTalk application with more than one Polling or TypedPolling operations for the same database or table.</span></span> <span data-ttu-id="9e9a2-121">若要支持这种方案，该适配器包括一个唯一的 ID- **InboundID**-连接 URI 中。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-121">To support such a scenario, the adapter includes a unique ID— **InboundID**—in the connection URI.</span></span> <span data-ttu-id="9e9a2-122">此 ID，当添加到连接 URI，使其唯一的从而支持单个 BizTalk 应用程序中的多个轮询操作。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-122">This ID, when added to the connection URI, makes it unique, thereby enabling multiple polling operations in a single BizTalk application.</span></span>  
  
 <span data-ttu-id="9e9a2-123">本部分中的主题提供有关如何在 BizTalk 应用程序中使用轮询、 TypedPolling 和 XmlPolling 的说明。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-123">The topics in this section provide instructions on how to use Polling, TypedPolling, and XmlPolling in a BizTalk application.</span></span> <span data-ttu-id="9e9a2-124">本部分还提供有关如何使用信息**InboundID**连接属性。</span><span class="sxs-lookup"><span data-stu-id="9e9a2-124">This section also provides information about how to use the **InboundID** connection property.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e9a2-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="9e9a2-125">In This Section</span></span>  
  
-   [<span data-ttu-id="9e9a2-126">使用 BizTalk Server 从 SQL Server 接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="9e9a2-126">Receive Polling-based Data-changed Messages from SQL Server by using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="9e9a2-127">使用 BizTalk Server 从 SQL Server 接收强类型基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="9e9a2-127">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [<span data-ttu-id="9e9a2-128">从 SQL 使用 BizTalk Server 接收轮询消息使用 SELECT 语句与 FOR XML 子句</span><span class="sxs-lookup"><span data-stu-id="9e9a2-128">Receive Polling Messages Using SELECT Statements with FOR XML Clause from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="9e9a2-129">从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口</span><span class="sxs-lookup"><span data-stu-id="9e9a2-129">Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e9a2-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e9a2-130">See Also</span></span>  
[<span data-ttu-id="9e9a2-131">开发使用 SQL 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="9e9a2-131">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)