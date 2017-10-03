---
title: "消息修复和新提交 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages
- resubmitting messages
- errors, messages
- messages, errors
- messages, resubmitting
ms.assetid: 5bc6bfa2-8210-4dd3-89bb-5455e294ca92
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bc15351848fe68d6ef54c31fc6d58c075bb1c58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-repair-and-new-submission"></a><span data-ttu-id="d1322-102">消息修复和新的提交</span><span class="sxs-lookup"><span data-stu-id="d1322-102">Message Repair and New Submission</span></span>
<span data-ttu-id="d1322-103">消息修复和新提交功能[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供有助于您修复 MT 和 MX 未通过验证的消息。</span><span class="sxs-lookup"><span data-stu-id="d1322-103">The Message Repair and New Submission feature of [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides a way for you to repair MT and MX messages that fail validation.</span></span> <span data-ttu-id="d1322-104">使用 MRSR SharePoint 站点 （由用户已部署），你可以看到如何消息未能通过验证。</span><span class="sxs-lookup"><span data-stu-id="d1322-104">Using the MRSR SharePoint site (deployed by user), you can see how the message failed validation.</span></span> <span data-ttu-id="d1322-105">从 MRSR 站点，可以打开的 InfoPath 窗体，可用于识别的错误、 修复消息，并将其提交进行重新处理中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d1322-105">From MRSR site, you can open the message in an InfoPath form that enables you to identify the error, repair the message, and submit it for reprocessing.</span></span>  
  
 <span data-ttu-id="d1322-106">消息修复和新提交支持基于角色的消息修复。</span><span class="sxs-lookup"><span data-stu-id="d1322-106">Message Repair and New Submission supports role-based message repair.</span></span> <span data-ttu-id="d1322-107">完整的修复工作流包括修复、 验证和批准。</span><span class="sxs-lookup"><span data-stu-id="d1322-107">A full repair workflow includes repair, verification, and approval.</span></span> <span data-ttu-id="d1322-108">修复工作流都与一个部门，定义工作流的角色 （或阶段），并配置每个角色的 A4SWIFT 用户关联。</span><span class="sxs-lookup"><span data-stu-id="d1322-108">A repair workflow is associated with a department that defines the roles (or stages) of the workflow and configures an A4SWIFT user for each role.</span></span> <span data-ttu-id="d1322-109">每个修复角色具有定制到角色的单独 MRSR 站点视图。</span><span class="sxs-lookup"><span data-stu-id="d1322-109">Each repair role has a separate MRSR site view tailored to the role.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d1322-110">执行验证和执行角色签名消息，每个 A4SWIFT 用户使用的证书，以确保安全的过程。</span><span class="sxs-lookup"><span data-stu-id="d1322-110"> performs validation, and each A4SWIFT user performing a role signs the message, using a certificate, to ensure a secure process.</span></span>  
  
 <span data-ttu-id="d1322-111">除消息修复 A4SWIFT 使您能够提交使用增强的新消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。</span><span class="sxs-lookup"><span data-stu-id="d1322-111">In addition to message repair, A4SWIFT enables you to submit a new message using an enhanced [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span> <span data-ttu-id="d1322-112">第四个 A4SWIFT 用户，创建者，执行此函数。</span><span class="sxs-lookup"><span data-stu-id="d1322-112">A fourth A4SWIFT user, a creator, performs this function.</span></span> <span data-ttu-id="d1322-113">此过程还执行验证，而可以涉及到修复、 验证和批准的角色，以确保成功提交。</span><span class="sxs-lookup"><span data-stu-id="d1322-113">The process also performs validation, and can involve repair, verification, and approval roles to ensure successful submission.</span></span> <span data-ttu-id="d1322-114">A4SWIFT 处理通过新消息提交[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体相同的方式，它处理的修复后的消息。</span><span class="sxs-lookup"><span data-stu-id="d1322-114">A4SWIFT handles new message submission through an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form the same way that it handles a repaired message.</span></span>  
  
 <span data-ttu-id="d1322-115">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="d1322-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="d1322-116">消息修复过程</span><span class="sxs-lookup"><span data-stu-id="d1322-116">Message Repair Process</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-process.md)  
  
-   [<span data-ttu-id="d1322-117">为消息修复和新提交创建部门和角色</span><span class="sxs-lookup"><span data-stu-id="d1322-117">Creating Departments and Roles for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="d1322-118">使用 InfoPath 窗体来修复消息或提交新消息</span><span class="sxs-lookup"><span data-stu-id="d1322-118">Using an InfoPath Form to Repair a Message or Submit a New Message</span></span>](../../adapters-and-accelerators/accelerator-swift/using-an-infopath-form-to-repair-a-message-or-submit-a-new-message.md)  
  
-   [<span data-ttu-id="d1322-119">在消息修复和新提交的特殊处理</span><span class="sxs-lookup"><span data-stu-id="d1322-119">Special Processing in Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="d1322-120">修复未分析的消息</span><span class="sxs-lookup"><span data-stu-id="d1322-120">Repairing Unparsed Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)  
  
-   [<span data-ttu-id="d1322-121">消息修复和新提交服务处理</span><span class="sxs-lookup"><span data-stu-id="d1322-121">Message Repair and New Submission Service Processing</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-service-processing.md)