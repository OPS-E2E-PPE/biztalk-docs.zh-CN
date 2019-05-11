---
title: 使用 EDI 确认的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a769a78e-8a49-4aa4-899e-e9f54fdd5f37
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9768bffc83589ae826a9110d994b19b83cdb3fbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380830"
---
# <a name="known-issues-with-edi-acknowledgments"></a><span data-ttu-id="e483c-102">EDI 确认的已知的问题</span><span class="sxs-lookup"><span data-stu-id="e483c-102">Known Issues with EDI Acknowledgments</span></span>
<span data-ttu-id="e483c-103">本主题介绍在 EDI 确认的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e483c-103">This topic describes known issues with EDI acknowledgments in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="ak102-in-a-997-acknowledgment-can-be-negative"></a><span data-ttu-id="e483c-104">997 确认中的 AK102 可以是负数</span><span class="sxs-lookup"><span data-stu-id="e483c-104">AK102 in a 997 Acknowledgment Can Be Negative</span></span>  
 <span data-ttu-id="e483c-105">AK102 数据元素 （组控制编号） 在 X12 997 确认可以是负值。</span><span class="sxs-lookup"><span data-stu-id="e483c-105">The AK102 data element (group control number) in an X12 997 acknowledgment can be a negative value.</span></span> <span data-ttu-id="e483c-106">带有负值 AK102 数据元素的确认将通过执行验证[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，即使为负值的组控制编号没有意义。</span><span class="sxs-lookup"><span data-stu-id="e483c-106">An acknowledgment with a negative AK102 data element will pass the validation performed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], even though a negative group control number is not meaningful.</span></span>  
  
## <a name="a-contrl-receipt-may-report-a-status-of-accepted-when-part-of-the-message-is-rejected"></a><span data-ttu-id="e483c-107">CONTRL 回执仍可能报告的状态消息的一部分被拒绝时接受</span><span class="sxs-lookup"><span data-stu-id="e483c-107">A CONTRL Receipt May Report a Status of Accepted when Part of the Message Is Rejected</span></span>  
 <span data-ttu-id="e483c-108">仅当传入的 EDIFACT 消息重复或信封 （例如，问题的字符集） 中有错误时，CONTRL 回执 （EDIFACT 技术确认） 报告的状态为"已拒绝"。</span><span class="sxs-lookup"><span data-stu-id="e483c-108">A CONTRL receipt (EDIFACT technical acknowledgment) reports a status of “Rejected” only when the incoming EDIFACT message is a duplicate or there are errors in the envelope (for example, an issue with the character set).</span></span> <span data-ttu-id="e483c-109">EDIFACT 不在 CONTRL 技术确认中报告的状态为"已接受交换但出现错误"，如 X12 在 TA1 确认的 TA104 字段中作用。</span><span class="sxs-lookup"><span data-stu-id="e483c-109">EDIFACT does not report a state of “Interchange accepted with errors” in the CONTRL technical acknowledgment, as X12 does in the TA104 field in a TA1 acknowledgment.</span></span> <span data-ttu-id="e483c-110">如果接受 EDIFACT 消息的一部分，CONTRL 技术确认将报告"已接受"。</span><span class="sxs-lookup"><span data-stu-id="e483c-110">If part of the EDIFACT message is accepted, the CONTRL technical acknowledgment will report “Accepted”.</span></span> <span data-ttu-id="e483c-111">在某些情况下，将被拒绝消息的一部分，但 CONTRL 确认仍将报告的状态为"已接受"。</span><span class="sxs-lookup"><span data-stu-id="e483c-111">In some scenarios, part of the message will be rejected, but the CONTRL acknowledgment will still report a status of “Accepted”.</span></span> <span data-ttu-id="e483c-112">在这种情况下，UCI5 元素可能报告错误。</span><span class="sxs-lookup"><span data-stu-id="e483c-112">In such scenarios, the UCI5 element may report the error.</span></span>  
  
