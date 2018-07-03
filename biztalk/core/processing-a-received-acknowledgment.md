---
title: 处理收到的确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f67a95-7368-40c2-a162-6ffc9de076fc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b39e1f0072c3a4b85860d851fcd9dad3fd53dda
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977454"
---
# <a name="processing-a-received-acknowledgment"></a><span data-ttu-id="4e116-102">处理接收的确认</span><span class="sxs-lookup"><span data-stu-id="4e116-102">Processing a Received Acknowledgment</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4e116-103"> 将要求技术确认，如果协议中指定的相关属性。</span><span class="sxs-lookup"><span data-stu-id="4e116-103"> will expect a technical acknowledgment if the relevant property is specified in the agreement.</span></span> <span data-ttu-id="4e116-104">对于 X12，这是**预期的 TA1**属性中的**确认**页中的单向协议**协议属性**对话框中或从回退协议属性。</span><span class="sxs-lookup"><span data-stu-id="4e116-104">For X12, this is the **TA1 Expected** property in the **Acknowledgements** page of the one-way agreement in the **Agreement Properties** dialog box or from fallback agreement properties.</span></span> <span data-ttu-id="4e116-105">对于 EDIFACT，这是**预期接收消息 (CONTRL)** 属性中的**确认**页中的单向协议**协议属性**对话框框或后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="4e116-105">For EDIFACT, this is the **Receipt of message (CONTRL) expected** property in the **Acknowledgements** page of the one-way agreement in the **Agreement Properties** dialog box or from fallback agreement properties.</span></span> <span data-ttu-id="4e116-106">当接收协议处理收到的消息时，它将生成技术确认，ISA14 或 UNB9 的值作为消息中。</span><span class="sxs-lookup"><span data-stu-id="4e116-106">When the receiving agreement processes the received message, it will generate the technical acknowledgment as a result of the value of ISA14 or UNB9 in the message.</span></span>  
  
 <span data-ttu-id="4e116-107">如果协议中指定了相关属性，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 预期将会对 X12 或 EDIFACT 编码进行功能确认。</span><span class="sxs-lookup"><span data-stu-id="4e116-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will expect a functional acknowledgment for either X12 or EDIFACT encoding if the relevant property is specified in the agreement.</span></span> <span data-ttu-id="4e116-108">对于 X12，此属性是**预期的 997**中**确认**页中的单向协议**协议属性**对话框中或从回退协议属性。</span><span class="sxs-lookup"><span data-stu-id="4e116-108">For X12, this property is the **997 Expected** in the **Acknowledgements** page of the one-way agreement in the **Agreement Properties** dialog box or from fallback agreement properties.</span></span> <span data-ttu-id="4e116-109">对于 EDIFACT，此属性是**确认 (CONTRL) 预期**属性中的**确认**页中的单向协议**协议属性**对话框中或后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="4e116-109">For EDIFACT, this property is the **Acknowledgement (CONTRL) expected** property in the **Acknowledgements** page of the one-way agreement in the **Agreement Properties** dialog box or from fallback agreement properties.</span></span> <span data-ttu-id="4e116-110">当接收协议处理收到的消息时，它将生成技术确认，ISA14 或 UNB9 的值作为消息中。</span><span class="sxs-lookup"><span data-stu-id="4e116-110">When the receiving agreement processes the received message, it will generate the technical acknowledgment as a result of the value of ISA14 or UNB9 in the message.</span></span>  
  
 <span data-ttu-id="4e116-111">当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到对 EDI 消息的确认时，将使用确认控制架构验证此确认。</span><span class="sxs-lookup"><span data-stu-id="4e116-111">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an acknowledgment to an EDI message, it validates the acknowledgment using the acknowledgment control schemas.</span></span> <span data-ttu-id="4e116-112">这些架构包括 X12_\<版本号\>*997.xsd 或 X12\\*\<版本号\>*对于 X12，EFACT TA1.xsd\\* \<版本号\>_CONTRL.xsd EDIFACT，和 HIPAA 5010 则为 X12_00501_997.xsd。</span><span class="sxs-lookup"><span data-stu-id="4e116-112">These schemas are X12_\<version number\>*997.xsd or X12\\*\<version number\>*TA1.xsd for X12, EFACT\\*\<Version number\>_CONTRL.xsd for EDIFACT, and X12_00501_997.xsd for HIPAA 5010.</span></span>  
  
 <span data-ttu-id="4e116-113">当接收管道处理传入确认时，管道会将此确认与已发送的 EDI 交换关联。</span><span class="sxs-lookup"><span data-stu-id="4e116-113">When the receive pipeline processes the incoming acknowledgment, it correlates the acknowledgment to the sent EDI interchange.</span></span> <span data-ttu-id="4e116-114">然后，管道将确认放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="4e116-114">The pipeline then drops the acknowledgment into the MessageBox.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4e116-115"> 不会对确认进行进一步处理。</span><span class="sxs-lookup"><span data-stu-id="4e116-115"> does not process the acknowledgment further.</span></span> <span data-ttu-id="4e116-116">此确认将挂起，除非您设置了处理确认的机制。</span><span class="sxs-lookup"><span data-stu-id="4e116-116">The acknowledgment will be suspended unless you set up a mechanism for processing it.</span></span> <span data-ttu-id="4e116-117">要处理确认，您可以设置订阅确认的发送端口，然后再将确认放置到某个文件夹中，您可以在此文件夹中例行删除确认。</span><span class="sxs-lookup"><span data-stu-id="4e116-117">To process the acknowledgment, you can set up a send port that subscribes to it, and then drops it into a folder where the acknowledgments can be routinely deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e116-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e116-118">See Also</span></span>  
 <span data-ttu-id="4e116-119">[EDI 确认结构](../core/edi-acknowledgment-structure.md) </span><span class="sxs-lookup"><span data-stu-id="4e116-119">[EDI Acknowledgment Structure](../core/edi-acknowledgment-structure.md) </span></span>  
 [<span data-ttu-id="4e116-120">发送 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="4e116-120">Sending an EDI Acknowledgment</span></span>](../core/sending-an-edi-acknowledgment.md)