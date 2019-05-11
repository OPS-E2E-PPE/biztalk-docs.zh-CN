---
title: 如何将多个程序集映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, tracking profiles
- tracking profiles, mapping assemblies
- assemblies, maps
ms.assetid: 136f1943-9643-4551-8b5b-150c4b4bfebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bdd70b7790599255ccd802d7f0e290df763982c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336344"
---
# <a name="how-to-map-multiple-assemblies"></a><span data-ttu-id="8487a-102">如何映射多个程序集</span><span class="sxs-lookup"><span data-stu-id="8487a-102">How to Map Multiple Assemblies</span></span>
<span data-ttu-id="8487a-103">BizTalk 应用程序可以包含多个 BAM 活动所引用的数据项目驻留在其中的程序集。</span><span class="sxs-lookup"><span data-stu-id="8487a-103">BizTalk applications can consist of multiple assemblies in which the data items that a BAM activity references reside.</span></span> <span data-ttu-id="8487a-104">以下过程演示如何将多个程序集映射到跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="8487a-104">The following procedure shows you how to map multiple assemblies to a tracking profile.</span></span>  
  
### <a name="to-map-multiple-assemblies"></a><span data-ttu-id="8487a-105">若要将多个程序集映射</span><span class="sxs-lookup"><span data-stu-id="8487a-105">To map multiple assemblies</span></span>  
  
1.  <span data-ttu-id="8487a-106">打开现有的跟踪配置文件或创建新的跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="8487a-106">Open an existing tracking profile or create a new tracking profile.</span></span> <span data-ttu-id="8487a-107">有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="8487a-107">For more information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="8487a-108">单击**选择事件源**按钮 （位于跟踪配置文件编辑器中的右窗格上方）。</span><span class="sxs-lookup"><span data-stu-id="8487a-108">Click the **Select Event Source** button (located above the right pane in the Tracking Profile Editor).</span></span>  
  
3.  <span data-ttu-id="8487a-109">选择**选择业务流程计划**级联菜单中的菜单项。</span><span class="sxs-lookup"><span data-stu-id="8487a-109">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
4.  <span data-ttu-id="8487a-110">选择要从中提取业务流程通过单击包含业务流程中的程序集的父程序集**程序集名称**列表框中，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8487a-110">Select the parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="8487a-111">选择业务流程中的数据项的源**业务流程名称**列表框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8487a-111">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="8487a-112">在右窗格中选择的数据项目，并将其拖到左窗格中的活动中的相应节点。</span><span class="sxs-lookup"><span data-stu-id="8487a-112">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
7.  <span data-ttu-id="8487a-113">重复步骤 2 到 6 映射其他程序集。</span><span class="sxs-lookup"><span data-stu-id="8487a-113">Repeat steps 2 through 6 to map additional assemblies.</span></span>  
  
### <a name="to-map-the-second-assembly"></a><span data-ttu-id="8487a-114">若要映射的第二个程序集</span><span class="sxs-lookup"><span data-stu-id="8487a-114">To map the second assembly</span></span>  
  
1.  <span data-ttu-id="8487a-115">单击**选择事件源**。</span><span class="sxs-lookup"><span data-stu-id="8487a-115">Click the **Select Event Source**.</span></span>  
  
2.  <span data-ttu-id="8487a-116">选择**选择业务流程计划**级联菜单中的菜单项。</span><span class="sxs-lookup"><span data-stu-id="8487a-116">Select the **Select Orchestration Schedule** menu item from the cascading menu.</span></span>  
  
3.  <span data-ttu-id="8487a-117">选择要从中提取业务流程通过单击包含业务流程中的程序集的下一步父程序集**程序集名称**列表框中，，然后单击**下一步**按钮。</span><span class="sxs-lookup"><span data-stu-id="8487a-117">Select the next parent assembly from which to draw the orchestration by clicking the assembly containing the orchestration in the **Assembly Name** list box, and then click the **Next** button.</span></span>  
  
4.  <span data-ttu-id="8487a-118">选择业务流程中的数据项的源**业务流程名称**列表框中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8487a-118">Select the orchestration that is the source for the data items in the **Orchestration Names** list box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="8487a-119">在右窗格中选择的数据项目，并将其拖到左窗格中的活动中的相应节点。</span><span class="sxs-lookup"><span data-stu-id="8487a-119">Select the data items in the right pane and drag them to the appropriate nodes in the activity in the left pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8487a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8487a-120">See Also</span></span>  
 <span data-ttu-id="8487a-121">[如何将映射事件源](../core/how-to-map-event-sources.md) </span><span class="sxs-lookup"><span data-stu-id="8487a-121">[How to Map Event Sources](../core/how-to-map-event-sources.md) </span></span>  
 [<span data-ttu-id="8487a-122">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="8487a-122">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)