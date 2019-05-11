---
title: 运行状况与活动跟踪 |Microsoft Docs
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
ms.openlocfilehash: 116f55c0824d66017e2fb1264cc3a27f388e9a85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344393"
---
# <a name="health-and-activity-tracking"></a><span data-ttu-id="4d081-102">运行状况与活动跟踪</span><span class="sxs-lookup"><span data-stu-id="4d081-102">Health and Activity Tracking</span></span>
<span data-ttu-id="4d081-103">**运行状况与活动跟踪 (HAT)** 工具中已删除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009年。</span><span class="sxs-lookup"><span data-stu-id="4d081-103">The **Health and Activity Tracking (HAT)** tool was removed in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009.</span></span>  <span data-ttu-id="4d081-104">HAT 工具的角色是用于跟踪和显示 live 相关的信息和历史消息数据存储在 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="4d081-104">The role of the HAT tool was to track and display information relating to live and historical message data stored in the BizTalk Tracking database.</span></span>  <span data-ttu-id="4d081-105">该工具允许调试业务流程并能够查看通过顺序显示消息流的流。</span><span class="sxs-lookup"><span data-stu-id="4d081-105">The tool allowed debugging of the flow of an orchestration and the ability to view the flow of a message through a sequential display.</span></span>  <span data-ttu-id="4d081-106">查询生成器允许使用标准和自定义查询的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="4d081-106">A Query Builder allowed standard and custom queries of the tracking data.</span></span>  
  
 <span data-ttu-id="4d081-107">尽管运行状况活动跟踪工具不能再直接从调用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]菜单中，其跟踪功能仍间接存在于内[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="4d081-107">While the Health Activity Tracking tool is no longer invoked directly from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] menu, its tracking functionality still indirectly exists from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  <span data-ttu-id="4d081-108">运行状况和活动信息是可通过改进的集成和附加跟踪 BizTalk Server 管理控制台中的组中心页中的查询。</span><span class="sxs-lookup"><span data-stu-id="4d081-108">Health and activity information is available through improved integration and additional tracking queries within the Group Hub page in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="4d081-109">大多数文档周围的跟踪运行状况与活动数据，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4d081-109">A majority of documentation surrounding tracking health and activity data can be found at [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  <span data-ttu-id="4d081-110">在本部分中的信息的一些包括[消息和实例数据跟踪的最佳实践](../core/best-practices-for-message-and-instance-data-tracking.md)，[了解跟踪数据](../core/understanding-tracked-data.md)，[查看历史记录和跟踪数据](../core/viewing-historical-and-tracked-data.md)，[查看消息流](../core/viewing-message-flow.md)，并[调试业务流程](../core/debugging-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="4d081-110">Some of the information in this section includes [Best Practices for Message and Instance Data Tracking](../core/best-practices-for-message-and-instance-data-tracking.md), [Understanding Tracked Data](../core/understanding-tracked-data.md), [Viewing Historical and Tracked Data](../core/viewing-historical-and-tracked-data.md), [Viewing Message Flow](../core/viewing-message-flow.md), and [Debugging an Orchestration](../core/debugging-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="4d081-111">有关的改进和其它查询的此页的其他信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="4d081-111">For additional information on the improvements and the additional queries to this page, refer to the following topics:</span></span>  
  
-   [<span data-ttu-id="4d081-112">使用“组中心”页</span><span class="sxs-lookup"><span data-stu-id="4d081-112">Using the Group Hub Page</span></span>](../core/using-the-group-hub-page.md)  
  
-   [<span data-ttu-id="4d081-113">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="4d081-113">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)  
  
-   [<span data-ttu-id="4d081-114">如何搜索跟踪的消息事件</span><span class="sxs-lookup"><span data-stu-id="4d081-114">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="4d081-115">如何搜索跟踪的服务实例</span><span class="sxs-lookup"><span data-stu-id="4d081-115">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)