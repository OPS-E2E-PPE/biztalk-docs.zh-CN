---
title: "开发 BizTalk 应用程序使用的 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5471f28e-bce1-4295-b56d-954690e60749
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9963764a298246c5a236d10b6010feee8497278f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-sql-adapter"></a><span data-ttu-id="5198c-102">开发使用 SQL 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5198c-102">Develop BizTalk applications using the SQL adapter</span></span>
<span data-ttu-id="5198c-103">开发 BizTalk 应用程序涉及到创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="5198c-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate XML schema.</span></span> <span data-ttu-id="5198c-104">一旦你已生成架构，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程，以发送和接收符合生成架构的消息。</span><span class="sxs-lookup"><span data-stu-id="5198c-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="5198c-105">CBR 可以用于的方案发送到 SQL Server 的消息不需要任何密集型处理。</span><span class="sxs-lookup"><span data-stu-id="5198c-105">CBR can be used in scenarios where the messages being sent to SQL Server do not require any intensive processing.</span></span> <span data-ttu-id="5198c-106">例如，如果你知道接收端口，将收到仅特定类型的消息，你可以发送端口相匹配筛选器表达式与发送端口将消息路由到添加筛选器。</span><span class="sxs-lookup"><span data-stu-id="5198c-106">For example, if you know that the receive port will receive messages only of a certain type, you can add a filter to the send port to route messages that match the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="5198c-107">在 BizTalk 业务流程中创建发送和接收端口发送和接收消息，并从[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这反过来将消息发送到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5198c-107">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5198c-108">本部分提供有关使用 BizTalk 业务流程执行对 SQL Server 使用的操作的信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5198c-108">This section provides information about using BizTalk orchestrations to perform operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="5198c-109">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]反过来使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这可以与的 WCF 绑定进行交互。</span><span class="sxs-lookup"><span data-stu-id="5198c-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5198c-110">若要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，始终必须设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="5198c-110">To use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="5198c-111">有关如何设置绑定属性的信息，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5198c-111">For information about how to set binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5198c-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="5198c-112">In This Section</span></span>  
  
-   [<span data-ttu-id="5198c-113">创建 SQL 应用程序使用的 SQL 适配器的先决条件</span><span class="sxs-lookup"><span data-stu-id="5198c-113">Prerequisites to create SQL applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md) 
  
-   [<span data-ttu-id="5198c-114">开发具有 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="5198c-114">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md) 
  
-   [<span data-ttu-id="5198c-115">插入、 更新、 删除和选择表和视图与 SQL 适配器上的操作</span><span class="sxs-lookup"><span data-stu-id="5198c-115">Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="5198c-116">在上运行操作表和视图使用使用 SQL 适配器的大型数据类型</span><span class="sxs-lookup"><span data-stu-id="5198c-116">Run Operations on Tables and Views with Large Data Types using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="5198c-117">在 SQL Server 中执行存储的过程，通过使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5198c-117">Execute Stored Procedures in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="5198c-118">执行与单个 XML 参数的存储的过程</span><span class="sxs-lookup"><span data-stu-id="5198c-118">Execute Stored Procedures With a Single XML Parameter</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)  
  
-   [<span data-ttu-id="5198c-119">执行存储过程具有 FOR XML 子句中使用 BizTalk server 的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="5198c-119">Execute Stored Procedures Having a FOR XML Clause in SQL Server using BizTalk server</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="5198c-120">使用 BizTalk Server 中运行 SQL Server 上的复合操作</span><span class="sxs-lookup"><span data-stu-id="5198c-120">Run Composite Operations on SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="5198c-121">使用 BizTalk Server 调用 SQL Server 中的标量函数</span><span class="sxs-lookup"><span data-stu-id="5198c-121">Invoke Scalar Functions in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="5198c-122">使用 BizTalk Server 调用 SQL Server 中的表值函数</span><span class="sxs-lookup"><span data-stu-id="5198c-122">Invoke Table-Valued Functions in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md) 
  
-   [<span data-ttu-id="5198c-123">使用 BizTalk Server 中执行 ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作</span><span class="sxs-lookup"><span data-stu-id="5198c-123">Performing ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="5198c-124">与 BizTalk Server 使用的 SQL 适配器轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="5198c-124">Polling SQL Server by Using the SQL Adapter with BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)  
  
-   [<span data-ttu-id="5198c-125">使用 BizTalk Server 接收 SQL 查询通知</span><span class="sxs-lookup"><span data-stu-id="5198c-125">Receive SQL Query Notifications by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="5198c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5198c-126">See Also</span></span>  
[<span data-ttu-id="5198c-127">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="5198c-127">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)