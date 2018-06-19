---
title: 从 SQL 使用 BizTalk Server 接收查询通知上多个接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9afbe98e-8901-417c-a807-8db97fd7a24b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa858483914b8325e9250e1e41f99ae03226f3ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223421"
---
# <a name="receive-query-notifications-on-multiple-receive-locations-from-sql-using-biztalk-server"></a><span data-ttu-id="4690e-102">从 SQL 使用 BizTalk Server 接收查询通知上多个接收位置</span><span class="sxs-lookup"><span data-stu-id="4690e-102">Receive query notifications On Multiple Receive Locations from SQL using BizTalk Server</span></span>
<span data-ttu-id="4690e-103">在同一数据库中假设你有多个接收位置不同的 BizTalk 应用程序配置为接收同一个表 （例如员工） 的查询通知的一部分创建的其中一个方案。</span><span class="sxs-lookup"><span data-stu-id="4690e-103">Consider a scenario where you have multiple receive locations created as part of different BizTalk applications configured to receive query notifications for the same table (e.g. Employee) in the same database.</span></span> <span data-ttu-id="4690e-104">如果上百个记录插入到同一个表中，所有接收位置将都收到通知消息。</span><span class="sxs-lookup"><span data-stu-id="4690e-104">If a hundred records are inserted into the same table, all the receive locations will get the notification message.</span></span> <span data-ttu-id="4690e-105">若要有效地接收通知跨多个接收位置、 可以从 BizTalk 应用程序如果逐个收到通知接收位置的此类的方式调用操作、 其他接收位置不会获取相同的通知。</span><span class="sxs-lookup"><span data-stu-id="4690e-105">To effectively receive notifications across multiple receive locations, you can call operations from your BizTalk application in such a way that if a notification is received by one receive location, the other receive location does not get the same notification.</span></span> <span data-ttu-id="4690e-106">这样，你可以有效地在多个位置上收到的负载平衡通知。</span><span class="sxs-lookup"><span data-stu-id="4690e-106">So, you can effectively load-balance notifications received on multiple locations.</span></span>  
  
 <span data-ttu-id="4690e-107">设置负载平衡接收通知的业务流程所需的任务是与，对于相同[接收查询通知以增量方式从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="4690e-107">The tasks required to set up an orchestration to load-balance receiving notifications are same as that for [Receive Query Notifications Incrementally from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md).</span></span> <span data-ttu-id="4690e-108">本主题列出了唯一两种方法之间的差异。</span><span class="sxs-lookup"><span data-stu-id="4690e-108">This topic lists the only the difference between the two approaches.</span></span>  
  
## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a><span data-ttu-id="4690e-109">在多个负载平衡查询通知接收位置</span><span class="sxs-lookup"><span data-stu-id="4690e-109">Load-Balancing Query Notifications Across Multiple Receive Locations</span></span>  
 <span data-ttu-id="4690e-110">如主题中[接收查询通知以增量方式从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)，通过在已通知的记录上执行 UPDATE 语句配置增量的通知。</span><span class="sxs-lookup"><span data-stu-id="4690e-110">Like in the topic [Receive Query Notifications Incrementally from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md), you configured incremental notifications by executing an UPDATE statement on the records that are already notified for.</span></span> <span data-ttu-id="4690e-111">若要配置负载平衡，无法执行删除已接到通知有关的记录的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="4690e-111">To configure load-balancing, you could execute a stored procedure that deletes the records that have been notified for.</span></span> <span data-ttu-id="4690e-112">例如，考虑存储的过程 PROCESS_EMPLOYEE 替换为以下定义：</span><span class="sxs-lookup"><span data-stu-id="4690e-112">For example, consider a stored procedure PROCESS_EMPLOYEE with the following definition:</span></span>  
  
```  
DECLARE @var int  
SELECT TOP 1 @var = Employee_ID FROM Employee  
SELECT * FROM Employee WHERE Employee_ID=@var  
DELETE FROM Employee WHERE Employee_ID=@var  
```  
  
 <span data-ttu-id="4690e-113">BizTalk 应用程序的一部分执行此存储的过程时，获取删除已收到通知时该记录。</span><span class="sxs-lookup"><span data-stu-id="4690e-113">When you execute this stored procedure as part of the BizTalk application, the record for which notification is already received gets deleted.</span></span> <span data-ttu-id="4690e-114">因此，其他接收下一条记录的位置获取的通知。</span><span class="sxs-lookup"><span data-stu-id="4690e-114">So, the other receive location gets notification for the next record.</span></span>  
  
 <span data-ttu-id="4690e-115">以下是配置负载平衡，用于接收通知时必须执行的高级步骤。</span><span class="sxs-lookup"><span data-stu-id="4690e-115">Here are the high-level steps you must perform to configure load-balancing for receiving notifications.</span></span>  
  
1.  <span data-ttu-id="4690e-116">创建架构**通知**（入站操作） 和**PROCESS_EMPLOYEE**存储过程 （出站操作）。</span><span class="sxs-lookup"><span data-stu-id="4690e-116">Create schema for **Notification** (inbound operation) and **PROCESS_EMPLOYEE** stored procedure (outbound operation).</span></span>  
  
2.  <span data-ttu-id="4690e-117">添加业务流程和添加接收通知、 执行存储的过程，并为存储过程获取响应的三条消息。</span><span class="sxs-lookup"><span data-stu-id="4690e-117">Add an orchestration and add three messages for receiving notification, executing stored procedure, and getting response for the stored procedure.</span></span>  
  
3.  <span data-ttu-id="4690e-118">通过添加 Send 和 Receive 形状、 构造消息形状和端口创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="4690e-118">Create an orchestration by adding Send and Receive shapes, Construct Message shape, and ports.</span></span> <span data-ttu-id="4690e-119">可以使用相同的示例代码用于构造一条消息，以调用 PROCESS_EMPLOYEE 存储过程。</span><span class="sxs-lookup"><span data-stu-id="4690e-119">You can use the same sample code for constructing a message to invoke the PROCESS_EMPLOYEE stored procedure.</span></span> <span data-ttu-id="4690e-120">请注意，尽管执行中的操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须具有 PROCESS_EMPLOYEE 请求消息中的位置 C:\TestLocation\MessageIn 存储过程。</span><span class="sxs-lookup"><span data-stu-id="4690e-120">Note that while performing the operation in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must have the request message for the PROCESS_EMPLOYEE stored procedure in the location C:\TestLocation\MessageIn.</span></span> <span data-ttu-id="4690e-121">这样做是因为在中创建业务流程的一部分调用的代码段[接收查询通知以增量方式从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)创建根据请求在 C:\ 中存在 XML 请求消息TestLocation\MessageIn。</span><span class="sxs-lookup"><span data-stu-id="4690e-121">You do so because the code snippet you invoke as part of the orchestration created in [Receive Query Notifications Incrementally from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md) creates a request message based on the request XML present in C:\TestLocation\MessageIn.</span></span>  
  
4.  <span data-ttu-id="4690e-122">生成和部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="4690e-122">Build and deploy the application.</span></span> <span data-ttu-id="4690e-123">若要演示负载平衡，你必须部署此业务流程至少具有两台不同计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="4690e-123">To demonstrate load-balancing, you must deploy this orchestration at least on two different computers that have [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed.</span></span>  
  
5.  <span data-ttu-id="4690e-124">在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]两台计算机上的管理控制台指定的 WCF 自定义或 WCF SQL 的以下绑定属性接收位置：</span><span class="sxs-lookup"><span data-stu-id="4690e-124">In the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console on both the computers, specify the following binding properties for the WCF-Custom or WCF-SQL receive location:</span></span>  
  
    |<span data-ttu-id="4690e-125">绑定属性</span><span class="sxs-lookup"><span data-stu-id="4690e-125">Binding Property</span></span>|<span data-ttu-id="4690e-126">值</span><span class="sxs-lookup"><span data-stu-id="4690e-126">Value</span></span>|  
    |----------------------|-----------|  
    |<span data-ttu-id="4690e-127">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="4690e-127">**InboundOperationType**</span></span>|<span data-ttu-id="4690e-128">将其设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="4690e-128">Set this to **Notification**.</span></span>|  
    |<span data-ttu-id="4690e-129">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="4690e-129">**NotificationStatement**</span></span>|<span data-ttu-id="4690e-130">将其设置为：</span><span class="sxs-lookup"><span data-stu-id="4690e-130">Set this to:</span></span><br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> <span data-ttu-id="4690e-131">**注意：** 对于通知语句，你必须始终指定表名称以及架构名称。</span><span class="sxs-lookup"><span data-stu-id="4690e-131">**Note:** For notification statements, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="4690e-132">例如， `dbo.Employee`。</span><span class="sxs-lookup"><span data-stu-id="4690e-132">For example, `dbo.Employee`.</span></span>|  
    |<span data-ttu-id="4690e-133">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="4690e-133">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="4690e-134">将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="4690e-134">Set this to **True**.</span></span>|  
  
6.  <span data-ttu-id="4690e-135">启动 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4690e-135">Start the BizTalk application.</span></span>  
  
7.  <span data-ttu-id="4690e-136">若要开始接收通知，请将上百个记录插入员工表。</span><span class="sxs-lookup"><span data-stu-id="4690e-136">To start receiving notifications, insert a hundred records into the EMPLOYEE table.</span></span> <span data-ttu-id="4690e-137">在这样做，请确保请求 XML 调用 PROCESS_EMPLOYEE 的存储过程是在 C:\TestLocation\MessageIn 中可用。</span><span class="sxs-lookup"><span data-stu-id="4690e-137">While doing so, make sure the request XML for invoking the PROCESS_EMPLOYEE stored procedure is available in C:\TestLocation\MessageIn.</span></span>  
  
8.  <span data-ttu-id="4690e-138">监视其中 BizTalk 应用程序将删除为通知消息 （在这两个计算机） 上的位置。</span><span class="sxs-lookup"><span data-stu-id="4690e-138">Monitor the location (on both the computers) where the BizTalk application will be dropping the notification messages.</span></span> <span data-ttu-id="4690e-139">你将注意到，几百个记录插入的一个位置获取一些记录的通知时其他位置获取剩余的记录的通知。</span><span class="sxs-lookup"><span data-stu-id="4690e-139">You will notice that of the hundred records inserted, one location gets notifications for some records while the other location gets notification for the remaining records.</span></span> <span data-ttu-id="4690e-140">在一起，这两个位置将会收到数百个的所有记录的通知。</span><span class="sxs-lookup"><span data-stu-id="4690e-140">Together, both the locations will get notification for all the hundred records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4690e-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4690e-141">See Also</span></span>  
 [<span data-ttu-id="4690e-142">接收使用 BizTalk Server 的 SQL 查询通知</span><span class="sxs-lookup"><span data-stu-id="4690e-142">Receive SQL Query Notifications using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)