---
title: 确定丢失的跟踪数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, HAT
- reporting tools
- Orchestration Debugger
- Tracking database, data loss
- HAT, data loss
- HAT, Operation View tool
- HAT, reporting tools
- Operation View tool, MessageBox database
- MessageBox database, Operation View tool
- Operation View tool, data loss
ms.assetid: 1ac13e2c-cd5e-437e-b924-d4547931874e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17116d3a560e968e8dd9da0e42f5af221c23f5d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982854"
---
# <a name="identifying-lost-tracking-data"></a><span data-ttu-id="ec19b-102">确定丢失的跟踪数据</span><span class="sxs-lookup"><span data-stu-id="ec19b-102">Identifying Lost Tracking Data</span></span>
<span data-ttu-id="ec19b-103">您可以使用 BizTalk Server 管理控制台来帮助标识哪些跟踪数据已因硬件失败而丢失。</span><span class="sxs-lookup"><span data-stu-id="ec19b-103">You can use the BizTalk Server Administration console to help identify which tracking data has been lost as a result of a hardware failure.</span></span> <span data-ttu-id="ec19b-104">您可以将 BizTalk Server 管理控制台用于实时数据或存档数据。</span><span class="sxs-lookup"><span data-stu-id="ec19b-104">You can use the BizTalk Server Administration console for live or archived data.</span></span>  
  
 <span data-ttu-id="ec19b-105">在 BizTalk Server 管理控制台可用于确定哪些服务处于活动状态恢复 MessageBox 时的时间。</span><span class="sxs-lookup"><span data-stu-id="ec19b-105">You can use the BizTalk Server Administration console to determine which services were active at the time the MessageBox was recovered.</span></span> <span data-ttu-id="ec19b-106">由于在恢复该数据库和发生硬件故障之间有时间差，因此可能无法确定某些事务的状态。</span><span class="sxs-lookup"><span data-stu-id="ec19b-106">Because there is a gap between the time that the database was recovered and the time of the hardware failure, you may not be able to determine the state of some of the transactions.</span></span>  
  
 <span data-ttu-id="ec19b-107">您可以使用跟踪数据来标识在恢复点后完成和启动的服务实例，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ec19b-107">You can use tracking data to identify which service instances completed and started after the point of recovery, as follows:</span></span>  
  
- <span data-ttu-id="ec19b-108">寻找自上次备份数据库以后完成或启动的实例。</span><span class="sxs-lookup"><span data-stu-id="ec19b-108">Look for which instances completed or started since the last time you backed up the database.</span></span>  
  
- <span data-ttu-id="ec19b-109">如果 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据指示消息已启动但未完成并且该消息不在数据库中，则该消息是在上一次备份之后发送的。</span><span class="sxs-lookup"><span data-stu-id="ec19b-109">If data in the BizTalk Tracking (BizTalkDTADb) database indicates that the message started but did not complete, and the message is not in the database, then that message was sent after the last backup.</span></span>  
  
  <span data-ttu-id="ec19b-110">跟踪可以报告任何已完成的服务，并且可以指示服务已启动。</span><span class="sxs-lookup"><span data-stu-id="ec19b-110">Tracking can report on any service that completed, and it can indicate that a service started.</span></span> <span data-ttu-id="ec19b-111">跟踪数据首先临时保存在 MessageBox 中，然后被移到 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="ec19b-111">Tracking data is first staged to the MessageBox and then moved to the BizTalk Tracking database.</span></span> <span data-ttu-id="ec19b-112">临时保存的数据可能会由于 BAM 事件总线服务积压而丢失。</span><span class="sxs-lookup"><span data-stu-id="ec19b-112">The data that was staged may have been lost to the backlog of the BAM Event Bus service.</span></span>  
  
  <span data-ttu-id="ec19b-113">尽管出于操作原因，所有数据库都需要还原到同一标记，但是您可以使用存档模式下的 BizTalk 跟踪数据库（未丢失）查看在该标记之后执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ec19b-113">While all databases need to be restored to the same mark for operational reasons, you can use a BizTalk Tracking database (that was not lost) in Archive mode to see what happened after the mark.</span></span>  
  
  <span data-ttu-id="ec19b-114">如果跟踪显示某个服务实例已完成，则可以终止该实例。</span><span class="sxs-lookup"><span data-stu-id="ec19b-114">If tracking shows a service instance as having completed, you can terminate that instance.</span></span> <span data-ttu-id="ec19b-115">它可以显示在恢复点之后启动的实例。</span><span class="sxs-lookup"><span data-stu-id="ec19b-115">It may show instances that started after the point of recovery.</span></span> <span data-ttu-id="ec19b-116">如果这样，您将需要补偿这些实例所执行的任何操作，然后重新提交它们的初始激活消息。</span><span class="sxs-lookup"><span data-stu-id="ec19b-116">If so, you will need to compensate for any actions these instances took and then resubmit their initial activation messages.</span></span>  
  
  <span data-ttu-id="ec19b-117">您可以使用业务流程调试器查看最后执行的形状，然后使用“消息流”查看本应发送或接收的消息。</span><span class="sxs-lookup"><span data-stu-id="ec19b-117">You can use the Orchestration Debugger to see the last shapes that executed, and then use Message Flow to see what message should have been sent or received.</span></span>  
  
  <span data-ttu-id="ec19b-118">如果 BizTalk 跟踪数据库丢失，则需要使用外部系统报告机制来查找恢复点之后执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="ec19b-118">If the BizTalk Tracking database was lost, all discovery of what happened past the point of recovery will need to be done by using the external systems reporting mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec19b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec19b-119">See Also</span></span>  
 [<span data-ttu-id="ec19b-120">解决数据丢失问题</span><span class="sxs-lookup"><span data-stu-id="ec19b-120">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)