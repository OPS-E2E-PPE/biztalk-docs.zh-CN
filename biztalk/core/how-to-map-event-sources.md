---
title: "如何将事件源映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, alerts
- orchestrations, schedules
- events, mapping sources
- orchestrations, tracking profiles
- events, orchestration schedules
- tracking profiles, orchestrations
- tracking profiles, alerts
- alerts, tracking profiles
- alerts, BAM
- tracking profiles, mapping event sources
- events, tracking profiles
ms.assetid: 507f1624-2cd8-4960-8c63-7797ab22519e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 588a394fb3404872554fc786efa3fe24fdd9b47a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-event-sources"></a><span data-ttu-id="cfc17-102">如何将映射事件源</span><span class="sxs-lookup"><span data-stu-id="cfc17-102">How to Map Event Sources</span></span>
<span data-ttu-id="cfc17-103">通过映射事件源可以访问 BAM 跟踪的数据项以生成警报。</span><span class="sxs-lookup"><span data-stu-id="cfc17-103">You map event sources to gain access to data items that BAM tracks to generate alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfc17-104">你可以将映射从四种不同的事件源类型的数据项： 业务流程计划、 消息负载、 上下文属性或消息属性。</span><span class="sxs-lookup"><span data-stu-id="cfc17-104">You can map data items from four different event source types: orchestration schedules, message payloads, context properties, or messaging properties.</span></span> <span data-ttu-id="cfc17-105">本主题简要介绍了从业务流程调度映射数据项的过程。</span><span class="sxs-lookup"><span data-stu-id="cfc17-105">The procedure in this topic outlines mapping data items from an orchestration schedule.</span></span>  
  
### <a name="to-map-an-orchestration-schedule-as-an-event-source"></a><span data-ttu-id="cfc17-106">将业务流程调度作为事件源进行映射</span><span class="sxs-lookup"><span data-stu-id="cfc17-106">To map an orchestration schedule as an event source</span></span>  
  
1.  <span data-ttu-id="cfc17-107">打开现有的跟踪配置文件，或创建一个新跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="cfc17-107">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="cfc17-108">有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc17-108">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="cfc17-109">单击**选择事件源**按钮 （位于右窗格中的跟踪配置文件中相应的编辑器上方）。</span><span class="sxs-lookup"><span data-stu-id="cfc17-109">Click the **Select Event Source** button (located above the right pane in the Tracking Profile Editor).</span></span>  
  
3.  <span data-ttu-id="cfc17-110">选择**选择业务流程计划**从级联菜单的菜单项。</span><span class="sxs-lookup"><span data-stu-id="cfc17-110">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
4.  <span data-ttu-id="cfc17-111">选择要从中业务流程，通过单击包含业务流程中的程序集的父程序集**程序集名称**列表框中，并依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="cfc17-111">Select the parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click **Next**.</span></span>  
  
     <span data-ttu-id="cfc17-112">![为事件中键入源选择父程序集](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")</span><span class="sxs-lookup"><span data-stu-id="cfc17-112">![Select Parent Assembly as event Source in the TPE](../core/media/tpeselectparentassembly.gif "TPESelectParentAssembly")</span></span>  
  
5.  <span data-ttu-id="cfc17-113">选择是中的数据项的源的业务流程**Orchestration 名称**列表框中，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="cfc17-113">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="cfc17-114">在右窗格中选择数据项，然后将其拖动到左窗格的活动中的相应节点。</span><span class="sxs-lookup"><span data-stu-id="cfc17-114">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc17-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfc17-115">See Also</span></span>  
 <span data-ttu-id="cfc17-116">[跟踪配置文件编辑器](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="cfc17-116">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="cfc17-117">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="cfc17-117">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)