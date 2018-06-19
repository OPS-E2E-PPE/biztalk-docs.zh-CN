---
title: 中的顺序处理阶段处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698005da-1ba8-4972-83db-f5ae45fd6a83
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a8eae6b814af36d0ea07065726ca66518984703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265093"
---
# <a name="processing-in-the-order-processing-stages"></a><span data-ttu-id="642ad-102">在订单处理阶段中处理</span><span class="sxs-lookup"><span data-stu-id="642ad-102">Processing in the Order Processing Stages</span></span>
<span data-ttu-id="642ad-103">业务流程管理解决方案包括两个阶段， **CableOrder1**和**CableOrder2**业务流程，执行处理操作的顺序。</span><span class="sxs-lookup"><span data-stu-id="642ad-103">The Business Process Management solution includes two stages, the **CableOrder1** and **CableOrder2** orchestrations, that perform the order processing actions.</span></span> <span data-ttu-id="642ad-104">有关如何订单过程已划分为阶段的详细信息，请参阅[处理阶段数](../core/number-of-processing-stages.md)。</span><span class="sxs-lookup"><span data-stu-id="642ad-104">For more information about how the order process was divided into stages, see [Number of Processing Stages](../core/number-of-processing-stages.md).</span></span>  
  
 <span data-ttu-id="642ad-105">这两个处理阶段开始时它们接收订单消息，同时使用到的状态消息回复**OrderManager**业务流程后它们已启动。</span><span class="sxs-lookup"><span data-stu-id="642ad-105">Both processing stages begin when they receive an order message and both reply with a status message to the **OrderManager** orchestration once they have started.</span></span> <span data-ttu-id="642ad-106">同样，一条消息回到这两个发送**OrderManager**指示阶段是否完成或终止，出现错误。</span><span class="sxs-lookup"><span data-stu-id="642ad-106">Similarly, both send a message back to the **OrderManager** to indicate whether the stage completed or terminated with an error.</span></span> <span data-ttu-id="642ad-107">有关详细信息之间的连接**OrderManager**业务流程和处理阶段中，请参阅[反直接合作伙伴绑定](../core/inverse-direct-partner-binding.md)。</span><span class="sxs-lookup"><span data-stu-id="642ad-107">For details about the connection between the **OrderManager** orchestration and the processing stages, see [Inverse Direct Partner Binding](../core/inverse-direct-partner-binding.md).</span></span>  
  
 <span data-ttu-id="642ad-108">这两种处理阶段使用自助关联，动态端口，以将信息发送回**OrderManger**。</span><span class="sxs-lookup"><span data-stu-id="642ad-108">Both processing stages use self-correlating, dynamic ports to send information back to the **OrderManger**.</span></span> <span data-ttu-id="642ad-109">通过动态端口，业务流程可将端口地址从消息复制到发送端口。</span><span class="sxs-lookup"><span data-stu-id="642ad-109">With dynamic ports, the orchestrations copy the port address from the message to send port.</span></span>  
  
 <span data-ttu-id="642ad-110">所有处理阶段接收的顺序消息都是在中创建的规范化的规范顺序消息**OrderBroker**。</span><span class="sxs-lookup"><span data-stu-id="642ad-110">All of the order messages the processing stages receive are the normalized, canonical order messages created in the **OrderBroker**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="642ad-111">由于**CableOrder1**和**CableOrder2**业务流程，你可能想要阅读此部分与 Microsoft Visual Studio 中打开的业务流程。</span><span class="sxs-lookup"><span data-stu-id="642ad-111">Because of the length of the **CableOrder1** and **CableOrder2** orchestrations, you may want to read this section with the orchestrations open in Microsoft Visual Studio.</span></span>  
  
