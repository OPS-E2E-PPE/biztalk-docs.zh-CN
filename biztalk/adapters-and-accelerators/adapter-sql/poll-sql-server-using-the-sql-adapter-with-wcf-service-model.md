---
title: "使用 WCF 服务模型的 SQL 适配器的轮询 SQL Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eef2e868-bd51-4393-b091-f67299b4759d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20d0ab576e5feddb0b5f3e867ca549a45bb2af97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="poll-sql-server-using-the-sql-adapter-with-wcf-service-model"></a><span data-ttu-id="a26bf-102">使用 WCF 服务模型的 SQL 适配器的轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="a26bf-102">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>
<span data-ttu-id="a26bf-103">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收基于轮询的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="a26bf-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive polling-based data-changed messages from SQL Server.</span></span> <span data-ttu-id="a26bf-104">你可以指定适配器执行轮询数据库轮询语句。</span><span class="sxs-lookup"><span data-stu-id="a26bf-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="a26bf-105">轮询语句可以是 SELECT 语句或存储的过程返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="a26bf-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="a26bf-106">基于收到的轮询消息类型，该适配器将公开不同轮询操作：</span><span class="sxs-lookup"><span data-stu-id="a26bf-106">Based on the type of polling message received, the adapter exposes different polling operations:</span></span>  
  
-   <span data-ttu-id="a26bf-107">**轮询**。</span><span class="sxs-lookup"><span data-stu-id="a26bf-107">**Polling**.</span></span> <span data-ttu-id="a26bf-108">此操作将返回数据集作为轮询消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="a26bf-108">This operation returns a data set as part of the polling message.</span></span>  
  
-   <span data-ttu-id="a26bf-109">**TypedPolling**。</span><span class="sxs-lookup"><span data-stu-id="a26bf-109">**TypedPolling**.</span></span> <span data-ttu-id="a26bf-110">此操作将返回强类型的轮询消息。</span><span class="sxs-lookup"><span data-stu-id="a26bf-110">This operation returns a strongly-typed polling message.</span></span>  
  
-   <span data-ttu-id="a26bf-111">**XmlPolling**。</span><span class="sxs-lookup"><span data-stu-id="a26bf-111">**XmlPolling**.</span></span> <span data-ttu-id="a26bf-112">此操作返回作为 XML 消息的轮询消息。</span><span class="sxs-lookup"><span data-stu-id="a26bf-112">This operation returns the polling message as an XML message.</span></span> <span data-ttu-id="a26bf-113">如果你想要使用的 SELECT 语句或使用 FOR XML 子句以 XML 消息形式返回数据的存储的过程，你必须使用此操作。</span><span class="sxs-lookup"><span data-stu-id="a26bf-113">You must use this operation if you want to use SELECT statements or stored procedures that use the FOR XML clause to return data as XML messages.</span></span> <span data-ttu-id="a26bf-114">[FOR XML 子句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)提供了详细的信息。</span><span class="sxs-lookup"><span data-stu-id="a26bf-114">[FOR XML clause](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server) provides more info.</span></span> 
  
 <span data-ttu-id="a26bf-115">有关这些轮询操作的详细信息，请参阅[轮询在 SQL 服务器上使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a26bf-115">For more information about these polling operations, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a26bf-116">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器的客户端需要具有相同的数据库或表的多个轮询或 TypedPolling 操作的单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="a26bf-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to have a single application with more than one Polling or TypedPolling operations for the same database or table.</span></span> <span data-ttu-id="a26bf-117">若要支持这种方案，该适配器包括一个唯一的 ID- **InboundID**-连接 URI 中。</span><span class="sxs-lookup"><span data-stu-id="a26bf-117">To support such a scenario, the adapter includes a unique ID— **InboundID**—in the connection URI.</span></span> <span data-ttu-id="a26bf-118">此 ID，当添加到连接 URI，使其唯一的从而支持在单个应用程序中的多个轮询操作。</span><span class="sxs-lookup"><span data-stu-id="a26bf-118">This ID, when added to the connection URI, makes it unique, thereby enabling multiple polling operations in a single application.</span></span>  
  
 <span data-ttu-id="a26bf-119">本部分中的主题提供有关如何在.NET 应用程序中使用轮询和 TypedPolling 操作的说明。</span><span class="sxs-lookup"><span data-stu-id="a26bf-119">The topics in this section provide instructions on how to use both Polling and TypedPolling operations in a .NET application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a26bf-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="a26bf-120">In This Section</span></span>  
  
-   [<span data-ttu-id="a26bf-121">使用 WCF 服务模型从 SQL Server 接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="a26bf-121">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)  
  
-   [<span data-ttu-id="a26bf-122">使用 WCF 服务模型从 SQL Server 接收强类型基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="a26bf-122">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="a26bf-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a26bf-123">See Also</span></span>  
[<span data-ttu-id="a26bf-124">开发 SQL 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="a26bf-124">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)