---
title: 修复消息和提交新消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- Message Repair and New Submission
- submitting, messages
- submitting, Message Repair and New Submission
- messages, Message Repair and New Submission
- messages, submitting
- Message Repair and New Submission. about Message Repair and New Submission
ms.assetid: 6abcce90-f611-422a-b3c8-e25f1e75b039
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569ab44588c2bd89c3533af8cc765e58f743a229
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003310"
---
# <a name="repairing-messages-and-submitting-new-messages"></a><span data-ttu-id="89aa0-102">修复消息和提交新消息</span><span class="sxs-lookup"><span data-stu-id="89aa0-102">Repairing Messages and Submitting New Messages</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="89aa0-103"> 消息修复和新提交，可修复未通过 XML 或业务规则引擎验证一条消息。</span><span class="sxs-lookup"><span data-stu-id="89aa0-103"> Message Repair and New Submission enables you to repair a message that has failed XML or Business Rules Engine validation.</span></span> <span data-ttu-id="89aa0-104">修复过程包括验证和审批步骤，以确保准确性和消息修复的适合程度。</span><span class="sxs-lookup"><span data-stu-id="89aa0-104">The repair process includes verification and approval steps that ensure the accuracy and appropriateness of the message repair.</span></span> <span data-ttu-id="89aa0-105">使用 Microsoft 执行此过程[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR 站点内的窗体。</span><span class="sxs-lookup"><span data-stu-id="89aa0-105">This process is performed using Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms within MRSR site.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="89aa0-106"> 此外可以提交新消息，使用此过程。</span><span class="sxs-lookup"><span data-stu-id="89aa0-106"> also enables you to submit a new message using this process.</span></span> <span data-ttu-id="89aa0-107">创建者将该消息，提交和工作流可以包含 repairer、 验证程序，并执行相同的任务，如下所示消息修复的审批者。</span><span class="sxs-lookup"><span data-stu-id="89aa0-107">A creator submits the message, and the workflow can include a repairer, a verifier, and an approver performing the same tasks as in message repair.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="89aa0-108"> 可将分配不同的用户执行每个任务以确保此过程的安全性。</span><span class="sxs-lookup"><span data-stu-id="89aa0-108"> ensures the security of this process by assigning different users to perform each task.</span></span> <span data-ttu-id="89aa0-109">分配适当的修复、 验证，或批准的这些用户，每个角色，并且每个用户必须使用特定证书来执行该任务。</span><span class="sxs-lookup"><span data-stu-id="89aa0-109">You assign the appropriate repair, verify, or approve role to each of these users, and each user must use a specific certificate to perform the task.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="89aa0-110"> 在处理消息修复和提交消息，还支持部门使用。</span><span class="sxs-lookup"><span data-stu-id="89aa0-110"> also supports the use of departments in processing repaired and submitted messages.</span></span> <span data-ttu-id="89aa0-111">每个部门涉及到特定的工作流的一组特定的消息上执行的任务。</span><span class="sxs-lookup"><span data-stu-id="89aa0-111">Each department involves a specific workflow of tasks performed on a specific set of messages.</span></span> <span data-ttu-id="89aa0-112">在任何创建的修复、 验证，或提交该消息时审批步骤，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]调用 BRE 验证并验证用户是否属于相应的部门。</span><span class="sxs-lookup"><span data-stu-id="89aa0-112">In any of the create, repair, verify, or approve steps, when you submit the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] calls BRE validation and verifies that the user is a member of the appropriate department.</span></span> <span data-ttu-id="89aa0-113">有关消息修复和新提交的详细信息，请参阅[消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="89aa0-113">For more information about message repair and new submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span>  
  
 <span data-ttu-id="89aa0-114">如果接收未分析的消息，消息修复和新提交显示的消息和中失败的描述[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，并使您可以打印该消息或将其保存到文件。</span><span class="sxs-lookup"><span data-stu-id="89aa0-114">If you receive an unparsed message, Message Repair and New Submission displays the message and a description of the failure in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, and enables you to print the message or save it to a file.</span></span> <span data-ttu-id="89aa0-115">然后，您可以修复重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="89aa0-115">You can then repair and resubmit the message.</span></span> <span data-ttu-id="89aa0-116">但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会调用 BRE 验证或提交已修复未分析的消息时检查部门中的成员身份。</span><span class="sxs-lookup"><span data-stu-id="89aa0-116">However, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] does not call BRE validation or check membership in a department when you submit an unparsed message that you have repaired.</span></span> <span data-ttu-id="89aa0-117">此外，不验证重新提交未分析的消息或将其批准。</span><span class="sxs-lookup"><span data-stu-id="89aa0-117">In addition, a resubmitted unparsed message is not verified or approved.</span></span> <span data-ttu-id="89aa0-118">有关未分析的消息的详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="89aa0-118">For more information about unparsed messages, see [Repairing Unparsed Messages](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).</span></span>  
  
 <span data-ttu-id="89aa0-119">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="89aa0-119">This section contains:</span></span>  
  
-   [<span data-ttu-id="89aa0-120">修复消息</span><span class="sxs-lookup"><span data-stu-id="89aa0-120">Repairing a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [<span data-ttu-id="89aa0-121">验证消息</span><span class="sxs-lookup"><span data-stu-id="89aa0-121">Verifying a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [<span data-ttu-id="89aa0-122">审核消息</span><span class="sxs-lookup"><span data-stu-id="89aa0-122">Approving a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [<span data-ttu-id="89aa0-123">处理未分析消息</span><span class="sxs-lookup"><span data-stu-id="89aa0-123">Handling an Unparsed Message</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [<span data-ttu-id="89aa0-124">创建和提交新消息</span><span class="sxs-lookup"><span data-stu-id="89aa0-124">Creating and Submitting a New Message</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [<span data-ttu-id="89aa0-125">创建新消息模板</span><span class="sxs-lookup"><span data-stu-id="89aa0-125">Creating a New Message Template</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)