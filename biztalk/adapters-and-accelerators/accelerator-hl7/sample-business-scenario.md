---
title: 示例业务方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c84acde2b7d3049c415954a561c1a53edb16a0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289941"
---
# <a name="sample-business-scenario"></a><span data-ttu-id="f8771-102">示例业务方案</span><span class="sxs-lookup"><span data-stu-id="f8771-102">Sample Business Scenario</span></span>
<span data-ttu-id="f8771-103">卫生保健进程通常很复杂，涉及到许多系统。</span><span class="sxs-lookup"><span data-stu-id="f8771-103">Health care processes are often complex and involve many systems.</span></span> <span data-ttu-id="f8771-104">示例是一个患者进入医院，时发生的过程和一名医生将发送的实验室测试患者。</span><span class="sxs-lookup"><span data-stu-id="f8771-104">An example is the process that occurs when a patient enters a hospital, and a physician sends the patient for a lab test.</span></span> <span data-ttu-id="f8771-105">在此过程中所涉及是五个参与方：</span><span class="sxs-lookup"><span data-stu-id="f8771-105">Involved in this procedure are five parties:</span></span>  
  
- <span data-ttu-id="f8771-106">参加医生</span><span class="sxs-lookup"><span data-stu-id="f8771-106">The attending physician</span></span>  
  
- <span data-ttu-id="f8771-107">医院注册系统</span><span class="sxs-lookup"><span data-stu-id="f8771-107">The Hospital Registration System</span></span>  
  
- <span data-ttu-id="f8771-108">临床订单输入系统</span><span class="sxs-lookup"><span data-stu-id="f8771-108">The Clinical Order Entry System</span></span>  
  
- <span data-ttu-id="f8771-109">与实验室系统</span><span class="sxs-lookup"><span data-stu-id="f8771-109">The Laboratory System</span></span>  
  
- <span data-ttu-id="f8771-110">计费系统</span><span class="sxs-lookup"><span data-stu-id="f8771-110">The Billing System</span></span>  
  
  <span data-ttu-id="f8771-111">在此过程中可能会执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f8771-111">The following steps might occur in this process:</span></span>  
  
1.  <span data-ttu-id="f8771-112">参加医生注册患者。</span><span class="sxs-lookup"><span data-stu-id="f8771-112">The attending doctor registers the patient.</span></span>  
  
    1.  <span data-ttu-id="f8771-113">ADT ^ O04 注册消息广播的医院注册系统。</span><span class="sxs-lookup"><span data-stu-id="f8771-113">An ADT^O04 registration message is broadcast by the Hospital Registration System.</span></span>  
  
    2.  <span data-ttu-id="f8771-114">ADT ^ O04 消息接收按订阅消息，包括临床订单输入系统和实验室系统的所有部门。</span><span class="sxs-lookup"><span data-stu-id="f8771-114">The ADT^O04 message is received by all departments that subscribe to the message, including the Clinical Order Entry System and the Laboratory System.</span></span>  
  
2.  <span data-ttu-id="f8771-115">医生排序从实验室设施诊断研究。</span><span class="sxs-lookup"><span data-stu-id="f8771-115">The doctor orders a diagnostic study from the laboratory facility.</span></span>  
  
    1.  <span data-ttu-id="f8771-116">ORM ^ O01 订单消息的业务规则验证后，从临床订单输入系统中，发送。</span><span class="sxs-lookup"><span data-stu-id="f8771-116">An ORM^O01 order message is sent from the Clinical Order Entry System, after validation of business rules.</span></span>  
  
    2.  <span data-ttu-id="f8771-117">ORM ^ O01 消息由与实验室系统接收。</span><span class="sxs-lookup"><span data-stu-id="f8771-117">The ORM^O01 message is received by the Laboratory System.</span></span>  
  
3.  <span data-ttu-id="f8771-118">实验室接收订单，并返回一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="f8771-118">The laboratory receives the order, and returns a confirmation.</span></span>  
  
    1.  <span data-ttu-id="f8771-119">ORR ^ O02 订单确认消息发送实验室系统中，指明可以执行顺序。</span><span class="sxs-lookup"><span data-stu-id="f8771-119">An ORR^O02 order-confirmation message is sent by the Laboratory System, indicating that the order can be executed.</span></span>  
  
    2.  <span data-ttu-id="f8771-120">ORR ^ 临床订单输入系统收到 O02 消息。</span><span class="sxs-lookup"><span data-stu-id="f8771-120">The ORR^O02 message is received by the Clinical Order Entry System.</span></span>  
  
