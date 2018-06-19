---
title: 如何创建一个延续任务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities, relating events
- tracking profiles, relating events
- continuations, tracking profiles
- activities, continuations
- events, relating
- orchestrations, business events
- tracking profiles, updating
- activities, tracking profiles
- tracking profiles, continuations
- tracking profiles, connecting activities
ms.assetid: 31d6fc24-676e-418c-8e78-1a46b045905d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e63983b290f0f4d7dff544cd2faea45f6cf46adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248845"
---
# <a name="how-to-create-a-continuation"></a><span data-ttu-id="26dea-102">如何创建一个延续任务</span><span class="sxs-lookup"><span data-stu-id="26dea-102">How to Create a Continuation</span></span>
<span data-ttu-id="26dea-103">创建继续符可以指示一个或多个业务流程中的哪些业务活动是通过构造连接的活动来关联的。</span><span class="sxs-lookup"><span data-stu-id="26dea-103">You create continuations to indicate which business events in one or more orchestrations are related by constructing connected activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="26dea-104">如果活动中包含 BAM 继续符，则更新跟踪配置文件可能会影响正在进行的活动实例。</span><span class="sxs-lookup"><span data-stu-id="26dea-104">Updating a tracking profile can impact activity instances in progress if the activity includes a BAM continuation.</span></span> <span data-ttu-id="26dea-105">具体而言，如果在更新跟踪配置文件时指定在下游对已记录的某个活动项进行数据侦听，则原始值可能会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="26dea-105">Specifically, if the update to the tracking profile specifies a downstream interception of data for an activity item already recorded, it is possible that the original value will be overwritten.</span></span> <span data-ttu-id="26dea-106">从本质而言，任何单个事件流将不会受跟踪配置文件更新的应用程序的影响，因为每个流对象是与活动/流开始时处于就绪状态的特定版本的配置文件相联系。</span><span class="sxs-lookup"><span data-stu-id="26dea-106">In essence, any single event stream will not be affected by the application of tracking profile updates because each stream object is tied to the specific version of the profile which was in place at the time the activity/stream started.</span></span>  <span data-ttu-id="26dea-107">但是，使用继续符就意味着将多个事件流相关联，在更新配置文件时还尚未开始的流将提取更新中所做的更改，从而导致上述可能出现的覆盖数据的情况。</span><span class="sxs-lookup"><span data-stu-id="26dea-107">However, because continuations are the means of correlating multiple event streams, streams not yet begun at the time of a profile update will pick up the changes in the update, thus introducing the possible data overwrite described.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26dea-108">你可以使用不处理消息的业务流程创建延续。</span><span class="sxs-lookup"><span data-stu-id="26dea-108">You can create continuations with orchestrations that do not process messages.</span></span> <span data-ttu-id="26dea-109">通过将参数传递到业务流程间的执行调用中，然后使用 BAM API 来处理继续符，可以获得与处理消息的业务流程相同的功能。</span><span class="sxs-lookup"><span data-stu-id="26dea-109">You can obtain the same functionality as you can for orchestrations that do process messages by passing parameters in execution calls between orchestrations and by using BAM APIs to process the continuation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26dea-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="26dea-110">Prerequisites</span></span>  
 <span data-ttu-id="26dea-111">若要执行此过程，必须已部署 BAM 活动定义和要连接到的业务流程。</span><span class="sxs-lookup"><span data-stu-id="26dea-111">To perform this procedure, you must have deployed BAM activity definitions and orchestrations that you will connect to.</span></span>  
  
### <a name="to-create-a-continuation"></a><span data-ttu-id="26dea-112">创建继续符</span><span class="sxs-lookup"><span data-stu-id="26dea-112">To create a continuation</span></span>  
  
1.  <span data-ttu-id="26dea-113">打开现有跟踪配置文件，或者创建一个跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="26dea-113">Open an existing tracking profile or create a tracking profile.</span></span> <span data-ttu-id="26dea-114">有关创建跟踪配置文件的信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="26dea-114">For information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="26dea-115">标识*继续标记、* 这是一种可供这两个活动的唯一信息。</span><span class="sxs-lookup"><span data-stu-id="26dea-115">Identify a *continuation token,* which is a piece of unique information that is available to both activities.</span></span> <span data-ttu-id="26dea-116">例如，如果**CreditHistory**活动从发送消息激活**LoanProcess**中的活动**EquityLoan**业务流程、 的 SSN 字段消息可以用作继续标记，因为它是这两个活动共有的。</span><span class="sxs-lookup"><span data-stu-id="26dea-116">For example, if a **CreditHistory** activity is activated by a message sent from a **LoanProcess** activity within an **EquityLoan**orchestration, the SSN field of the message can be used as a continuation token because it is common to both activities.</span></span>  
  
3.  <span data-ttu-id="26dea-117">右键单击该活动，然后选择**新的延续**若要创建一个延续任务 (CreditHistory)。</span><span class="sxs-lookup"><span data-stu-id="26dea-117">Right-click the activity and then select **New Continuation** to create a continuation (CreditHistory).</span></span> <span data-ttu-id="26dea-118">命名您刚创建的继续符节点。</span><span class="sxs-lookup"><span data-stu-id="26dea-118">Name the continuation node you just created.</span></span>  
  
4.  <span data-ttu-id="26dea-119">从“业务流程调度”视图中，选择在步骤 2 中选择的继续符，例如 SSN（本例中为“发送”操作的 SSN），然后将它放到在步骤 3 中创建的继续符节点中。</span><span class="sxs-lookup"><span data-stu-id="26dea-119">From the Orchestration Schedule View, select the continuation token you chose in step 2, such as SSN (in this case from the Send action) and drop it into the continuation node you created in step 3.</span></span>  
  
5.  <span data-ttu-id="26dea-120">右键单击该活动，然后选择**新 ContinuationID**以创建一个延续 ID 节点。</span><span class="sxs-lookup"><span data-stu-id="26dea-120">Right-click the activity and select **New ContinuationID** to create a Continuation ID node.</span></span> <span data-ttu-id="26dea-121">使用在步骤 3 中选择的名称命名该节点，然后将其放到包含相应数据项的节点（本例中为接收操作的 SSN）中。</span><span class="sxs-lookup"><span data-stu-id="26dea-121">Name it using the name you chose in step 3, and drop it in the node that contains the corresponding data item (in this case, SSN from the Receive action).</span></span>  
  
6.  <span data-ttu-id="26dea-122">上**文件**菜单上，单击**另存为**以将跟踪配置文件另存为.btt 文件到 BizTalk 管理数据库和避免覆盖任何现有的.btt 文件。</span><span class="sxs-lookup"><span data-stu-id="26dea-122">On the **File**menu, click **Save As**to save the tracking profile as a .btt file to the BizTalk Management database and to avoid overwriting any existing .btt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26dea-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26dea-123">See Also</span></span>  
 <span data-ttu-id="26dea-124">[延续任务，并 ContinuationID 节点](../core/continuation-and-continuationid-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="26dea-124">[Continuation and ContinuationID Nodes](../core/continuation-and-continuationid-nodes.md) </span></span>  
 [<span data-ttu-id="26dea-125">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="26dea-125">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)