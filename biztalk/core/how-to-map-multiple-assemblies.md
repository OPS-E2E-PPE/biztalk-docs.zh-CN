---
title: "如何将多个程序集映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, tracking profiles
- tracking profiles, mapping assemblies
- assemblies, maps
ms.assetid: 136f1943-9643-4551-8b5b-150c4b4bfebe
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a55b6e88889ccfa36adcac11fe548ab1b25bc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-multiple-assemblies"></a><span data-ttu-id="09a32-102">如何映射多个程序集</span><span class="sxs-lookup"><span data-stu-id="09a32-102">How to Map Multiple Assemblies</span></span>
<span data-ttu-id="09a32-103">BizTalk 应用程序可包含多个含有 BAM 活动所引用的数据项的程序集。</span><span class="sxs-lookup"><span data-stu-id="09a32-103">BizTalk applications can consist of multiple assemblies in which the data items that a BAM activity references reside.</span></span> <span data-ttu-id="09a32-104">以下过程说明如何将多个程序集映射到一个跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="09a32-104">The following procedure shows you how to map multiple assemblies to a tracking profile.</span></span>  
  
### <a name="to-map-multiple-assemblies"></a><span data-ttu-id="09a32-105">映射多个程序集</span><span class="sxs-lookup"><span data-stu-id="09a32-105">To map multiple assemblies</span></span>  
  
1.  <span data-ttu-id="09a32-106">打开现有的跟踪配置文件，或创建一个新跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="09a32-106">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="09a32-107">有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="09a32-107">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="09a32-108">单击**选择事件源**按钮 （位于右窗格中的跟踪配置文件中相应的编辑器上方）。</span><span class="sxs-lookup"><span data-stu-id="09a32-108">Click the **Select Event Source** button (located above the right pane in the Tracking Profile Editor).</span></span>  
  
3.  <span data-ttu-id="09a32-109">选择**选择业务流程计划**从级联菜单的菜单项。</span><span class="sxs-lookup"><span data-stu-id="09a32-109">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
4.  <span data-ttu-id="09a32-110">选择要从中业务流程，通过单击包含业务流程中的程序集的父程序集**程序集名称**列表框中，并依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="09a32-110">Select the parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="09a32-111">选择是中的数据项的源的业务流程**Orchestration 名称**列表框中，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="09a32-111">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="09a32-112">在右窗格中选择数据项，然后将其拖动到左窗格的活动中的相应节点。</span><span class="sxs-lookup"><span data-stu-id="09a32-112">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
7.  <span data-ttu-id="09a32-113">重复步骤 2 至 6 映射其他程序集。</span><span class="sxs-lookup"><span data-stu-id="09a32-113">Repeat steps 2 through 6 to map additional assemblies.</span></span>  
  
### <a name="to-map-the-second-assembly"></a><span data-ttu-id="09a32-114">映射第二个程序集</span><span class="sxs-lookup"><span data-stu-id="09a32-114">To map the second assembly</span></span>  
  
1.  <span data-ttu-id="09a32-115">单击**选择事件源**。</span><span class="sxs-lookup"><span data-stu-id="09a32-115">Click the **Select Event Source**.</span></span>  
  
2.  <span data-ttu-id="09a32-116">选择**选择业务流程计划**从级联菜单的菜单项。</span><span class="sxs-lookup"><span data-stu-id="09a32-116">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
3.  <span data-ttu-id="09a32-117">选择要从中通过单击包含业务流程中的程序集的业务流程的下一步父程序集**程序集名称**列表框中，并依次**下一步**按钮。</span><span class="sxs-lookup"><span data-stu-id="09a32-117">Select the next parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click the **Next** button.</span></span>  
  
4.  <span data-ttu-id="09a32-118">选择是中的数据项的源的业务流程**Orchestration 名称**列表框中，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="09a32-118">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="09a32-119">在右窗格中选择数据项，然后将其拖动到左窗格的活动中的相应节点。</span><span class="sxs-lookup"><span data-stu-id="09a32-119">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a32-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09a32-120">See Also</span></span>  
 <span data-ttu-id="09a32-121">[如何将映射事件源](../core/how-to-map-event-sources.md) </span><span class="sxs-lookup"><span data-stu-id="09a32-121">[How to Map Event Sources](../core/how-to-map-event-sources.md) </span></span>  
 [<span data-ttu-id="09a32-122">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="09a32-122">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)