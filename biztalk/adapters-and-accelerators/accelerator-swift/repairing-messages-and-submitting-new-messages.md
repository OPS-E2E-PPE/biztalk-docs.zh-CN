---
title: 修复消息和提交新消息 |Microsoft 文档
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
ms.openlocfilehash: 59ece524ce06430492a3927c0cd1437eef4b216d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214021"
---
# <a name="repairing-messages-and-submitting-new-messages"></a><span data-ttu-id="d372b-102">修复消息和提交新消息</span><span class="sxs-lookup"><span data-stu-id="d372b-102">Repairing Messages and Submitting New Messages</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="d372b-103">消息修复和新的提交，可修复 XML 或业务规则引擎的验证失败的消息。</span><span class="sxs-lookup"><span data-stu-id="d372b-103"> Message Repair and New Submission enables you to repair a message that has failed XML or Business Rules Engine validation.</span></span> <span data-ttu-id="d372b-104">修复过程包括验证和审核的步骤，以确保准确性和消息修复的适合程度。</span><span class="sxs-lookup"><span data-stu-id="d372b-104">The repair process includes verification and approval steps that ensure the accuracy and appropriateness of the message repair.</span></span> <span data-ttu-id="d372b-105">执行此过程使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR 站点内的窗体。</span><span class="sxs-lookup"><span data-stu-id="d372b-105">This process is performed using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms within MRSR site.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="d372b-106">另外，可以提交新消息使用此过程。</span><span class="sxs-lookup"><span data-stu-id="d372b-106"> also enables you to submit a new message using this process.</span></span> <span data-ttu-id="d372b-107">创建者提交消息，并且工作流可以包括 repairer、 验证程序和审批者执行相同的任务，如下所示消息修复。</span><span class="sxs-lookup"><span data-stu-id="d372b-107">A creator submits the message, and the workflow can include a repairer, a verifier, and an approver performing the same tasks as in message repair.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="d372b-108">通过分配不同的用户可以执行每项任务，可确保此过程的安全性。</span><span class="sxs-lookup"><span data-stu-id="d372b-108"> ensures the security of this process by assigning different users to perform each task.</span></span> <span data-ttu-id="d372b-109">分配适当的修复、 验证，或批准角色到每个这些用户，并且每个用户必须使用特定证书以执行的任务。</span><span class="sxs-lookup"><span data-stu-id="d372b-109">You assign the appropriate repair, verify, or approve role to each of these users, and each user must use a specific certificate to perform the task.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="d372b-110">此外支持在处理过程中的部门使用修复和提交消息。</span><span class="sxs-lookup"><span data-stu-id="d372b-110"> also supports the use of departments in processing repaired and submitted messages.</span></span> <span data-ttu-id="d372b-111">每个部门涉及到一组特定的消息上执行的任务的特定工作流。</span><span class="sxs-lookup"><span data-stu-id="d372b-111">Each department involves a specific workflow of tasks performed on a specific set of messages.</span></span> <span data-ttu-id="d372b-112">在任何创建的修复、 验证，或时提交消息，批准步骤，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]调用 BRE 验证，并验证用户是否属于相应的部门。</span><span class="sxs-lookup"><span data-stu-id="d372b-112">In any of the create, repair, verify, or approve steps, when you submit the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] calls BRE validation and verifies that the user is a member of the appropriate department.</span></span> <span data-ttu-id="d372b-113">有关消息修复和新提交的详细信息，请参阅[消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="d372b-113">For more information about message repair and new submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span>  
  
 <span data-ttu-id="d372b-114">如果接收未分析的消息，消息修复和新提交显示的消息和中失败的描述[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，并使你能够打印消息或将其保存到文件。</span><span class="sxs-lookup"><span data-stu-id="d372b-114">If you receive an unparsed message, Message Repair and New Submission displays the message and a description of the failure in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, and enables you to print the message or save it to a file.</span></span> <span data-ttu-id="d372b-115">然后，你可以修复并重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="d372b-115">You can then repair and resubmit the message.</span></span> <span data-ttu-id="d372b-116">但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会调用 BRE 验证或提交已修复未分析的消息时检查部门中的成员身份。</span><span class="sxs-lookup"><span data-stu-id="d372b-116">However, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] does not call BRE validation or check membership in a department when you submit an unparsed message that you have repaired.</span></span> <span data-ttu-id="d372b-117">此外，不验证重新提交未分析的消息或将其批准。</span><span class="sxs-lookup"><span data-stu-id="d372b-117">In addition, a resubmitted unparsed message is not verified or approved.</span></span> <span data-ttu-id="d372b-118">未分析消息有关的详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="d372b-118">For more information about unparsed messages, see [Repairing Unparsed Messages](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).</span></span>  
  
 <span data-ttu-id="d372b-119">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="d372b-119">This section contains:</span></span>  
  
-   [<span data-ttu-id="d372b-120">修复消息</span><span class="sxs-lookup"><span data-stu-id="d372b-120">Repairing a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [<span data-ttu-id="d372b-121">验证消息</span><span class="sxs-lookup"><span data-stu-id="d372b-121">Verifying a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [<span data-ttu-id="d372b-122">批准一条消息</span><span class="sxs-lookup"><span data-stu-id="d372b-122">Approving a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [<span data-ttu-id="d372b-123">处理未分析的消息</span><span class="sxs-lookup"><span data-stu-id="d372b-123">Handling an Unparsed Message</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [<span data-ttu-id="d372b-124">创建和提交新消息</span><span class="sxs-lookup"><span data-stu-id="d372b-124">Creating and Submitting a New Message</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [<span data-ttu-id="d372b-125">创建新的消息模板</span><span class="sxs-lookup"><span data-stu-id="d372b-125">Creating a New Message Template</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)