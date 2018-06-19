---
title: MLLP 适配器已知问题 |Microsoft 文档
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
ms.openlocfilehash: 5cbae1bf4bf04e2ecf4e643ad5107b9e0fd70f70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206053"
---
# <a name="mllp-adapter-known-issues"></a><span data-ttu-id="06450-102">MLLP 适配器已知问题</span><span class="sxs-lookup"><span data-stu-id="06450-102">MLLP Adapter Known Issues</span></span>
<span data-ttu-id="06450-103">本节包含可以帮助您避免最小较低层协议 (MLLP) 适配器错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="06450-103">This section contains useful information that may help you avoid Minimal Lower Layer Protocol (MLLP) adapter errors.</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="06450-104">双向 MLLP 适配器可能不会检测 ACK 问题</span><span class="sxs-lookup"><span data-stu-id="06450-104">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="06450-105">当[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) 收到确认 (ACK) 上的双向 MLLP 适配器，适配器执行 ACK 以确定其有效性轻型验证。</span><span class="sxs-lookup"><span data-stu-id="06450-105">When [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) receives an acknowledgment (ACK) on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="06450-106">如果找到有效，则提取 MSA1 字段，而且根据其值，该适配器将重试、 将挂起，或删除原始消息回复 ACK。</span><span class="sxs-lookup"><span data-stu-id="06450-106">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="06450-107">但是，由于执行适配器验证不是完整的验证，很可能该适配器将不会检测确认问题</span><span class="sxs-lookup"><span data-stu-id="06450-107">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="06450-108">例如，该适配器无法确定 ACK 无效，并且删除原始消息，而管道将确定 ACK 不是格式良好，挂起的确认消息。</span><span class="sxs-lookup"><span data-stu-id="06450-108">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="06450-109">MLLP 性能计数器进行计数确认</span><span class="sxs-lookup"><span data-stu-id="06450-109">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="06450-110">性能的一个度量值将由 MLLP 适配器，处理的消息数，如 MLLP 性能计数器所示。</span><span class="sxs-lookup"><span data-stu-id="06450-110">One measure of performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="06450-111">此计数测量接收或传输的消息的数量。</span><span class="sxs-lookup"><span data-stu-id="06450-111">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="06450-112">但是，计数不衡量 Ack 接收或发送的数。</span><span class="sxs-lookup"><span data-stu-id="06450-112">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a><span data-ttu-id="06450-113">不保证 MLLP 适配器连接名称都是唯一的</span><span class="sxs-lookup"><span data-stu-id="06450-113">MLLP adapter connection names are not guaranteed to be unique</span></span>  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="06450-114">不保证 MLLP 适配器的属性页中输入的连接名称的唯一性。</span><span class="sxs-lookup"><span data-stu-id="06450-114"> does not guarantee the uniqueness of the connection name entered in the property pages of an MLLP adapter.</span></span> <span data-ttu-id="06450-115">确保在此必填字段中输入名称该具说明性且更相关连接。</span><span class="sxs-lookup"><span data-stu-id="06450-115">Ensure that descriptive and relevant connection names are entered in this required field.</span></span> <span data-ttu-id="06450-116">尝试了解连接行为时，使用表示业务线应用程序的连接名称很有用。</span><span class="sxs-lookup"><span data-stu-id="06450-116">Using connection names that represent line-of-business applications can be useful when trying to understand the behavior of the connection.</span></span> <span data-ttu-id="06450-117">例如，PerfMon 计数器使用的连接名称。</span><span class="sxs-lookup"><span data-stu-id="06450-117">For example, PerfMon counters use the connection name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06450-118">BTAHL7 可以确保的唯一性接收位置或发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="06450-118">BTAHL7 does ensure the uniqueness of receive locations or send port names.</span></span>  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a><span data-ttu-id="06450-119">双向 MLLP 适配器不会发送一批中的所有消息提交确认</span><span class="sxs-lookup"><span data-stu-id="06450-119">Two-way MLLP adapters do not send Commit ACKs for all messages in a batch</span></span>  
 <span data-ttu-id="06450-120">当在一个批次以生成提交的 ACK，配置每条消息，然后系统会将发送到批处理双向 MLLP 接收适配器，适配器就只会发送提交 ACK 对应批处理中的第一个消息。</span><span class="sxs-lookup"><span data-stu-id="06450-120">When you configure each message in a batch to generate a Commit ACK, and the system sends the batch to a two-way MLLP receive adapter, the adapter will only send the Commit ACK corresponding to the first message in the batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06450-121">建议使用单向 MLLP 适配器来传输批次。</span><span class="sxs-lookup"><span data-stu-id="06450-121">It is recommended that you use a one-way MLLP adapter to transport batches.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="06450-122">生成的双向 MLLP 适配器否认</span><span class="sxs-lookup"><span data-stu-id="06450-122">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="06450-123">当双向 MLLP 适配器将挂起任何消息时，MLLP 适配器生成否认 （否定确认），并将它放在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="06450-123">When a two-way MLLP adapter suspends any message, the MLLP adapter generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="06450-124">这可能是意外的行为。</span><span class="sxs-lookup"><span data-stu-id="06450-124">This may be unexpected behavior.</span></span> <span data-ttu-id="06450-125">你可能想要从 MessageBox 数据库中删除否认或将其映射到另一条消息。</span><span class="sxs-lookup"><span data-stu-id="06450-125">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a><span data-ttu-id="06450-126">双向 MLLP 适配器仅支持 2.X 消息格式</span><span class="sxs-lookup"><span data-stu-id="06450-126">Two-way MLLP adapter only supports the 2.X message format</span></span>  
 <span data-ttu-id="06450-127">双向 MLLP 适配器当前支持 2.X 的消息格式。</span><span class="sxs-lookup"><span data-stu-id="06450-127">The two-way MLLP adapter currently supports only the 2.X message format.</span></span>  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a><span data-ttu-id="06450-128">双向 MLLP 适配器不支持静态确认</span><span class="sxs-lookup"><span data-stu-id="06450-128">Two-way MLLP adapter does not support static acknowledgments</span></span>  
 <span data-ttu-id="06450-129">双向发送适配器不支持处理静态确认。</span><span class="sxs-lookup"><span data-stu-id="06450-129">The two-way send adapter does not support processing static acknowledgments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06450-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06450-130">See Also</span></span>  
 [<span data-ttu-id="06450-131">已知问题</span><span class="sxs-lookup"><span data-stu-id="06450-131">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)