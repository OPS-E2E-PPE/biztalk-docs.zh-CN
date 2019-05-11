---
title: 了解跟踪的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f8119c78bdab44279feebef3a4460303b3ae78c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292769"
---
# <a name="understanding-tracked-data"></a><span data-ttu-id="7920c-102">了解跟踪数据</span><span class="sxs-lookup"><span data-stu-id="7920c-102">Understanding Tracked Data</span></span>
<span data-ttu-id="7920c-103">运行时跟踪查询，被跟踪的信息将显示在查询结果窗口底部的结果列表中。</span><span class="sxs-lookup"><span data-stu-id="7920c-103">When you run a tracking query, the tracked information appears in the results list at the bottom of the Query Results window.</span></span>  
  
## <a name="viewing-message-details"></a><span data-ttu-id="7920c-104">查看消息详细信息</span><span class="sxs-lookup"><span data-stu-id="7920c-104">Viewing message details</span></span>  
 <span data-ttu-id="7920c-105">你可以跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="7920c-105">You can track message properties.</span></span> <span data-ttu-id="7920c-106">此外可以将跟踪的消息正文保存到文件，并查看它们使用非 Microsoft 工具。</span><span class="sxs-lookup"><span data-stu-id="7920c-106">You can also save tracked message bodies to a file and view them using non-Microsoft tools.</span></span>  
  
-   <span data-ttu-id="7920c-107">您可以右键单击服务实例引用的任何消息，并选择消息详细信息。</span><span class="sxs-lookup"><span data-stu-id="7920c-107">You can right-click any message referenced by a service instance and select Message details.</span></span>  
  
-   <span data-ttu-id="7920c-108">如果消息已处理但被跟踪，因为启用了跟踪功能，可以将其保存到硬盘并对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="7920c-108">If the message is already processed but it was tracked—because you had tracking turned on—you can save it to your hard disk and examine it.</span></span>  
  
-   <span data-ttu-id="7920c-109">可以将附加到业务流程实例，并使用业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="7920c-109">You can attach to the orchestration instance and use the Orchestration Debugger.</span></span>  
  
## <a name="viewing-service-events"></a><span data-ttu-id="7920c-110">查看服务事件</span><span class="sxs-lookup"><span data-stu-id="7920c-110">Viewing service events</span></span>  
 <span data-ttu-id="7920c-111">当挂起的服务出现在事件日志时，可以通过查看服务**消息流**，**业务流程调试器**，**显示跟踪的消息事件**，**显示实时服务实例**，从选项**上下文**菜单。</span><span class="sxs-lookup"><span data-stu-id="7920c-111">When a suspended service appears in the event log, you can investigate a service by using the **Message Flow**, **Orchestration Debugger**, **Show Tracked Message Events**, **Show Live Service Instances**, options from the **Context** menu.</span></span>  
  
## <a name="viewing-orchestration-events"></a><span data-ttu-id="7920c-112">查看业务流程事件</span><span class="sxs-lookup"><span data-stu-id="7920c-112">Viewing orchestration events</span></span>  
 <span data-ttu-id="7920c-113">使用业务流程调试器可以查看消息实例的路径已通过业务流程。</span><span class="sxs-lookup"><span data-stu-id="7920c-113">Use the Orchestration Debugger to view the path a message instance has taken through an orchestration.</span></span> <span data-ttu-id="7920c-114">单步执行，该业务流程的呈现的图像显示进度消息，并允许您将断点放置在业务流程中以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="7920c-114">As you step through, a rendered image of the orchestration shows the progress of the message, and allows you to place breakpoints in the orchestration for debugging purposes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7920c-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="7920c-115">In This Section</span></span>  
  
-   [<span data-ttu-id="7920c-116">消息跟踪概述</span><span class="sxs-lookup"><span data-stu-id="7920c-116">What is Message Tracking?</span></span>](../core/what-is-message-tracking.md)  
  
-   [<span data-ttu-id="7920c-117">事件跟踪概述</span><span class="sxs-lookup"><span data-stu-id="7920c-117">What is Event Tracking?</span></span>](../core/what-is-event-tracking.md)