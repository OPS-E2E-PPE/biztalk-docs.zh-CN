---
title: MLLP 适配器已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP adapters, known issues
- known issues, MLLP adapters
ms.assetid: 66af8fcc-981a-4a77-80b7-84824bfae608
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb90c62baebb8fc73b939c0a3ea20eb85e9b0e28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970830"
---
# <a name="mllp-adapter-known-issues"></a><span data-ttu-id="6e87f-102">MLLP 适配器已知问题</span><span class="sxs-lookup"><span data-stu-id="6e87f-102">MLLP Adapter Known Issues</span></span>
<span data-ttu-id="6e87f-103">本部分包含可帮助你避免最少的较低层协议 (MLLP) 适配器错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="6e87f-103">This section contains useful information that may help you avoid Minimal Lower Layer Protocol (MLLP) adapter errors.</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="6e87f-104">双向处的 MLLP 适配器可能没有检测到一个 ACK 的问题</span><span class="sxs-lookup"><span data-stu-id="6e87f-104">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="6e87f-105">当 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) 接收的确认 (ACK) 上的双向 MLLP 适配器，适配器将执行上确认以确定其有效性的轻量验证。</span><span class="sxs-lookup"><span data-stu-id="6e87f-105">When Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) receives an acknowledgment (ACK) on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="6e87f-106">如果找到有效，提取 MSA1 字段，并根据其值，适配器将重试次数、 挂起或删除原始消息回复确认。</span><span class="sxs-lookup"><span data-stu-id="6e87f-106">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="6e87f-107">但是，由于适配器执行的验证不是完整的验证，则可能适配器将不会检测问题的确认。</span><span class="sxs-lookup"><span data-stu-id="6e87f-107">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="6e87f-108">例如，适配器可以确定将确认有效，并且删除原始消息，而该管道会确定确认不是格式正确，并挂起的确认消息。</span><span class="sxs-lookup"><span data-stu-id="6e87f-108">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="6e87f-109">MLLP 性能计数器进行计数的 Ack</span><span class="sxs-lookup"><span data-stu-id="6e87f-109">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="6e87f-110">一个性能度量值将由 MLLP 适配器，处理的消息数，如 MLLP 性能计数器所示。</span><span class="sxs-lookup"><span data-stu-id="6e87f-110">One measure of performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="6e87f-111">此计数度量值接收或传输的消息的数。</span><span class="sxs-lookup"><span data-stu-id="6e87f-111">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="6e87f-112">但是，计数不衡量确认已接收或发送数。</span><span class="sxs-lookup"><span data-stu-id="6e87f-112">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a><span data-ttu-id="6e87f-113">MLLP 适配器连接名称不能保证是唯一的</span><span class="sxs-lookup"><span data-stu-id="6e87f-113">MLLP adapter connection names are not guaranteed to be unique</span></span>  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="6e87f-114"> 不保证处的 MLLP 适配器的属性页中输入的连接名称的唯一性。</span><span class="sxs-lookup"><span data-stu-id="6e87f-114"> does not guarantee the uniqueness of the connection name entered in the property pages of an MLLP adapter.</span></span> <span data-ttu-id="6e87f-115">请确保该名称在此必填字段中输入的描述性和相关连接。</span><span class="sxs-lookup"><span data-stu-id="6e87f-115">Ensure that descriptive and relevant connection names are entered in this required field.</span></span> <span data-ttu-id="6e87f-116">尝试了解连接的行为时，使用表示业务线应用程序的连接名称可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="6e87f-116">Using connection names that represent line-of-business applications can be useful when trying to understand the behavior of the connection.</span></span> <span data-ttu-id="6e87f-117">例如，PerfMon 计数器使用的连接名称。</span><span class="sxs-lookup"><span data-stu-id="6e87f-117">For example, PerfMon counters use the connection name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e87f-118">BTAHL7 确保唯一性的接收位置或发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="6e87f-118">BTAHL7 does ensure the uniqueness of receive locations or send port names.</span></span>  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a><span data-ttu-id="6e87f-119">双向 MLLP 适配器不会发送一批中的所有消息的提交确认</span><span class="sxs-lookup"><span data-stu-id="6e87f-119">Two-way MLLP adapters do not send Commit ACKs for all messages in a batch</span></span>  
 <span data-ttu-id="6e87f-120">生成了提交确认，批处理中配置每个消息和系统发送到批处理时双向 MLLP 接收适配器，适配器仅发送与批处理中的第一个消息对应提交确认。</span><span class="sxs-lookup"><span data-stu-id="6e87f-120">When you configure each message in a batch to generate a Commit ACK, and the system sends the batch to a two-way MLLP receive adapter, the adapter will only send the Commit ACK corresponding to the first message in the batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e87f-121">建议使用单向处的 MLLP 适配器传输批。</span><span class="sxs-lookup"><span data-stu-id="6e87f-121">It is recommended that you use a one-way MLLP adapter to transport batches.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="6e87f-122">生成的双向处的 MLLP 适配器 NAK</span><span class="sxs-lookup"><span data-stu-id="6e87f-122">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="6e87f-123">双向处的 MLLP 适配器将挂起任何消息，当处的 MLLP 适配器生成 NAK （否定确认），并将其放置在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="6e87f-123">When a two-way MLLP adapter suspends any message, the MLLP adapter generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="6e87f-124">这可能会出现意外的行为。</span><span class="sxs-lookup"><span data-stu-id="6e87f-124">This may be unexpected behavior.</span></span> <span data-ttu-id="6e87f-125">您可能想要从 MessageBox 数据库删除 NAK 或将其映射到另一条消息。</span><span class="sxs-lookup"><span data-stu-id="6e87f-125">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a><span data-ttu-id="6e87f-126">双向处的 MLLP 适配器仅支持 2.X 消息格式</span><span class="sxs-lookup"><span data-stu-id="6e87f-126">Two-way MLLP adapter only supports the 2.X message format</span></span>  
 <span data-ttu-id="6e87f-127">双向处的 MLLP 适配器目前支持仅 2.X 消息格式。</span><span class="sxs-lookup"><span data-stu-id="6e87f-127">The two-way MLLP adapter currently supports only the 2.X message format.</span></span>  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a><span data-ttu-id="6e87f-128">双向处的 MLLP 适配器不支持静态确认</span><span class="sxs-lookup"><span data-stu-id="6e87f-128">Two-way MLLP adapter does not support static acknowledgments</span></span>  
 <span data-ttu-id="6e87f-129">双向发送适配器不支持处理静态确认。</span><span class="sxs-lookup"><span data-stu-id="6e87f-129">The two-way send adapter does not support processing static acknowledgments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e87f-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e87f-130">See Also</span></span>  
 [<span data-ttu-id="6e87f-131">已知问题</span><span class="sxs-lookup"><span data-stu-id="6e87f-131">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)