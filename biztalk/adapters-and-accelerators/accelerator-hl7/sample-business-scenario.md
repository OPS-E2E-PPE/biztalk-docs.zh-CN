---
title: "示例业务方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78229d903461fe2b84033b036ef02b2838832fc0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="sample-business-scenario"></a><span data-ttu-id="26890-102">示例业务方案</span><span class="sxs-lookup"><span data-stu-id="26890-102">Sample Business Scenario</span></span>
<span data-ttu-id="26890-103">卫生保健进程通常很复杂且涉及许多系统。</span><span class="sxs-lookup"><span data-stu-id="26890-103">Health care processes are often complex and involve many systems.</span></span> <span data-ttu-id="26890-104">一个示例是一个患者进入医院时发生的过程并医生发送实验室测试将患者。</span><span class="sxs-lookup"><span data-stu-id="26890-104">An example is the process that occurs when a patient enters a hospital, and a physician sends the patient for a lab test.</span></span> <span data-ttu-id="26890-105">在此过程中涉及是五个方：</span><span class="sxs-lookup"><span data-stu-id="26890-105">Involved in this procedure are five parties:</span></span>  
  
-   <span data-ttu-id="26890-106">越过医生</span><span class="sxs-lookup"><span data-stu-id="26890-106">The attending physician</span></span>  
  
-   <span data-ttu-id="26890-107">医院注册系统</span><span class="sxs-lookup"><span data-stu-id="26890-107">The Hospital Registration System</span></span>  
  
-   <span data-ttu-id="26890-108">临床订单输入系统</span><span class="sxs-lookup"><span data-stu-id="26890-108">The Clinical Order Entry System</span></span>  
  
-   <span data-ttu-id="26890-109">与实验室系统</span><span class="sxs-lookup"><span data-stu-id="26890-109">The Laboratory System</span></span>  
  
-   <span data-ttu-id="26890-110">计费系统</span><span class="sxs-lookup"><span data-stu-id="26890-110">The Billing System</span></span>  
  
 <span data-ttu-id="26890-111">在此过程中可能会执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="26890-111">The following steps might occur in this process:</span></span>  
  
1.  <span data-ttu-id="26890-112">越过 doctor 注册患者。</span><span class="sxs-lookup"><span data-stu-id="26890-112">The attending doctor registers the patient.</span></span>  
  
    1.  <span data-ttu-id="26890-113">ADT ^ O04 注册消息广播医院注册系统。</span><span class="sxs-lookup"><span data-stu-id="26890-113">An ADT^O04 registration message is broadcast by the Hospital Registration System.</span></span>  
  
    2.  <span data-ttu-id="26890-114">ADT ^ O04 消息接收的所有订阅的消息，包括临床订单输入系统和与实验室系统的部门。</span><span class="sxs-lookup"><span data-stu-id="26890-114">The ADT^O04 message is received by all departments that subscribe to the message, including the Clinical Order Entry System and the Laboratory System.</span></span>  
  
2.  <span data-ttu-id="26890-115">Doctor 排序从实验室设施诊断研究。</span><span class="sxs-lookup"><span data-stu-id="26890-115">The doctor orders a diagnostic study from the laboratory facility.</span></span>  
  
    1.  <span data-ttu-id="26890-116">ORM ^ O01 订单消息的业务规则验证之后，从临床订单输入系统，发送。</span><span class="sxs-lookup"><span data-stu-id="26890-116">An ORM^O01 order message is sent from the Clinical Order Entry System, after validation of business rules.</span></span>  
  
    2.  <span data-ttu-id="26890-117">ORM ^ 与实验室系统收到 O01 消息。</span><span class="sxs-lookup"><span data-stu-id="26890-117">The ORM^O01 message is received by the Laboratory System.</span></span>  
  
3.  <span data-ttu-id="26890-118">实验室接收顺序，并返回一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="26890-118">The laboratory receives the order, and returns a confirmation.</span></span>  
  
    1.  <span data-ttu-id="26890-119">ORR ^ O02 订单确认消息发送实验室系统，指示可以执行顺序。</span><span class="sxs-lookup"><span data-stu-id="26890-119">An ORR^O02 order-confirmation message is sent by the Laboratory System, indicating that the order can be executed.</span></span>  
  
    2.  <span data-ttu-id="26890-120">ORR ^ 临床订单输入系统收到 O02 消息。</span><span class="sxs-lookup"><span data-stu-id="26890-120">The ORR^O02 message is received by the Clinical Order Entry System.</span></span>  
  
