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
ms.openlocfilehash: f6facf54500f3ff28ddba25d03b8a1d96f9cf25d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396999"
---
# <a name="processing-a-received-acknowledgment"></a><span data-ttu-id="3d4da-102">处理收到的确认</span><span class="sxs-lookup"><span data-stu-id="3d4da-102">Processing a Received Acknowledgment</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3d4da-103">将要求技术确认，如果协议中指定的相关属性。</span><span class="sxs-lookup"><span data-stu-id="3d4da-103">will expect a technical acknowledgment if the relevant property is specified in the agreement.</span></span> <span data-ttu-id="3d4da-104">对于 X12，这是**预期的 TA1**属性中的**确认**页中的单向协议**协议属性**对话框中或从回退协议属性。</span><span class="sxs-lookup"><span data-stu-id="3d4da-104">For X12, this is the **TA1 Expected** property in the **Acknowledgements** page of the one-way agreement in the **Agreement Properties** dialog box or from fallback agreement properties.</span></span> <span data-ttu-id="3d4da-105">对于 EDIFACT，这是**预期接收消息 (CONTRL)** 属性中的**确认**页中的单向协议**协议属性**对话框框或后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="3d4da-105">For EDIFACT, this is the **Receipt of message (CONTRL) expected** property in the **Acknowledgements** page of the one-way agreement in the **Agreement Properties** dialog box or from fallback agreement properties.</span></span> <span data-ttu-id="3d4da-106">当接收协议处理收到的消息时，它将生成技术确认，ISA14 或 UNB9 的值作为消息中。</span><span class="sxs-lookup"><span data-stu-id="3d4da-106">When the receiving agreement processes the received message, it will generate the technical acknowledgment as a result of the value of ISA14 or UNB9 in the message.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3d4da-107">将要求针对 X12 或 EDIFACT 编码，如果协议中指定的相关属性功能确认。</span><span class="sxs-lookup"><span data-stu-id="3d4da-107">will expect a functional acknowledgment for either X12 or EDIFACT encoding if the relevant property is specified in the agreement.</span></span> <span data-ttu-id="3d4da-108">对于 X12，此属性是**预期的 997**中**确认**页中的单向协议**协议属性**对话框中或从回退协议属性。</span><span class="sxs-lookup"><span data-stu-id="3d4da-108">For X12, this property is the **997 Expected** in the **Acknowledgements** page of the one-way agreement in the **Agreement Properties** dialog box or from fallback agreement properties.</span></span> <span data-ttu-id="3d4da-109">对于 EDIFACT，此属性是**确认 (CONTRL) 预期**属性中的**确认**页中的单向协议**协议属性**对话框中或后备协议属性。</span><span class="sxs-lookup"><span data-stu-id="3d4da-109">For EDIFACT, this property is the **Acknowledgement (CONTRL) expected** property in the **Acknowledgements** page of the one-way agreement in the **Agreement Properties** dialog box or from fallback agreement properties.</span></span> <span data-ttu-id="3d4da-110">当接收协议处理收到的消息时，它将生成技术确认，ISA14 或 UNB9 的值作为消息中。</span><span class="sxs-lookup"><span data-stu-id="3d4da-110">When the receiving agreement processes the received message, it will generate the technical acknowledgment as a result of the value of ISA14 or UNB9 in the message.</span></span>  
  
 <span data-ttu-id="3d4da-111">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]收到确认对 EDI 消息，它会验证确认使用确认控制架构。</span><span class="sxs-lookup"><span data-stu-id="3d4da-111">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an acknowledgment to an EDI message, it validates the acknowledgment using the acknowledgment control schemas.</span></span> <span data-ttu-id="3d4da-112">这些架构包括 X12_\<版本号\>*997.xsd 或 X12\\*\<版本号\>*对于 X12，EFACT TA1.xsd\\* \<版本号\>_CONTRL.xsd EDIFACT，和 HIPAA 5010 则为 X12_00501_997.xsd。</span><span class="sxs-lookup"><span data-stu-id="3d4da-112">These schemas are X12_\<version number\>*997.xsd or X12\\*\<version number\>*TA1.xsd for X12, EFACT\\*\<Version number\>_CONTRL.xsd for EDIFACT, and X12_00501_997.xsd for HIPAA 5010.</span></span>  
  
 <span data-ttu-id="3d4da-113">当接收管道处理传入的确认时，它会将此确认与已发送的 EDI 交换关联起来。</span><span class="sxs-lookup"><span data-stu-id="3d4da-113">When the receive pipeline processes the incoming acknowledgment, it correlates the acknowledgment to the sent EDI interchange.</span></span> <span data-ttu-id="3d4da-114">然后，管道将确认放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="3d4da-114">The pipeline then drops the acknowledgment into the MessageBox.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3d4da-115">不会对确认进行进一步处理。</span><span class="sxs-lookup"><span data-stu-id="3d4da-115">does not process the acknowledgment further.</span></span> <span data-ttu-id="3d4da-116">确认将被挂起，除非设置了一种机制，用于处理它。</span><span class="sxs-lookup"><span data-stu-id="3d4da-116">The acknowledgment will be suspended unless you set up a mechanism for processing it.</span></span> <span data-ttu-id="3d4da-117">若要处理确认，可以设置它，订阅，然后将其放入其中可以例行删除确认的文件夹的发送端口。</span><span class="sxs-lookup"><span data-stu-id="3d4da-117">To process the acknowledgment, you can set up a send port that subscribes to it, and then drops it into a folder where the acknowledgments can be routinely deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4da-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d4da-118">See Also</span></span>  
 <span data-ttu-id="3d4da-119">[EDI 确认结构](../core/edi-acknowledgment-structure.md) </span><span class="sxs-lookup"><span data-stu-id="3d4da-119">[EDI Acknowledgment Structure](../core/edi-acknowledgment-structure.md) </span></span>  
 [<span data-ttu-id="3d4da-120">发送 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="3d4da-120">Sending an EDI Acknowledgment</span></span>](../core/sending-an-edi-acknowledgment.md)