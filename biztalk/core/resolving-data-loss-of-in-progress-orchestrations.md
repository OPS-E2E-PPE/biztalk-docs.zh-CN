---
title: 解决正在进行中的业务流程的数据丢失问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, MessageBox database
- data recovery
- data loss, recovery
- data loss, orchestrations
- data recovery, MessageBox database
- data recovery, orchestrations
- data loss, data recovery
- orchestrations, data recovery
- orchestrations, data loss
ms.assetid: dc6f1fd2-1976-40f2-ab57-41c7db40705e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caef8b0cb30b739406a64a6f1ee5add8939ac38e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254972"
---
# <a name="resolving-data-loss-of-in-progress-orchestrations"></a><span data-ttu-id="53ea1-102">解决正在进行中的业务流程的数据丢失问题</span><span class="sxs-lookup"><span data-stu-id="53ea1-102">Resolving Data Loss of In-Progress Orchestrations</span></span>
<span data-ttu-id="53ea1-103">MessageBox 数据库包含当前正在进行的业务流程的状态。</span><span class="sxs-lookup"><span data-stu-id="53ea1-103">MessageBox databases contain the state of orchestrations that are currently in progress.</span></span> <span data-ttu-id="53ea1-104">尽管无法知道哪些数据已被完全从 MessageBox 数据库中丢失，但有一些可用于收集有关数据丢失的信息的步骤：</span><span class="sxs-lookup"><span data-stu-id="53ea1-104">Although there is no way to tell exactly what data has been lost from the MessageBox databases, there are some steps you can take to gather information about the lost data:</span></span>  
  
-   <span data-ttu-id="53ea1-105">确定哪些消息已发送并收到在当前业务流程，以及哪些外部系统已使用的恢复点后。</span><span class="sxs-lookup"><span data-stu-id="53ea1-105">Determine what messages have been sent and received in the current orchestrations, and what external systems have been used after the point of recovery.</span></span> <span data-ttu-id="53ea1-106">例如，如果您的系统维护外部的消息和事件日志，可以检查该日志。</span><span class="sxs-lookup"><span data-stu-id="53ea1-106">For example, if your system maintains an external log of messages and events, you can examine that log.</span></span> <span data-ttu-id="53ea1-107">您可能还需要手动查看外部系统，以查看发生了哪些活动。</span><span class="sxs-lookup"><span data-stu-id="53ea1-107">You may also need to manually review the external systems to see what activities have occurred.</span></span>  
  
-   <span data-ttu-id="53ea1-108">确定数据丢失的原因后，便可以更正已还原的系统，确定哪些进程可以继续，必须终止的进程，并将其重新启动 （通过重新提交丢失的激活消息），以及哪些过程都已完成已成功，可以终止。</span><span class="sxs-lookup"><span data-stu-id="53ea1-108">After you determine the cause of the data loss, you can begin to correct the restored system, deciding which processes can continue, which processes must be terminated and restarted (by resubmitting the lost activation messages), and which processes have completed successfully and can be terminated.</span></span> <span data-ttu-id="53ea1-109">此过程很大程度上取决于您的系统的体系结构，必须考虑作为系统恢复规划的一部分。</span><span class="sxs-lookup"><span data-stu-id="53ea1-109">This process depends largely on the architecture of your system and must be considered as part of your system recovery planning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53ea1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="53ea1-110">See Also</span></span>  
 [<span data-ttu-id="53ea1-111">解决数据丢失问题</span><span class="sxs-lookup"><span data-stu-id="53ea1-111">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)