---
title: 消息和实例数据跟踪的最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, best practices
- best practices, HAT
ms.assetid: 2ac5c87b-2059-4912-9cec-2ae4eaac56df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8415547ec5f4300a89d8a96ffc3ee78325c7c57d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358197"
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a><span data-ttu-id="f327a-102">消息和实例数据跟踪的最佳实践</span><span class="sxs-lookup"><span data-stu-id="f327a-102">Best Practices for Message and Instance Data Tracking</span></span>
<span data-ttu-id="f327a-103">查看使用历史记录和跟踪数据的以下最佳实践。</span><span class="sxs-lookup"><span data-stu-id="f327a-103">Review the following best practices for using historical and tracked data.</span></span>  
  
-   <span data-ttu-id="f327a-104">**查看使用历史记录和跟踪数据的安全注意事项**</span><span class="sxs-lookup"><span data-stu-id="f327a-104">**Review the security considerations for using historical and tracked data**</span></span>  
  
    -   <span data-ttu-id="f327a-105">有关历史记录和跟踪数据的安全注意事项的详细信息，请参阅[消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)。</span><span class="sxs-lookup"><span data-stu-id="f327a-105">For more information about security considerations for historical and tracked data, see [Security Considerations for Message and Instance Data Tracking](../core/security-considerations-for-message-and-instance-data-tracking.md).</span></span>  
  
-   <span data-ttu-id="f327a-106">**确保所有 MessageBox 数据库上运行的 SQL Server 代理服务**</span><span class="sxs-lookup"><span data-stu-id="f327a-106">**Ensure that the SQL Server Agent service is running on all MessageBox databases**</span></span>  
  
    -   <span data-ttu-id="f327a-107">SQL Server 代理使得消息正文用于 WMI、 历史记录和跟踪数据可用。</span><span class="sxs-lookup"><span data-stu-id="f327a-107">SQL Server Agent makes message bodies available to WMI, and historical and tracked data.</span></span> <span data-ttu-id="f327a-108">这使您可以运行作业来清理 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="f327a-108">This enables you to run jobs to clean up the MessageBox databases.</span></span> <span data-ttu-id="f327a-109">有关 SQL Server 代理的详细信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="f327a-109">For more information about SQL Server Agent, see SQL Server Books Online.</span></span>  
  
-   <span data-ttu-id="f327a-110">**启用消息正文跟踪**</span><span class="sxs-lookup"><span data-stu-id="f327a-110">**Enable message body tracking**</span></span>  
  
    -   <span data-ttu-id="f327a-111">消息正文跟踪需要处理的服务实例后保存消息已完成。</span><span class="sxs-lookup"><span data-stu-id="f327a-111">Message body tracking is required to save messages after service instances processing is complete.</span></span>  
  
-   <span data-ttu-id="f327a-112">**配置跟踪以适合你的业务需求**</span><span class="sxs-lookup"><span data-stu-id="f327a-112">**Configure tracking as appropriate for your business needs**</span></span>  
  
    -   <span data-ttu-id="f327a-113">你可以查看历史记录和跟踪数据之前，必须先配置使用 BizTalk Server 管理控制台的跟踪。</span><span class="sxs-lookup"><span data-stu-id="f327a-113">Before you can view historical and tracked data, you must first configure tracking using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="f327a-114">有多个注意事项需要牢记，在启用或禁用跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="f327a-114">There are multiple considerations to keep in mind when enabling or disabling tracking options.</span></span> <span data-ttu-id="f327a-115">跟踪数据越多，速度就越快 BizTalk 跟踪 (BizTalkDTADb) 数据库将在大小增大，这可能会在运行时性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="f327a-115">The more data you track, the faster your BizTalk Tracking (BizTalkDTADb) database will grow in size, which can adversely affect your runtime performance.</span></span> <span data-ttu-id="f327a-116">有关详细信息，请参阅[配置使用 BizTalk Server 管理控制台跟踪](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)。</span><span class="sxs-lookup"><span data-stu-id="f327a-116">For more information, see [Configuring Tracking Using the BizTalk Server Administration Console](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef).</span></span>  
  
