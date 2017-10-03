---
title: "确认已知的问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues, acknowledgements
- acknowledgements, known issues
ms.assetid: cb45f80e-ba89-4b3f-a770-4b1cf9b8e220
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af5964e94f2ddc1d53d5259b174f8e551353711d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments-known-issues"></a><span data-ttu-id="25a7c-102">确认已知的问题</span><span class="sxs-lookup"><span data-stu-id="25a7c-102">Acknowledgments Known Issues</span></span>
<span data-ttu-id="25a7c-103">本节包含可以帮助您避免确认 (ACK) 错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="25a7c-103">This section contains useful information that may help you avoid acknowledgment (ACK) errors.</span></span>  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a><span data-ttu-id="25a7c-104">即使它包含 MSA6 字段接受通信 HL7 2.1 版的确认消息</span><span class="sxs-lookup"><span data-stu-id="25a7c-104">HL7 V2.1 acknowledgment message accepted even if it contains MSA6 field</span></span>  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="25a7c-105">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将接受 HL7 V2.1 确认消息，即使包含 MSA6 字段。</span><span class="sxs-lookup"><span data-stu-id="25a7c-105"> [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) will accept a HL7 V2.1 acknowledgment message even if contains the MSA6 field.</span></span>  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a><span data-ttu-id="25a7c-106">MSA-01 值不会提交确认错误的生成</span><span class="sxs-lookup"><span data-stu-id="25a7c-106">MSA-01 value not generated for commit acknowledgment errors</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="25a7c-107">不生成提交确认错误 (CE) MSA-01 确认代码。</span><span class="sxs-lookup"><span data-stu-id="25a7c-107"> does not generate an MSA-01 acknowledgment code for commit acknowledgments errors (CE).</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="25a7c-108">双向 MLLP 适配器可能不会检测 ACK 问题</span><span class="sxs-lookup"><span data-stu-id="25a7c-108">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="25a7c-109">当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]收到 ACK 双向 MLLP 适配器，适配器执行 ACK 以确定其有效性轻型验证。</span><span class="sxs-lookup"><span data-stu-id="25a7c-109">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="25a7c-110">如果找到有效，则提取 MSA1 字段，而且根据其值，该适配器将重试、 将挂起，或删除原始消息回复 ACK。</span><span class="sxs-lookup"><span data-stu-id="25a7c-110">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="25a7c-111">但是，由于执行适配器验证不是完整的验证，很可能该适配器将不会检测确认问题</span><span class="sxs-lookup"><span data-stu-id="25a7c-111">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="25a7c-112">例如，该适配器无法确定 ACK 无效，并且删除原始消息，而管道将确定 ACK 不是格式良好，挂起的确认消息。</span><span class="sxs-lookup"><span data-stu-id="25a7c-112">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a><span data-ttu-id="25a7c-113">V2。使用多个错误的 XML 确认将未通过验证</span><span class="sxs-lookup"><span data-stu-id="25a7c-113">V2.XML ACKs with multiple errors will fail validation</span></span>  
 <span data-ttu-id="25a7c-114">如果传入 V2。XML 消息包含多个错误，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器可能会生成 V2。与错误字段中的多个错误的 XML ACK。</span><span class="sxs-lookup"><span data-stu-id="25a7c-114">If an incoming V2.XML message contains more than one error, the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser may generate a V2.XML ACK with more than one error in the error field.</span></span> <span data-ttu-id="25a7c-115">此类 V2。XML ACK 将未通过验证，因为 HL7 标准指定分析器可以报告 V2 中的只有一个错误。XML ACK 错误字段。</span><span class="sxs-lookup"><span data-stu-id="25a7c-115">Such a V2.XML ACK will fail validation, because the HL7 standard specifies that the parser can report only one error in a V2.XML ACK error field.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="25a7c-116">MLLP 性能计数器进行计数确认</span><span class="sxs-lookup"><span data-stu-id="25a7c-116">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="25a7c-117">一个度量值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]性能将由 MLLP 适配器，处理的消息数，如 MLLP 性能计数器所示。</span><span class="sxs-lookup"><span data-stu-id="25a7c-117">One measure of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="25a7c-118">此计数测量接收或传输的消息的数量。</span><span class="sxs-lookup"><span data-stu-id="25a7c-118">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="25a7c-119">但是，计数不衡量 Ack 接收或发送的数。</span><span class="sxs-lookup"><span data-stu-id="25a7c-119">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="25a7c-120">生成的双向 MLLP 适配器否认</span><span class="sxs-lookup"><span data-stu-id="25a7c-120">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="25a7c-121">何时双向 MLLP 适配器挂起消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成否认 （否定确认） 并将其放在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="25a7c-121">When a two-way MLLP adapter suspends a message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="25a7c-122">这可能是意外的行为。</span><span class="sxs-lookup"><span data-stu-id="25a7c-122">This may be unexpected behavior.</span></span> <span data-ttu-id="25a7c-123">你可能想要从 MessageBox 数据库中删除否认或将其映射到另一条消息。</span><span class="sxs-lookup"><span data-stu-id="25a7c-123">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a><span data-ttu-id="25a7c-124">数据类型的批处理消息的确认</span><span class="sxs-lookup"><span data-stu-id="25a7c-124">Data type of an ACK to a batch message</span></span>  
 <span data-ttu-id="25a7c-125">在批处理消息响应中生成一条确认消息，在 MSH10 字段 (消息控件 ID) 将使用的 GUID，而不是基于批处理消息中的 MSH10 字段的数据类型。</span><span class="sxs-lookup"><span data-stu-id="25a7c-125">In an ACK message generated in response to a batch message, the MSH10 field (message control ID) will be a GUID, rather than being based on the data type of the MSH10 field in the batch message.</span></span>  
  
## <a name="generated-acknowledgments-doc-type"></a><span data-ttu-id="25a7c-126">生成的确认文档类型</span><span class="sxs-lookup"><span data-stu-id="25a7c-126">Generated acknowledgments DOC type</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="25a7c-127">生成使用文档类型 http:// 确认[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_24_GLO_DEF 或 http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X #ACK_25_GLO_DEF。</span><span class="sxs-lookup"><span data-stu-id="25a7c-127"> generates acknowledgments using the DOC type http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_24_GLO_DEF or http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_25_GLO_DEF.</span></span> <span data-ttu-id="25a7c-128">如果你的目标方使用不同的命名空间，你必须应用中发送端口; 正文映射否则，可能会遇到序列化错误。</span><span class="sxs-lookup"><span data-stu-id="25a7c-128">If your destination party uses a different namespace, you must apply a body map in the send port; otherwise, you may encounter serialization errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a7c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25a7c-129">See Also</span></span>  
 [<span data-ttu-id="25a7c-130">已知问题</span><span class="sxs-lookup"><span data-stu-id="25a7c-130">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)