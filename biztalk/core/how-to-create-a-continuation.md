---
title: 如何创建一个继续符 |Microsoft Docs
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
ms.openlocfilehash: d0cf558ec136cf25bece9c899cad13e1c9d75f1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340095"
---
# <a name="how-to-create-a-continuation"></a><span data-ttu-id="401af-102">如何创建一个继续符</span><span class="sxs-lookup"><span data-stu-id="401af-102">How to Create a Continuation</span></span>
<span data-ttu-id="401af-103">创建继续符可以指示一个或多个业务流程中的业务事件通过构造连接的活动相关。</span><span class="sxs-lookup"><span data-stu-id="401af-103">You create continuations to indicate which business events in one or more orchestrations are related by constructing connected activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="401af-104">如果该活动将包含 BAM 继续符，更新跟踪配置文件可能会影响正在进行中的活动实例。</span><span class="sxs-lookup"><span data-stu-id="401af-104">Updating a tracking profile can impact activity instances in progress if the activity includes a BAM continuation.</span></span> <span data-ttu-id="401af-105">具体而言，如果跟踪配置文件更新指定的已记录某个活动项的数据的下游拦截，就可以将覆盖原始值。</span><span class="sxs-lookup"><span data-stu-id="401af-105">Specifically, if the update to the tracking profile specifies a downstream interception of data for an activity item already recorded, it is possible that the original value will be overwritten.</span></span> <span data-ttu-id="401af-106">从本质上讲，任何单个事件流不会受跟踪配置文件更新，因为每个流对象绑定到活动/流开始时就已存在的配置文件的特定版本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="401af-106">In essence, any single event stream will not be affected by the application of tracking profile updates because each stream object is tied to the specific version of the profile which was in place at the time the activity/stream started.</span></span>  <span data-ttu-id="401af-107">但是，由于延续关联多个事件流的方式，流尚未开始更新配置文件的时间会选取更新，从而导致可能覆盖数据的情况中的更改。</span><span class="sxs-lookup"><span data-stu-id="401af-107">However, because continuations are the means of correlating multiple event streams, streams not yet begun at the time of a profile update will pick up the changes in the update, thus introducing the possible data overwrite described.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="401af-108">您可以与不处理消息的业务流程创建继续符。</span><span class="sxs-lookup"><span data-stu-id="401af-108">You can create continuations with orchestrations that do not process messages.</span></span> <span data-ttu-id="401af-109">可以通过在业务流程之间执行调用中传递参数并使用 BAM Api 来处理继续符处理消息的业务流程，你可以获取相同的功能。</span><span class="sxs-lookup"><span data-stu-id="401af-109">You can obtain the same functionality as you can for orchestrations that do process messages by passing parameters in execution calls between orchestrations and by using BAM APIs to process the continuation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="401af-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="401af-110">Prerequisites</span></span>  
 <span data-ttu-id="401af-111">若要执行此过程，必须部署 BAM 活动定义和将连接到的业务流程。</span><span class="sxs-lookup"><span data-stu-id="401af-111">To perform this procedure, you must have deployed BAM activity definitions and orchestrations that you will connect to.</span></span>  
  
### <a name="to-create-a-continuation"></a><span data-ttu-id="401af-112">若要创建一个继续符</span><span class="sxs-lookup"><span data-stu-id="401af-112">To create a continuation</span></span>  
  
1.  <span data-ttu-id="401af-113">打开现有的跟踪配置文件或创建跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="401af-113">Open an existing tracking profile or create a tracking profile.</span></span> <span data-ttu-id="401af-114">有关创建跟踪配置文件的信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="401af-114">For information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="401af-115">识别*继续标记、* 这是一种可供这两个活动的唯一信息。</span><span class="sxs-lookup"><span data-stu-id="401af-115">Identify a *continuation token,* which is a piece of unique information that is available to both activities.</span></span> <span data-ttu-id="401af-116">例如，如果**CreditHistory**活动从发送一条消息来激活**LoanProcess**中的活动**EquityLoan**业务流程、 的 SSN 字段消息可以用作一个继续标记，因为它是普遍适用于这两个活动。</span><span class="sxs-lookup"><span data-stu-id="401af-116">For example, if a **CreditHistory** activity is activated by a message sent from a **LoanProcess** activity within an **EquityLoan**orchestration, the SSN field of the message can be used as a continuation token because it is common to both activities.</span></span>  
  
3.  <span data-ttu-id="401af-117">右键单击该活动，然后选择**新的延续**来创建继续符 (CreditHistory)。</span><span class="sxs-lookup"><span data-stu-id="401af-117">Right-click the activity and then select **New Continuation** to create a continuation (CreditHistory).</span></span> <span data-ttu-id="401af-118">命名您刚创建的继续符节点。</span><span class="sxs-lookup"><span data-stu-id="401af-118">Name the continuation node you just created.</span></span>  
  
4.  <span data-ttu-id="401af-119">从业务流程调度视图中，选择在步骤 2 中，例如 SSN （在此情况下从发送操作） 中选择的继续标记，并将其放到在步骤 3 中创建的继续符节点。</span><span class="sxs-lookup"><span data-stu-id="401af-119">From the Orchestration Schedule View, select the continuation token you chose in step 2, such as SSN (in this case from the Send action) and drop it into the continuation node you created in step 3.</span></span>  
  
5.  <span data-ttu-id="401af-120">右键单击该活动，然后选择**新建 ContinuationID**创建继续符 ID 节点。</span><span class="sxs-lookup"><span data-stu-id="401af-120">Right-click the activity and select **New ContinuationID** to create a Continuation ID node.</span></span> <span data-ttu-id="401af-121">其使用步骤 3 中选择的名称命名，并将其放在包含 （在此情况下，从接收操作的 SSN） 相应数据项的节点。</span><span class="sxs-lookup"><span data-stu-id="401af-121">Name it using the name you chose in step 3, and drop it in the node that contains the corresponding data item (in this case, SSN from the Receive action).</span></span>  
  
6.  <span data-ttu-id="401af-122">上**文件**菜单上，单击**另存为**保存跟踪配置文件作为.btt 文件到 BizTalk 管理数据库，以避免覆盖任何现有的.btt 文件。</span><span class="sxs-lookup"><span data-stu-id="401af-122">On the **File**menu, click **Save As**to save the tracking profile as a .btt file to the BizTalk Management database and to avoid overwriting any existing .btt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401af-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="401af-123">See Also</span></span>  
 <span data-ttu-id="401af-124">[继续符和 ContinuationID 节点](../core/continuation-and-continuationid-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="401af-124">[Continuation and ContinuationID Nodes](../core/continuation-and-continuationid-nodes.md) </span></span>  
 [<span data-ttu-id="401af-125">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="401af-125">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)