## <a name="the-cableorder1-orchestration"></a><span data-ttu-id="642ad-112">CableOrder1 业务流程</span><span class="sxs-lookup"><span data-stu-id="642ad-112">The CableOrder1 Orchestration</span></span>  
 <span data-ttu-id="642ad-113">**CableOrder1**时接收顺序消息时，业务流程将启动。</span><span class="sxs-lookup"><span data-stu-id="642ad-113">The **CableOrder1** orchestration starts when it receives an order message.</span></span> <span data-ttu-id="642ad-114">然后将消息中的答复地址复制到阶段完成端口。</span><span class="sxs-lookup"><span data-stu-id="642ad-114">It then copies the reply address from the message to the stage completion port.</span></span> <span data-ttu-id="642ad-115">接下来，构造一条确认消息，并将其发送的响应**BeginStagePort**端口，，然后将路由信息保存在本地变量。</span><span class="sxs-lookup"><span data-stu-id="642ad-115">Next, it constructs an acknowledgement message and sends it as a response to the **BeginStagePort** port, and then saves the routing information in a local variable.</span></span>  
  
 <span data-ttu-id="642ad-116">此业务流程接着获取 SSO 的配置信息。</span><span class="sxs-lookup"><span data-stu-id="642ad-116">The orchestration next gets the configuration information from SSO.</span></span> <span data-ttu-id="642ad-117">有关如何解决方案使用 SSO 的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="642ad-117">For more information about how the solution uses SSO, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="642ad-118">然后，业务流程创建的实例**OrderHandler**对象，以便与后端进程通信、 检查消息的有效性，将分析该消息，确定服务类型中，并要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="642ad-118">The orchestration then creates an instance of the **OrderHandler** object to communicate with the backend processes, checks the validity of the message, analyzes the message, determines the service type, and which action to take.</span></span> <span data-ttu-id="642ad-119">具体取决于要执行的操作，它调用的顺序操作业务流程中的一个**激活**，**更改**，或**取消**并将传递**OrderHandler**业务流程的对象。</span><span class="sxs-lookup"><span data-stu-id="642ad-119">Depending on the action to take, it calls one of the order action orchestrations **Activate**, **Change**, or **Cancel** and passes the **OrderHandler** object to the orchestration.</span></span>  
  
 <span data-ttu-id="642ad-120">**CableOrder1**业务流程，然后将为中断，发送到设备组并等待的消息以了解签。</span><span class="sxs-lookup"><span data-stu-id="642ad-120">The **CableOrder1** orchestration then checks for an interrupt, sends a message to the facilities group and waits to hear back.</span></span> <span data-ttu-id="642ad-121">如果业务流程收到功能组发回的消息，则会继续进行处理。</span><span class="sxs-lookup"><span data-stu-id="642ad-121">If the orchestration gets a message back from the facilities group, it continues processing.</span></span> <span data-ttu-id="642ad-122">否则，业务流程将在出现中断时引发中断异常。</span><span class="sxs-lookup"><span data-stu-id="642ad-122">Otherwise, if there is an interrupt, the orchestration throws an interrupt exception.</span></span>  
  
 <span data-ttu-id="642ad-123">业务流程完成方法是构造一条完成消息并将其通过发送**StageCompletion**端口。</span><span class="sxs-lookup"><span data-stu-id="642ad-123">The orchestration finishes by constructing a completion message and sending it through the **StageCompletion** port.</span></span>  
  
## <a name="the-cableorder2-orchestration"></a><span data-ttu-id="642ad-124">CableOrder2 业务流程</span><span class="sxs-lookup"><span data-stu-id="642ad-124">The CableOrder2 Orchestration</span></span>  
 <span data-ttu-id="642ad-125">CableOrder2 业务流程执行相同 CableOrder1 业务流程的路由的信息，SSO 配置信息，以启动步骤并创建的实例**OrderHandler**对象。</span><span class="sxs-lookup"><span data-stu-id="642ad-125">The CableOrder2 orchestration performs the same starting steps as the CableOrder1 orchestration for the routing information, SSO configuration information, and creating an instance of the **OrderHandler** object.</span></span>  
  
 <span data-ttu-id="642ad-126">业务流程然后检查中断和传递**OrderHandler**对的调用中的对象**完成**业务流程。</span><span class="sxs-lookup"><span data-stu-id="642ad-126">The orchestration then checks for an interrupt and passes the **OrderHandler** object in a call to the **Complete** orchestration.</span></span> <span data-ttu-id="642ad-127">接下来，业务流程创建订单状态消息、 更新订单历史记录，并将发送一条完成消息通过**StageCompletion**端口。</span><span class="sxs-lookup"><span data-stu-id="642ad-127">Next, the orchestration creates an order status message, updates the order history, and sends a completion message through the **StageCompletion** port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642ad-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="642ad-128">See Also</span></span>  
 <span data-ttu-id="642ad-129">[版本控制业务流程管理解决方案](../core/versioning-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="642ad-129">[Versioning the Business Process Management Solution](../core/versioning-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="642ad-130">在业务流程管理解决方案中进行处理</span><span class="sxs-lookup"><span data-stu-id="642ad-130">Processing in the Business Process Management Solution</span></span>](../core/processing-in-the-business-process-management-solution.md)