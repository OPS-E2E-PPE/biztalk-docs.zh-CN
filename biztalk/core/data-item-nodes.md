---
title: "数据项节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definition files [BAM], data items
- Data Item nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 95856bfa-90e3-49d9-b55b-5f1b35a23f78
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a968bf7533697922938eeb8953f17813c77147c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-item-nodes"></a><span data-ttu-id="23e9c-102">数据项节点</span><span class="sxs-lookup"><span data-stu-id="23e9c-102">Data Item Nodes</span></span>
<span data-ttu-id="23e9c-103">数据项节点存在于开发人员从业务分析员创建的观察模型所导入的活动定义文件中。</span><span class="sxs-lookup"><span data-stu-id="23e9c-103">Data Item nodes exist in the activity definition file that the developer imports from the created observation model created by the business analyst.</span></span> <span data-ttu-id="23e9c-104">跟踪配置文件编辑器 (TPE) 将为所跟踪的数据项命名相应的节点（如“客户姓名”）。</span><span class="sxs-lookup"><span data-stu-id="23e9c-104">The Tracking Profile Editor (TPE) names them for the data items they are tracking, such as Customer Name.</span></span> <span data-ttu-id="23e9c-105">然后，您可以将一个或多个数据项从消息架构视图拖到对应于“客户姓名”的节点。</span><span class="sxs-lookup"><span data-stu-id="23e9c-105">You then drop one or more data items from the Message Schema View onto the node that corresponds to Customer Name.</span></span>  
  
## <a name="working-with-data-item-nodes"></a><span data-ttu-id="23e9c-106">使用数据项节点</span><span class="sxs-lookup"><span data-stu-id="23e9c-106">Working with data item nodes</span></span>  
 <span data-ttu-id="23e9c-107">映射数据项节点时，如果业务流程涉及多个跟踪配置文件，则只应在每个业务流程中跟踪数据项一次。</span><span class="sxs-lookup"><span data-stu-id="23e9c-107">When mapping Data Item nodes you should only track data items once per business process when that business process spans multiple tracking profiles.</span></span> <span data-ttu-id="23e9c-108">如果业务流程中有一个条件路径，则可以同时从这两个路径中选择数据项，因为只运行其中一个。</span><span class="sxs-lookup"><span data-stu-id="23e9c-108">If you have a conditional path in your orchestration, you can select the data item from both paths because only one will run.</span></span> <span data-ttu-id="23e9c-109">但是，除非每一迭代数据项的值都不同，否则请不要选择循环中的形状。</span><span class="sxs-lookup"><span data-stu-id="23e9c-109">However, you should not choose a shape inside a loop unless the values will be different for the data item with each iteration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e9c-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23e9c-110">See Also</span></span>  
 <span data-ttu-id="23e9c-111">[如何将映射项数据](../core/how-to-map-item-data.md) </span><span class="sxs-lookup"><span data-stu-id="23e9c-111">[How to Map Item Data](../core/how-to-map-item-data.md) </span></span>  
 [<span data-ttu-id="23e9c-112">键入活动视图节点</span><span class="sxs-lookup"><span data-stu-id="23e9c-112">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)