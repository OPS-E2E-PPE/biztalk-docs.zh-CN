---
title: 在 BAM 门户网站上的活动搜索页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], searching
- Activity Search page [BAM portal]
- BAM portal, activity searches
ms.assetid: 24a5111c-026f-4f77-8a17-65955aafd24c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b01e85495f0cf673c5c781e3accaaf1fc340025
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994118"
---
# <a name="activity-search-on-the-bam-portal-page"></a><span data-ttu-id="11540-102">BAM 门户页的活动搜索</span><span class="sxs-lookup"><span data-stu-id="11540-102">Activity Search on the BAM Portal Page</span></span>
<span data-ttu-id="11540-103">当业务最终用户、开发人员和业务分析员需要对 BAM 数据进行搜索以查找某个流程的具体案例时，他们可使用 BAM 门户页。</span><span class="sxs-lookup"><span data-stu-id="11540-103">Business end users, developers, and business analysts can use the BAM portal page when they need to perform searches against BAM data to find specific cases of a particular process.</span></span> <span data-ttu-id="11540-104">这些流程是作为 BAM 活动定义的。</span><span class="sxs-lookup"><span data-stu-id="11540-104">These processes are defined as BAM activities.</span></span> <span data-ttu-id="11540-105">BAM 活动代表业务中的工作单位，例如采购订单或贷款申请。</span><span class="sxs-lookup"><span data-stu-id="11540-105">A BAM activity represents a unit of work in a business, such as a purchase order or loan application.</span></span>  
  
## <a name="how-an-activity-search-works"></a><span data-ttu-id="11540-106">活动搜索如何运行</span><span class="sxs-lookup"><span data-stu-id="11540-106">How an activity search works</span></span>  
 <span data-ttu-id="11540-107">活动搜索，可对 BAM 数据，以查找指定基于跟踪的值和项可在 BAM 视图中，该匹配条件的活动并显示活动，以便可以对其进行编辑，也可以根据其创建警报执行搜索。</span><span class="sxs-lookup"><span data-stu-id="11540-107">An activity search allows you to perform searches against BAM data to find activities that match criteria you specify based on tracked values and items available in a BAM view, and to display the activities so that you can edit them or create alerts based on them.</span></span>  
  
 <span data-ttu-id="11540-108">您为搜索创建的查询可以保存并重用。</span><span class="sxs-lookup"><span data-stu-id="11540-108">Queries that you create for your searches can be saved and reused.</span></span> <span data-ttu-id="11540-109">您还可以将它们用作警报的依据，例如，“当指定的客户所下的采购订单到达时通知我”。</span><span class="sxs-lookup"><span data-stu-id="11540-109">You can also use them as the basis for an alert, for example, "Notify me any time a purchase order arrives from the specified customer."</span></span> <span data-ttu-id="11540-110">您可以使用内容页顶部的按钮来保存、打开和运行查询，以及设置警报。</span><span class="sxs-lookup"><span data-stu-id="11540-110">You use the buttons at the top of the content page to save, open, and run queries, as well as to set alerts.</span></span>  
  
 <span data-ttu-id="11540-111">使用活动搜索可以查找要监视的活动。</span><span class="sxs-lookup"><span data-stu-id="11540-111">Activity searches allow you to locate the activities that you want to monitor.</span></span> <span data-ttu-id="11540-112">创建活动搜索后，您可以使用该搜索创建通知您目标事件的警报。</span><span class="sxs-lookup"><span data-stu-id="11540-112">Once you create an activity search, you can use that search to create an alert that will notify you of events that are of interest.</span></span>  
  
## <a name="the-activity-search-page"></a><span data-ttu-id="11540-113">“活动搜索”页</span><span class="sxs-lookup"><span data-stu-id="11540-113">The Activity Search page</span></span>  
 <span data-ttu-id="11540-114">在内容框架内，“活动搜索”页分成了三个主要部分：</span><span class="sxs-lookup"><span data-stu-id="11540-114">The Activity Search page is divided into three main sections inside the Content frame:</span></span>  
  
- <span data-ttu-id="11540-115">**查询**： 此部分允许用户通过构建搜索子句基于特定的跟踪的数据项来搜索活动。</span><span class="sxs-lookup"><span data-stu-id="11540-115">**Query**: This section allows users to search for activities by building search clauses based on specific tracked data items.</span></span> <span data-ttu-id="11540-116">用户可以根据需要添加和删除子句。</span><span class="sxs-lookup"><span data-stu-id="11540-116">The user can add and remove clauses as required.</span></span>  
  
- <span data-ttu-id="11540-117">**列选择器**： 本部分允许用户指定的项的数据，从那些可在该视图中，若要返回的任何记录如果与搜索条件匹配。</span><span class="sxs-lookup"><span data-stu-id="11540-117">**Column Chooser**: This section allows users to specify which items of data, from those available in that view, to return if any records match the search criteria.</span></span>  
  
- <span data-ttu-id="11540-118">**结果**： 在本部分中显示查询的结果。</span><span class="sxs-lookup"><span data-stu-id="11540-118">**Results**: Results of the query display in this section.</span></span>  
  
  <span data-ttu-id="11540-119">有关活动搜索和活动搜索页的详细信息，请参阅[BAM 门户中的活动搜索](../core/activity-searches-in-the-bam-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="11540-119">For more information about activity searches and the Activity Search page, see [Activity Searches in the BAM Portal](../core/activity-searches-in-the-bam-portal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11540-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="11540-120">See Also</span></span>  
 <span data-ttu-id="11540-121">[BAM 门户](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="11540-121">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="11540-122">[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="11540-122">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 [<span data-ttu-id="11540-123">“BAM 门户”页中的警报管理器</span><span class="sxs-lookup"><span data-stu-id="11540-123">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)