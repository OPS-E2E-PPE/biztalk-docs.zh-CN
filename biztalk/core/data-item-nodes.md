---
title: 数据项节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definition files [BAM], data items
- Data Item nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 95856bfa-90e3-49d9-b55b-5f1b35a23f78
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 379e88e074387772678af1c00a7891d7b59cdcfb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389982"
---
# <a name="data-item-nodes"></a><span data-ttu-id="04f75-102">数据项节点</span><span class="sxs-lookup"><span data-stu-id="04f75-102">Data Item Nodes</span></span>
<span data-ttu-id="04f75-103">数据项节点存在，开发人员将从创建由业务分析员的观察模型导入的活动定义文件中。</span><span class="sxs-lookup"><span data-stu-id="04f75-103">Data Item nodes exist in the activity definition file that the developer imports from the created observation model created by the business analyst.</span></span> <span data-ttu-id="04f75-104">跟踪配置文件编辑器 (TPE) 命名这些跟踪，如客户名称的数据项。</span><span class="sxs-lookup"><span data-stu-id="04f75-104">The Tracking Profile Editor (TPE) names them for the data items they are tracking, such as Customer Name.</span></span> <span data-ttu-id="04f75-105">然后从消息架构视图与客户名称相对应的节点上删除一个或多个数据项。</span><span class="sxs-lookup"><span data-stu-id="04f75-105">You then drop one or more data items from the Message Schema View onto the node that corresponds to Customer Name.</span></span>  
  
## <a name="working-with-data-item-nodes"></a><span data-ttu-id="04f75-106">使用数据项节点</span><span class="sxs-lookup"><span data-stu-id="04f75-106">Working with data item nodes</span></span>  
 <span data-ttu-id="04f75-107">映射数据项节点时应只跟踪数据项一次每个业务流程，该业务流程涉及多个跟踪配置文件时。</span><span class="sxs-lookup"><span data-stu-id="04f75-107">When mapping Data Item nodes you should only track data items once per business process when that business process spans multiple tracking profiles.</span></span> <span data-ttu-id="04f75-108">如果在业务流程中有一个条件路径，可以选择这两个路径中的数据项，因为只有一个将运行。</span><span class="sxs-lookup"><span data-stu-id="04f75-108">If you have a conditional path in your orchestration, you can select the data item from both paths because only one will run.</span></span> <span data-ttu-id="04f75-109">但是，除非的值将是不同的每次迭代数据项不应选择一个循环内的形状。</span><span class="sxs-lookup"><span data-stu-id="04f75-109">However, you should not choose a shape inside a loop unless the values will be different for the data item with each iteration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f75-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="04f75-110">See Also</span></span>  
 <span data-ttu-id="04f75-111">[如何映射项数据](../core/how-to-map-item-data.md) </span><span class="sxs-lookup"><span data-stu-id="04f75-111">[How to Map Item Data](../core/how-to-map-item-data.md) </span></span>  
 [<span data-ttu-id="04f75-112">“TPE 活动视图”节点</span><span class="sxs-lookup"><span data-stu-id="04f75-112">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)