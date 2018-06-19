---
title: 使用组中心页 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50693ccc-a3b2-4ad0-9a05-d60dab404a07
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e035a363b71b70db390d88a8b0e32e2e9b531d92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288085"
---
# <a name="using-the-group-hub-page"></a><span data-ttu-id="f9c7d-102">使用“组中心”页</span><span class="sxs-lookup"><span data-stu-id="f9c7d-102">Using the Group Hub Page</span></span>
<span data-ttu-id="f9c7d-103">选择**BizTalk 组**节点在 BizTalk Server 管理控制台中，显示 BizTalk Server 组中心数据库页的详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-103">Selecting the **BizTalk Group** node in the BizTalk Server Administration Console, displays the BizTalk Server Group Hub page in the details pane.</span></span> <span data-ttu-id="f9c7d-104">BizTalk Server 组中心页分为三个部分，提供 BizTalk Server 系统运行状况的总体概况。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-104">The BizTalk Server Group Hub page is divided into three sections that provide an overall view of the health of your BizTalk Server system:</span></span>  
  
-   <span data-ttu-id="f9c7d-105">**配置概述**部分中，在组中心数据库页的上半部分中找到通过显示应用程序，主机实例的状态来指示 BizTalk 组的总体运行状况和适配器处理程序配置中此组中。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-105">The **Configuration Overview** section, located in the upper part of the Group Hub page, indicates the overall health of the BizTalk group by displaying the state of the applications, host instances, and adapter handlers configured in this group.</span></span>  
  
-   <span data-ttu-id="f9c7d-106">**正在进行的工作**和**挂起项**部分位于中间组中心数据库页。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-106">The **Work in Progress**  and **Suspended Items** sections are located in the middle of the Group Hub page.</span></span>  
  
    -   <span data-ttu-id="f9c7d-107">**正在进行的工作**部分显示运行服务实例、 冻结的业务流程，正在重试和空闲端口、 就绪的服务实例和计划的服务实例。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-107">The **Work in Progress** section displays running service instances, dehydrated orchestrations, retrying and idle ports, ready service instances, and scheduled service instances.</span></span>  
  
    -   <span data-ttu-id="f9c7d-108">**挂起项**部分显示的挂起的服务实例和可恢复和非可恢复实例数。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-108">The **Suspended Items** section displays the number of suspended service instances, and resumable and non-resumable instances.</span></span>  
  
-   <span data-ttu-id="f9c7d-109">**分组挂起的服务实例**部分显示按应用程序、 服务名称、 错误代码和 URI 分组的挂起的服务实例。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-109">The **Grouped Suspended Service Instances** section displays suspended service instances grouped by application, service name, error code, and URI.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9c7d-110">“组中心”页上列出的数目只是近似数目。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-110">The numbers listed on the Group Hub page are approximate counts only.</span></span> <span data-ttu-id="f9c7d-111">例如下, 显示的数字**正在运行的服务实例**或**挂起的服务实例**可能不等于正在运行的服务实例或挂起的服务实例的总数因为正在生成中心页面上的各种统计信息时，无法更改系统的状态。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-111">For example, the numbers displayed under **Running service instances** or **Suspended service instances** might not equal the total number of running service instances or suspended service instances because the state of the system could change while the various statistics on the Hub page are being generated.</span></span>  
  
-   <span data-ttu-id="f9c7d-112">**跟踪服务实例**和**跟踪消息事件**部分执行查询的消息活动和最大匹配的服务实例的状态 = 50。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-112">The **Tracked Service Instances** and **Tracked Message Events** sections execute queries on message events and the state of service instances with a maximum match = 50.</span></span>  
  
    -   <span data-ttu-id="f9c7d-113">**跟踪服务实例**查询将搜索跟踪的服务实例。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-113">**Tracked service instances** query searches for tracked service instances.</span></span>  
  
    -   <span data-ttu-id="f9c7d-114">**已完成实例**查询将搜索具有相等完成状态的跟踪的服务实例。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-114">**Completed instances** query searches for tracked service instances with state equal to completed.</span></span>  
  
    -   <span data-ttu-id="f9c7d-115">**终止实例**查询将搜索具有相等的状态终止跟踪的服务实例。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-115">**Terminated instances** query searches for tracked service instances with state equal to terminated.</span></span>  
  
    -   <span data-ttu-id="f9c7d-116">**跟踪消息事件**查询搜索的跟踪的消息事件。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-116">**Tracked message events** query searches for tracked message events.</span></span>  
  
    -   <span data-ttu-id="f9c7d-117">**传输失败事件**查询将搜索的跟踪的消息事件的事件类型的传输故障。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-117">**Transmission failure events** query searches for tracked message events with an event type of transmission failure.</span></span>  
  
-   <span data-ttu-id="f9c7d-118">**EDI 状态报告**和**EDIINT 状态报告**部分中，位于底部的组中心数据库页显示有关 EDI 的交换的四个报告和有关 AS2 的交换： EDI 交换和关联 ACK 状态报表、 批处理状态报表、 交换聚合报表、 事务组聚合报表和 AS2 消息和相关 MDN 状态报表。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-118">The **EDI Status Reports** and **EDIINT Status Reports** sections, located at the bottom of the Group Hub page, displays four reports about EDI interchanges and one about AS2 interchanges: the EDI Interchange and Correlated ACK Status reports, the Batch Status report, the Interchange Aggregation Report, the Transaction Set Aggregation Report, and the AS2 Message and Correlated MDN Status report.</span></span> <span data-ttu-id="f9c7d-119">有关这些报表的详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-119">For more information about these reports, see [EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9c7d-120">如果为此 BizTalk 组配置 EDI/AS2 功能，才会显示 EDI 和 EDIINT 状态报表部分。</span><span class="sxs-lookup"><span data-stu-id="f9c7d-120">The EDI and EDIINT Status Report sections will only be displayed if the EDI/AS2 features are configured for this BizTalk group.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9c7d-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="f9c7d-121">In This Section</span></span>  
  
-   [<span data-ttu-id="f9c7d-122">服务实例状态</span><span class="sxs-lookup"><span data-stu-id="f9c7d-122">Service Instance States</span></span>](../core/service-instance-states.md)  
  
-   [<span data-ttu-id="f9c7d-123">调查业务流程、 端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="f9c7d-123">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)  
  
-   [<span data-ttu-id="f9c7d-124">使用管理控制台的查询选项卡</span><span class="sxs-lookup"><span data-stu-id="f9c7d-124">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)  
  
-   [<span data-ttu-id="f9c7d-125">查看跟踪的消息和实例数据</span><span class="sxs-lookup"><span data-stu-id="f9c7d-125">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [<span data-ttu-id="f9c7d-126">运行状况和活动跟踪</span><span class="sxs-lookup"><span data-stu-id="f9c7d-126">Health and Activity Tracking</span></span>](../core/health-and-activity-tracking.md)