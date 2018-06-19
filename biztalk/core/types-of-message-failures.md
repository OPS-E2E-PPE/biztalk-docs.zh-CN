---
title: 类型的消息失败 |Microsoft 文档
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
ms.openlocfilehash: 466c7c21fd1a00e192307dd82384dc613b6697a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286749"
---
# <a name="types-of-message-failures"></a><span data-ttu-id="97c7f-102">类型的消息失败</span><span class="sxs-lookup"><span data-stu-id="97c7f-102">Types of Message Failures</span></span>
<span data-ttu-id="97c7f-103">本主题列出了可能会发生消息失败的点。</span><span class="sxs-lookup"><span data-stu-id="97c7f-103">This topic lists different points where a message failure may occur.</span></span>  
  
 <span data-ttu-id="97c7f-104">**在反汇编阶段失败**</span><span class="sxs-lookup"><span data-stu-id="97c7f-104">**Failures in the disassembly phase**</span></span>  
  
 <span data-ttu-id="97c7f-105">处理也可能在拆装阶段失败；即在某个管道组件中失败。</span><span class="sxs-lookup"><span data-stu-id="97c7f-105">Processing might also fail during the disassembly phase; that is, failure in one of the pipeline components.</span></span> <span data-ttu-id="97c7f-106">例如，由于在处理服务器上没有解密证书而导致解密失败，或者由于架构或消息中的问题而导致解析失败。</span><span class="sxs-lookup"><span data-stu-id="97c7f-106">For example, decryption failed due to absence of decryption cert on the processing server, or parsing failure due to problem either in the schema or in the message.</span></span>  
  
 <span data-ttu-id="97c7f-107">**路由中的故障**</span><span class="sxs-lookup"><span data-stu-id="97c7f-107">**Failures in routing**</span></span>  
  
 <span data-ttu-id="97c7f-108">当消息拆装成功后，下一个可能的故障点就是路由过程；例如，用户启用某个业务流程的相应接收位置，而忘记登记该业务流程。</span><span class="sxs-lookup"><span data-stu-id="97c7f-108">After a message disassembles successfully, the next potential failure point is routing; for example, users enable a corresponding receive location of an orchestration and forget to enlist the orchestration.</span></span> <span data-ttu-id="97c7f-109">在这种情况下，从接收位置提取的消息将无法进行路由，MessageBox 数据库将会生成路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="97c7f-109">In this case, the message picked up from the receive location fails routing and the MessageBox database generates a Routing Failure report.</span></span>  
  
 <span data-ttu-id="97c7f-110">路由故障报告将作为不可恢复的挂起消息列出于 BizTalk Server 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="97c7f-110">Routing Failure reports are listed in the BizTalk Server Administration Console as non-resumable suspended messages.</span></span> <span data-ttu-id="97c7f-111">每个路由故障报告都包含一个在路由故障发生时拍取的消息属性快照。</span><span class="sxs-lookup"><span data-stu-id="97c7f-111">Each Routing Failure report contains a message property snap shot taken when the routing failure occurred.</span></span> <span data-ttu-id="97c7f-112">您可以使用每个报告中的信息为其相关联的消息确定路由失败的原因。</span><span class="sxs-lookup"><span data-stu-id="97c7f-112">You can use the information in each report to determine why routing failed for its associated message.</span></span> <span data-ttu-id="97c7f-113">如果相关联的消息可恢复，则可以更正路由问题并恢复该消息，这样，就可以继续进行处理。</span><span class="sxs-lookup"><span data-stu-id="97c7f-113">If the associated message is resumable, you can correct the routing problem and resume the message so that processing continues.</span></span> <span data-ttu-id="97c7f-114">将在结果列表中列出路由故障报告，其中服务名和服务类型为空。</span><span class="sxs-lookup"><span data-stu-id="97c7f-114">Routing Failure reports are listed in the results list with a blank service name and service type.</span></span> <span data-ttu-id="97c7f-115">在终止已挂起的实例时，Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 作业将自动删除与已挂起的实例相关联的路由故障报告，默认情况下，该作业每隔一分钟运行一次。</span><span class="sxs-lookup"><span data-stu-id="97c7f-115">When you terminate a suspended instance, the Routing Failure report associated with the suspended instance is automatically deleted by the Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job that runs every minute by default.</span></span> <span data-ttu-id="97c7f-116">有关 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 作业的详细信息，请参阅[数据库结构和作业](../core/database-structure-and-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="97c7f-116">For more information about the Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job, see [Database Structure and Jobs](../core/database-structure-and-jobs.md).</span></span>  
  
 <span data-ttu-id="97c7f-117">**转换阶段期间出现的故障**</span><span class="sxs-lookup"><span data-stu-id="97c7f-117">**Failures during the transformation phase**</span></span>  
  
-   <span data-ttu-id="97c7f-118">**收到消息**。</span><span class="sxs-lookup"><span data-stu-id="97c7f-118">**Received Messages**.</span></span> <span data-ttu-id="97c7f-119">从接收位置收到消息后，会将消息进行拆装（例如解密或解析），通过接收端口上指定的入站映射可能会选择将消息转换成其他格式，并将其发布到 MessageBox 以路由至业务流程或发送端口。</span><span class="sxs-lookup"><span data-stu-id="97c7f-119">When a message is received from Receive Location, the message is disassembled (for example, decrypted and parsed), the message might optionally be transformed to a different format via an Inbound Map specified on a receive Port, and published to the MessageBox for routing to an orchestration or a Send Port.</span></span> <span data-ttu-id="97c7f-120">在这种情况下，在转换阶段中可能会由于入站映射不正确或者架构或收到的消息中存在问题而导致处理失败。</span><span class="sxs-lookup"><span data-stu-id="97c7f-120">In this case, processing may fail during transformation phase due to incorrect Inbound Map, or problems in the schema or in the message received.</span></span>  
  
-   <span data-ttu-id="97c7f-121">**已发送的邮件**。</span><span class="sxs-lookup"><span data-stu-id="97c7f-121">**Sent Messages**.</span></span> <span data-ttu-id="97c7f-122">在将消息发送到发送位置时，在发送端口上配置的出站映射可能会选择转换该消息。</span><span class="sxs-lookup"><span data-stu-id="97c7f-122">When a message is to be sent to a Send Location, an Outbound Map configured on Send Port might optionally transform the message.</span></span> <span data-ttu-id="97c7f-123">然后，对转换后的消息进行组装，并将其传送给适配器，以最终传输到发送位置。</span><span class="sxs-lookup"><span data-stu-id="97c7f-123">Then the transformed message is assembled and handed to the adapter for final transmission to the Send Location.</span></span> <span data-ttu-id="97c7f-124">在这种情况下，在转换阶段中可能会由于出站映射不正确或者架构或源消息中存在问题而导致处理失败。</span><span class="sxs-lookup"><span data-stu-id="97c7f-124">In this case, processing may fail during transformation phase due to incorrect Outbound Map or problem in schema or source message.</span></span>  
  
 <span data-ttu-id="97c7f-125">**在消息的程序集阶段失败**</span><span class="sxs-lookup"><span data-stu-id="97c7f-125">**Failures in the message assembly phase**</span></span>  
  
 <span data-ttu-id="97c7f-126">处理也可以在消息组装阶段失败 – 换句话说 ， 在管道组件中失败 。</span><span class="sxs-lookup"><span data-stu-id="97c7f-126">Processing can also fail during message assembly phase – in other words, failing in pipeline component.</span></span> <span data-ttu-id="97c7f-127">当消息成功组装后，下一个可能的故障点会出现在向发送位置进行传输的过程中；例如，发送位置（属于合作伙伴）可能已关闭或不存在。</span><span class="sxs-lookup"><span data-stu-id="97c7f-127">After a message successfully assembles, the next potential failure point becomes transmission to Send Location; for example, the Send Location (which belongs to the partner) might be down or not exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c7f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97c7f-128">See Also</span></span>  
 [<span data-ttu-id="97c7f-129">调查业务流程、 端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="97c7f-129">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)