---
title: 在订单处理阶段中处理 |Microsoft Docs
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
ms.openlocfilehash: 2cf62be2b8a4e11ce7a6acc5b9807207aea89d00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299858"
---
# <a name="processing-in-the-order-processing-stages"></a><span data-ttu-id="399d8-102">在订单处理阶段中处理</span><span class="sxs-lookup"><span data-stu-id="399d8-102">Processing in the Order Processing Stages</span></span>
<span data-ttu-id="399d8-103">该业务流程管理解决方案包含两个阶段**CableOrder1**并**CableOrder2**执行订单处理操作的业务流程。</span><span class="sxs-lookup"><span data-stu-id="399d8-103">The Business Process Management solution includes two stages, the **CableOrder1** and **CableOrder2** orchestrations, that perform the order processing actions.</span></span> <span data-ttu-id="399d8-104">有关如何订单流程已分为若干阶段的详细信息，请参阅[处理阶段数](../core/number-of-processing-stages.md)。</span><span class="sxs-lookup"><span data-stu-id="399d8-104">For more information about how the order process was divided into stages, see [Number of Processing Stages](../core/number-of-processing-stages.md).</span></span>  
  
 <span data-ttu-id="399d8-105">这两个处理阶段开始时收到订单消息和状态消息作为答复**OrderManager**业务流程在开始之后。</span><span class="sxs-lookup"><span data-stu-id="399d8-105">Both processing stages begin when they receive an order message and both reply with a status message to the **OrderManager** orchestration once they have started.</span></span> <span data-ttu-id="399d8-106">同样，这两个将发送一条消息回**OrderManager**以指示是否在阶段已完成或终止，出现错误。</span><span class="sxs-lookup"><span data-stu-id="399d8-106">Similarly, both send a message back to the **OrderManager** to indicate whether the stage completed or terminated with an error.</span></span> <span data-ttu-id="399d8-107">有关详细信息之间的连接**OrderManager**业务流程和处理阶段中，请参阅[反转直接合作伙伴绑定](../core/inverse-direct-partner-binding.md)。</span><span class="sxs-lookup"><span data-stu-id="399d8-107">For details about the connection between the **OrderManager** orchestration and the processing stages, see [Inverse Direct Partner Binding](../core/inverse-direct-partner-binding.md).</span></span>  
  
 <span data-ttu-id="399d8-108">这两种处理阶段使用自相关，动态端口，以将信息发送回**OrderManger**。</span><span class="sxs-lookup"><span data-stu-id="399d8-108">Both processing stages use self-correlating, dynamic ports to send information back to the **OrderManger**.</span></span> <span data-ttu-id="399d8-109">通过动态端口，业务流程从消息将发送端口将复制的端口地址。</span><span class="sxs-lookup"><span data-stu-id="399d8-109">With dynamic ports, the orchestrations copy the port address from the message to send port.</span></span>  
  
 <span data-ttu-id="399d8-110">所有处理阶段接收的订单消息都是在创建的标准化、 规范化订单消息**OrderBroker**。</span><span class="sxs-lookup"><span data-stu-id="399d8-110">All of the order messages the processing stages receive are the normalized, canonical order messages created in the **OrderBroker**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="399d8-111">由于的长度**CableOrder1**并**CableOrder2**业务流程，你可能想要阅读此部分在 Microsoft Visual Studio 中打开该业务流程。</span><span class="sxs-lookup"><span data-stu-id="399d8-111">Because of the length of the **CableOrder1** and **CableOrder2** orchestrations, you may want to read this section with the orchestrations open in Microsoft Visual Studio.</span></span>  
  
