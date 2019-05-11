---
title: 什么是源事件视图？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, Source Event view
- Source Event view [Tracking Profile Editor]
- message schemas, Tracking Profile Editor
- orchestrations, Tracking Profile Editor
- Tracking Profile Editor, message schemas
- Tracking Profile Editor, orchestrations
ms.assetid: 72e74780-8590-484b-899d-cdc3d2a908be
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfc45ad952dca12acb2c325399dc318ddf7dbf50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242927"
---
# <a name="what-is-the-source-event-view"></a><span data-ttu-id="e703c-103">什么是源事件视图？</span><span class="sxs-lookup"><span data-stu-id="e703c-103">What Is the Source Event View?</span></span>
<span data-ttu-id="e703c-104">事件源视图是跟踪配置文件编辑器 (TPE) 提供的业务流程或消息架构的程序集或映射到活动定义的上下文属性从选择的显示。</span><span class="sxs-lookup"><span data-stu-id="e703c-104">The Event Source View is where the Tracking Profile Editor (TPE) presents the orchestrations or message schemas selected from the assemblies or the context properties which you map to the activity definition.</span></span>  
  
 <span data-ttu-id="e703c-105">源事件视图显示在用户界面的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="e703c-105">The Source Event View is presented in the right pane of user interface.</span></span> <span data-ttu-id="e703c-106">所选数据源根据有所不同窗格的内容。</span><span class="sxs-lookup"><span data-stu-id="e703c-106">The contents of the pane vary based on the data source you selected.</span></span>  
  
## <a name="event-source-options"></a><span data-ttu-id="e703c-107">事件源选项</span><span class="sxs-lookup"><span data-stu-id="e703c-107">Event source options</span></span>  
 <span data-ttu-id="e703c-108">有四个选项可用于事件源： 业务流程调度、 消息传送负载、 上下文属性和消息传送属性。</span><span class="sxs-lookup"><span data-stu-id="e703c-108">You have four options for event sources: orchestration schedules, messaging payloads, context properties, and messaging properties.</span></span>  
  
 <span data-ttu-id="e703c-109">业务流程和消息传送负载要求选择要从中映射数据项的程序集。</span><span class="sxs-lookup"><span data-stu-id="e703c-109">Orchestrations and messaging payloads require that you select an assembly from which to map your data items.</span></span> <span data-ttu-id="e703c-110">然后从该程序集选择特定的业务流程或感兴趣的消息负载架构。</span><span class="sxs-lookup"><span data-stu-id="e703c-110">You then select the specific orchestrations or message payload schemas of interest from the assembly.</span></span> <span data-ttu-id="e703c-111">对于业务流程计划您的程序集中提供的业务流程的列表。</span><span class="sxs-lookup"><span data-stu-id="e703c-111">For orchestration schedules you are given a list of the orchestrations in the assembly.</span></span> <span data-ttu-id="e703c-112">消息传送负载可用于从消息传送负载架构的列表中选择和上下文属性中的程序集和可公开访问的系统架构中显示的架构列表。</span><span class="sxs-lookup"><span data-stu-id="e703c-112">Messaging payloads allow you to select from a list of messaging payload schemas, and context properties present a list of schemas in the assembly and in system schemas that are publicly available.</span></span>  
  
 <span data-ttu-id="e703c-113">当你选择上下文属性时，系统将首先提供上下文属性名称的列表。</span><span class="sxs-lookup"><span data-stu-id="e703c-113">When you select context properties, you are first given a list of context property names.</span></span> <span data-ttu-id="e703c-114">时选择上下文属性，在右窗格中显示的上下文属性相关的架构。</span><span class="sxs-lookup"><span data-stu-id="e703c-114">When you select the context property, the related schema of the context property is shown in the right pane.</span></span> <span data-ttu-id="e703c-115">通过拖放到活动节点上的属性，然后可以将上下文属性映射到您的活动。</span><span class="sxs-lookup"><span data-stu-id="e703c-115">You can then map the context property to your activity by dragging and dropping the property onto an activity node.</span></span>  
  
 <span data-ttu-id="e703c-116">选择消息传送属性时系统将提供则可以映射到活动的已知消息传送属性的列表。</span><span class="sxs-lookup"><span data-stu-id="e703c-116">When you select messaging properties you are given a list of the known messaging properties that you can then map to the activity.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e703c-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="e703c-117">In This Section</span></span>  
  
-   [<span data-ttu-id="e703c-118">“业务流程调度”视图</span><span class="sxs-lookup"><span data-stu-id="e703c-118">Orchestration Schedule View</span></span>](../core/orchestration-schedule-view.md)  
  
-   [<span data-ttu-id="e703c-119">“消息传送负载”视图</span><span class="sxs-lookup"><span data-stu-id="e703c-119">Messaging Payload View</span></span>](../core/messaging-payload-view.md)  
  
-   [<span data-ttu-id="e703c-120">“上下文属性”视图</span><span class="sxs-lookup"><span data-stu-id="e703c-120">Context Property View</span></span>](../core/context-property-view.md)  
  
-   [<span data-ttu-id="e703c-121">“消息传送属性”视图</span><span class="sxs-lookup"><span data-stu-id="e703c-121">Messaging Property View</span></span>](../core/messaging-property-view.md)