4.  <span data-ttu-id="f8771-121">测试完成后，实验室将结果发送到医生和其他部门。</span><span class="sxs-lookup"><span data-stu-id="f8771-121">On completion of the tests, the laboratory sends the results to the doctor and other departments.</span></span>  
  
    1.  <span data-ttu-id="f8771-122">ORU ^ 从实验室系统发送 R01 测试结果消息。</span><span class="sxs-lookup"><span data-stu-id="f8771-122">An ORU^R01 test-results message is sent from the Laboratory System.</span></span>  
  
    2.  <span data-ttu-id="f8771-123">ORU ^ 临床订单输入系统和计费系统接收 R01 消息。</span><span class="sxs-lookup"><span data-stu-id="f8771-123">The ORU^R01 message is received by the Clinical Order Entry System and the Billing System.</span></span>  
  
    3.  <span data-ttu-id="f8771-124">接口引擎会将电子邮件消息将发送到博士，接收无线 PDA 的实验室结果。</span><span class="sxs-lookup"><span data-stu-id="f8771-124">The Interface Engine sends out an e-mail message to the doctor, who receives the lab results on his wireless PDA.</span></span>  
  
## <a name="the-btahl7-solution"></a><span data-ttu-id="f8771-125">BTAHL7 解决方案</span><span class="sxs-lookup"><span data-stu-id="f8771-125">The BTAHL7 Solution</span></span>  
 <span data-ttu-id="f8771-126">上面所述的示例业务方案是卫生保健系统集成所需的示例。</span><span class="sxs-lookup"><span data-stu-id="f8771-126">The sample business scenario outlined above is an example of a health care system that needs integration.</span></span> <span data-ttu-id="f8771-127">使用 Microsoft BizTalk Accelerator for HL7 MicrosoftBizTalk 服务器 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 为此方案中，具有以下功能提供了解决方案：</span><span class="sxs-lookup"><span data-stu-id="f8771-127">MicrosoftBizTalk Server with Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) provides a solution for this scenario that features the following functionality:</span></span>  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f8771-128">集成的所有参与中心辐射型结构系统。</span><span class="sxs-lookup"><span data-stu-id="f8771-128">integrates all of the systems involved in a hub-and-spoke arrangement.</span></span> <span data-ttu-id="f8771-129">直接与每个系统进行通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f8771-129">Each system communicates directly with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f8771-130">它们不需要直接彼此进行通信。</span><span class="sxs-lookup"><span data-stu-id="f8771-130">They do not have to communicate directly to each other.</span></span>  
  
2. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="f8771-131">本机处理 HL7 编码的消息。</span><span class="sxs-lookup"><span data-stu-id="f8771-131">handles HL7-encoded messages natively.</span></span> <span data-ttu-id="f8771-132">无自定义编码是必需的。</span><span class="sxs-lookup"><span data-stu-id="f8771-132">No custom coding is required.</span></span>  
  
3. <span data-ttu-id="f8771-133">ADT ^ O04 注册消息广播到所有订阅它的系统。</span><span class="sxs-lookup"><span data-stu-id="f8771-133">The ADT^O04 registration message is broadcast to all systems that subscribe to it.</span></span> <span data-ttu-id="f8771-134">有关的发布程序-订阅消息传送模型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以灵活地设置和维护系统订阅消息的列表。</span><span class="sxs-lookup"><span data-stu-id="f8771-134">The publisher-subscriber messaging model for [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] provides flexibility in setting up and maintaining the list of systems subscribing to the message.</span></span> <span data-ttu-id="f8771-135">可以添加到系统，或将其从删除的订阅列表而不会影响系统的其余部分。</span><span class="sxs-lookup"><span data-stu-id="f8771-135">You can add systems to or delete them from the subscription list without affecting the rest of the system.</span></span>  
  
4. <span data-ttu-id="f8771-136">业务规则用于验证 ORM ^ O01 订单消息可以动态更改而不会影响系统的其余部分。</span><span class="sxs-lookup"><span data-stu-id="f8771-136">The business rule used to validate the ORM^O01 order message can be changed dynamically without affecting the rest of the system.</span></span>  
  
5. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="f8771-137">可以配置为自动生成 ORR ^ O02 订单确认 (ACK) 消息。</span><span class="sxs-lookup"><span data-stu-id="f8771-137">can be configured to automatically generate the ORR^O02 order-confirmation (ACK) message.</span></span>  
  
6. <span data-ttu-id="f8771-138">如有必要，可以任何用于发送，与其他人的消息进行批处理和批处理内从回执上处理这些事件。</span><span class="sxs-lookup"><span data-stu-id="f8771-138">If necessary, you can batch any of the messages with others for sending, and process them on receipt from within the batch.</span></span>  
  
7. <span data-ttu-id="f8771-139">你可以验证所有消息引擎中和对[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 组织发布 2 X 架构。</span><span class="sxs-lookup"><span data-stu-id="f8771-139">You can validate all messages in the engine and against the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2X schemas published by the HL7 organization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8771-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8771-140">See Also</span></span>  
 [<span data-ttu-id="f8771-141">BizTalk Server 如何满足业务需求</span><span class="sxs-lookup"><span data-stu-id="f8771-141">How BizTalk Server Solves the Business Need</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)