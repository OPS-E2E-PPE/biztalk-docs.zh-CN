---
title: ACK 消息模式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122f0851005c7d8abba6c1739ae86a1d65d89625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204397"
---
# <a name="ack-message-modes"></a><span data-ttu-id="cecbc-102">ACK 消息模式</span><span class="sxs-lookup"><span data-stu-id="cecbc-102">ACK Message Modes</span></span>
<span data-ttu-id="cecbc-103">确认 (ACK) 消息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 确定确认模式和要用于填充 MSH15 和 MSH16 你想要生成的确认字段值。</span><span class="sxs-lookup"><span data-stu-id="cecbc-103">For acknowledgment (ACK) messages, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) determines the acknowledgment mode and values to use for populating MSH15 and MSH16 fields of the ACK you want to generate.</span></span> <span data-ttu-id="cecbc-104">这些值是贸易合作伙伴管理 (TPM) 配置中存在。</span><span class="sxs-lookup"><span data-stu-id="cecbc-104">These values are present in the Trading Partner Management (TPM) configuration.</span></span> <span data-ttu-id="cecbc-105">还为 ACK 模式可能有以下值：</span><span class="sxs-lookup"><span data-stu-id="cecbc-105">The following values are possible for ACK mode:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cecbc-106">在以下列表中，该 HL7 规范强制包含项 1 至 3，并且它们包含 MSH15 和 MSH16 值。</span><span class="sxs-lookup"><span data-stu-id="cecbc-106">In the following list, the HL7 specification mandates items 1 through 3 and that they contain MSH15 and MSH16 values.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="cecbc-107">定义项目 4 以表示不应生成确认。</span><span class="sxs-lookup"><span data-stu-id="cecbc-107"> defines item 4 to signify that an acknowledgment should not be generated.</span></span>  
  
1.  <span data-ttu-id="cecbc-108">原始-在验证标头和正文之后发送一个 ACK。</span><span class="sxs-lookup"><span data-stu-id="cecbc-108">Original - One ACK sent after validating the header and body.</span></span> <span data-ttu-id="cecbc-109">此模式涉及架构验证。</span><span class="sxs-lookup"><span data-stu-id="cecbc-109">This mode involves schema validation.</span></span>  
  
2.  <span data-ttu-id="cecbc-110">增强-发送的两个 ACK 消息：</span><span class="sxs-lookup"><span data-stu-id="cecbc-110">Enhanced - Two ACK messages sent:</span></span>  
  
    -   <span data-ttu-id="cecbc-111">接受 ACK – 接收系统会将此类型的 ACK 发送的标头在验证之后。</span><span class="sxs-lookup"><span data-stu-id="cecbc-111">Accept ACK – The receiving system sends this type of ACK after validation of the header.</span></span> <span data-ttu-id="cecbc-112">此 ACK 向发出信号，启动应用程序消息已提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="cecbc-112">This ACK signals to the initiating application that the message is committed to the database.</span></span>  
  
    -   <span data-ttu-id="cecbc-113">应用程序 ACK 接收系统会将此类型的 ACK 发送后完成的消息验证，包括标头和正文。</span><span class="sxs-lookup"><span data-stu-id="cecbc-113">Application ACK- The receiving system sends this type of ACK after complete message validation, including the header and the body.</span></span>  
  
3.  <span data-ttu-id="cecbc-114">延迟的两个 ACK 消息发送。</span><span class="sxs-lookup"><span data-stu-id="cecbc-114">Deferred - Two ACK messages sent.</span></span>  
  
    -   <span data-ttu-id="cecbc-115">原始模式： 接收的系统会将此类型的 ACK 发送的标头和正文在验证之后。</span><span class="sxs-lookup"><span data-stu-id="cecbc-115">Original Mode: The receiving system sends this type of ACK after validation of the header and body.</span></span> <span data-ttu-id="cecbc-116">此模式涉及架构验证。</span><span class="sxs-lookup"><span data-stu-id="cecbc-116">This mode involves schema validation.</span></span>  
  
    -   <span data-ttu-id="cecbc-117">延迟模式： 业务线应用程序对其进行处理后确认消息。</span><span class="sxs-lookup"><span data-stu-id="cecbc-117">Deferred Mode: The line-of-business application acknowledges the message after processing it.</span></span> <span data-ttu-id="cecbc-118">应用程序提供对延迟的消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，它将它作为独立消息处理，并将其传递给目标。</span><span class="sxs-lookup"><span data-stu-id="cecbc-118">The application delivers the deferred message to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], which process it as a stand-alone message and delivers it to the destination.</span></span>  
  
4.  <span data-ttu-id="cecbc-119">静态-在成功或失败发送的 ACK。</span><span class="sxs-lookup"><span data-stu-id="cecbc-119">Static - An on success or on failure ACK sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecbc-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cecbc-120">See Also</span></span>  
 <span data-ttu-id="cecbc-121">[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="cecbc-121">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="cecbc-122">[编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="cecbc-122">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 <span data-ttu-id="cecbc-123">[ACK 进程模型](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span><span class="sxs-lookup"><span data-stu-id="cecbc-123">[ACK Process Model](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span></span>  
 [<span data-ttu-id="cecbc-124">静态确认</span><span class="sxs-lookup"><span data-stu-id="cecbc-124">Static Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)