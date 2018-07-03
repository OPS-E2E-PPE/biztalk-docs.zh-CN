---
title: 使用 SQL 适配器与 BizTalk Server 轮询 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef9a4b4-552d-4552-b318-1deab506bad9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 971de39bff2149b1b6bdb5d20d6e8b721821a8ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996438"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a><span data-ttu-id="93a70-102">使用 SQL 适配器与 BizTalk Server 轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="93a70-102">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>
<span data-ttu-id="93a70-103">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收基于轮询的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="93a70-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive polling-based data-changed messages from SQL Server.</span></span> <span data-ttu-id="93a70-104">可以指定适配器轮询数据库将执行的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="93a70-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="93a70-105">轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。</span><span class="sxs-lookup"><span data-stu-id="93a70-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="93a70-106">根据接收轮询消息的类型，该适配器公开轮询的三种不同的方式：</span><span class="sxs-lookup"><span data-stu-id="93a70-106">Based on the type of polling message received, the adapter exposes three different ways of polling:</span></span>  
  
- <span data-ttu-id="93a70-107">**轮询**。</span><span class="sxs-lookup"><span data-stu-id="93a70-107">**Polling**.</span></span> <span data-ttu-id="93a70-108">此操作将返回一个数据集作为轮询消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="93a70-108">This operation returns a data set as part of the polling message.</span></span> <span data-ttu-id="93a70-109">在设计时，轮询的数据库对象的架构不可用。</span><span class="sxs-lookup"><span data-stu-id="93a70-109">At design time, the schema of the database object being polled is not available.</span></span> <span data-ttu-id="93a70-110">相反，架构是可作为在运行时轮询消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="93a70-110">Instead, the schema is available as part of the polling message during run time.</span></span>  
  
- <span data-ttu-id="93a70-111">**TypedPolling**。</span><span class="sxs-lookup"><span data-stu-id="93a70-111">**TypedPolling**.</span></span> <span data-ttu-id="93a70-112">此操作将返回强类型的轮询消息。</span><span class="sxs-lookup"><span data-stu-id="93a70-112">This operation returns a strongly-typed polling message.</span></span> <span data-ttu-id="93a70-113">在设计时的数据库对象的架构是也可用。</span><span class="sxs-lookup"><span data-stu-id="93a70-113">At design time, the schema of the database object is also available.</span></span> <span data-ttu-id="93a70-114">必须使用此操作用于轮询如果你想要将映射到另一个架构，可能是用于另一操作轮询消息中的某些元素。</span><span class="sxs-lookup"><span data-stu-id="93a70-114">You must use this operation for polling if you want to map certain elements from the polling message to another schema, which could be for another operation.</span></span>  
  
- <span data-ttu-id="93a70-115">**XmlPolling**。</span><span class="sxs-lookup"><span data-stu-id="93a70-115">**XmlPolling**.</span></span> <span data-ttu-id="93a70-116">此操作将返回作为 XML 消息轮询消息。</span><span class="sxs-lookup"><span data-stu-id="93a70-116">This operation returns the polling message as an XML message.</span></span> <span data-ttu-id="93a70-117">如果你想要使用的 SELECT 语句或使用 FOR XML 子句以 XML 消息形式返回数据的存储的过程，则必须使用此操作。</span><span class="sxs-lookup"><span data-stu-id="93a70-117">You must use this operation if you want to use SELECT statements or stored procedures that use the FOR XML clause to return data as XML messages.</span></span> <span data-ttu-id="93a70-118">有关 FOR XML 子句的详细信息，请参阅[FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93a70-118">For more information about the FOR XML clause, see [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx).</span></span> 
  
  <span data-ttu-id="93a70-119">有关这些轮询操作的详细信息，请参阅[支持的轮询](https://msdn.microsoft.com/library/dd788416.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93a70-119">For more information about these polling operations, see [Support for Polling](https://msdn.microsoft.com/library/dd788416.aspx).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93a70-120">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]允许适配器客户端有多个轮询或 TypedPolling 操作相同的数据库或表的单个 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="93a70-120">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to have a single BizTalk application with more than one Polling or TypedPolling operations for the same database or table.</span></span> <span data-ttu-id="93a70-121">若要支持这种方案，该适配器包括唯一 ID- **InboundID**— 连接 URI 中。</span><span class="sxs-lookup"><span data-stu-id="93a70-121">To support such a scenario, the adapter includes a unique ID— **InboundID**—in the connection URI.</span></span> <span data-ttu-id="93a70-122">此 ID，当添加到连接 URI，使其唯一的从而支持在单个 BizTalk 应用程序中的多个轮询操作。</span><span class="sxs-lookup"><span data-stu-id="93a70-122">This ID, when added to the connection URI, makes it unique, thereby enabling multiple polling operations in a single BizTalk application.</span></span>  
  
 <span data-ttu-id="93a70-123">在本部分中的主题提供有关如何在 BizTalk 应用程序中使用轮询和 TypedPolling，XmlPolling 说明。</span><span class="sxs-lookup"><span data-stu-id="93a70-123">The topics in this section provide instructions on how to use Polling, TypedPolling, and XmlPolling in a BizTalk application.</span></span> <span data-ttu-id="93a70-124">本部分还提供了有关如何使用信息**InboundID**连接属性。</span><span class="sxs-lookup"><span data-stu-id="93a70-124">This section also provides information about how to use the **InboundID** connection property.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93a70-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="93a70-125">In This Section</span></span>  
  
-   [<span data-ttu-id="93a70-126">使用 BizTalk Server 从 SQL Server 接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="93a70-126">Receive Polling-based Data-changed Messages from SQL Server by using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="93a70-127">从 SQL Server 使用 BizTalk Server 接收强类型基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="93a70-127">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [<span data-ttu-id="93a70-128">从 SQL 使用 BizTalk Server 接收轮询消息使用 SELECT 语句与 FOR XML 子句</span><span class="sxs-lookup"><span data-stu-id="93a70-128">Receive Polling Messages Using SELECT Statements with FOR XML Clause from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="93a70-129">从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口</span><span class="sxs-lookup"><span data-stu-id="93a70-129">Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a><span data-ttu-id="93a70-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="93a70-130">See Also</span></span>  
[<span data-ttu-id="93a70-131">使用 SQL 适配器开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="93a70-131">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)