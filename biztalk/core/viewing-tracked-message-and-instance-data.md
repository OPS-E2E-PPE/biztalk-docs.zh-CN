---
title: "查看跟踪的消息和实例数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring, HAT
- HAT, about HAT
ms.assetid: e3cc7bef-90c7-4375-9f6c-7df00391132e
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 592fa5c85913a69f4536055cdd790d638b15bc32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="viewing-tracked-message-and-instance-data"></a><span data-ttu-id="b0341-102">查看跟踪的消息和实例数据</span><span class="sxs-lookup"><span data-stu-id="b0341-102">Viewing Tracked Message and Instance Data</span></span>
<span data-ttu-id="b0341-103">您可以使用历史记录和跟踪的数据，来帮助您对 BizTalk Server 应用程序中的问题进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="b0341-103">You can use historical and tracked data to help troubleshoot your BizTalk Server applications.</span></span> <span data-ttu-id="b0341-104">例如，系统管理员可以使用历史记录和跟踪数据完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="b0341-104">For example, system administrators can use historical and tracked data to:</span></span>  
  
-   <span data-ttu-id="b0341-105">查看在消息流的各个阶段中的跟踪消息事件、消息属性和消息正文。</span><span class="sxs-lookup"><span data-stu-id="b0341-105">View tracked message events, message properties, and message bodies at various stages in a message’s flow.</span></span> <span data-ttu-id="b0341-106">这些数据可用于排除故障或审核用途。</span><span class="sxs-lookup"><span data-stu-id="b0341-106">This data can be used for troubleshooting or auditing purposes.</span></span>  
  
-   <span data-ttu-id="b0341-107">重播特定业务流程实例的执行过程。</span><span class="sxs-lookup"><span data-stu-id="b0341-107">Replay the execution of a specific orchestration instance.</span></span>  
  
-   <span data-ttu-id="b0341-108">跟踪规则触发事件以便将来重新构造事件顺序。</span><span class="sxs-lookup"><span data-stu-id="b0341-108">Track rule firing events to reconstruct the sequence of events at a later point in time.</span></span>  
  
-   <span data-ttu-id="b0341-109">通过指定标准（如消息架构和消息属性/值对）来查询消息。</span><span class="sxs-lookup"><span data-stu-id="b0341-109">Query for messages by specifying criteria such as message schema and message property/value pairs.</span></span> <span data-ttu-id="b0341-110">使用此方法找到消息后，用户便可确定消息在消息流中已执行到哪一点。</span><span class="sxs-lookup"><span data-stu-id="b0341-110">Having thus located the message, users can determine the point in the message flow to which the message has progressed.</span></span> <span data-ttu-id="b0341-111">高级用户还可以为消息创建自定义 SQL Server 查询。</span><span class="sxs-lookup"><span data-stu-id="b0341-111">Advanced users can also create custom SQL Server queries for messages.</span></span>  
  
-   <span data-ttu-id="b0341-112">搜索存档数据库中的存档数据。</span><span class="sxs-lookup"><span data-stu-id="b0341-112">Search for archived data in an archived database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0341-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="b0341-113">In This Section</span></span>  
  
-   [<span data-ttu-id="b0341-114">清单： 消息和实例数据跟踪</span><span class="sxs-lookup"><span data-stu-id="b0341-114">Checklist: Message and Instance Data Tracking</span></span>](../core/checklist-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="b0341-115">消息和实例数据跟踪的最佳做法</span><span class="sxs-lookup"><span data-stu-id="b0341-115">Best Practices for Message and Instance Data Tracking</span></span>](../core/best-practices-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="b0341-116">消息和实例数据跟踪的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="b0341-116">Security Considerations for Message and Instance Data Tracking</span></span>](../core/security-considerations-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="b0341-117">了解跟踪数据</span><span class="sxs-lookup"><span data-stu-id="b0341-117">Understanding Tracked Data</span></span>](../core/understanding-tracked-data.md)  
  
-   [<span data-ttu-id="b0341-118">查看历史记录和跟踪数据</span><span class="sxs-lookup"><span data-stu-id="b0341-118">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)  
  
-   [<span data-ttu-id="b0341-119">如何选择实时或已存档的数据源</span><span class="sxs-lookup"><span data-stu-id="b0341-119">How to Select a Live or Archived Data Source</span></span>](../core/how-to-select-a-live-or-archived-data-source.md)  
  
-   [<span data-ttu-id="b0341-120">如何更改跟踪 QueryTimeout 值</span><span class="sxs-lookup"><span data-stu-id="b0341-120">How to Change the Tracking QueryTimeout Value</span></span>](../core/how-to-change-the-tracking-querytimeout-value.md)  
  
-   [<span data-ttu-id="b0341-121">如何保存跟踪查询</span><span class="sxs-lookup"><span data-stu-id="b0341-121">How to Save a Tracking Query</span></span>](../core/how-to-save-a-tracking-query.md)  
  
-   [<span data-ttu-id="b0341-122">如何打开已保存的跟踪查询</span><span class="sxs-lookup"><span data-stu-id="b0341-122">How to Open a Saved Tracking Query</span></span>](../core/how-to-open-a-saved-tracking-query.md)  
  
-   [<span data-ttu-id="b0341-123">查看消息流</span><span class="sxs-lookup"><span data-stu-id="b0341-123">Viewing Message Flow</span></span>](../core/viewing-message-flow.md)  
  
-   [<span data-ttu-id="b0341-124">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="b0341-124">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)  
  
-   [<span data-ttu-id="b0341-125">使用结果列表</span><span class="sxs-lookup"><span data-stu-id="b0341-125">Working with the Results List</span></span>](../core/working-with-the-results-list.md)