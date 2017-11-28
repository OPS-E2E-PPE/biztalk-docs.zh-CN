---
title: "了解跟踪的数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- instances, viewing
- service instances, viewing
- viewing, suspended instances
- messages, viewing
- viewing, service details
- viewing, orchestration details
- viewing, message details
- orchestrations, viewing
- suspended instances
- instances, suspended
ms.assetid: dcc3fbd5-cd2c-4780-a577-0ccd521cf5eb
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed30934ca154c8b6921682112b12d016c57f92be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-tracked-data"></a><span data-ttu-id="e0082-102">了解跟踪数据</span><span class="sxs-lookup"><span data-stu-id="e0082-102">Understanding Tracked Data</span></span>
<span data-ttu-id="e0082-103">跟踪查询运行时，在结果列表底部的查询结果窗口会显示跟踪的信息。</span><span class="sxs-lookup"><span data-stu-id="e0082-103">When you run a tracking query, the tracked information appears in the results list at the bottom of the Query Results window.</span></span>  
  
## <a name="viewing-message-details"></a><span data-ttu-id="e0082-104">查看消息详细信息</span><span class="sxs-lookup"><span data-stu-id="e0082-104">Viewing message details</span></span>  
 <span data-ttu-id="e0082-105">您可以跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="e0082-105">You can track message properties.</span></span> <span data-ttu-id="e0082-106">也可以将跟踪消息正文保存到文件中，然后使用非 Microsoft 工具查看它们。</span><span class="sxs-lookup"><span data-stu-id="e0082-106">You can also save tracked message bodies to a file and view them using non-Microsoft tools.</span></span>  
  
-   <span data-ttu-id="e0082-107">可以右键单击服务实例所引用的任何消息，然后选择消息详细信息。</span><span class="sxs-lookup"><span data-stu-id="e0082-107">You can right-click any message referenced by a service instance and select Message details.</span></span>  
  
-   <span data-ttu-id="e0082-108">如果消息已处理但被跟踪（因为启用了跟踪功能），则可以将其保存到硬盘并对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="e0082-108">If the message is already processed but it was tracked—because you had tracking turned on—you can save it to your hard disk and examine it.</span></span>  
  
-   <span data-ttu-id="e0082-109">可以附加到业务流程实例，然后使用业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="e0082-109">You can attach to the orchestration instance and use the Orchestration Debugger.</span></span>  
  
## <a name="viewing-service-events"></a><span data-ttu-id="e0082-110">查看服务事件</span><span class="sxs-lookup"><span data-stu-id="e0082-110">Viewing service events</span></span>  
 <span data-ttu-id="e0082-111">当挂起的服务出现在事件日志时，则可以通过使用调查服务**消息流**，**业务流程调试器**，**显示跟踪消息事件**，**显示实时服务实例**，选项从**上下文**菜单。</span><span class="sxs-lookup"><span data-stu-id="e0082-111">When a suspended service appears in the event log, you can investigate a service by using the **Message Flow**, **Orchestration Debugger**, **Show Tracked Message Events**, **Show Live Service Instances**, options from the **Context** menu.</span></span>  
  
## <a name="viewing-orchestration-events"></a><span data-ttu-id="e0082-112">查看业务流程事件</span><span class="sxs-lookup"><span data-stu-id="e0082-112">Viewing orchestration events</span></span>  
 <span data-ttu-id="e0082-113">使用业务流程调试器可以查看消息实例在通过业务流程时所经过的路径。</span><span class="sxs-lookup"><span data-stu-id="e0082-113">Use the Orchestration Debugger to view the path a message instance has taken through an orchestration.</span></span> <span data-ttu-id="e0082-114">在逐步执行时，业务流程的呈现图像将显示消息的进度，您可以在业务流程中放置断点，以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="e0082-114">As you step through, a rendered image of the orchestration shows the progress of the message, and allows you to place breakpoints in the orchestration for debugging purposes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0082-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="e0082-115">In This Section</span></span>  
  
-   [<span data-ttu-id="e0082-116">什么是邮件跟踪？</span><span class="sxs-lookup"><span data-stu-id="e0082-116">What is Message Tracking?</span></span>](../core/what-is-message-tracking.md)  
  
-   [<span data-ttu-id="e0082-117">什么是事件跟踪？</span><span class="sxs-lookup"><span data-stu-id="e0082-117">What is Event Tracking?</span></span>](../core/what-is-event-tracking.md)