## <a name="x12-acknowledgments-will-show-accepted-for-a-preserved-interchange-suspend-interchange-on-error-when-a-group-header-or-trailer-is-in-error"></a><span data-ttu-id="e483c-113">X12 确认将显示已接受的针对保留交换 （挂起交换错误） 时组标头或尾部处于错误</span><span class="sxs-lookup"><span data-stu-id="e483c-113">X12 Acknowledgments Will Show Accepted for a Preserved Interchange (Suspend Interchange on Error) When a Group Header or Trailer is in Error</span></span>  
 <span data-ttu-id="e483c-114">如果入站的批处理选项 X12 消息是设置为"保留交换-出错时挂起交换"和组标头或尾部中的字段无效，将为已接受 TA1 和 997 确认中报告状态。</span><span class="sxs-lookup"><span data-stu-id="e483c-114">If the inbound batch processing option for an X12 message is set to “Preserve Interchange – suspend interchange on error”, and a field in the group header or trailer is invalid, the status will be reported as Accepted in both TA1 and 997 acknowledgments.</span></span> <span data-ttu-id="e483c-115">EDI 状态报告和事务集详细信息也将指示已接受状态。</span><span class="sxs-lookup"><span data-stu-id="e483c-115">The EDI status report and transaction set details will also indicate a status of Accepted.</span></span> <span data-ttu-id="e483c-116">即使交换将挂起，并且在事件查看器中的出现错误，将指示交换已挂起，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e483c-116">This occurs even though the interchange will be suspended, and an error in the Event Viewer will indicate that the interchange was suspended.</span></span>  
  
 <span data-ttu-id="e483c-117">TA1 确认将显示的状态为已接受，因为它用于验证 ISA 标头和 IEA 尾部的正确性，而不是 GS 标头和 GE 尾部的正确性。</span><span class="sxs-lookup"><span data-stu-id="e483c-117">The TA1 acknowledgment will show a status of Accepted because it is intended to verify the correctness of the ISA header and IEA trailer, but not the correctness of the GS header and GE trailer.</span></span> <span data-ttu-id="e483c-118">但是，997 确认也将显示已接受状态。</span><span class="sxs-lookup"><span data-stu-id="e483c-118">However, the 997 acknowledgment will also show a status of Accepted.</span></span>  
  
## <a name="if-groups-in-an-interchange-have-the-same-name-the-status-report-will-show-twice-as-many-acknowledgments"></a><span data-ttu-id="e483c-119">如果交换中的组具有相同的名称，在状态报告将显示两次确认</span><span class="sxs-lookup"><span data-stu-id="e483c-119">If groups in an interchange have the same name, the status report will show twice as many acknowledgments</span></span>  
 <span data-ttu-id="e483c-120">如果 BizTalk Server 处理 EDI 交换与具有相同名称的多个组，EDI 交换和相关 ACK 状态报表将按预期方式列出功能确认数两倍。</span><span class="sxs-lookup"><span data-stu-id="e483c-120">If BizTalk Server processes an EDI interchange with multiple groups that have the same name, the EDI Interchange and Correlated ACK status report will list twice as many functional acknowledgments as expected.</span></span> <span data-ttu-id="e483c-121">例如，如果交换中的两个组具有相同的名称，在状态报告将列出四个确认，而不是两个。</span><span class="sxs-lookup"><span data-stu-id="e483c-121">For example, if two groups in an interchange have the same name, the status report will list four acknowledgments, rather than two.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e483c-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e483c-122">See Also</span></span>  
 <span data-ttu-id="e483c-123">[EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="e483c-123">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="e483c-124">[发送 EDI 确认](../core/sending-an-edi-acknowledgment.md) </span><span class="sxs-lookup"><span data-stu-id="e483c-124">[Sending an EDI Acknowledgment](../core/sending-an-edi-acknowledgment.md) </span></span>  
 <span data-ttu-id="e483c-125">[处理收到的确认](../core/processing-a-received-acknowledgment.md) </span><span class="sxs-lookup"><span data-stu-id="e483c-125">[Processing a Received Acknowledgment](../core/processing-a-received-acknowledgment.md) </span></span>  
 [<span data-ttu-id="e483c-126">配置 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="e483c-126">Configuring EDI Acknowledgments</span></span>](../core/configuring-edi-acknowledgments.md)