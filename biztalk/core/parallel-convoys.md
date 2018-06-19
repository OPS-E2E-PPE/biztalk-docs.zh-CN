---
title: 并行保护 |Microsoft 文档
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
ms.openlocfilehash: a9c6993aa3c5dd47cb5b554dd8ab2080020ebb80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264837"
---
# <a name="parallel-convoys"></a><span data-ttu-id="bad8a-102">并行的保护</span><span class="sxs-lookup"><span data-stu-id="bad8a-102">Parallel Convoys</span></span>
<span data-ttu-id="bad8a-103">一个并行的队列允许多个单个消息联接在一起以获得所需的结果。</span><span class="sxs-lookup"><span data-stu-id="bad8a-103">A parallel convoy enables multiple single messages to join together to achieve a required result.</span></span> <span data-ttu-id="bad8a-104">一组相关消息可以按任何顺序到达，但 BizTalk Server 必须在启动进程之前收到所有这些。</span><span class="sxs-lookup"><span data-stu-id="bad8a-104">The set of related messages can arrive in any order, but BizTalk Server must receive all of them before starting the process.</span></span>  
  
 <span data-ttu-id="bad8a-105">例如，当医院承认新患者，医院需要几个部分从 patient，包括过去的医疗历史记录和联系信息的保险信息的信息。</span><span class="sxs-lookup"><span data-stu-id="bad8a-105">For example, when a hospital admits a new patient, the hospital requires several pieces of information from the patient, including insurance information, past medical history, and contact information.</span></span> <span data-ttu-id="bad8a-106">多个不同的人收集此信息，包括保险专家、 护士和接线员。</span><span class="sxs-lookup"><span data-stu-id="bad8a-106">Several different people collect this information, including an insurance specialist, a nurse, and a receptionist.</span></span> <span data-ttu-id="bad8a-107">有几个不同系统处理此信息。</span><span class="sxs-lookup"><span data-stu-id="bad8a-107">Several different systems process this information.</span></span> <span data-ttu-id="bad8a-108">此提交的集合中的顺序信息发生不能保证。</span><span class="sxs-lookup"><span data-stu-id="bad8a-108">The order in which collection and submission of this information occurs is not guaranteed.</span></span> <span data-ttu-id="bad8a-109">例如，信息收集器可能忙于处理其他患者、 医疗记录部门在其计划，可能会在后面或保险系统可能不正常。</span><span class="sxs-lookup"><span data-stu-id="bad8a-109">For example, information collectors may be busy with other patients, the medical records department may be behind in their schedule, or the insurance system may not be functioning correctly.</span></span> <span data-ttu-id="bad8a-110">组织的方式组装患者此信息必须贯穿整个患者在医院所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="bad8a-110">Assembling this information for the patient in an organized manner must occur throughout the time the patient spends at the hospital.</span></span> <span data-ttu-id="bad8a-111">这可确保将患者接收适当的小心和准确的计费。</span><span class="sxs-lookup"><span data-stu-id="bad8a-111">This guarantees that the patient receives appropriate care and accurate billing.</span></span>  
  
 <span data-ttu-id="bad8a-112">前面的方案是需要并行的队列消息处理的业务方案的示例。</span><span class="sxs-lookup"><span data-stu-id="bad8a-112">The preceding scenario is an example of a business scenario that requires parallel convoy message processing.</span></span> <span data-ttu-id="bad8a-113">企业要求规定之前接收到医院患者收到的三个不同类型的消息。</span><span class="sxs-lookup"><span data-stu-id="bad8a-113">The business requirements dictate the receipt of three different types of messages before admitting the patient into the hospital.</span></span> <span data-ttu-id="bad8a-114">这些三个消息是保险、 历史记录和患者的消息。</span><span class="sxs-lookup"><span data-stu-id="bad8a-114">These three messages are the Insurance, History, and Patient messages.</span></span> <span data-ttu-id="bad8a-115">任一这些消息可以是第一条消息到达个 patient，并且这将创建的争用条件。</span><span class="sxs-lookup"><span data-stu-id="bad8a-115">Any one of these messages can be the first message to arrive for the patient, and this creates a race condition.</span></span> <span data-ttu-id="bad8a-116">若要解决此问题，请三个**接收**形状放入**并行操作**形状和每个接收标记为激活 = True。</span><span class="sxs-lookup"><span data-stu-id="bad8a-116">To resolve this issue, three **Receive** shapes are put into a **Parallel Actions** shape and each receive is marked as Activate = True.</span></span> <span data-ttu-id="bad8a-117">这样，要启动业务流程的三个消息的任何一个。</span><span class="sxs-lookup"><span data-stu-id="bad8a-117">This enables any one of the three messages to start the orchestration.</span></span> <span data-ttu-id="bad8a-118">业务流程实例等待，直到在继续之前到达进一步处理到其他两条消息。</span><span class="sxs-lookup"><span data-stu-id="bad8a-118">The orchestration instance waits until the other two messages arrive before proceeding to further processing.</span></span>  
  
## <a name="implementing-parallel-convoys"></a><span data-ttu-id="bad8a-119">实现并行保护</span><span class="sxs-lookup"><span data-stu-id="bad8a-119">Implementing Parallel Convoys</span></span>  
 <span data-ttu-id="bad8a-120">您可以使用 BizTalk Server 中的“并行关联接收”消息传送设计模式来实现并行保护。</span><span class="sxs-lookup"><span data-stu-id="bad8a-120">You can implement parallel convoys by using the "parallel correlated receives" messaging design pattern in BizTalk Server.</span></span> <span data-ttu-id="bad8a-121">并行关联接收相关的两个或多个分支中接收语句**并行操作**形状。</span><span class="sxs-lookup"><span data-stu-id="bad8a-121">Parallel correlated receives are correlated receive statements in two or more branches of a **Parallel Actions** shape.</span></span> <span data-ttu-id="bad8a-122">如果在多个并行任务中初始化一个相关性，每个关联的接收必须初始化完全相同的关联集。</span><span class="sxs-lookup"><span data-stu-id="bad8a-122">If a correlation is initialized in more than one parallel task, each correlated receive must initialize exactly the same set of correlations.</span></span> <span data-ttu-id="bad8a-123">这种任务接收到关联的消息会首先执行的实际初始化，以及在中的其他任务上执行验证**并行操作**业务流程中的形状。</span><span class="sxs-lookup"><span data-stu-id="bad8a-123">The first such task that receives a correlated message performs the actual initialization, and validation is performed on the other tasks in the **Parallel Actions** shape in orchestration.</span></span>  
  
 <span data-ttu-id="bad8a-124">并行的队列实现的示例，请参阅"并行保护"中的 SDK 示例在[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="bad8a-124">For an example of parallel convoy implementation, see the SDK sample "Parallel Convoy" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad8a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bad8a-125">See Also</span></span>  
 <span data-ttu-id="bad8a-126">[使用队列方案](../core/working-with-convoy-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="bad8a-126">[Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md) </span></span>  
 [<span data-ttu-id="bad8a-127">顺序保护</span><span class="sxs-lookup"><span data-stu-id="bad8a-127">Sequential Convoys</span></span>](../core/sequential-convoys.md)