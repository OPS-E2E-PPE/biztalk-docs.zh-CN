---
title: 管理 BAM 事件总线服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, migrating data
- Primary Import database [BAM], migrating data
- migrating, data [BAM]
- managing [BAM], Event Bus Service
- Event Bus Service [BAM], managing
- Tracking Data Decode Service (TDDS)
ms.assetid: 556e7fe2-4a7d-46f6-8e55-f41be4e666dc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f265201e371a86072c06b336b4d00bb1742f5f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262813"
---
# <a name="managing-the-bam-event-bus-service"></a><span data-ttu-id="02e08-102">管理 BAM 事件总线服务</span><span class="sxs-lookup"><span data-stu-id="02e08-102">Managing the BAM Event Bus Service</span></span>
<span data-ttu-id="02e08-103">“BAM 事件总线服务”也称为“跟踪数据解码服务 (TDDS)”，该服务处理源数据库中存储的跟踪数据（数据流），并将这些数据以日后可轻松查询的方式保存。</span><span class="sxs-lookup"><span data-stu-id="02e08-103">The BAM Event Bus Service, also known as the Tracking Data Decode Service (TDDS), processes tracking data (streams) stored in a source database and persists that data in such a way that it is easy to query it at a later date.</span></span>  
  
 <span data-ttu-id="02e08-104">BAM 事件总线服务将商业智能数据移动到 BAM 主导入数据库，而将 BizTalk 运行状况监视数据移动到 DTA 数据库。</span><span class="sxs-lookup"><span data-stu-id="02e08-104">The BAM Event Bus service moves Business intelligence data to the BAM Primary Import database and BizTalk Health Monitoring data to the DTA database.</span></span> <span data-ttu-id="02e08-105">BAM 事件总线服务作为 BizTalk 服务内的子服务运行。</span><span class="sxs-lookup"><span data-stu-id="02e08-105">The BAM Event Bus service runs as a sub-service within the BizTalk service.</span></span>  
  
 <span data-ttu-id="02e08-106">通过在执行期间，收集事件数据，然后临时存储数据的应用程序状态与同一数据库中监视的活动事务的应用程序，如 Microsoft BizTalk® Server — 例如，MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="02e08-106">You monitor the activities of a transactional application, such as Microsoft BizTalk® Server, by collecting event data during execution, and then temporarily storing the data in the same database as the application state—for example, the MessageBox database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02e08-107">避免创建多个承载为不同的 BizTalk 组跟踪的同一计算机上的应用程序实例。</span><span class="sxs-lookup"><span data-stu-id="02e08-107">Avoid creating more than one application instance that hosts tracking for different BizTalk Groups on the same computer.</span></span> <span data-ttu-id="02e08-108">如果同一台计算机中存在多个跟踪不同 BizTalk 组的实例，您将无法在 BizTalk 管理控制台或事件日志中区分哪个事件属于哪个 BizTalk 组，因为所有 BizTalk 组都显示为相同的名称。</span><span class="sxs-lookup"><span data-stu-id="02e08-108">If instances that track different BizTalk Groups exist on the same computer, you will not be able to distinguish which events belong to which BizTalk Groups in the BizTalk Administration Console or in the event log because all BizTalk Groups are displayed with the same name.</span></span>  
  
 <span data-ttu-id="02e08-109">BAM 事件总线服务读取并解码事件数据，然后将其存储到 Microsoft SQL Server™ 数据库中，在该数据库中，您可以轻松查询数据。</span><span class="sxs-lookup"><span data-stu-id="02e08-109">The BAM Event Bus service reads the event data, decodes it, and then stores it in a Microsoft SQL Server™ database, where you can easily query the data.</span></span>  
  
 <span data-ttu-id="02e08-110">BAM 事件总线服务提供以下优点：</span><span class="sxs-lookup"><span data-stu-id="02e08-110">The BAM Event Bus service provides the following advantages:</span></span>  
  
-   <span data-ttu-id="02e08-111">事件数据始终与应用程序的状态匹配，并且永远不会公开未提交的进度。</span><span class="sxs-lookup"><span data-stu-id="02e08-111">Event data always matches the state of the application, and it never exposes uncommitted progress.</span></span>  
  
-   <span data-ttu-id="02e08-112">上运行的应用程序的性能影响很小，因为事件数据将尽可能少的记录保存在应用程序状态更改在同一个本地事务。</span><span class="sxs-lookup"><span data-stu-id="02e08-112">Performance impact on the running application is minimal because the event data saves as few records in the same local transaction as the application state change.</span></span>  
  
-   <span data-ttu-id="02e08-113">针对执行性能进一步优化应用程序状态的 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="02e08-113">SQL Server storage for the application state is further optimized for execution performance.</span></span> <span data-ttu-id="02e08-114">数据是由 TDDS 解码，并存储在单独的数据库，BAM 主导入数据库或 DTA 数据库。</span><span class="sxs-lookup"><span data-stu-id="02e08-114">The data is decoded by TDDS and stored in a separate database, either the BAM Primary import database or the DTA database.</span></span> <span data-ttu-id="02e08-115">生成报表时的数据从数据库查询，并会影响存储的应用程序状态的消息框数据库。</span><span class="sxs-lookup"><span data-stu-id="02e08-115">When reports are generated the data is queried from the database and does impact the Message Box database, which stores the application state.</span></span>  
  
