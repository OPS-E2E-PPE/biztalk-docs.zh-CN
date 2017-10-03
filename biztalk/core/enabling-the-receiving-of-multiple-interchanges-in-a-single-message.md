---
title: "在一条消息中启用多个接收交换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c98bcd2e-495a-49d8-a471-6e23b1e161f9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec1b282908424100ddfd0363fd6bede9011d53a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-the-receiving-of-multiple-interchanges-in-a-single-message"></a><span data-ttu-id="a942c-102">启用接收单个消息中的多个交换</span><span class="sxs-lookup"><span data-stu-id="a942c-102">Enabling the Receiving of Multiple Interchanges in a Single Message</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a942c-103"> 可以处理包含多个交换的消息。</span><span class="sxs-lookup"><span data-stu-id="a942c-103"> can process a message that contains multiple interchanges.</span></span> <span data-ttu-id="a942c-104">对于 X12 消息，此类消息将包括多个 ISA 标头和 IEA 尾部。</span><span class="sxs-lookup"><span data-stu-id="a942c-104">For an X12 message, such a message would include multiple ISA headers and IEA trailers.</span></span> <span data-ttu-id="a942c-105">对于 EDIFACT 消息，此类消息将包括多个 UNA/UNB 标头和 UNZ 尾部。</span><span class="sxs-lookup"><span data-stu-id="a942c-105">For an EDIFACT message, such a message would include multiple UNA/UNB headers and UNZ trailers.</span></span>  
  
 <span data-ttu-id="a942c-106">若要启用 EDI 反汇编程序 EdiReceive 或 AS2EdiReceive 管道中，若要分析一条消息中的多个交换，必须设置**DetectMID**管道属性**True**。</span><span class="sxs-lookup"><span data-stu-id="a942c-106">To enable the EDI Disassembler in the EdiReceive or AS2EdiReceive pipeline to parse multiple interchanges in a single message, you must set the **DetectMID** pipeline property to **True**.</span></span> <span data-ttu-id="a942c-107">（MID 表示多个交换拆装。）默认情况下，该属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="a942c-107">(MID stands for multiple interchange disassembling.) This property is set to True by default.</span></span>  
  
 <span data-ttu-id="a942c-108">当包括 EDI 拆装器的接收管道收到具有多个交换的消息时，该拆装器将从交换标头至交换尾部解析每个交换。</span><span class="sxs-lookup"><span data-stu-id="a942c-108">When the receive pipeline that includes the EDI Disassembler receives a message with multiple interchange, the Disassembler will parse each interchange from the interchange header to the interchange trailer.</span></span> <span data-ttu-id="a942c-109">此处理依据的规则如下：</span><span class="sxs-lookup"><span data-stu-id="a942c-109">This processing is done according to the following rules:</span></span>  
  
-   <span data-ttu-id="a942c-110">相同消息中的所有交换必须具有相同的编码类型，X12 或 EDIFACT。</span><span class="sxs-lookup"><span data-stu-id="a942c-110">All interchanges in the same message must be of the same encoding type, either X12 or EDIFACT.</span></span> <span data-ttu-id="a942c-111">如果消息包含的交换具有多个编码类型，EDI 拆装器会将具有相同编码类型的所有交换作为该消息中的第一个交换进行处理。</span><span class="sxs-lookup"><span data-stu-id="a942c-111">If the message contains interchanges of more than one encoding type, the EDI Disassembler will process all interchanges that have the same encoding type as the first interchange in the message.</span></span> <span data-ttu-id="a942c-112">拆装器将忽略其编码类型不同于第一个交换的所有交换。</span><span class="sxs-lookup"><span data-stu-id="a942c-112">The Disassembler will ignore all interchanges that are of a different encoding type from the first interchange.</span></span>  
  
-   <span data-ttu-id="a942c-113">EDI 拆装器将忽略某一交换的交换尾部和下一交换的交换标头之间的任何字符。</span><span class="sxs-lookup"><span data-stu-id="a942c-113">The EDI Disassembler will ignore any character between the interchange trailer of one interchange and the interchange heading of the next interchange.</span></span>  
  
-   <span data-ttu-id="a942c-114">如果选择启用身份验证**丢弃的消息，如果身份验证失败**或**身份验证失败时保留消息**属性接收端口，然后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将如果任一消息中的多个交换失败，则挂起整个消息。</span><span class="sxs-lookup"><span data-stu-id="a942c-114">If you enable authentication by selecting either the **Drop messages if authentication fails** or the **Keep messages if authentication fails** property for the receive port, then [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the entire message if any one of the multiple interchanges in the message fails.</span></span>  
  
-   <span data-ttu-id="a942c-115">如果启用验证，当同一消息中的任一交换未解析到协议时，将挂起该消息中的所有交换，并且不会返回任何确认，即使对于已解析到协议的交换也是如此。</span><span class="sxs-lookup"><span data-stu-id="a942c-115">If you enable authentication, and if any one interchange in the same message does not resolve to an agreement, then all interchanges in the message will be suspended, and no acknowledgments will be returned, even for those interchanges that did resolve to an agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a942c-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="a942c-116">Prerequisites</span></span>  
 <span data-ttu-id="a942c-117">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="a942c-117">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-enable-the-receiving-of-multiple-interchanges-in-a-message"></a><span data-ttu-id="a942c-118">启用接收一个消息中的多个交换</span><span class="sxs-lookup"><span data-stu-id="a942c-118">To enable the receiving of multiple interchanges in a message</span></span>  
  
1.  <span data-ttu-id="a942c-119">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**接收位置**节点，右键单击你想要启用接收多个接收位置交换中单个消息，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a942c-119">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Receive Locations** node, right-click the receive location that you want to enable to receive multiple interchange in a single message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a942c-120">单击接收管道（必须是 EdiReceive 或 AS2EdiReceive）旁的省略号。</span><span class="sxs-lookup"><span data-stu-id="a942c-120">Click the ellipses next to the receive pipeline (which must be either EdiReceive or AS2EdiReceive).</span></span>  
  
3.  <span data-ttu-id="a942c-121">在**配置管道**对话框中，设置**DetectMID**管道属性**True**。</span><span class="sxs-lookup"><span data-stu-id="a942c-121">In the **Configure Pipeline** dialog box, set the **DetectMID** pipeline property to **True**.</span></span>  
  
4.  <span data-ttu-id="a942c-122">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="a942c-122">Click **OK**, then click **OK** again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a942c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a942c-123">See Also</span></span>  
 [<span data-ttu-id="a942c-124">为 EDI 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="a942c-124">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)