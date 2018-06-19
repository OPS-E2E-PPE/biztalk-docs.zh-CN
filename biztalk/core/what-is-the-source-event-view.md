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
ms.openlocfilehash: e2437d2effe2fa03078e7f92fdb06f378c9e7cac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289477"
---
# <a name="what-is-the-source-event-view"></a><span data-ttu-id="52741-103">什么是源事件视图？</span><span class="sxs-lookup"><span data-stu-id="52741-103">What Is the Source Event View?</span></span>
<span data-ttu-id="52741-104">“事件源”视图是跟踪配置文件编辑器 (TPE) 显示从程序集中选择的业务流程或消息架构或者映射到活动定义的上下文属性的地方。</span><span class="sxs-lookup"><span data-stu-id="52741-104">The Event Source View is where the Tracking Profile Editor (TPE) presents the orchestrations or message schemas selected from the assemblies or the context properties which you map to the activity definition.</span></span>  
  
 <span data-ttu-id="52741-105">“事件源”视图显示在用户界面的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="52741-105">The Source Event View is presented in the right pane of user interface.</span></span> <span data-ttu-id="52741-106">该窗格的内容随所选数据源而变化。</span><span class="sxs-lookup"><span data-stu-id="52741-106">The contents of the pane vary based on the data source you selected.</span></span>  
  
## <a name="event-source-options"></a><span data-ttu-id="52741-107">事件源选项</span><span class="sxs-lookup"><span data-stu-id="52741-107">Event source options</span></span>  
 <span data-ttu-id="52741-108">你可以为事件源的四个选项： 业务流程计划、 消息传递负载、 上下文属性和消息传递的属性。</span><span class="sxs-lookup"><span data-stu-id="52741-108">You have four options for event sources: orchestration schedules, messaging payloads, context properties, and messaging properties.</span></span>  
  
 <span data-ttu-id="52741-109">业务流程和消息传送负载要求选择要从中映射数据项的程序集。</span><span class="sxs-lookup"><span data-stu-id="52741-109">Orchestrations and messaging payloads require that you select an assembly from which to map your data items.</span></span> <span data-ttu-id="52741-110">然后从该程序集中选择特定的业务流程或目标消息负载架构。</span><span class="sxs-lookup"><span data-stu-id="52741-110">You then select the specific orchestrations or message payload schemas of interest from the assembly.</span></span> <span data-ttu-id="52741-111">对于业务流程调度，系统为您提供了程序集中的业务流程的列表。</span><span class="sxs-lookup"><span data-stu-id="52741-111">For orchestration schedules you are given a list of the orchestrations in the assembly.</span></span> <span data-ttu-id="52741-112">使用消息传送负载，可以在消息传送架构列表中进行选择，上下文属性显示程序集和系统架构中可公用的架构的列表。</span><span class="sxs-lookup"><span data-stu-id="52741-112">Messaging payloads allow you to select from a list of messaging payload schemas, and context properties present a list of schemas in the assembly and in system schemas that are publicly available.</span></span>  
  
 <span data-ttu-id="52741-113">选择上下文属性时，系统首先为您提供一个上下文属性名称列表。</span><span class="sxs-lookup"><span data-stu-id="52741-113">When you select context properties, you are first given a list of context property names.</span></span> <span data-ttu-id="52741-114">当您选择某个上下文属性时，该上下文属性的相关架构会显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="52741-114">When you select the context property, the related schema of the context property is shown in the right pane.</span></span> <span data-ttu-id="52741-115">然后，通过将该上下文属性拖放到某个活动节点上，可以将该属性映射到相应活动中。</span><span class="sxs-lookup"><span data-stu-id="52741-115">You can then map the context property to your activity by dragging and dropping the property onto an activity node.</span></span>  
  
 <span data-ttu-id="52741-116">选择消息传送属性时，系统会为您提供能映射到活动的已知消息传送属性的列表。</span><span class="sxs-lookup"><span data-stu-id="52741-116">When you select messaging properties you are given a list of the known messaging properties that you can then map to the activity.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52741-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="52741-117">In This Section</span></span>  
  
-   [<span data-ttu-id="52741-118">业务流程计划视图</span><span class="sxs-lookup"><span data-stu-id="52741-118">Orchestration Schedule View</span></span>](../core/orchestration-schedule-view.md)  
  
-   [<span data-ttu-id="52741-119">消息传递负载视图</span><span class="sxs-lookup"><span data-stu-id="52741-119">Messaging Payload View</span></span>](../core/messaging-payload-view.md)  
  
-   [<span data-ttu-id="52741-120">上下文属性视图</span><span class="sxs-lookup"><span data-stu-id="52741-120">Context Property View</span></span>](../core/context-property-view.md)  
  
-   [<span data-ttu-id="52741-121">消息属性视图</span><span class="sxs-lookup"><span data-stu-id="52741-121">Messaging Property View</span></span>](../core/messaging-property-view.md)