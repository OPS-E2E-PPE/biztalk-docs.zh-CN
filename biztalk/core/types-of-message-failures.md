---
title: 消息失败的类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transformation stage
- assembly stage
- errors, disassembly stage
- errors, assembly stage
- routing, errors
- errors, transformation stage
- errors, messages [HAT]
- errors, routing
- disassembly stage, errors
- messages, errors [HAT]
ms.assetid: 3a8e1c58-4b53-4439-837d-aaa233eb9158
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c72db5870f89525a6a0db5f88a54bbe2db3f24
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268813"
---
# <a name="types-of-message-failures"></a><span data-ttu-id="aad56-102">消息失败的类型</span><span class="sxs-lookup"><span data-stu-id="aad56-102">Types of Message Failures</span></span>
<span data-ttu-id="aad56-103">本主题列出了可能发生消息故障时的不同时间点。</span><span class="sxs-lookup"><span data-stu-id="aad56-103">This topic lists different points where a message failure may occur.</span></span>  
  
 <span data-ttu-id="aad56-104">**在拆装阶段失败**</span><span class="sxs-lookup"><span data-stu-id="aad56-104">**Failures in the disassembly phase**</span></span>  
  
 <span data-ttu-id="aad56-105">在拆装阶段中; 也可能会失败处理也就是说，一个管道组件中的故障。</span><span class="sxs-lookup"><span data-stu-id="aad56-105">Processing might also fail during the disassembly phase; that is, failure in one of the pipeline components.</span></span> <span data-ttu-id="aad56-106">例如，解密失败，因为没有由于架构中或在消息中的问题进行分析失败的处理服务器上的解密证书。</span><span class="sxs-lookup"><span data-stu-id="aad56-106">For example, decryption failed due to absence of decryption cert on the processing server, or parsing failure due to problem either in the schema or in the message.</span></span>  
  
 <span data-ttu-id="aad56-107">**路由过程中失败**</span><span class="sxs-lookup"><span data-stu-id="aad56-107">**Failures in routing**</span></span>  
  
 <span data-ttu-id="aad56-108">当消息拆装成功后下, 一步的潜在故障点就路由;例如，相应的用户启用接收位置的业务流程，而忘记登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="aad56-108">After a message disassembles successfully, the next potential failure point is routing; for example, users enable a corresponding receive location of an orchestration and forget to enlist the orchestration.</span></span> <span data-ttu-id="aad56-109">在这种情况下，无法从接收位置提取的消息进行路由，MessageBox 数据库会生成路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="aad56-109">In this case, the message picked up from the receive location fails routing and the MessageBox database generates a Routing Failure report.</span></span>  
  
 <span data-ttu-id="aad56-110">BizTalk Server 管理控制台中作为不可恢复的挂起消息列出路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="aad56-110">Routing Failure reports are listed in the BizTalk Server Administration Console as non-resumable suspended messages.</span></span> <span data-ttu-id="aad56-111">每个路由故障报告包含消息属性时拍取路由故障发生。</span><span class="sxs-lookup"><span data-stu-id="aad56-111">Each Routing Failure report contains a message property snap shot taken when the routing failure occurred.</span></span> <span data-ttu-id="aad56-112">可以使用每个报表中的信息来确定路由失败的原因为其关联的消息。</span><span class="sxs-lookup"><span data-stu-id="aad56-112">You can use the information in each report to determine why routing failed for its associated message.</span></span> <span data-ttu-id="aad56-113">如果相关联的消息是可恢复，可以更正路由问题并恢复该消息，以便继续进行处理。</span><span class="sxs-lookup"><span data-stu-id="aad56-113">If the associated message is resumable, you can correct the routing problem and resume the message so that processing continues.</span></span> <span data-ttu-id="aad56-114">具有空白服务名称和服务类型的结果列表中列出路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="aad56-114">Routing Failure reports are listed in the results list with a blank service name and service type.</span></span> <span data-ttu-id="aad56-115">终止挂起的实例时，默认情况下运行每隔一分钟的 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 作业自动删除与挂起的实例关联的路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="aad56-115">When you terminate a suspended instance, the Routing Failure report associated with the suspended instance is automatically deleted by the Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job that runs every minute by default.</span></span> <span data-ttu-id="aad56-116">有关 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 作业的详细信息，请参阅[数据库结构和作业](../core/database-structure-and-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="aad56-116">For more information about the Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job, see [Database Structure and Jobs](../core/database-structure-and-jobs.md).</span></span>  
  
 <span data-ttu-id="aad56-117">**在转换阶段失败**</span><span class="sxs-lookup"><span data-stu-id="aad56-117">**Failures during the transformation phase**</span></span>  
  
- <span data-ttu-id="aad56-118">**收到的消息**。</span><span class="sxs-lookup"><span data-stu-id="aad56-118">**Received Messages**.</span></span> <span data-ttu-id="aad56-119">当从接收位置收到的消息时，该消息被拆装 （例如解密或解析），消息可能会根据需要转换为入站映射指定接收端口，并将发布到 MessageBox 中以便通过不同的格式路由到业务流程或发送端口。</span><span class="sxs-lookup"><span data-stu-id="aad56-119">When a message is received from Receive Location, the message is disassembled (for example, decrypted and parsed), the message might optionally be transformed to a different format via an Inbound Map specified on a receive Port, and published to the MessageBox for routing to an orchestration or a Send Port.</span></span> <span data-ttu-id="aad56-120">在这种情况下，处理可能会在转换阶段，由于不正确的入站映射或架构中或在收到的消息时出现问题而失败。</span><span class="sxs-lookup"><span data-stu-id="aad56-120">In this case, processing may fail during transformation phase due to incorrect Inbound Map, or problems in the schema or in the message received.</span></span>  
  
- <span data-ttu-id="aad56-121">**发送的消息，**。</span><span class="sxs-lookup"><span data-stu-id="aad56-121">**Sent Messages**.</span></span> <span data-ttu-id="aad56-122">当消息发送到发送位置时，发送端口上配置出站映射可能会选择转换该消息。</span><span class="sxs-lookup"><span data-stu-id="aad56-122">When a message is to be sent to a Send Location, an Outbound Map configured on Send Port might optionally transform the message.</span></span> <span data-ttu-id="aad56-123">然后转换后的消息是收集组，并且传递到适配器以最终传输到发送位置。</span><span class="sxs-lookup"><span data-stu-id="aad56-123">Then the transformed message is assembled and handed to the adapter for final transmission to the Send Location.</span></span> <span data-ttu-id="aad56-124">在这种情况下，处理可能会在转换阶段，由于不正确的出站映射或架构或源消息中的问题而失败。</span><span class="sxs-lookup"><span data-stu-id="aad56-124">In this case, processing may fail during transformation phase due to incorrect Outbound Map or problem in schema or source message.</span></span>  
  
  <span data-ttu-id="aad56-125">**在消息组装阶段中失败**</span><span class="sxs-lookup"><span data-stu-id="aad56-125">**Failures in the message assembly phase**</span></span>  
  
  <span data-ttu-id="aad56-126">处理可能也会失败在消息组装阶段 – 换而言之，在管道组件中的失败。</span><span class="sxs-lookup"><span data-stu-id="aad56-126">Processing can also fail during message assembly phase – in other words, failing in pipeline component.</span></span> <span data-ttu-id="aad56-127">当消息成功组装后下, 一步的潜在故障点将恢复传输到发送位置;例如，发送位置 （属于合作伙伴） 可能已关闭或不存在。</span><span class="sxs-lookup"><span data-stu-id="aad56-127">After a message successfully assembles, the next potential failure point becomes transmission to Send Location; for example, the Send Location (which belongs to the partner) might be down or not exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad56-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="aad56-128">See Also</span></span>  
 [<span data-ttu-id="aad56-129">调查业务流程、端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="aad56-129">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)