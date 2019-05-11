---
title: 关系节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definition files [BAM], relationships
- definition files [BAM], Tracking Profile Editor
- Relationship nodes [Tracking Profile Editor]
- activities [BAM], relationships
- activities [BAM], Tracking Profile Editor
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 74090133-24d1-4aba-a4fc-f12d19c881fb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7acbed8914fa7af8c80e739c9d29279df1054d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397985"
---
# <a name="relationship-nodes"></a><span data-ttu-id="2e33f-102">关系节点</span><span class="sxs-lookup"><span data-stu-id="2e33f-102">Relationship Nodes</span></span>
<span data-ttu-id="2e33f-103">当活动定义文件中包含多个活动时使用关系文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e33f-103">Relationship folders are used whenever an activity definition file contains more than one activity.</span></span> <span data-ttu-id="2e33f-104">文件夹的名称匹配关联的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="2e33f-104">The names of the folders match the name of the associated activity.</span></span> <span data-ttu-id="2e33f-105">通过向相关活动的活动 ID 的关系文件夹的名称匹配的和匹配的值的数据项目，可以形成链接。</span><span class="sxs-lookup"><span data-stu-id="2e33f-105">You form the link by matching the name of the relationship folder to the activity ID of the related activity and by matching the values for the data items.</span></span> <span data-ttu-id="2e33f-106">定义使用单独的节点的每个关系。</span><span class="sxs-lookup"><span data-stu-id="2e33f-106">You define each relationship using a separate node.</span></span>  
  
## <a name="working-with-relationship-nodes"></a><span data-ttu-id="2e33f-107">使用关系节点</span><span class="sxs-lookup"><span data-stu-id="2e33f-107">Working with Relationship nodes</span></span>  
 <span data-ttu-id="2e33f-108">指示链接的活动之间的数据项目的唯一实例标识符：</span><span class="sxs-lookup"><span data-stu-id="2e33f-108">To indicate the unique instance identifier that links the data item between activities:</span></span>  
  
- <span data-ttu-id="2e33f-109">将一个数据项映射到主业务流程的 ActivityId 节点。</span><span class="sxs-lookup"><span data-stu-id="2e33f-109">Map a data item to the ActivityId node of the main orchestration.</span></span>  
  
- <span data-ttu-id="2e33f-110">拖放相关活动中具有相同的名称上面的关系节点到的数据项。</span><span class="sxs-lookup"><span data-stu-id="2e33f-110">Drag and drop a data item with the same name as above to the Relationship node in the related activity.</span></span> <span data-ttu-id="2e33f-111">关系节点具有与主活动的活动节点相同的名称。</span><span class="sxs-lookup"><span data-stu-id="2e33f-111">The Relationship node has the same name as the Activity node of the main activity.</span></span>  
  
  <span data-ttu-id="2e33f-112">例如，在示例方案中，可能有相关但不同的业务流程表示在调用 RefinanceOrchestration 业务流程中。</span><span class="sxs-lookup"><span data-stu-id="2e33f-112">For example, in the sample scenario, there could be a related but separate business process represented in an orchestration called RefinanceOrchestration.</span></span> <span data-ttu-id="2e33f-113">该业务流程可以包含 LoanRefinance 活动节点、 Refinance ActivityID 和业务流程形状，如接收评价请求。</span><span class="sxs-lookup"><span data-stu-id="2e33f-113">That orchestration could contain a LoanRefinance Activity node, a Refinance ActivityID, and orchestration shapes such as Receive Appraisal Request.</span></span> <span data-ttu-id="2e33f-114">关系节点和关系 ID，但是，可以是 LoanID，指示链接到原始 LoanProcess 活动。</span><span class="sxs-lookup"><span data-stu-id="2e33f-114">The Relationship node and relationship ID, however, could be LoanID, indicating the link to the original LoanProcess activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e33f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e33f-115">See Also</span></span>  
 [<span data-ttu-id="2e33f-116">“TPE 活动视图”节点</span><span class="sxs-lookup"><span data-stu-id="2e33f-116">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)