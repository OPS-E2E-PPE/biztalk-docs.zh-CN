---
title: "FRR 否认处理程序示例的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f11bd20-3a0e-4d96-8e0a-32fecc7eed7e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009cb0c3dffce5f88c72207866f6778e3deb7b28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-frr-nak-handler-sample-works"></a><span data-ttu-id="5e222-102">FRR 否认处理程序示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="5e222-102">How the FRR NAK Handler Sample Works</span></span>
<span data-ttu-id="5e222-103">作为 FIN 响应对帐 (FRR) 业务流程和消息修复业务流程的中介服务示例 FRR 否认自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="5e222-103">The sample FRR NAK custom handler serves as an intermediary between the FIN Response Reconciliation (FRR) orchestration and the message-repair orchestration.</span></span> <span data-ttu-id="5e222-104">FRR 业务流程标识 SWIFT 网络尝试接收消息时发生的错误。</span><span class="sxs-lookup"><span data-stu-id="5e222-104">The FRR orchestration identifies the error that occurred when the SWIFT network attempted to receive the message.</span></span> <span data-ttu-id="5e222-105">FRR 业务流程的输出是一个部分消息与对象时出错。</span><span class="sxs-lookup"><span data-stu-id="5e222-105">The output of the FRR orchestration is a one-part message with an error object.</span></span> <span data-ttu-id="5e222-106">FRR 否认自定义处理程序将该消息转换成的两个部分构成的消息，指示发生，启用要拾取消息修复业务流程的消息的错误的错误部分。</span><span class="sxs-lookup"><span data-stu-id="5e222-106">The FRR NAK custom handler transforms that message into a two-part message, with an error part that indicates the error that occurred, enabling the message to be picked up by the message-repair orchestration.</span></span> <span data-ttu-id="5e222-107">消息修复业务流程会打开在邮件[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体，可用于发现的错误是、 相应地，修复消息并将其重新提交，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以重新发送到 SAA。</span><span class="sxs-lookup"><span data-stu-id="5e222-107">The message-repair orchestration opens the message in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form that enables you to find out what the error was, repair the message accordingly, and resubmit it so that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can resend it to SAA.</span></span>  
  
 <span data-ttu-id="5e222-108">当 FRR 否认自定义处理程序处理 SWIFT 网络无法成功接收消息时，将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5e222-108">The following steps occur when the FRR NAK custom handler processes a message that the SWIFT network could not successfully receive:</span></span>  
  
1.  <span data-ttu-id="5e222-109">FRR 业务流程具有相关的失败的消息与 MTS21_FIN_ACKNAK 否认消息后，RepairSWIFTRejectedMessage 业务流程 （自定义处理程序） 从那里获取原始消息的消息框。</span><span class="sxs-lookup"><span data-stu-id="5e222-109">After the FRR orchestration has correlated the failed message to the MTS21_FIN_ACKNAK NAK message, the RepairSWIFTRejectedMessage orchestration (the custom handler) picks up the original message from the MessageBox.</span></span> <span data-ttu-id="5e222-110">它未因此由于它在 A4SWIFT_FRRFailed 上筛选 = = True 和 A4SWIFT_SendingServiceType ="A4SWIFT_FrrService"。</span><span class="sxs-lookup"><span data-stu-id="5e222-110">It does so because it filters on A4SWIFT_FRRFailed==True and A4SWIFT_SendingServiceType="A4SWIFT_FrrService".</span></span>  
  
2.  <span data-ttu-id="5e222-111">自定义处理程序没有获得与原始消息关联 FRR MTS21_FIN_ACKNAK 否认消息。</span><span class="sxs-lookup"><span data-stu-id="5e222-111">The custom handler does not pick up the MTS21_FIN_ACKNAK NAK message that FRR correlated to the original message.</span></span> <span data-ttu-id="5e222-112">相反，它创建集合对象时出错，BRE 验证错误，该值指示 A4SWIFT_FRRFailedReason 属性，并将其添加到原始消息，并用其填充它。</span><span class="sxs-lookup"><span data-stu-id="5e222-112">Instead, it creates an error collection object, populates it with a BRE validation error that indicates what the A4SWIFT_FRRFailedReason property was, and adds it to the original message.</span></span> <span data-ttu-id="5e222-113">消息修复业务流程可以处理此两个部分构成消息。</span><span class="sxs-lookup"><span data-stu-id="5e222-113">The message-repair orchestration can process this two-part message.</span></span>  
  
3.  <span data-ttu-id="5e222-114">自定义处理程序将升级以下属性，以使条消息，以拾取消息修复业务流程： A4SWIFT_Failed = = True，A4SWIFT_SwiftBound = = True 和 BTS。操作 ="A4SWIFT_DASMMarkedAsFailed"。</span><span class="sxs-lookup"><span data-stu-id="5e222-114">The custom handler promotes the following properties to cause the message to be picked up by the message-repair orchestration: A4SWIFT_Failed==True, A4SWIFT_SwiftBound==True, and BTS.Operation="A4SWIFT_DASMMarkedAsFailed".</span></span> <span data-ttu-id="5e222-115">它将部件属性数设置为 2，并设置相应的错误属性。</span><span class="sxs-lookup"><span data-stu-id="5e222-115">It sets the number of parts property to 2, and sets the appropriate error properties.</span></span>  
  
4.  <span data-ttu-id="5e222-116">由于提升的属性中，消息修复业务流程选取该消息，并 RepairSWIFTRejectedMessage 业务流程终止。</span><span class="sxs-lookup"><span data-stu-id="5e222-116">As a result of the promoted properties, the message-repair orchestration picks up the message, and the RepairSWIFTRejectedMessage orchestration terminates.</span></span>