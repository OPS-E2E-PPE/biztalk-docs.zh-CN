---
title: 并行保护 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Parallel Task shape [Orchestration Designer], concurrent receive tasks
- messages, convoys
- correlation sets, concurrent receive tasks
- correlation sets, Parallel Task shape [Orchestration Designer]
- orchestrations, messages
- messages, correlating to orchestrations
ms.assetid: 036aa8c0-f49c-47f0-ac1e-6c667bca3811
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edc797c59332d9a2453f38afd5daffabfbcdac9d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393412"
---
# <a name="parallel-convoys"></a><span data-ttu-id="266a9-102">并行保护</span><span class="sxs-lookup"><span data-stu-id="266a9-102">Parallel Convoys</span></span>
<span data-ttu-id="266a9-103">并行保护可以使多个单独的消息以实现所需的效果。</span><span class="sxs-lookup"><span data-stu-id="266a9-103">A parallel convoy enables multiple single messages to join together to achieve a required result.</span></span> <span data-ttu-id="266a9-104">组相关消息可以按任意顺序到达，但 BizTalk Server 必须在启动进程之前收到所有项。</span><span class="sxs-lookup"><span data-stu-id="266a9-104">The set of related messages can arrive in any order, but BizTalk Server must receive all of them before starting the process.</span></span>  
  
 <span data-ttu-id="266a9-105">例如，当医院承认这一点新患者，医院需要一些相关的信息从患者，包括保险信息、 过去的医疗历史记录和联系信息。</span><span class="sxs-lookup"><span data-stu-id="266a9-105">For example, when a hospital admits a new patient, the hospital requires several pieces of information from the patient, including insurance information, past medical history, and contact information.</span></span> <span data-ttu-id="266a9-106">多个人员收集此信息，包括保险专家、 护士和接线员。</span><span class="sxs-lookup"><span data-stu-id="266a9-106">Several different people collect this information, including an insurance specialist, a nurse, and a receptionist.</span></span> <span data-ttu-id="266a9-107">多个不同的系统处理此信息。</span><span class="sxs-lookup"><span data-stu-id="266a9-107">Several different systems process this information.</span></span> <span data-ttu-id="266a9-108">在哪个集合中，此提交订单信息发生不能保证。</span><span class="sxs-lookup"><span data-stu-id="266a9-108">The order in which collection and submission of this information occurs is not guaranteed.</span></span> <span data-ttu-id="266a9-109">例如，信息收集器可能还忙于其他患者、 医疗记录部门可能在其计划中，在后面或保险系统可能不正常。</span><span class="sxs-lookup"><span data-stu-id="266a9-109">For example, information collectors may be busy with other patients, the medical records department may be behind in their schedule, or the insurance system may not be functioning correctly.</span></span> <span data-ttu-id="266a9-110">以有序的方式组装病人的此信息必须贯穿整个在医院患者所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="266a9-110">Assembling this information for the patient in an organized manner must occur throughout the time the patient spends at the hospital.</span></span> <span data-ttu-id="266a9-111">这可确保将患者接收相应管理和精确的计费。</span><span class="sxs-lookup"><span data-stu-id="266a9-111">This guarantees that the patient receives appropriate care and accurate billing.</span></span>  
  
 <span data-ttu-id="266a9-112">前面的方案是需要并行保护消息处理的商业应用场景的示例。</span><span class="sxs-lookup"><span data-stu-id="266a9-112">The preceding scenario is an example of a business scenario that requires parallel convoy message processing.</span></span> <span data-ttu-id="266a9-113">业务要求规定病人入院到医院之前的三个不同类型的消息的接收。</span><span class="sxs-lookup"><span data-stu-id="266a9-113">The business requirements dictate the receipt of three different types of messages before admitting the patient into the hospital.</span></span> <span data-ttu-id="266a9-114">这些三个消息是保险、 历史记录和患者的消息。</span><span class="sxs-lookup"><span data-stu-id="266a9-114">These three messages are the Insurance, History, and Patient messages.</span></span> <span data-ttu-id="266a9-115">这些消息的任何一个可以是第一条消息到达患者，并且这将创建一个争用条件。</span><span class="sxs-lookup"><span data-stu-id="266a9-115">Any one of these messages can be the first message to arrive for the patient, and this creates a race condition.</span></span> <span data-ttu-id="266a9-116">若要解决此问题，三个**接收**形状放入**并行操作**形状并且每个接收标记为 Activate = True。</span><span class="sxs-lookup"><span data-stu-id="266a9-116">To resolve this issue, three **Receive** shapes are put into a **Parallel Actions** shape and each receive is marked as Activate = True.</span></span> <span data-ttu-id="266a9-117">这样，三条消息以启动业务流程的任何一个。</span><span class="sxs-lookup"><span data-stu-id="266a9-117">This enables any one of the three messages to start the orchestration.</span></span> <span data-ttu-id="266a9-118">业务流程实例等待，直到其他两条消息到达到继续进行处理后，再继续下一步。</span><span class="sxs-lookup"><span data-stu-id="266a9-118">The orchestration instance waits until the other two messages arrive before proceeding to further processing.</span></span>  
  
## <a name="implementing-parallel-convoys"></a><span data-ttu-id="266a9-119">实现并行保护</span><span class="sxs-lookup"><span data-stu-id="266a9-119">Implementing Parallel Convoys</span></span>  
 <span data-ttu-id="266a9-120">您可以通过使用实现并行保护"并行关联接收"消息传送在 BizTalk Server 中的设计模式。</span><span class="sxs-lookup"><span data-stu-id="266a9-120">You can implement parallel convoys by using the "parallel correlated receives" messaging design pattern in BizTalk Server.</span></span> <span data-ttu-id="266a9-121">并行关联接收相关的两个或多个分支中接收语句**并行操作**形状。</span><span class="sxs-lookup"><span data-stu-id="266a9-121">Parallel correlated receives are correlated receive statements in two or more branches of a **Parallel Actions** shape.</span></span> <span data-ttu-id="266a9-122">如果在多个并行任务中初始化该相关时，每个相关的接收必须初始化一组完全相同的相关性。</span><span class="sxs-lookup"><span data-stu-id="266a9-122">If a correlation is initialized in more than one parallel task, each correlated receive must initialize exactly the same set of correlations.</span></span> <span data-ttu-id="266a9-123">接收相关的消息的此类任务首先执行实际的初始化，并对中的其他任务执行的验证**并行操作**形状在业务流程中。</span><span class="sxs-lookup"><span data-stu-id="266a9-123">The first such task that receives a correlated message performs the actual initialization, and validation is performed on the other tasks in the **Parallel Actions** shape in orchestration.</span></span>  
  
 <span data-ttu-id="266a9-124">有关并行保护实现的示例，请参阅 SDK 示例"并行保护"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="266a9-124">For an example of parallel convoy implementation, see the SDK sample "Parallel Convoy" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="266a9-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="266a9-125">See Also</span></span>  
 <span data-ttu-id="266a9-126">[使用保护方案](../core/working-with-convoy-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="266a9-126">[Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md) </span></span>  
 [<span data-ttu-id="266a9-127">顺序保护</span><span class="sxs-lookup"><span data-stu-id="266a9-127">Sequential Convoys</span></span>](../core/sequential-convoys.md)