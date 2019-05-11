---
title: 拆分批处理的 EDI 交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29c79b06-cc88-4cc8-aa99-40f24a1bdcde
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a771d499116093b36605d2e3d518774a5b5994c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243236"
---
# <a name="splitting-a-batched-edi-interchange"></a><span data-ttu-id="3bbc6-102">拆分批处理的 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="3bbc6-102">Splitting a Batched EDI Interchange</span></span>
> [!NOTE]
>  <span data-ttu-id="3bbc6-103">本主题中所述的所有用户界面选项都位于**本地主机设置**页 (**接收方设置**部分) 中的单向协议选项卡的**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-103">All the user interface options mentioned in this topic are available in the **Local Host Settings** page (**Receiver’s Settings** section) of the one-way agreement tabs in the **Agreement Properties** dialog box.</span></span>  
  
 <span data-ttu-id="3bbc6-104">EDI 接收管道拆分传入 EDI 交换批如果设置了**入站批处理选项**协议属性设置为**交换拆分为事务集**。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-104">The EDI receive pipeline splits an incoming EDI interchange batch if you have set the **Inbound batch processing option** agreement property to **Split Interchange as Transaction Sets**.</span></span>  
  
 <span data-ttu-id="3bbc6-105">当 EDI 接收管道将拆分传入批处理的 EDI 交换时，会创建每个 EDI 事务集/消息的一个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-105">When the EDI receive pipeline splits an incoming batched EDI interchange, it creates one XML file for each EDI transaction set/message.</span></span> <span data-ttu-id="3bbc6-106">管道将整个交换和组标头的每个事务的上下文从交换集拆分。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-106">The pipeline promotes the entire interchange and group headers into the context of each transaction set split from the interchange.</span></span> <span data-ttu-id="3bbc6-107">它还会升级某些特定交换和组标头，如 ISA6、 GS1 和 GS2，以便这些字段可用于路由。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-107">It also promotes certain specific interchange and group headers, such as ISA6, GS1, and GS2, so that these fields can be used for routing.</span></span> <span data-ttu-id="3bbc6-108">可以通过选择屏蔽标头中的安全信息**屏蔽安全/授权/密码信息**属性。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-108">You can mask the security information in the header by selecting the **Mask security/authorization/password information** property.</span></span>  
  
 <span data-ttu-id="3bbc6-109">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]尝试将交换拆分为事务集，某些 ISA 中的任何错误 (ISA1 至 ISA13) 或 UNB 标头字段将导致该交换被拒绝。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-109">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] attempts to split an interchange into transaction sets, any error in certain ISA (ISA1 through ISA13) or UNB header fields will lead to the interchange being rejected.</span></span> <span data-ttu-id="3bbc6-110">这也是这种情况时的交换控制编号重复项，如果协议或后备协议属性中启用了重复的交换控制编号的检查。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-110">This is also the case when the interchange control number is a duplicate, if the check for a duplicate interchange control number is enabled in the agreement or fallback agreement properties.</span></span> <span data-ttu-id="3bbc6-111">其他交换标头字段中的错误 （除 ISA1 至 ISA13 对于 X12 交换） 或组标头中的字段不会导致交换处理失败。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-111">An error in other interchange header fields (other than ISA1 through ISA13 for X12 interchange) or in the group header fields would not cause interchange processing to fail.</span></span>  
  
 <span data-ttu-id="3bbc6-112">如果**将交换拆分为事务集-出错时挂起事务集**协议属性中选择[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将挂起的事务集出错时。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-112">If **Split Interchange as Transaction Sets - suspend Transaction Sets on Error** is selected in agreement properties, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the transaction set if an error occurs.</span></span> <span data-ttu-id="3bbc6-113">如果**交换拆分为事务集-出错时挂起交换**已选中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将挂起该交换。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-113">If **Split Interchange as Transaction Sets – suspend Interchange on Error** is selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
 <span data-ttu-id="3bbc6-114">每个 XML 批元素将路由到 MessageBox，并由发送端口或业务流程的订阅批元素处理。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-114">Each XML batch element is routed to the MessageBox, and processed by the send ports or orchestrations that subscribe to the batch element.</span></span> <span data-ttu-id="3bbc6-115">作为已拆分消息经过处理之后可能不保留的交换中事务集的排序。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-115">The ordering of transaction sets in the interchange may not be retained after they are processed as split messages.</span></span> <span data-ttu-id="3bbc6-116">在接收端，消息将按顺序，它们出现在交换，并会将它们放在 messagebox 中该顺序，但必须使用保护或按序的送达发送端口来保持此排序在发送端处理。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-116">On the receive side, the messages will be processed in the order that they appear in the interchange, and they will be placed in the MessageBox in that order, but you would have to use convoys or ordered delivery send ports to maintain that order on the send side.</span></span>  
  
 <span data-ttu-id="3bbc6-117">如果从批处理拆分的元素将包含在传出批，BatchMarker 管道组件将升级所需的属性。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-117">If the elements split from a batch will be included in an outgoing batch, the BatchMarker pipeline component promotes the required properties.</span></span> <span data-ttu-id="3bbc6-118">有关详细信息，请参阅[批处理传出 EDI 消息](../core/batching-outgoing-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="3bbc6-118">For more information, see [Batching Outgoing EDI Messages](../core/batching-outgoing-edi-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbc6-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bbc6-119">See Also</span></span>  
 <span data-ttu-id="3bbc6-120">[处理传入批](../core/processing-incoming-batches.md) </span><span class="sxs-lookup"><span data-stu-id="3bbc6-120">[Processing Incoming Batches](../core/processing-incoming-batches.md) </span></span>  
 [<span data-ttu-id="3bbc6-121">对传出 EDI 消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="3bbc6-121">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)