-   <span data-ttu-id="f327a-117">**选择适当类型的跟踪进行故障排除或审核**</span><span class="sxs-lookup"><span data-stu-id="f327a-117">**Select the appropriate type of tracking for troubleshooting or auditing**</span></span>  
  
    -   <span data-ttu-id="f327a-118">有关故障排除在开发环境中，或在过渡或生产环境中，应启用所有跟踪选项，以便可以查看项目事件、 消息属性、 消息正文和业务流程事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f327a-118">For troubleshooting either in a development environment, or in a staging or production environment, you should enable all tracking options so that you can see artifact events, message properties, message bodies and orchestration events in detail.</span></span> <span data-ttu-id="f327a-119">这提供了一套丰富的跟踪可用于在您的系统中重新创建的事件顺序和调试应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="f327a-119">This provides a rich set of tracked information that you can use to recreate the sequence of events in your system and debug your application.</span></span>  
  
    -   <span data-ttu-id="f327a-120">对于生产级别的审核，请仔细选择你想要审核，然后启用仅对这些事件的跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="f327a-120">For production level auditing, carefully choose the events you want to audit and then enable tracking only for those events.</span></span> <span data-ttu-id="f327a-121">例如，许多企业希望能够证明消息进入和退出系统。</span><span class="sxs-lookup"><span data-stu-id="f327a-121">For example, many enterprises want to be able to prove that a message entered and exited the system.</span></span> <span data-ttu-id="f327a-122">若要实现此目的，应启用入站的跟踪相应的接收端口和出站跟踪对相应发送端口。</span><span class="sxs-lookup"><span data-stu-id="f327a-122">To achieve this, you should enable inbound tracking on the corresponding receive port and enable outbound tracking on the corresponding send port.</span></span> <span data-ttu-id="f327a-123">如有必要，可以添加消息属性和消息正文跟踪。</span><span class="sxs-lookup"><span data-stu-id="f327a-123">If necessary, you can add message property and message body tracking.</span></span>  
  
    -   <span data-ttu-id="f327a-124">用于测量业务关键绩效指标 (Kpi) 或由指定的业务里程碑的成就度量的进度，应使用业务活动监视 (BAM) 跟踪。</span><span class="sxs-lookup"><span data-stu-id="f327a-124">For measuring business Key Performance Indicators (KPIs) or progress as measured by the achievement of specified business milestones, you should use Business Activity Monitoring (BAM) tracking.</span></span> <span data-ttu-id="f327a-125">BAM 跟踪具有有限的功能来跟踪和存储消息正文，因此，如果这是重要的是，应与 BAM 跟踪结合使用历史记录和跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="f327a-125">BAM tracking has limited abilities to track and store message bodies, so if this is important, you should use historical and tracked data  in conjunction with BAM tracking.</span></span> <span data-ttu-id="f327a-126">有关 BAM 跟踪的详细信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="f327a-126">For more information about BAM tracking, see [Using Business Activity Monitoring](../core/using-business-activity-monitoring.md).</span></span>  
  
-   <span data-ttu-id="f327a-127">**存档和清除 BizTalk 跟踪 (BizTalkDTADb) 数据库定期的数据**</span><span class="sxs-lookup"><span data-stu-id="f327a-127">**Archive and purge data from the BizTalk Tracking (BizTalkDTADb) database on a regular basis**</span></span>  
  
    -   <span data-ttu-id="f327a-128">如果已启用跟踪，你应存档，并清除 BizTalk 跟踪数据库定期帮助保持适当的大小，该数据库，可帮助提高系统性能的数据。</span><span class="sxs-lookup"><span data-stu-id="f327a-128">If you have enabled tracking, you should archive and purge data from the BizTalk Tracking database on a regular basis to help keep the database appropriately sized, which helps improve system performance.</span></span> <span data-ttu-id="f327a-129">有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。</span><span class="sxs-lookup"><span data-stu-id="f327a-129">For more information, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f327a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="f327a-130">See Also</span></span>  
 [<span data-ttu-id="f327a-131">查看跟踪的消息和实例数据</span><span class="sxs-lookup"><span data-stu-id="f327a-131">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)