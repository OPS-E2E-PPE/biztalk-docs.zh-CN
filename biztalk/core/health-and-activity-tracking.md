---
title: 运行状况和活动跟踪 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c5d7415-38da-47b5-8dbc-0a2ea74548d9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b1720535b58a50fe0c5bd3478bc9b9ec90d0d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246597"
---
# <a name="health-and-activity-tracking"></a><span data-ttu-id="29afb-102">运行状况与活动跟踪</span><span class="sxs-lookup"><span data-stu-id="29afb-102">Health and Activity Tracking</span></span>
<span data-ttu-id="29afb-103">**运行状况和活动跟踪 (HAT)** 工具已删除在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009年。</span><span class="sxs-lookup"><span data-stu-id="29afb-103">The **Health and Activity Tracking (HAT)** tool was removed in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009.</span></span>  <span data-ttu-id="29afb-104">HAT 工具的角色是跟踪并显示相关生存的信息和历史消息数据存储在 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="29afb-104">The role of the HAT tool was to track and display information relating to live and historical message data stored in the BizTalk Tracking database.</span></span>  <span data-ttu-id="29afb-105">该工具允许调试业务流程并能够通过顺序显示来查看消息流。</span><span class="sxs-lookup"><span data-stu-id="29afb-105">The tool allowed debugging of the flow of an orchestration and the ability to view the flow of a message through a sequential display.</span></span>  <span data-ttu-id="29afb-106">查询生成器允许对跟踪数据进行标准和自定义查询。</span><span class="sxs-lookup"><span data-stu-id="29afb-106">A Query Builder allowed standard and custom queries of the tracking data.</span></span>  
  
 <span data-ttu-id="29afb-107">尽管不再直接从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 菜单中调用运行状况活动跟踪工具，但其跟踪功能仍间接存在于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中。</span><span class="sxs-lookup"><span data-stu-id="29afb-107">While the Health Activity Tracking tool is no longer invoked directly from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] menu, its tracking functionality still indirectly exists from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  <span data-ttu-id="29afb-108">可通过 BizTalk Server 管理控制台的“组中心”页中改善的集成和附加跟踪查询来获取运行状况和活动信息。</span><span class="sxs-lookup"><span data-stu-id="29afb-108">Health and activity information is available through improved integration and additional tracking queries within the Group Hub page in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="29afb-109">大部分周围的文档跟踪运行状况和活动的数据可以找到在[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="29afb-109">A majority of documentation surrounding tracking health and activity data can be found at [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  <span data-ttu-id="29afb-110">此部分中的信息的一些包括[消息和实例数据跟踪的最佳做法](../core/best-practices-for-message-and-instance-data-tracking.md)，[了解跟踪数据](../core/understanding-tracked-data.md)，[查看历史记录和跟踪数据](../core/viewing-historical-and-tracked-data.md)，[查看消息流](../core/viewing-message-flow.md)，和[调试业务流程](../core/debugging-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="29afb-110">Some of the information in this section includes [Best Practices for Message and Instance Data Tracking](../core/best-practices-for-message-and-instance-data-tracking.md), [Understanding Tracked Data](../core/understanding-tracked-data.md), [Viewing Historical and Tracked Data](../core/viewing-historical-and-tracked-data.md), [Viewing Message Flow](../core/viewing-message-flow.md), and [Debugging an Orchestration](../core/debugging-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="29afb-111">有关此页面的改进和其它查询的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="29afb-111">For additional information on the improvements and the additional queries to this page, refer to the following topics:</span></span>  
  
-   [<span data-ttu-id="29afb-112">使用组中心页</span><span class="sxs-lookup"><span data-stu-id="29afb-112">Using the Group Hub Page</span></span>](../core/using-the-group-hub-page.md)  
  
-   [<span data-ttu-id="29afb-113">使用管理控制台的查询选项卡</span><span class="sxs-lookup"><span data-stu-id="29afb-113">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)  
  
-   [<span data-ttu-id="29afb-114">如何搜索跟踪的消息事件</span><span class="sxs-lookup"><span data-stu-id="29afb-114">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="29afb-115">如何搜索跟踪的服务实例</span><span class="sxs-lookup"><span data-stu-id="29afb-115">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)