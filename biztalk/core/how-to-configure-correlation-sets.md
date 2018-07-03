---
title: 如何配置相关集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, send activities
- correlation sets, assigning correlation types
- correlation types, correlation sets
- correlation sets, receive activities
- configuring, correlation sets
- correlation sets, configuring
- correlation types, assigning
ms.assetid: 060bf2ba-c173-4dca-a8c4-4c5341e5ceaa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c56d7f319023bb0379050452253c65634929c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968854"
---
# <a name="how-to-configure-correlation-sets"></a><span data-ttu-id="ae71a-102">如何配置相关集</span><span class="sxs-lookup"><span data-stu-id="ae71a-102">How to Configure Correlation Sets</span></span>
<span data-ttu-id="ae71a-103">若要配置相关集，您可以选择现有相关类型、创建新的相关类型或修改现有相关类型。</span><span class="sxs-lookup"><span data-stu-id="ae71a-103">To configure your correlation set, you can select an existing correlation type, create a new correlation type, or modify an existing correlation type.</span></span>  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a><span data-ttu-id="ae71a-104">向相关集分配相关类型</span><span class="sxs-lookup"><span data-stu-id="ae71a-104">To assign a correlation type to a correlation set</span></span>  
  
- <span data-ttu-id="ae71a-105">选择现有相关类型。</span><span class="sxs-lookup"><span data-stu-id="ae71a-105">Select an existing correlation type.</span></span>  
  
   <span data-ttu-id="ae71a-106">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="ae71a-106">\- Or -</span></span>  
  
   <span data-ttu-id="ae71a-107">右键单击新相关类型并选择**配置相关性属性**。</span><span class="sxs-lookup"><span data-stu-id="ae71a-107">Right-click the new correlation type and select **Configure Correlation Properties**.</span></span>  
  
   <span data-ttu-id="ae71a-108">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="ae71a-108">\- Or -</span></span>  
  
   <span data-ttu-id="ae71a-109">单击省略号 (**...**) 按钮**相关**中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="ae71a-109">Click the Ellipsis (**...**) button on **Correlation** Properties in the **Properties** window.</span></span>  
  
   <span data-ttu-id="ae71a-110">**相关性属性**弹出对话框。</span><span class="sxs-lookup"><span data-stu-id="ae71a-110">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="ae71a-111">添加要包含在相关集中的属性。</span><span class="sxs-lookup"><span data-stu-id="ae71a-111">Add properties that you want to include in your correlation set.</span></span> <span data-ttu-id="ae71a-112">如果尚未将相关类型分配给相关集，则将创建一个新相关类型。</span><span class="sxs-lookup"><span data-stu-id="ae71a-112">If a correlation type was not already assigned to your correlation set, a new correlation type will be created.</span></span>  
  
  <span data-ttu-id="ae71a-113">如果某一相关类型已存在的相关集，并且添加或删除具有的属性**相关性属性**对话框中，现有相关类型将进行相应修改。</span><span class="sxs-lookup"><span data-stu-id="ae71a-113">If a correlation type already exists for your correlation set, and you add or remove properties with the **Correlation Properties** dialog box, the existing correlation type will be modified.</span></span>  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a><span data-ttu-id="ae71a-114">将发送和接收活动与相关集相关联</span><span class="sxs-lookup"><span data-stu-id="ae71a-114">To associate send and receive activities with a correlation set</span></span>  
  
1.  <span data-ttu-id="ae71a-115">展开**相关集**节点。</span><span class="sxs-lookup"><span data-stu-id="ae71a-115">Expand the **Correlation Set** node.</span></span>  
  
2.  <span data-ttu-id="ae71a-116">从下拉列表中选择发送或接收活动。</span><span class="sxs-lookup"><span data-stu-id="ae71a-116">Select a send or receive activity from the drop-down.</span></span>  
  
     <span data-ttu-id="ae71a-117">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="ae71a-117">\- Or -</span></span>  
  
     <span data-ttu-id="ae71a-118">选择相关集中任意一种**初始化相关集**属性或**沿用相关集**中的属性**属性**为每个窗口**发送**或**接收**你想要将与相关集相关联的形状。</span><span class="sxs-lookup"><span data-stu-id="ae71a-118">Select the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to associate with the correlation set.</span></span>  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a><span data-ttu-id="ae71a-119">取消发送和接收活动与相关集的关联</span><span class="sxs-lookup"><span data-stu-id="ae71a-119">To disassociate send and receive activities from a correlation set</span></span>  
  
-   <span data-ttu-id="ae71a-120">在中**业务流程视图**窗口中，如有必要展开相关集节点，右键单击你想要删除，然后单击的活动**删除**。</span><span class="sxs-lookup"><span data-stu-id="ae71a-120">In the **Orchestration View** window, expand the correlation set node if necessary, right-click the activity you want to remove, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="ae71a-121">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="ae71a-121">\- Or -</span></span>  
  
     <span data-ttu-id="ae71a-122">清除相关集中任意一种**初始化相关集**属性或**沿用相关集**中的属性**属性**窗口中的每个**发送**或**接收**你想要从该相关集取消关联的形状。</span><span class="sxs-lookup"><span data-stu-id="ae71a-122">Clear the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to disassociate from the correlation set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae71a-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae71a-123">See Also</span></span>  
 <span data-ttu-id="ae71a-124">[接收消息形状中使用筛选器](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="ae71a-124">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 [<span data-ttu-id="ae71a-125">在业务流程中使用关联</span><span class="sxs-lookup"><span data-stu-id="ae71a-125">Using Correlations in Orchestrations</span></span>](../core/using-correlations-in-orchestrations.md)