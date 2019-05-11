---
title: 查看跟踪的消息和实例数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, HAT
- HAT, about HAT
ms.assetid: e3cc7bef-90c7-4375-9f6c-7df00391132e
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18e08e4f7aa98941dcd859557661d2e5883c76ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253583"
---
# <a name="viewing-tracked-message-and-instance-data"></a><span data-ttu-id="f677b-102">查看跟踪的消息和实例数据</span><span class="sxs-lookup"><span data-stu-id="f677b-102">Viewing Tracked Message and Instance Data</span></span>
<span data-ttu-id="f677b-103">历史记录和跟踪数据可用于帮助解决您的 BizTalk Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f677b-103">You can use historical and tracked data to help troubleshoot your BizTalk Server applications.</span></span> <span data-ttu-id="f677b-104">例如，系统管理员可以使用历史记录和跟踪数据：</span><span class="sxs-lookup"><span data-stu-id="f677b-104">For example, system administrators can use historical and tracked data to:</span></span>  
  
-   <span data-ttu-id="f677b-105">查看在各个阶段中的消息流跟踪的消息事件、 消息属性和消息正文。</span><span class="sxs-lookup"><span data-stu-id="f677b-105">View tracked message events, message properties, and message bodies at various stages in a message’s flow.</span></span> <span data-ttu-id="f677b-106">此数据可用于排除故障或审核目的。</span><span class="sxs-lookup"><span data-stu-id="f677b-106">This data can be used for troubleshooting or auditing purposes.</span></span>  
  
-   <span data-ttu-id="f677b-107">重播特定业务流程实例的执行。</span><span class="sxs-lookup"><span data-stu-id="f677b-107">Replay the execution of a specific orchestration instance.</span></span>  
  
-   <span data-ttu-id="f677b-108">跟踪规则触发事件以便将来重新构造在以后的事件的顺序。</span><span class="sxs-lookup"><span data-stu-id="f677b-108">Track rule firing events to reconstruct the sequence of events at a later point in time.</span></span>  
  
-   <span data-ttu-id="f677b-109">查询通过指定条件，如消息架构和消息属性/值对的消息。</span><span class="sxs-lookup"><span data-stu-id="f677b-109">Query for messages by specifying criteria such as message schema and message property/value pairs.</span></span> <span data-ttu-id="f677b-110">具有因此位于该消息，用户可确定该消息已发展到的消息流中的点。</span><span class="sxs-lookup"><span data-stu-id="f677b-110">Having thus located the message, users can determine the point in the message flow to which the message has progressed.</span></span> <span data-ttu-id="f677b-111">高级的用户还可以创建自定义的消息的 SQL Server 查询。</span><span class="sxs-lookup"><span data-stu-id="f677b-111">Advanced users can also create custom SQL Server queries for messages.</span></span>  
  
-   <span data-ttu-id="f677b-112">搜索存档数据库中的存档数据。</span><span class="sxs-lookup"><span data-stu-id="f677b-112">Search for archived data in an archived database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f677b-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="f677b-113">In This Section</span></span>  
  
-   [<span data-ttu-id="f677b-114">清单：消息和实例数据跟踪</span><span class="sxs-lookup"><span data-stu-id="f677b-114">Checklist: Message and Instance Data Tracking</span></span>](../core/checklist-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="f677b-115">消息和实例数据跟踪的最佳做法</span><span class="sxs-lookup"><span data-stu-id="f677b-115">Best Practices for Message and Instance Data Tracking</span></span>](../core/best-practices-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="f677b-116">消息和实例数据跟踪的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="f677b-116">Security Considerations for Message and Instance Data Tracking</span></span>](../core/security-considerations-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="f677b-117">了解跟踪数据</span><span class="sxs-lookup"><span data-stu-id="f677b-117">Understanding Tracked Data</span></span>](../core/understanding-tracked-data.md)  
  
-   [<span data-ttu-id="f677b-118">查看历史数据和跟踪数据</span><span class="sxs-lookup"><span data-stu-id="f677b-118">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)  
  
-   [<span data-ttu-id="f677b-119">如何选择实时或存档的数据源</span><span class="sxs-lookup"><span data-stu-id="f677b-119">How to Select a Live or Archived Data Source</span></span>](../core/how-to-select-a-live-or-archived-data-source.md)  
  
-   [<span data-ttu-id="f677b-120">如何更改跟踪 QueryTimeout 值</span><span class="sxs-lookup"><span data-stu-id="f677b-120">How to Change the Tracking QueryTimeout Value</span></span>](../core/how-to-change-the-tracking-querytimeout-value.md)  
  
-   [<span data-ttu-id="f677b-121">如何保存跟踪查询</span><span class="sxs-lookup"><span data-stu-id="f677b-121">How to Save a Tracking Query</span></span>](../core/how-to-save-a-tracking-query.md)  
  
-   [<span data-ttu-id="f677b-122">如何打开已保存的跟踪查询</span><span class="sxs-lookup"><span data-stu-id="f677b-122">How to Open a Saved Tracking Query</span></span>](../core/how-to-open-a-saved-tracking-query.md)  
  
-   [<span data-ttu-id="f677b-123">查看消息流</span><span class="sxs-lookup"><span data-stu-id="f677b-123">Viewing Message Flow</span></span>](../core/viewing-message-flow.md)  
  
-   [<span data-ttu-id="f677b-124">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="f677b-124">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)  
  
-   [<span data-ttu-id="f677b-125">使用“结果”列表</span><span class="sxs-lookup"><span data-stu-id="f677b-125">Working with the Results List</span></span>](../core/working-with-the-results-list.md)