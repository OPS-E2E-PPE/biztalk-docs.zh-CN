---
title: 业务事件节点 |Microsoft Docs
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
ms.openlocfilehash: 213f97f2a0e4276cfc3e49d52ff69c222b6b7959
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357687"
---
# <a name="business-event-nodes"></a><span data-ttu-id="39948-102">业务事件节点</span><span class="sxs-lookup"><span data-stu-id="39948-102">Business Event Nodes</span></span>
<span data-ttu-id="39948-103">业务事件或里程碑节点定义特定于日期或时间的事件。</span><span class="sxs-lookup"><span data-stu-id="39948-103">Business Event or milestone nodes define events that are date- or time-specific.</span></span> <span data-ttu-id="39948-104">从业务最终用户导入活动定义中的预定义的业务事件和里程碑文件夹存在并且不能删除它们而无需重新导入活动定义文件。</span><span class="sxs-lookup"><span data-stu-id="39948-104">Pre-defined business event and milestone folders exist in the activity definition you import from the business end user, and you cannot delete them without reimporting the activity definition file.</span></span>  
  
## <a name="working-with-business-event-nodes"></a><span data-ttu-id="39948-105">使用业务事件节点</span><span class="sxs-lookup"><span data-stu-id="39948-105">Working with business event nodes</span></span>  
 <span data-ttu-id="39948-106">您可以将形状从业务流程拖到业务事件文件夹，以执行形状完成时跟踪这些事件。</span><span class="sxs-lookup"><span data-stu-id="39948-106">You can drag shapes from the orchestration into the Business Events folder to track those events as the execution of the shapes is completed.</span></span>  
  
 <span data-ttu-id="39948-107">TPE 将形状的名称用于事件文件夹的名称和此文件夹将具有一个唯一的图标。</span><span class="sxs-lookup"><span data-stu-id="39948-107">TPE uses the name of the shape for the name of the event folder, and this folder will have a unique icon.</span></span> <span data-ttu-id="39948-108">例如，在示例贷款流程方案中，tpe 根据事件，如 Approved 或 Denied。</span><span class="sxs-lookup"><span data-stu-id="39948-108">For example, in the sample loan-process scenario, TPE names them according to the event, such as Approved or Denied.</span></span> <span data-ttu-id="39948-109">该业务流程涉及多个跟踪配置文件时，应只跟踪一次每个业务流程的业务事件。</span><span class="sxs-lookup"><span data-stu-id="39948-109">You should only track business events once per business process when that business process spans multiple tracking profiles.</span></span> <span data-ttu-id="39948-110">如果在业务流程中有一个条件路径，可以选择这两个路径中的业务事件，因为只有一个会执行。</span><span class="sxs-lookup"><span data-stu-id="39948-110">If you have a conditional path in your orchestration, you can select the business event from both paths, as only one will ever execute.</span></span> <span data-ttu-id="39948-111">不应选择一个循环内的形状。</span><span class="sxs-lookup"><span data-stu-id="39948-111">You should not select a shape inside a loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39948-112">虽然您无法删除文件夹，而无需重新导入活动定义，可以删除形状 （事件）。</span><span class="sxs-lookup"><span data-stu-id="39948-112">While you cannot delete folders without reimporting the activity definition, you can delete shapes (events).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39948-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="39948-113">See Also</span></span>  
 [<span data-ttu-id="39948-114">“TPE 活动视图”节点</span><span class="sxs-lookup"><span data-stu-id="39948-114">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)