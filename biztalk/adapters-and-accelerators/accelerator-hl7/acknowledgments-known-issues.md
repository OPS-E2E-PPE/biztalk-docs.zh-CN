---
title: 确认已知的问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, acknowledgements
- acknowledgements, known issues
ms.assetid: cb45f80e-ba89-4b3f-a770-4b1cf9b8e220
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f585c9f0b147f50bd915bb757a3ed3c09a56ee8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966150"
---
# <a name="acknowledgments-known-issues"></a><span data-ttu-id="e4cfa-102">确认已知的问题</span><span class="sxs-lookup"><span data-stu-id="e4cfa-102">Acknowledgments Known Issues</span></span>
<span data-ttu-id="e4cfa-103">本部分包含可帮助你避免确认 (ACK) 错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-103">This section contains useful information that may help you avoid acknowledgment (ACK) errors.</span></span>  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a><span data-ttu-id="e4cfa-104">HL7 2.1 版的确认消息，即使它包含 MSA6 字段会被接受</span><span class="sxs-lookup"><span data-stu-id="e4cfa-104">HL7 V2.1 acknowledgment message accepted even if it contains MSA6 field</span></span>  
 <span data-ttu-id="e4cfa-105">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将接受，即使包含 MSA6 字段一 HL7 2.1 版的确认消息。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-105">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) will accept a HL7 V2.1 acknowledgment message even if contains the MSA6 field.</span></span>  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a><span data-ttu-id="e4cfa-106">MSA 01 值不生成的提交确认错误</span><span class="sxs-lookup"><span data-stu-id="e4cfa-106">MSA-01 value not generated for commit acknowledgment errors</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e4cfa-107"> 不会生成提交确认错误 (CE) 的 MSA 01 确认代码。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-107"> does not generate an MSA-01 acknowledgment code for commit acknowledgments errors (CE).</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="e4cfa-108">双向处的 MLLP 适配器可能没有检测到一个 ACK 的问题</span><span class="sxs-lookup"><span data-stu-id="e4cfa-108">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="e4cfa-109">当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]收到 ACK 上双向处的 MLLP 适配器，适配器执行轻量验证上确认以确定其有效性。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-109">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="e4cfa-110">如果找到有效，提取 MSA1 字段，并根据其值，适配器将重试次数、 挂起或删除原始消息回复确认。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-110">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="e4cfa-111">但是，由于适配器执行的验证不是完整的验证，则可能适配器将不会检测问题的确认。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-111">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="e4cfa-112">例如，适配器可以确定将确认有效，并且删除原始消息，而该管道会确定确认不是格式正确，并挂起的确认消息。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-112">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a><span data-ttu-id="e4cfa-113">V2。带有多个错误的 XML Ack 验证将失败</span><span class="sxs-lookup"><span data-stu-id="e4cfa-113">V2.XML ACKs with multiple errors will fail validation</span></span>  
 <span data-ttu-id="e4cfa-114">如果传入 V2。XML 消息包含多个错误，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器可能会生成 V2。在错误字段中的多个错误的 XML 确认。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-114">If an incoming V2.XML message contains more than one error, the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser may generate a V2.XML ACK with more than one error in the error field.</span></span> <span data-ttu-id="e4cfa-115">此类第 2 版。XML 确认将验证失败，因为 HL7 标准指定分析器可以报告 V2 中的只有一个错误。XML 确认错误字段。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-115">Such a V2.XML ACK will fail validation, because the HL7 standard specifies that the parser can report only one error in a V2.XML ACK error field.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="e4cfa-116">MLLP 性能计数器进行计数的 Ack</span><span class="sxs-lookup"><span data-stu-id="e4cfa-116">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="e4cfa-117">一个度量值的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]性能将 MLLP 适配器，处理的消息数，如 MLLP 性能计数器所示。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-117">One measure of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="e4cfa-118">此计数度量值接收或传输的消息的数。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-118">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="e4cfa-119">但是，计数不衡量确认已接收或发送数。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-119">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="e4cfa-120">生成的双向处的 MLLP 适配器 NAK</span><span class="sxs-lookup"><span data-stu-id="e4cfa-120">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="e4cfa-121">双向处的 MLLP 适配器挂起消息，当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成 NAK （否定确认），并将它放在 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-121">When a two-way MLLP adapter suspends a message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="e4cfa-122">这可能会出现意外的行为。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-122">This may be unexpected behavior.</span></span> <span data-ttu-id="e4cfa-123">您可能想要从 MessageBox 数据库删除 NAK 或将其映射到另一条消息。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-123">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a><span data-ttu-id="e4cfa-124">数据类型的批处理消息的确认</span><span class="sxs-lookup"><span data-stu-id="e4cfa-124">Data type of an ACK to a batch message</span></span>  
 <span data-ttu-id="e4cfa-125">在响应的批处理消息中生成的确认消息，MSH10 字段 (消息控件 ID) 将是一个 GUID，而不是基于批处理消息中的 MSH10 字段的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-125">In an ACK message generated in response to a batch message, the MSH10 field (message control ID) will be a GUID, rather than being based on the data type of the MSH10 field in the batch message.</span></span>  
  
## <a name="generated-acknowledgments-doc-type"></a><span data-ttu-id="e4cfa-126">生成的确认文档类型</span><span class="sxs-lookup"><span data-stu-id="e4cfa-126">Generated acknowledgments DOC type</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e4cfa-127"> 生成使用文档类型的确认 http://Microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF 或 http://Microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF 。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-127"> generates acknowledgments using the DOC type http://Microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF or http://Microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.</span></span> <span data-ttu-id="e4cfa-128">如果目标参与方使用不同的命名空间，则必须应用的正文映射中的发送端口;否则，可能会遇到序列化错误。</span><span class="sxs-lookup"><span data-stu-id="e4cfa-128">If your destination party uses a different namespace, you must apply a body map in the send port; otherwise, you may encounter serialization errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cfa-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4cfa-129">See Also</span></span>  
 [<span data-ttu-id="e4cfa-130">已知问题</span><span class="sxs-lookup"><span data-stu-id="e4cfa-130">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)