## <a name="the-cableorder1-orchestration"></a><span data-ttu-id="399d8-112">CableOrder1 业务流程</span><span class="sxs-lookup"><span data-stu-id="399d8-112">The CableOrder1 Orchestration</span></span>  
 <span data-ttu-id="399d8-113">**CableOrder1**业务流程将启动时收到订单消息。</span><span class="sxs-lookup"><span data-stu-id="399d8-113">The **CableOrder1** orchestration starts when it receives an order message.</span></span> <span data-ttu-id="399d8-114">它然后回复地址将从消息复制到阶段完成端口。</span><span class="sxs-lookup"><span data-stu-id="399d8-114">It then copies the reply address from the message to the stage completion port.</span></span> <span data-ttu-id="399d8-115">接下来，它构造一个确认消息并将其作为响应发送**BeginStagePort**端口，，然后将路由信息保存在本地变量。</span><span class="sxs-lookup"><span data-stu-id="399d8-115">Next, it constructs an acknowledgement message and sends it as a response to the **BeginStagePort** port, and then saves the routing information in a local variable.</span></span>  
  
 <span data-ttu-id="399d8-116">接下来，业务流程从 SSO 获取配置信息。</span><span class="sxs-lookup"><span data-stu-id="399d8-116">The orchestration next gets the configuration information from SSO.</span></span> <span data-ttu-id="399d8-117">有关该解决方案如何使用 SSO 的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="399d8-117">For more information about how the solution uses SSO, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="399d8-118">该业务流程将创建的实例**OrderHandler**对象与后端进程进行通信、 检查消息的有效性、 分析消息、 确定服务类型和要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="399d8-118">The orchestration then creates an instance of the **OrderHandler** object to communicate with the backend processes, checks the validity of the message, analyzes the message, determines the service type, and which action to take.</span></span> <span data-ttu-id="399d8-119">具体取决于要执行的操作，它将调用一个订单操作业务流程**激活**，**更改**，或**取消**，并将传递**OrderHandler**向业务流程的对象。</span><span class="sxs-lookup"><span data-stu-id="399d8-119">Depending on the action to take, it calls one of the order action orchestrations **Activate**, **Change**, or **Cancel** and passes the **OrderHandler** object to the orchestration.</span></span>  
  
 <span data-ttu-id="399d8-120">**CableOrder1**业务流程将检查中断，将消息发送到的功能组和等待听到备份。</span><span class="sxs-lookup"><span data-stu-id="399d8-120">The **CableOrder1** orchestration then checks for an interrupt, sends a message to the facilities group and waits to hear back.</span></span> <span data-ttu-id="399d8-121">如果业务流程获取一条消息返回功能组，它将继续处理。</span><span class="sxs-lookup"><span data-stu-id="399d8-121">If the orchestration gets a message back from the facilities group, it continues processing.</span></span> <span data-ttu-id="399d8-122">否则，如果存在中断，业务流程将引发中断异常。</span><span class="sxs-lookup"><span data-stu-id="399d8-122">Otherwise, if there is an interrupt, the orchestration throws an interrupt exception.</span></span>  
  
 <span data-ttu-id="399d8-123">在业务流程完成构建一条完成消息并将其通过发送**StageCompletion**端口。</span><span class="sxs-lookup"><span data-stu-id="399d8-123">The orchestration finishes by constructing a completion message and sending it through the **StageCompletion** port.</span></span>  
  
## <a name="the-cableorder2-orchestration"></a><span data-ttu-id="399d8-124">CableOrder2 业务流程</span><span class="sxs-lookup"><span data-stu-id="399d8-124">The CableOrder2 Orchestration</span></span>  
 <span data-ttu-id="399d8-125">CableOrder2 业务流程执行相同 CableOrder1 业务流程的路由的信息，SSO 配置信息，以启动步骤并创建的实例**OrderHandler**对象。</span><span class="sxs-lookup"><span data-stu-id="399d8-125">The CableOrder2 orchestration performs the same starting steps as the CableOrder1 orchestration for the routing information, SSO configuration information, and creating an instance of the **OrderHandler** object.</span></span>  
  
 <span data-ttu-id="399d8-126">业务流程接着检查中断，并传递**OrderHandler**调用中的对象**完成**业务流程。</span><span class="sxs-lookup"><span data-stu-id="399d8-126">The orchestration then checks for an interrupt and passes the **OrderHandler** object in a call to the **Complete** orchestration.</span></span> <span data-ttu-id="399d8-127">接下来，该业务流程创建一个订单状态消息，更新订单历史记录，并发送完成消息通过**StageCompletion**端口。</span><span class="sxs-lookup"><span data-stu-id="399d8-127">Next, the orchestration creates an order status message, updates the order history, and sends a completion message through the **StageCompletion** port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399d8-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="399d8-128">See Also</span></span>  
 <span data-ttu-id="399d8-129">[版本控制业务流程管理解决方案](../core/versioning-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="399d8-129">[Versioning the Business Process Management Solution](../core/versioning-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="399d8-130">在业务流程管理解决方案中处理</span><span class="sxs-lookup"><span data-stu-id="399d8-130">Processing in the Business Process Management Solution</span></span>](../core/processing-in-the-business-process-management-solution.md)