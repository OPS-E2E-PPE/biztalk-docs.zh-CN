---
title: "接收使用 BizTalk Server 的 SQL 查询通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69444df7-f2ae-4d1a-9b49-817b437517d8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1632bde50a0daf9df22b9c1cfb7aaca8d59fbce7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-sql-query-notifications-using-biztalk-server"></a><span data-ttu-id="77a3d-102">接收使用 BizTalk Server 的 SQL 查询通知</span><span class="sxs-lookup"><span data-stu-id="77a3d-102">Receive SQL Query Notifications using BizTalk Server</span></span>
<span data-ttu-id="77a3d-103">你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以接收通知消息的 SQL Server 表或视图。</span><span class="sxs-lookup"><span data-stu-id="77a3d-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive notification messages for SQL Server tables or views.</span></span> <span data-ttu-id="77a3d-104">你可以指定适配器用于与 SQL Server 通知注册的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="77a3d-104">You can specify a SQL statement that the adapter uses to register for notifications with SQL Server.</span></span> <span data-ttu-id="77a3d-105">通知语句可以是 SELECT 语句或存储的过程返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="77a3d-105">The notification statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="77a3d-106">有关查询通知的详细信息，请参阅"使用查询通知"网址[http://go.microsoft.com/fwlink/?LinkId=122159](http://go.microsoft.com/fwlink/?LinkId=122159)。</span><span class="sxs-lookup"><span data-stu-id="77a3d-106">For more information about query notifications, see “Using Query Notifications” at  [http://go.microsoft.com/fwlink/?LinkId=122159](http://go.microsoft.com/fwlink/?LinkId=122159).</span></span> <span data-ttu-id="77a3d-107">有关可以用于查询通知的查询的信息，请参阅"创建查询的通知"网址[http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160)。</span><span class="sxs-lookup"><span data-stu-id="77a3d-107">For information about queries that can be used for query notifications, see “Creating a Query for Notification” at [http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160).</span></span>  
  
 <span data-ttu-id="77a3d-108">从 SQL Server 接收查询通知是类似于轮询 SQL Server，有一些关键的区别。</span><span class="sxs-lookup"><span data-stu-id="77a3d-108">Receiving query notifications from SQL Server is similar to polling SQL Server, with a few key differences.</span></span> <span data-ttu-id="77a3d-109">差异的列表，请参阅[注意事项接收查询通知使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="77a3d-109">For the list of differences, see [Considerations Receiving Query Notifications Using the SQL adapter](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md).</span></span>  
  
 <span data-ttu-id="77a3d-110">以下是某些情况下，你可以在其中配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 SQL Server 接收通知：</span><span class="sxs-lookup"><span data-stu-id="77a3d-110">Following are some scenarios in which you can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to receive notifications from SQL Server:</span></span>  
  
-   <span data-ttu-id="77a3d-111">适配器客户端获取仅"增量"通知，例如，仅为已对数据库表从上次通知这些更改。</span><span class="sxs-lookup"><span data-stu-id="77a3d-111">Adapter clients get only “incremental” notification, for example, only for those changes that were made to a database table since the last notification.</span></span>  
  
-   <span data-ttu-id="77a3d-112">如果多行插入到数据库表中，适配器客户端可以配置多个接收到的负载平衡接收通知的位置。</span><span class="sxs-lookup"><span data-stu-id="77a3d-112">If many rows are inserted into a database table, the adapter clients can configure multiple receive locations to load-balance receiving notifications.</span></span>  
  
-   <span data-ttu-id="77a3d-113">如果适配器客户端在其接收通知的接收位置出现故障，适配器客户端可以配置的适配器接收位置再次已启动时，就会立即收到通知。</span><span class="sxs-lookup"><span data-stu-id="77a3d-113">If the receive location on which the adapter clients are receiving notifications goes down, the adapter clients can configure the adapter to receive a notification as soon as the receive location is up again.</span></span> <span data-ttu-id="77a3d-114">客户端还必须在其应用程序来处理可能已插入、 更新，或接收位置已关闭时删除的记录中实现的逻辑。</span><span class="sxs-lookup"><span data-stu-id="77a3d-114">The clients must also implement the logic in their application to process the records that may have been inserted, updated, or deleted while the receive location was down.</span></span>  
  
 <span data-ttu-id="77a3d-115">一旦适配器客户端收到的通知消息，他们可以执行特定任务根据收到的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="77a3d-115">Once the adapter clients receive a notification message, they can perform specific tasks based on the kind of notification received.</span></span> <span data-ttu-id="77a3d-116">例如，它执行的任务，如果收到插入通知的一组和另一组任务的如果收到更新通知的方式可以设计 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="77a3d-116">For example, a BizTalk orchestration can be designed in such a way that it performs one set of tasks if an insert notification is received and another set of tasks if an update notification is received.</span></span>  
  
 <span data-ttu-id="77a3d-117">此部分中的主题提供有关如何配置每种方案的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="77a3d-117">The topics in this section provide information about how to configure the adapter for each of these scenarios.</span></span> <span data-ttu-id="77a3d-118">若要开始获取来自 SQL Server 使用的通知[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，你必须指定特定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="77a3d-118">To start getting notifications from SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must specify certain binding properties.</span></span> <span data-ttu-id="77a3d-119">有关如何适配器支持接收消息的详细信息，请参阅[注意事项接收查询通知使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="77a3d-119">For more information about how the adapter supports receiving messages, see [Considerations Receiving Query Notifications Using the SQL adapter](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md).</span></span> <span data-ttu-id="77a3d-120">有关与通知相关的绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="77a3d-120">For more information about the binding properties related to notifications, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="77a3d-121">有关通知消息结构的详细信息，请参阅[查询通知的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="77a3d-121">For more information about the structure of notification messages, see [Message Schemas for Query Notification](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md).</span></span>  
  
 <span data-ttu-id="77a3d-122">您还必须启用查询通知的 SQL Server 上执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="77a3d-122">You must also perform the following tasks on SQL Server to enable query notifications.</span></span>  
  
-   <span data-ttu-id="77a3d-123">你必须为 SQL Server 数据库中启用 Service Broker。</span><span class="sxs-lookup"><span data-stu-id="77a3d-123">You must enable Service Broker for the SQL Server database.</span></span>  
  
-   <span data-ttu-id="77a3d-124">你必须确保适配器客户端具有足够的权限来执行命令以请求通知。</span><span class="sxs-lookup"><span data-stu-id="77a3d-124">You must ensure that the adapter client has the necessary permissions to execute commands to request notification.</span></span>  
  
 <span data-ttu-id="77a3d-125">有关这些任务的详细信息，请参阅"启用查询通知"网址[http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323)。</span><span class="sxs-lookup"><span data-stu-id="77a3d-125">For more information about these tasks, see “Enabling Query Notifications” at [http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77a3d-126">本节内容</span><span class="sxs-lookup"><span data-stu-id="77a3d-126">In This Section</span></span>  
  
-   [<span data-ttu-id="77a3d-127">注意事项接收查询通知使用的 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="77a3d-127">Considerations Receiving Query Notifications Using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="77a3d-128">若要完成 SQL 使用 BizTalk Server 中的特定任务的进程通知消息</span><span class="sxs-lookup"><span data-stu-id="77a3d-128">Process Notification Messages to complete Specific Tasks in SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)  
  
-   [<span data-ttu-id="77a3d-129">从使用 BizTalk Server 的 SQL 查询通知以增量方式接收</span><span class="sxs-lookup"><span data-stu-id="77a3d-129">Receive Query Notifications Incrementally from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)  
  
-   [<span data-ttu-id="77a3d-130">从 SQL 使用 BizTalk Server 接收查询通知上多个接收位置</span><span class="sxs-lookup"><span data-stu-id="77a3d-130">Receive Query Notifications On Multiple Receive Locations from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-on-receive-locations-from-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="77a3d-131">接收查询通知后接收位置分解 SQL 使用 BizTalk Server 中</span><span class="sxs-lookup"><span data-stu-id="77a3d-131">Receive Query Notifications After a Receive Location Breakdown in SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)  
  
## <a name="see-also"></a><span data-ttu-id="77a3d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77a3d-132">See Also</span></span>  
[<span data-ttu-id="77a3d-133">开发使用 SQL 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="77a3d-133">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)