---
title: "业务流程计划视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Orchestration view [Tracking Profile Editor]
- orchestrations, Tracking Profile Editor
- Tracking Profile Editor, Orchestration view
- Tracking Profile Editor, orchestrations
ms.assetid: b3e0014b-000e-4f58-9f70-d331d78e487e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ad11500cabb10d345ce0a725e9b8f92cf0d4734
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-schedule-view"></a><span data-ttu-id="2f9a9-102">业务流程调度视图</span><span class="sxs-lookup"><span data-stu-id="2f9a9-102">Orchestration Schedule View</span></span>
<span data-ttu-id="2f9a9-103">业务流程视图显示 BAM 处理所选业务流程内包含的业务流程的步骤。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-103">The Orchestration View displays the steps by which BAM transacts the business process contained within the selected orchestration.</span></span> <span data-ttu-id="2f9a9-104">该视图位于跟踪配置文件编辑器 (TPE) 用户界面的右窗格中。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-104">The view is located on the right pane of the Tracking Profile Editor (TPE) user interface.</span></span>  
  
## <a name="working-with-the-orchestration-schedule-view"></a><span data-ttu-id="2f9a9-105">使用业务流程计划视图</span><span class="sxs-lookup"><span data-stu-id="2f9a9-105">Working with the Orchestration Schedule view</span></span>  
 <span data-ttu-id="2f9a9-106">通过单击选择你的业务流程视图**选择事件源**按钮并单击**选择业务流程计划**菜单项。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-106">You select your orchestration view by clicking the **Select Event Source** button and clicking the **Select Orchestration Schedule** menu item.</span></span> <span data-ttu-id="2f9a9-107">然后选择要从中选择业务流程的程序集。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-107">You then choose an assembly from which to select an orchestration.</span></span> <span data-ttu-id="2f9a9-108">在选择业务流程后，可以将表示业务流程构造或操作的业务流程形状从该业务流程拖到活动视图的业务里程碑文件夹中，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2f9a9-108">Once you select the orchestration, you can drag orchestration shapes that represent orchestration constructs or actions from the orchestration into the business milestone folders in the activity view to do the following:</span></span>  
  
-   <span data-ttu-id="2f9a9-109">创建业务流程低级别实现与 BAM 活动之间的映射。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-109">Create a mapping between the low-level implementation of the business process and the BAM activity.</span></span>  
  
-   <span data-ttu-id="2f9a9-110">指出关联的底层构造或操作完成后要跟踪的时间戳。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-110">Indicate the time stamp to track when the associated underlying construct or action has completed.</span></span>  
  
 <span data-ttu-id="2f9a9-111">右键单击业务流程计划中的某个形状，将会打开上下文菜单，您可以从中查看与该形状关联的任何消息负载、上下文属性或消息属性。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-111">Right-clicking a shape in the orchestration schedule view opens a context menu that allows you to view any message payloads, context properties, or message properties that are associated with the shape.</span></span>  
  
 <span data-ttu-id="2f9a9-112">在业务流程视图中显示的说明，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-112">For an explanation of the displayed in the Orchestration View, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
 <span data-ttu-id="2f9a9-113">可用的业务流程的列表可能非常大。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-113">The list of available orchestrations can be extensive.</span></span> <span data-ttu-id="2f9a9-114">如果你知道业务流程，而你要搜索的名称的一部分，您可以键入**中字符串**文本框中，然后单击**搜索**按钮。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-114">If you know part of the name of the orchestration for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="2f9a9-115">搜索结果中将只显示那些包含您所输入的部分字符串的业务流程。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-115">This will select only those orchestrations that contain the partial string you have entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f9a9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f9a9-116">See Also</span></span>  
 <span data-ttu-id="2f9a9-117">[源事件视图是什么？](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="2f9a9-117">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="2f9a9-118">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="2f9a9-118">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)