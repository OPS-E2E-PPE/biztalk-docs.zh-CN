---
title: "消息和实例数据跟踪的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HAT, best practices
- best practices, HAT
ms.assetid: 2ac5c87b-2059-4912-9cec-2ae4eaac56df
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6f673b0a70903575918eb87dc4bd8edc9841e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a><span data-ttu-id="6e3e8-102">消息和实例数据跟踪的最佳实践</span><span class="sxs-lookup"><span data-stu-id="6e3e8-102">Best Practices for Message and Instance Data Tracking</span></span>
<span data-ttu-id="6e3e8-103">请查看以下使用历史数据和跟踪数据的最佳操作。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-103">Review the following best practices for using historical and tracked data.</span></span>  
  
-   <span data-ttu-id="6e3e8-104">**查看有关使用历史数据和跟踪数据的安全注意事项**</span><span class="sxs-lookup"><span data-stu-id="6e3e8-104">**Review the security considerations for using historical and tracked data**</span></span>  
  
    -   <span data-ttu-id="6e3e8-105">有关历史数据和跟踪数据的安全注意事项的详细信息，请参阅[消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-105">For more information about security considerations for historical and tracked data, see [Security Considerations for Message and Instance Data Tracking](../core/security-considerations-for-message-and-instance-data-tracking.md).</span></span>  
  
-   <span data-ttu-id="6e3e8-106">**确保所有 MessageBox 数据库上正在运行的 SQL Server 代理服务**</span><span class="sxs-lookup"><span data-stu-id="6e3e8-106">**Ensure that the SQL Server Agent service is running on all MessageBox databases**</span></span>  
  
    -   <span data-ttu-id="6e3e8-107">SQL Server 代理使得消息正文可用于 WMI、历史数据和跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-107">SQL Server Agent makes message bodies available to WMI, and historical and tracked data.</span></span> <span data-ttu-id="6e3e8-108">这使您能够运行作业来清理 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-108">This enables you to run jobs to clean up the MessageBox databases.</span></span> <span data-ttu-id="6e3e8-109">有关 SQL Server 代理的详细信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-109">For more information about SQL Server Agent, see SQL Server Books Online.</span></span>  
  
-   <span data-ttu-id="6e3e8-110">**启用消息正文跟踪**</span><span class="sxs-lookup"><span data-stu-id="6e3e8-110">**Enable message body tracking**</span></span>  
  
    -   <span data-ttu-id="6e3e8-111">若要在服务实例处理完成后保存消息，则需要消息正文跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-111">Message body tracking is required to save messages after service instances processing is complete.</span></span>  
  
-   <span data-ttu-id="6e3e8-112">**配置跟踪以适合你的业务需求**</span><span class="sxs-lookup"><span data-stu-id="6e3e8-112">**Configure tracking as appropriate for your business needs**</span></span>  
  
    -   <span data-ttu-id="6e3e8-113">可以查看历史数据和跟踪数据前，必须先使用 BizTalk Server 管理控制台配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-113">Before you can view historical and tracked data, you must first configure tracking using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="6e3e8-114">启用或禁用跟踪选项时，要时刻牢记几个注意事项。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-114">There are multiple considerations to keep in mind when enabling or disabling tracking options.</span></span> <span data-ttu-id="6e3e8-115">跟踪的数据越多，BizTalk 跟踪 (BizTalkDTADb) 数据库的大小增长的越快，这将对系统的运行时性能产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-115">The more data you track, the faster your BizTalk Tracking (BizTalkDTADb) database will grow in size, which can adversely affect your runtime performance.</span></span> <span data-ttu-id="6e3e8-116">有关详细信息，请参阅[配置跟踪使用 BizTalk Server 管理控制台](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-116">For more information, see [Configuring Tracking Using the BizTalk Server Administration Console](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef).</span></span>  
  
-   <span data-ttu-id="6e3e8-117">**选择适当类型的跟踪以进行故障排除或审核**</span><span class="sxs-lookup"><span data-stu-id="6e3e8-117">**Select the appropriate type of tracking for troubleshooting or auditing**</span></span>  
  
    -   <span data-ttu-id="6e3e8-118">为了解决在开发环境、过渡环境或生产环境中出现的问题，应启用所有跟踪选项，以便可查看项目事件、消息属性、消息正文和业务流程事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-118">For troubleshooting either in a development environment, or in a staging or production environment, you should enable all tracking options so that you can see artifact events, message properties, message bodies and orchestration events in detail.</span></span> <span data-ttu-id="6e3e8-119">这些跟踪信息内容丰富，使用这些信息可重建系统中的事件序列并调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-119">This provides a rich set of tracked information that you can use to recreate the sequence of events in your system and debug your application.</span></span>  
  
    -   <span data-ttu-id="6e3e8-120">对于生产级别的审核，应仔细选择要审核的事件，然后仅启用对这些事件的跟踪。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-120">For production level auditing, carefully choose the events you want to audit and then enable tracking only for those events.</span></span> <span data-ttu-id="6e3e8-121">例如，许多企业希望能够对进入和退出系统的消息进行审批。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-121">For example, many enterprises want to be able to prove that a message entered and exited the system.</span></span> <span data-ttu-id="6e3e8-122">为此，应启用对相应接收端口的入站跟踪，和对相应发送端口的出站跟踪。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-122">To achieve this, you should enable inbound tracking on the corresponding receive port and enable outbound tracking on the corresponding send port.</span></span> <span data-ttu-id="6e3e8-123">必要时，可添加对消息属性和消息正文的跟踪。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-123">If necessary, you can add message property and message body tracking.</span></span>  
  
    -   <span data-ttu-id="6e3e8-124">为了度量业务关键性能指标 (KPI) 或由指定业务里程碑的完成所标识的进度，应使用业务活动监视 (BAM) 跟踪。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-124">For measuring business Key Performance Indicators (KPIs) or progress as measured by the achievement of specified business milestones, you should use Business Activity Monitoring (BAM) tracking.</span></span> <span data-ttu-id="6e3e8-125">BAM 跟踪在跟踪和存储消息正文方面能力有限，所以如果这些方面的数据非常重要的话，则应同时使用历史数据和跟踪数据以及 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-125">BAM tracking has limited abilities to track and store message bodies, so if this is important, you should use historical and tracked data  in conjunction with BAM tracking.</span></span> <span data-ttu-id="6e3e8-126">有关 BAM 跟踪的详细信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-126">For more information about BAM tracking, see [Using Business Activity Monitoring](../core/using-business-activity-monitoring.md).</span></span>  
  
-   <span data-ttu-id="6e3e8-127">**存档和清除数据从定期 BizTalk 跟踪 (BizTalkDTADb) 数据库**</span><span class="sxs-lookup"><span data-stu-id="6e3e8-127">**Archive and purge data from the BizTalk Tracking (BizTalkDTADb) database on a regular basis**</span></span>  
  
    -   <span data-ttu-id="6e3e8-128">如果启用了跟踪，则应定期存档和清除 BizTalk 跟踪数据库中的数据，以使该数据库保持适当的大小，这有助于改善系统性能。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-128">If you have enabled tracking, you should archive and purge data from the BizTalk Tracking database on a regular basis to help keep the database appropriately sized, which helps improve system performance.</span></span> <span data-ttu-id="6e3e8-129">有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。</span><span class="sxs-lookup"><span data-stu-id="6e3e8-129">For more information, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3e8-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e3e8-130">See Also</span></span>  
 [<span data-ttu-id="6e3e8-131">查看跟踪的消息和实例数据</span><span class="sxs-lookup"><span data-stu-id="6e3e8-131">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)