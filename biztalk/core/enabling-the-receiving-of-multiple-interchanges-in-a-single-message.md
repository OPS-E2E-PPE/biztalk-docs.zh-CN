---
title: 启用多个接收交换中的单个消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98bcd2e-495a-49d8-a471-6e23b1e161f9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b27e4fa04957afd2a5bb25d3aa5b73c1c9c2df8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389092"
---
# <a name="enabling-the-receiving-of-multiple-interchanges-in-a-single-message"></a><span data-ttu-id="0fb13-102">启用接收单个消息中的多个交换</span><span class="sxs-lookup"><span data-stu-id="0fb13-102">Enabling the Receiving of Multiple Interchanges in a Single Message</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0fb13-103">可以处理包含多个交换的消息。</span><span class="sxs-lookup"><span data-stu-id="0fb13-103">can process a message that contains multiple interchanges.</span></span> <span data-ttu-id="0fb13-104">对于 X12 消息，此类消息将包括多个 ISA 标头和 IEA 尾部。</span><span class="sxs-lookup"><span data-stu-id="0fb13-104">For an X12 message, such a message would include multiple ISA headers and IEA trailers.</span></span> <span data-ttu-id="0fb13-105">对于 EDIFACT 消息，此类消息将包括多个 UNA/UNB 标头和 UNZ 尾部。</span><span class="sxs-lookup"><span data-stu-id="0fb13-105">For an EDIFACT message, such a message would include multiple UNA/UNB headers and UNZ trailers.</span></span>  
  
 <span data-ttu-id="0fb13-106">若要启用 EDI 拆装器在 EdiReceive 或 AS2EdiReceive 管道中，以便解析单个消息中的多个交换，必须设置**DetectMID**管道属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="0fb13-106">To enable the EDI Disassembler in the EdiReceive or AS2EdiReceive pipeline to parse multiple interchanges in a single message, you must set the **DetectMID** pipeline property to **True**.</span></span> <span data-ttu-id="0fb13-107">（MID 代表多个交换拆装。）默认情况下，此属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="0fb13-107">(MID stands for multiple interchange disassembling.) This property is set to True by default.</span></span>  
  
 <span data-ttu-id="0fb13-108">当包括 EDI 拆装器的接收管道收到具有多个交换消息时，拆装器将分析从交换标头至交换尾部的每个交换。</span><span class="sxs-lookup"><span data-stu-id="0fb13-108">When the receive pipeline that includes the EDI Disassembler receives a message with multiple interchange, the Disassembler will parse each interchange from the interchange header to the interchange trailer.</span></span> <span data-ttu-id="0fb13-109">此处理已完成根据以下规则：</span><span class="sxs-lookup"><span data-stu-id="0fb13-109">This processing is done according to the following rules:</span></span>  
  
- <span data-ttu-id="0fb13-110">相同的消息中的所有交换必须都是相同的编码类型，X12 或 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="0fb13-110">All interchanges in the same message must be of the same encoding type, either X12 or EDIFACT.</span></span> <span data-ttu-id="0fb13-111">如果消息包含多个编码类型的交换，EDI 拆装器将处理所有消息中具有相同的编码类型作为第一个交换的交换。</span><span class="sxs-lookup"><span data-stu-id="0fb13-111">If the message contains interchanges of more than one encoding type, the EDI Disassembler will process all interchanges that have the same encoding type as the first interchange in the message.</span></span> <span data-ttu-id="0fb13-112">拆装器将忽略所有属于不同的编码类型的第一个交换的交换。</span><span class="sxs-lookup"><span data-stu-id="0fb13-112">The Disassembler will ignore all interchanges that are of a different encoding type from the first interchange.</span></span>  
  
- <span data-ttu-id="0fb13-113">EDI 拆装器将忽略任何一个交换的交换尾部和下一个交换的交换标头之间的字符。</span><span class="sxs-lookup"><span data-stu-id="0fb13-113">The EDI Disassembler will ignore any character between the interchange trailer of one interchange and the interchange heading of the next interchange.</span></span>  
  
- <span data-ttu-id="0fb13-114">如果通过选择启用身份验证**身份验证失败时删除消息**或**身份验证失败时保留消息**属性的接收端口，然后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将如果消息中多个交换的任何一个失败，则挂起整个消息。</span><span class="sxs-lookup"><span data-stu-id="0fb13-114">If you enable authentication by selecting either the **Drop messages if authentication fails** or the **Keep messages if authentication fails** property for the receive port, then [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the entire message if any one of the multiple interchanges in the message fails.</span></span>  
  
- <span data-ttu-id="0fb13-115">如果启用身份验证，并且同一消息中的任何一个交换未解析到协议，然后将挂起消息中的所有交换，并且会返回任何确认，即使对于已解析到协议的交换.</span><span class="sxs-lookup"><span data-stu-id="0fb13-115">If you enable authentication, and if any one interchange in the same message does not resolve to an agreement, then all interchanges in the message will be suspended, and no acknowledgments will be returned, even for those interchanges that did resolve to an agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0fb13-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="0fb13-116">Prerequisites</span></span>  
 <span data-ttu-id="0fb13-117">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="0fb13-117">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-enable-the-receiving-of-multiple-interchanges-in-a-message"></a><span data-ttu-id="0fb13-118">若要启用接收的消息中的多个交换</span><span class="sxs-lookup"><span data-stu-id="0fb13-118">To enable the receiving of multiple interchanges in a message</span></span>  
  
1. <span data-ttu-id="0fb13-119">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**接收位置**节点，右键单击你想要启用以接收多个接收位置交换中一条消息，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0fb13-119">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Receive Locations** node, right-click the receive location that you want to enable to receive multiple interchange in a single message, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="0fb13-120">单击接收管道 （它必须是 EdiReceive 或 AS2EdiReceive） 旁的省略号。</span><span class="sxs-lookup"><span data-stu-id="0fb13-120">Click the ellipses next to the receive pipeline (which must be either EdiReceive or AS2EdiReceive).</span></span>  
  
3. <span data-ttu-id="0fb13-121">在中**配置管道**对话框中，将**DetectMID**管道属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="0fb13-121">In the **Configure Pipeline** dialog box, set the **DetectMID** pipeline property to **True**.</span></span>  
  
4. <span data-ttu-id="0fb13-122">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="0fb13-122">Click **OK**, then click **OK** again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb13-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fb13-123">See Also</span></span>  
 [<span data-ttu-id="0fb13-124">为 EDI 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="0fb13-124">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)