-   <span data-ttu-id="02e08-116">应用程序服务器和数据库中不执行存储可以查询的窗体中的事件数据的工作。</span><span class="sxs-lookup"><span data-stu-id="02e08-116">The work to store the event data in a form that you can query is not done in the application servers and databases.</span></span> <span data-ttu-id="02e08-117">它被卸载给运行 BAM 事件总线服务和目标 SQL Server 数据库的计算机。</span><span class="sxs-lookup"><span data-stu-id="02e08-117">It is offloaded to the machines that run the BAM Event Bus service and the Destination SQL Server database.</span></span>  
  
-   <span data-ttu-id="02e08-118">事件的数据处理和低延迟时间更快地这样 TDDS 查询过程。</span><span class="sxs-lookup"><span data-stu-id="02e08-118">Event data is processed with low latency which allows TDDS queries process faster.</span></span> <span data-ttu-id="02e08-119">BAM 事件总线服务协调其资源以获得可能的最小延迟。</span><span class="sxs-lookup"><span data-stu-id="02e08-119">The BAM Event Bus services coordinate their resources to achieve the minimum possible latency.</span></span>  
  
 <span data-ttu-id="02e08-120">BAM 事件总线服务器通过使用到中央数据库，其中包含的配置信息的连接协调及其资源。</span><span class="sxs-lookup"><span data-stu-id="02e08-120">The BAM Event Bus server coordinates its resources by using a connection to a central database, which contains the configuration information.</span></span> <span data-ttu-id="02e08-121">每分钟每个活动的 BAM 事件总线服务将消息发送到中央数据库，其中包含在该点及时 BAM 事件总线服务的状态。</span><span class="sxs-lookup"><span data-stu-id="02e08-121">Every minute, each active BAM Event Bus service sends a message to the central database, which contains the state of the BAM Event Bus service at that point in time.</span></span>  
  
 <span data-ttu-id="02e08-122">此消息被称为检测信号消息。</span><span class="sxs-lookup"><span data-stu-id="02e08-122">This message is referred to as a heartbeat message.</span></span> <span data-ttu-id="02e08-123">每个 BAM 事件总线服务还检查新需要完成的工作。</span><span class="sxs-lookup"><span data-stu-id="02e08-123">Each BAM Event Bus service also checks for new work that needs to be done.</span></span> <span data-ttu-id="02e08-124">例如，与 BAM 事件总线服务检查不属于，如 MessageBox 数据库已添加的会话。</span><span class="sxs-lookup"><span data-stu-id="02e08-124">For example, the BAM Event Bus service checks for sessions that are not owned, such as a MessageBox database that has been added.</span></span>  
  
 <span data-ttu-id="02e08-125">BAM 事件总线会话是从源数据库，如消息框中，指向包含事件数据的格式。 您可以查询目标数据库的事件数据移动。</span><span class="sxs-lookup"><span data-stu-id="02e08-125">The BAM Event Bus session is the movement of the event data from the source database, such as the MessageBox, to the destination database that contains the event data in a format that you can query.</span></span> <span data-ttu-id="02e08-126">相同的 BAM 事件总线服务可以处理一个或多个会话。</span><span class="sxs-lookup"><span data-stu-id="02e08-126">The same BAM Event Bus service can process one or more sessions.</span></span>  
  
 <span data-ttu-id="02e08-127">下图显示一组构成 BAM 事件总线服务器池的 BAM 事件总线服务器。</span><span class="sxs-lookup"><span data-stu-id="02e08-127">The following figure shows a group of BAM Event Bus servers, which make up a BAM Event Bus server pool.</span></span>  
  
 ![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")  
<span data-ttu-id="02e08-128">BAM 事件总线服务器池的关系图</span><span class="sxs-lookup"><span data-stu-id="02e08-128">Diagram of a BAM Event Bus server pool</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02e08-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="02e08-129">In This Section</span></span>  
  
-   [<span data-ttu-id="02e08-130">BAM 性能计数器</span><span class="sxs-lookup"><span data-stu-id="02e08-130">BAM Performance Counters</span></span>](../core/bam-performance-counters.md)  
  
-   [<span data-ttu-id="02e08-131">BAM 事件总线服务存储过程</span><span class="sxs-lookup"><span data-stu-id="02e08-131">BAM Event Bus Service Stored Procedures</span></span>](../core/bam-event-bus-service-stored-procedures.md)  
  
-   [<span data-ttu-id="02e08-132">BAM 事件总线服务服务器故障转移</span><span class="sxs-lookup"><span data-stu-id="02e08-132">BAM Event Bus Service Server Failover</span></span>](../core/bam-event-bus-service-server-failover.md)  
  
-   [<span data-ttu-id="02e08-133">创建 BAM 事件总线服务的实例</span><span class="sxs-lookup"><span data-stu-id="02e08-133">Creating Instances of the BAM Event Bus Service</span></span>](../core/creating-instances-of-the-bam-event-bus-service.md)