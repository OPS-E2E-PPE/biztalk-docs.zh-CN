---
title: FRR NAK 处理程序示例的工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f11bd20-3a0e-4d96-8e0a-32fecc7eed7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b64fb92f130defe6bd7d55ac6ccdc3b7391091
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377436"
---
# <a name="how-the-frr-nak-handler-sample-works"></a><span data-ttu-id="7b83f-102">FRR NAK 处理程序示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="7b83f-102">How the FRR NAK Handler Sample Works</span></span>
<span data-ttu-id="7b83f-103">FRR NAK 自定义处理程序的示例可作为 FIN 响应对帐 (FRR) 业务流程和消息修复业务流程之间的媒介。</span><span class="sxs-lookup"><span data-stu-id="7b83f-103">The sample FRR NAK custom handler serves as an intermediary between the FIN Response Reconciliation (FRR) orchestration and the message-repair orchestration.</span></span> <span data-ttu-id="7b83f-104">FRR 业务流程标识的 SWIFT 网络尝试接收消息时发生的错误。</span><span class="sxs-lookup"><span data-stu-id="7b83f-104">The FRR orchestration identifies the error that occurred when the SWIFT network attempted to receive the message.</span></span> <span data-ttu-id="7b83f-105">FRR 业务流程的输出是一个错误对象的一部分消息。</span><span class="sxs-lookup"><span data-stu-id="7b83f-105">The output of the FRR orchestration is a one-part message with an error object.</span></span> <span data-ttu-id="7b83f-106">FRR NAK 自定义处理程序将该消息转换成两部分消息，指示发生，启用要拾取消息修复业务流程的消息的错误的错误部分。</span><span class="sxs-lookup"><span data-stu-id="7b83f-106">The FRR NAK custom handler transforms that message into a two-part message, with an error part that indicates the error that occurred, enabling the message to be picked up by the message-repair orchestration.</span></span> <span data-ttu-id="7b83f-107">消息修复业务流程将打开中的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体，可用于找出错误，相应地，修复消息并重新提交它，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以重新发送给 SAA。</span><span class="sxs-lookup"><span data-stu-id="7b83f-107">The message-repair orchestration opens the message in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form that enables you to find out what the error was, repair the message accordingly, and resubmit it so that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can resend it to SAA.</span></span>  
  
 <span data-ttu-id="7b83f-108">FRR NAK 自定义处理程序处理的 SWIFT 网络无法成功接收的消息时，将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7b83f-108">The following steps occur when the FRR NAK custom handler processes a message that the SWIFT network could not successfully receive:</span></span>  
  
1.  <span data-ttu-id="7b83f-109">FRR 业务流程具有相关的失败的消息到 MTS21_FIN_ACKNAK NAK 消息后，RepairSWIFTRejectedMessage 业务流程 （自定义处理程序） 从 MessageBox 提取原始消息。</span><span class="sxs-lookup"><span data-stu-id="7b83f-109">After the FRR orchestration has correlated the failed message to the MTS21_FIN_ACKNAK NAK message, the RepairSWIFTRejectedMessage orchestration (the custom handler) picks up the original message from the MessageBox.</span></span> <span data-ttu-id="7b83f-110">它 does 因此因为 A4SWIFT_FRRFailed 上筛选器 = = True 和 A4SWIFT_SendingServiceType ="A4SWIFT_FrrService"。</span><span class="sxs-lookup"><span data-stu-id="7b83f-110">It does so because it filters on A4SWIFT_FRRFailed==True and A4SWIFT_SendingServiceType="A4SWIFT_FrrService".</span></span>  
  
2.  <span data-ttu-id="7b83f-111">自定义处理程序不提取与原始消息相关的 FRR NAK MTS21_FIN_ACKNAK 消息。</span><span class="sxs-lookup"><span data-stu-id="7b83f-111">The custom handler does not pick up the MTS21_FIN_ACKNAK NAK message that FRR correlated to the original message.</span></span> <span data-ttu-id="7b83f-112">相反，它创建一个错误集合对象，其中填充 BRE 验证错误，指示 A4SWIFT_FRRFailedReason 属性，并将其添加到原始消息。</span><span class="sxs-lookup"><span data-stu-id="7b83f-112">Instead, it creates an error collection object, populates it with a BRE validation error that indicates what the A4SWIFT_FRRFailedReason property was, and adds it to the original message.</span></span> <span data-ttu-id="7b83f-113">消息修复业务流程可以处理这两个部分构成的消息。</span><span class="sxs-lookup"><span data-stu-id="7b83f-113">The message-repair orchestration can process this two-part message.</span></span>  
  
3.  <span data-ttu-id="7b83f-114">自定义处理程序将升级以下属性以导致要拾取消息修复业务流程的消息：A4SWIFT_Failed = = True，A4SWIFT_SwiftBound = = True，和 BTS。操作 ="A4SWIFT_DASMMarkedAsFailed"。</span><span class="sxs-lookup"><span data-stu-id="7b83f-114">The custom handler promotes the following properties to cause the message to be picked up by the message-repair orchestration: A4SWIFT_Failed==True, A4SWIFT_SwiftBound==True, and BTS.Operation="A4SWIFT_DASMMarkedAsFailed".</span></span> <span data-ttu-id="7b83f-115">它将部件属性数设置为 2，并设置相应的错误属性。</span><span class="sxs-lookup"><span data-stu-id="7b83f-115">It sets the number of parts property to 2, and sets the appropriate error properties.</span></span>  
  
4.  <span data-ttu-id="7b83f-116">由于升级属性，而消息修复业务流程将提取该消息，并 RepairSWIFTRejectedMessage 业务流程将终止。</span><span class="sxs-lookup"><span data-stu-id="7b83f-116">As a result of the promoted properties, the message-repair orchestration picks up the message, and the RepairSWIFTRejectedMessage orchestration terminates.</span></span>