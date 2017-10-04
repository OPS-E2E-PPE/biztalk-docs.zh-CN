---
title: "使用管理控制台的查询选项卡 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], Query tab
- Query tab [Administration Console]
ms.assetid: 7655f0b6-9217-46c4-88e0-ca2e661ce7a6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20046580913ee8ea3ccb4a742ab693bcaa08d38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-administration-console-query-tab"></a><span data-ttu-id="2a767-102">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="2a767-102">Using the Administration Console Query Tab</span></span>
<span data-ttu-id="2a767-103">您可以使用 BizTalk Server 管理控制台的“组中心”页中的“查询”选项卡来搜索和定位正在运行或挂起的特定服务实例、消息或订阅。</span><span class="sxs-lookup"><span data-stu-id="2a767-103">You can use the Query tab on the Group Hub page in the BizTalk Server Administration Console to search for and locate specific running and suspended service instances, messages, or subscriptions.</span></span> <span data-ttu-id="2a767-104">使用管理控制台执行的查询可定位存储在 MessageBox 数据库中的实时项。</span><span class="sxs-lookup"><span data-stu-id="2a767-104">Queries performed using the Administration Console locate live items, which are stored in the MessageBox database.</span></span> <span data-ttu-id="2a767-105">每次运行新查询时，都会显示一个新的查询选项卡。</span><span class="sxs-lookup"><span data-stu-id="2a767-105">A new query tab appears each time you run a new query.</span></span>  
  
 <span data-ttu-id="2a767-106">若要定位跟踪或存档的消息或服务实例，请使用消息事件和服务实例跟踪。</span><span class="sxs-lookup"><span data-stu-id="2a767-106">To locate tracked or archived messages or service instances, you use message event and service instance tracking.</span></span> <span data-ttu-id="2a767-107">有关详细信息，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2a767-107">For more information, see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a767-108">返回的结果集执行对服务实例的查询时，将显示的值**\<名称不可用 >**为**ServiceName**字段的服务实例如果对应发送端口，接收位置，或业务流程已被删除。</span><span class="sxs-lookup"><span data-stu-id="2a767-108">When you execute a query for service instances, the result set that is returned will display a value of **\<Name is not available>** for the **ServiceName** field of a service instance if the corresponding send port, receive location, or orchestration has been deleted.</span></span>  <span data-ttu-id="2a767-109">**ServiceName**查找到发送端口的友好名称的 BizTalk 管理数据库填充服务实例的字段、 接收位置或业务流程。</span><span class="sxs-lookup"><span data-stu-id="2a767-109">The **ServiceName** field of a service instance is populated by a lookup into the BizTalk management database for the friendly name of the send port, receive location, or orchestration.</span></span>  <span data-ttu-id="2a767-110">如果发送端口接收位置，或删除业务流程则友好名称查找失败和**\<名称不可用 >**显示。</span><span class="sxs-lookup"><span data-stu-id="2a767-110">If the send port, receive location, or orchestration is deleted then the lookup for the friendly name fails and **\<Name is not available>** is displayed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a767-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="2a767-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2a767-112">如何打开已保存的查询</span><span class="sxs-lookup"><span data-stu-id="2a767-112">How to Open a Saved Query</span></span>](../core/how-to-open-a-saved-query.md)  
  
-   [<span data-ttu-id="2a767-113">如何搜索所有服务实例</span><span class="sxs-lookup"><span data-stu-id="2a767-113">How to Search for All Service Instances</span></span>](../core/how-to-search-for-all-service-instances.md)  
  
-   [<span data-ttu-id="2a767-114">如何运行服务实例的搜索</span><span class="sxs-lookup"><span data-stu-id="2a767-114">How to Search for Running Service Instances</span></span>](../core/how-to-search-for-running-service-instances.md)  
  
-   [<span data-ttu-id="2a767-115">如何搜索挂起的服务实例</span><span class="sxs-lookup"><span data-stu-id="2a767-115">How to Search for Suspended Service Instances</span></span>](../core/how-to-search-for-suspended-service-instances.md)  
  
-   [<span data-ttu-id="2a767-116">如何搜索消息</span><span class="sxs-lookup"><span data-stu-id="2a767-116">How to Search for Messages</span></span>](../core/how-to-search-for-messages.md)  
  
-   [<span data-ttu-id="2a767-117">如何搜索订阅</span><span class="sxs-lookup"><span data-stu-id="2a767-117">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)  
  
-   [<span data-ttu-id="2a767-118">如何将查询保存</span><span class="sxs-lookup"><span data-stu-id="2a767-118">How to Save a Query</span></span>](../core/how-to-save-a-query.md)  
  
-   [<span data-ttu-id="2a767-119">如何搜索跟踪的消息事件</span><span class="sxs-lookup"><span data-stu-id="2a767-119">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="2a767-120">如何搜索跟踪的服务实例</span><span class="sxs-lookup"><span data-stu-id="2a767-120">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)