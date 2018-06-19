---
title: 业务事件节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, Tracking Profile Editor
- events, date specific
- events, time specific
- Tracking Profile Editor, node descriptions
- Business Event nodes [Tracking Profile Editor]
- Tracking Profile Editor, events
ms.assetid: 177bc3c4-e762-42fe-80bc-edede5cd4fcd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44c3d06e553f129abb36eb53c4dde9c5ab9c25f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230901"
---
# <a name="business-event-nodes"></a><span data-ttu-id="c17ed-102">业务事件节点</span><span class="sxs-lookup"><span data-stu-id="c17ed-102">Business Event Nodes</span></span>
<span data-ttu-id="c17ed-103">业务事件节点或里程碑节点定义特定于日期或时间的事件。</span><span class="sxs-lookup"><span data-stu-id="c17ed-103">Business Event or milestone nodes define events that are date- or time-specific.</span></span> <span data-ttu-id="c17ed-104">预定义的业务事件文件夹和里程碑文件夹包含在从业务最终用户导入的活动定义中，您在没有重新导入活动定义文件时不能删除这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="c17ed-104">Pre-defined business event and milestone folders exist in the activity definition you import from the business end user, and you cannot delete them without reimporting the activity definition file.</span></span>  
  
## <a name="working-with-business-event-nodes"></a><span data-ttu-id="c17ed-105">使用业务事件节点</span><span class="sxs-lookup"><span data-stu-id="c17ed-105">Working with business event nodes</span></span>  
 <span data-ttu-id="c17ed-106">可以将业务流程中的形状拖动到业务事件文件夹，以在执行形状完成时跟踪这些事件。</span><span class="sxs-lookup"><span data-stu-id="c17ed-106">You can drag shapes from the orchestration into the Business Events folder to track those events as the execution of the shapes is completed.</span></span>  
  
 <span data-ttu-id="c17ed-107">TPE 将形状的名称用作事件文件夹的名称，并且此文件夹将具有一个唯一的图标。</span><span class="sxs-lookup"><span data-stu-id="c17ed-107">TPE uses the name of the shape for the name of the event folder, and this folder will have a unique icon.</span></span> <span data-ttu-id="c17ed-108">例如，在贷款流程方案示例中，TPE 根据事件命名文件夹（如 Approved 或 Denied）。</span><span class="sxs-lookup"><span data-stu-id="c17ed-108">For example, in the sample loan-process scenario, TPE names them according to the event, such as Approved or Denied.</span></span> <span data-ttu-id="c17ed-109">当业务流程涉及多个跟踪配置文件时，对每个业务流程应只跟踪一次业务事件。</span><span class="sxs-lookup"><span data-stu-id="c17ed-109">You should only track business events once per business process when that business process spans multiple tracking profiles.</span></span> <span data-ttu-id="c17ed-110">如果业务流程中有一个条件路径，则可以从条件的两个路径中选择业务事件，而只会执行一个路径中的业务事件。</span><span class="sxs-lookup"><span data-stu-id="c17ed-110">If you have a conditional path in your orchestration, you can select the business event from both paths, as only one will ever execute.</span></span> <span data-ttu-id="c17ed-111">不要选择循环内的形状。</span><span class="sxs-lookup"><span data-stu-id="c17ed-111">You should not select a shape inside a loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c17ed-112">不重新导入活动定义就不能删除文件夹，但可以删除形状（事件）。</span><span class="sxs-lookup"><span data-stu-id="c17ed-112">While you cannot delete folders without reimporting the activity definition, you can delete shapes (events).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17ed-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c17ed-113">See Also</span></span>  
 [<span data-ttu-id="c17ed-114">键入活动视图节点</span><span class="sxs-lookup"><span data-stu-id="c17ed-114">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)