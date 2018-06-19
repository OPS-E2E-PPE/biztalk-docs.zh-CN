---
title: 接收使用 BizTalk Server 的 Oracle 数据库更改通知 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495a29bc-72f6-4140-8160-0b917d935503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69d4b4b3a0b528109caac60ecec3c3614e5d7a5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215221"
---
# <a name="receive-oracle-database-change-notifications-using-biztalk-server"></a><span data-ttu-id="917e1-102">接收使用 BizTalk Server 的 Oracle 数据库更改通知</span><span class="sxs-lookup"><span data-stu-id="917e1-102">Receive Oracle Database Change Notifications Using BizTalk Server</span></span>
<span data-ttu-id="917e1-103">你可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以接收从 Oracle 数据库的数据库更改通知消息。</span><span class="sxs-lookup"><span data-stu-id="917e1-103">You can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive database change notification messages from the Oracle database.</span></span> <span data-ttu-id="917e1-104">你可以指定适配器用于与 Oracle 数据库的通知注册的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="917e1-104">You can specify a SELECT statement that the adapter uses to register for notifications with the Oracle database.</span></span> <span data-ttu-id="917e1-105">适配器将结果集中为 SELECT 语句中，为通知注册更改时接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="917e1-105">The adapter receives a notification message when the result set for the SELECT statement, registered for notification, changes.</span></span> <span data-ttu-id="917e1-106">有关如何适配器支持通知的详细信息，请参阅[接收使用 Oracle 数据库适配器数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="917e1-106">For more information about how the adapter supports notification, see [Considerations for Receiving Database Change Notifications using the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).</span></span>  
  
 <span data-ttu-id="917e1-107">以下是某些情况下，你可以在其中配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 Oracle 数据库接收通知：</span><span class="sxs-lookup"><span data-stu-id="917e1-107">Following are some scenarios in which you can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to receive notifications from the Oracle database:</span></span>  
  
-   <span data-ttu-id="917e1-108">适配器客户端获取仅"增量"通知，例如，仅为已对数据库表从上次通知这些更改。</span><span class="sxs-lookup"><span data-stu-id="917e1-108">Adapter clients get only “incremental” notification, for example, only for those changes that were made to a database table since the last notification.</span></span>  
  
-   <span data-ttu-id="917e1-109">如果大量行插入到数据库表中，适配器客户端可以配置多个接收到的负载平衡接收通知的位置。</span><span class="sxs-lookup"><span data-stu-id="917e1-109">If large number of rows are inserted into a database table, the adapter clients can configure multiple receive locations to load-balance receiving notifications.</span></span>  
  
 <span data-ttu-id="917e1-110">一旦适配器客户端收到的通知消息，他们可以执行特定任务根据收到的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="917e1-110">Once the adapter clients receive a notification message, they can perform specific tasks based on the kind of notification received.</span></span> <span data-ttu-id="917e1-111">例如，它执行的任务，如果收到插入通知的一组和另一组任务的如果收到更新通知的方式可以设计 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="917e1-111">For example, a BizTalk orchestration can be designed in such a way that it performs one set of tasks if an insert notification is received and another set of tasks if an update notification is received.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="917e1-112">如果没有在 Oracle 数据库和适配器客户端之间的网络中断，通知将不发送到适配器客户端的网络中断期间对 Oracle 数据库进行的更改并且之后。</span><span class="sxs-lookup"><span data-stu-id="917e1-112">If there is a network outage between the Oracle database and the adapter client, the notifications will not be sent to the adapter clients for the changes done on the Oracle database during the period of network outage, and thereafter.</span></span> <span data-ttu-id="917e1-113">因此，你必须使用轮询操作而不是关键方案的通知操作。</span><span class="sxs-lookup"><span data-stu-id="917e1-113">Therefore, you must use the Polling operation instead of the Notification operation for critical scenarios.</span></span>  
  
 <span data-ttu-id="917e1-114">此部分中的主题提供有关如何配置每种方案的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="917e1-114">The topics in this section provide information on how to configure the adapter for each of these scenarios.</span></span> <span data-ttu-id="917e1-115">若要开始从 Oracle 数据库使用获取通知[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，你必须指定特定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="917e1-115">To start getting notifications from the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must specify certain binding properties.</span></span> <span data-ttu-id="917e1-116">有关与通知相关的绑定属性的详细信息，请参阅[使用绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="917e1-116">For more information about the binding properties related to notifications, see [Working with binding properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span> <span data-ttu-id="917e1-117">有关通知消息结构的详细信息，请参阅[通知操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)。</span><span class="sxs-lookup"><span data-stu-id="917e1-117">For more information about structure of notification messages, see [Message Schemas for the Notification Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md).</span></span>  
  
 <span data-ttu-id="917e1-118">用于从 Oracle 数据库接收通知，请确保：</span><span class="sxs-lookup"><span data-stu-id="917e1-118">For receiving notifications from the Oracle database, make sure:</span></span>  
  
-   <span data-ttu-id="917e1-119">你可以使用该适配器连接到 Oracle 数据库版本 10.2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="917e1-119">You use the adapter to connect to Oracle database version 10.2 or later.</span></span> <span data-ttu-id="917e1-120">10.2 之前的 oracle 数据库版本不支持通知。</span><span class="sxs-lookup"><span data-stu-id="917e1-120">Oracle database versions prior to 10.2 do not support notifications.</span></span>  
  
-   <span data-ttu-id="917e1-121">用来连接到 Oracle 通知的凭据具有`change notification`特权。</span><span class="sxs-lookup"><span data-stu-id="917e1-121">The credentials you use to connect to Oracle for notifications has `change notification` privilege.</span></span> <span data-ttu-id="917e1-122">此权限是必需的数据库更改通知的接收。</span><span class="sxs-lookup"><span data-stu-id="917e1-122">This privilege is required for receiving database change notifications.</span></span> <span data-ttu-id="917e1-123">为此，请连接到 Oracle 数据库使用管理权限，然后在 SQL 提示符处键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="917e1-123">To do so, connect to Oracle database using administrative privileges and then type the following command on the SQL prompt.</span></span>  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   <span data-ttu-id="917e1-124">决定在 TCP 端口上要 ODP.NET 用于接收从 Oracle 数据库的数据库更改通知。</span><span class="sxs-lookup"><span data-stu-id="917e1-124">Decide on a TCP port you want ODP.NET to use for receiving database change notifications from Oracle database.</span></span> <span data-ttu-id="917e1-125">将该端口添加到 Windows 防火墙例外列表。</span><span class="sxs-lookup"><span data-stu-id="917e1-125">Add that port to Windows Firewall exceptions list.</span></span> <span data-ttu-id="917e1-126">有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。</span><span class="sxs-lookup"><span data-stu-id="917e1-126">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span> <span data-ttu-id="917e1-127">必须提供相同的端口号为**NotificationPort**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="917e1-127">You must provide the same port number for the **NotificationPort** binding property.</span></span> <span data-ttu-id="917e1-128">有关绑定属性的详细信息，请参阅[使用绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="917e1-128">For more information about the binding property, see [Working with binding properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="917e1-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="917e1-129">In This Section</span></span>  
  
-   [<span data-ttu-id="917e1-130">接收使用 Oracle 数据库适配器的数据库更改通知时的注意事项</span><span class="sxs-lookup"><span data-stu-id="917e1-130">Considerations for Receiving Database Change Notifications Using the Oracle Database Adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="917e1-131">处理使用 BizTalk Server 的 Oracle 数据库中完成特定任务的通知消息</span><span class="sxs-lookup"><span data-stu-id="917e1-131">Processing Notification Messages to Complete Specific Tasks in Oracle Database using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)  
  
-   [<span data-ttu-id="917e1-132">接收以增量方式使用 BizTalk Server 的 Oracle 数据库更改通知</span><span class="sxs-lookup"><span data-stu-id="917e1-132">Receiving Oracle Database Change Notifications Incrementally Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [<span data-ttu-id="917e1-133">接收 Oracle 数据库更改通知上多个接收位置</span><span class="sxs-lookup"><span data-stu-id="917e1-133">Receiving Oracle Database Change Notifications On Multiple Receive Locations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [<span data-ttu-id="917e1-134">接收后的 Oracle 数据库更改通知接收位置细分</span><span class="sxs-lookup"><span data-stu-id="917e1-134">Receiving Oracle Database Change Notifications After a Receive Location Breakdown</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)  
  
## <a name="see-also"></a><span data-ttu-id="917e1-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="917e1-135">See Also</span></span>  
[<span data-ttu-id="917e1-136">开发与 Oracle 数据库的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="917e1-136">Building Blocks to Develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)