4.  <span data-ttu-id="26890-121">在完成的测试实验室将结果发送到 doctor 和其他部门。</span><span class="sxs-lookup"><span data-stu-id="26890-121">On completion of the tests, the laboratory sends the results to the doctor and other departments.</span></span>  
  
    1.  <span data-ttu-id="26890-122">ORU ^ 从与实验室系统发送 R01 测试结果消息。</span><span class="sxs-lookup"><span data-stu-id="26890-122">An ORU^R01 test-results message is sent from the Laboratory System.</span></span>  
  
    2.  <span data-ttu-id="26890-123">ORU ^ R01 消息接收临床订单输入系统和计费系统。</span><span class="sxs-lookup"><span data-stu-id="26890-123">The ORU^R01 message is received by the Clinical Order Entry System and the Billing System.</span></span>  
  
    3.  <span data-ttu-id="26890-124">接口引擎将出一封电子邮件发送到 doctor，接收其无线 PDA 上的实验室结果。</span><span class="sxs-lookup"><span data-stu-id="26890-124">The Interface Engine sends out an e-mail message to the doctor, who receives the lab results on his wireless PDA.</span></span>  
  
## <a name="the-btahl7-solution"></a><span data-ttu-id="26890-125">BTAHL7 解决方案</span><span class="sxs-lookup"><span data-stu-id="26890-125">The BTAHL7 Solution</span></span>  
 <span data-ttu-id="26890-126">上述示例业务方案是卫生保健系统集成所需的一个示例。</span><span class="sxs-lookup"><span data-stu-id="26890-126">The sample business scenario outlined above is an example of a health care system that needs integration.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="26890-127">与 BizTalk Server [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 为此应用场景，具有以下功能提供了解决方案：</span><span class="sxs-lookup"><span data-stu-id="26890-127">BizTalk Server with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) provides a solution for this scenario that features the following functionality:</span></span>  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="26890-128">集成所有中心辐射型结构中所涉及的系统。</span><span class="sxs-lookup"><span data-stu-id="26890-128"> integrates all of the systems involved in a hub-and-spoke arrangement.</span></span> <span data-ttu-id="26890-129">每个系统直接与通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="26890-129">Each system communicates directly with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="26890-130">它们无需直接相互通信。</span><span class="sxs-lookup"><span data-stu-id="26890-130">They do not have to communicate directly to each other.</span></span>  
  
2.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="26890-131">本机处理 HL7 编码消息。</span><span class="sxs-lookup"><span data-stu-id="26890-131"> handles HL7-encoded messages natively.</span></span> <span data-ttu-id="26890-132">无需进行自定义编码是必需的。</span><span class="sxs-lookup"><span data-stu-id="26890-132">No custom coding is required.</span></span>  
  
3.  <span data-ttu-id="26890-133">ADT ^ O04 注册消息广播到所有订阅它的系统。</span><span class="sxs-lookup"><span data-stu-id="26890-133">The ADT^O04 registration message is broadcast to all systems that subscribe to it.</span></span> <span data-ttu-id="26890-134">有关的发行者-订户消息传送模型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以灵活地设置和维护订阅到消息的系统的列表。</span><span class="sxs-lookup"><span data-stu-id="26890-134">The publisher-subscriber messaging model for [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] provides flexibility in setting up and maintaining the list of systems subscribing to the message.</span></span> <span data-ttu-id="26890-135">你可以添加到系统，或将其从订阅列表删除而不会影响系统的其余部分。</span><span class="sxs-lookup"><span data-stu-id="26890-135">You can add systems to or delete them from the subscription list without affecting the rest of the system.</span></span>  
  
4.  <span data-ttu-id="26890-136">用于验证 ORM 的业务规则 ^ O01 订单消息可以动态更改而不会影响系统的其余部分。</span><span class="sxs-lookup"><span data-stu-id="26890-136">The business rule used to validate the ORM^O01 order message can be changed dynamically without affecting the rest of the system.</span></span>  
  
5.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="26890-137">可以配置为自动生成 ORR ^ O02 订单确认 (ACK) 消息。</span><span class="sxs-lookup"><span data-stu-id="26890-137"> can be configured to automatically generate the ORR^O02 order-confirmation (ACK) message.</span></span>  
  
6.  <span data-ttu-id="26890-138">如有必要，你可以批处理任何用于发送，与其他消息，然后在批处理中从回执上处理它们。</span><span class="sxs-lookup"><span data-stu-id="26890-138">If necessary, you can batch any of the messages with others for sending, and process them on receipt from within the batch.</span></span>  
  
7.  <span data-ttu-id="26890-139">你可以验证所有消息在引擎和针对[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X 架构发布的 HL7 组织。</span><span class="sxs-lookup"><span data-stu-id="26890-139">You can validate all messages in the engine and against the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2X schemas published by the HL7 organization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26890-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26890-140">See Also</span></span>  
 [<span data-ttu-id="26890-141">BizTalk Server 如何满足业务需求</span><span class="sxs-lookup"><span data-stu-id="26890-141">How BizTalk Server Solves the Business Need</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)