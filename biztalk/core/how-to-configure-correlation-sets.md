---
title: 如何配置相关设置 |Microsoft 文档
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
ms.openlocfilehash: 52bcb0216fc24e14107c7632df97671b64f2ac1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248165"
---
# <a name="how-to-configure-correlation-sets"></a><span data-ttu-id="7bc07-102">如何配置相关设置</span><span class="sxs-lookup"><span data-stu-id="7bc07-102">How to Configure Correlation Sets</span></span>
<span data-ttu-id="7bc07-103">若要配置相关集，您可以选择现有相关类型、创建新的相关类型或修改现有相关类型。</span><span class="sxs-lookup"><span data-stu-id="7bc07-103">To configure your correlation set, you can select an existing correlation type, create a new correlation type, or modify an existing correlation type.</span></span>  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a><span data-ttu-id="7bc07-104">向相关集分配相关类型</span><span class="sxs-lookup"><span data-stu-id="7bc07-104">To assign a correlation type to a correlation set</span></span>  
  
-   <span data-ttu-id="7bc07-105">选择现有相关类型。</span><span class="sxs-lookup"><span data-stu-id="7bc07-105">Select an existing correlation type.</span></span>  
  
     <span data-ttu-id="7bc07-106">\-或者-</span><span class="sxs-lookup"><span data-stu-id="7bc07-106">\- Or -</span></span>  
  
     <span data-ttu-id="7bc07-107">右键单击新的相关类型并选择**配置相关性属性**。</span><span class="sxs-lookup"><span data-stu-id="7bc07-107">Right-click the new correlation type and select **Configure Correlation Properties**.</span></span>  
  
     <span data-ttu-id="7bc07-108">\-或者-</span><span class="sxs-lookup"><span data-stu-id="7bc07-108">\- Or -</span></span>  
  
     <span data-ttu-id="7bc07-109">单击省略号 (**...**) 上的按钮**相关**中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="7bc07-109">Click the Ellipsis (**...**) button on **Correlation** Properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="7bc07-110">**相关性属性**弹出对话框。</span><span class="sxs-lookup"><span data-stu-id="7bc07-110">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="7bc07-111">添加要包含在相关集中的属性。</span><span class="sxs-lookup"><span data-stu-id="7bc07-111">Add properties that you want to include in your correlation set.</span></span> <span data-ttu-id="7bc07-112">如果尚未将相关类型分配给相关集，则将创建一个新相关类型。</span><span class="sxs-lookup"><span data-stu-id="7bc07-112">If a correlation type was not already assigned to your correlation set, a new correlation type will be created.</span></span>  
  
 <span data-ttu-id="7bc07-113">如果你的关联集，已存在的相关类型和添加或删除具有属性**相关性属性**对话框中，现有相关性类型将进行相应修改。</span><span class="sxs-lookup"><span data-stu-id="7bc07-113">If a correlation type already exists for your correlation set, and you add or remove properties with the **Correlation Properties** dialog box, the existing correlation type will be modified.</span></span>  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a><span data-ttu-id="7bc07-114">将发送和接收活动与相关集相关联</span><span class="sxs-lookup"><span data-stu-id="7bc07-114">To associate send and receive activities with a correlation set</span></span>  
  
1.  <span data-ttu-id="7bc07-115">展开**相关设置**节点。</span><span class="sxs-lookup"><span data-stu-id="7bc07-115">Expand the **Correlation Set** node.</span></span>  
  
2.  <span data-ttu-id="7bc07-116">从下拉列表中选择发送或接收活动。</span><span class="sxs-lookup"><span data-stu-id="7bc07-116">Select a send or receive activity from the drop-down.</span></span>  
  
     <span data-ttu-id="7bc07-117">\-或者-</span><span class="sxs-lookup"><span data-stu-id="7bc07-117">\- Or -</span></span>  
  
     <span data-ttu-id="7bc07-118">选择设置中的相关**初始化关联集**属性或**以下相关集**中的属性**属性**每个窗口**发送**或**接收**你想要将与相关集相关联的形状。</span><span class="sxs-lookup"><span data-stu-id="7bc07-118">Select the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to associate with the correlation set.</span></span>  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a><span data-ttu-id="7bc07-119">取消发送和接收活动与相关集的关联</span><span class="sxs-lookup"><span data-stu-id="7bc07-119">To disassociate send and receive activities from a correlation set</span></span>  
  
-   <span data-ttu-id="7bc07-120">在**业务流程视图**窗口中，根据需要展开相关集节点，右键单击你想要删除，，然后单击的活动**删除**。</span><span class="sxs-lookup"><span data-stu-id="7bc07-120">In the **Orchestration View** window, expand the correlation set node if necessary, right-click the activity you want to remove, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="7bc07-121">\-或者-</span><span class="sxs-lookup"><span data-stu-id="7bc07-121">\- Or -</span></span>  
  
     <span data-ttu-id="7bc07-122">清除关联集在**初始化关联集**属性或**以下相关集**中的属性**属性**每个窗口**发送**或**接收**你想要解除与相关集关联的形状。</span><span class="sxs-lookup"><span data-stu-id="7bc07-122">Clear the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to disassociate from the correlation set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc07-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bc07-123">See Also</span></span>  
 <span data-ttu-id="7bc07-124">[使用接收消息形状使用筛选器](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="7bc07-124">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 [<span data-ttu-id="7bc07-125">在业务流程中使用相关性</span><span class="sxs-lookup"><span data-stu-id="7bc07-125">Using Correlations in Orchestrations</span></span>](../core/using-correlations-in-orchestrations.md)