---
title: 为消息修复和新提交创建部门和角色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- departments, creating
- creating, roles
- roles, requirements
- roles, creating
- creating, departments
- certificates, messages
- messages, certificates
ms.assetid: 6337bd57-63c5-4d97-b558-ac27d5eb60d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fbfe21ff49a8793e818215b72fe7f844cae85e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378411"
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a><span data-ttu-id="f6e3e-102">为消息修复和新提交创建部门和角色</span><span class="sxs-lookup"><span data-stu-id="f6e3e-102">Creating Departments and Roles for Message Repair and New Submission</span></span>
<span data-ttu-id="f6e3e-103">消息修复和新提交涉及以下四个不同的操作：</span><span class="sxs-lookup"><span data-stu-id="f6e3e-103">Message Repair and New Submission involves the following four different operations:</span></span>  
  
- <span data-ttu-id="f6e3e-104">一条消息，未通过验证的修复</span><span class="sxs-lookup"><span data-stu-id="f6e3e-104">Repair of a message that has failed validation</span></span>  
  
- <span data-ttu-id="f6e3e-105">修复 （包括重新生成密钥） 的验证</span><span class="sxs-lookup"><span data-stu-id="f6e3e-105">Verification of the repair (including rekeying)</span></span>  
  
- <span data-ttu-id="f6e3e-106">批准的修复</span><span class="sxs-lookup"><span data-stu-id="f6e3e-106">Approval of the repair</span></span>  
  
- <span data-ttu-id="f6e3e-107">创建新消息</span><span class="sxs-lookup"><span data-stu-id="f6e3e-107">Creation of a new message</span></span>  
  
  <span data-ttu-id="f6e3e-108">若要执行这些操作之一，用户必须假设与操作关联的角色。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-108">To perform one of these operations, a user must assume the role associated with the operation.</span></span> <span data-ttu-id="f6e3e-109">角色还必须处理部门 （如下所述） 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-109">The role must also be a part of the processing department (described below).</span></span> <span data-ttu-id="f6e3e-110">若要将消息提交工作流中执行一个阶段后，用户必须使用与用户关联的有效证书签名消息。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-110">To submit the message after performing a stage in the workflow, the user must sign the message with a valid certificate associated with the user.</span></span>  
  
## <a name="creating-departments-and-roles"></a><span data-ttu-id="f6e3e-111">创建部门和角色</span><span class="sxs-lookup"><span data-stu-id="f6e3e-111">Creating Departments and Roles</span></span>  
 <span data-ttu-id="f6e3e-112">配置文件 Web 客户端文档，请参阅。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-112">Refer Profile Web client documentation.</span></span>  
  
## <a name="rules-of-role-use"></a><span data-ttu-id="f6e3e-113">角色使用的规则</span><span class="sxs-lookup"><span data-stu-id="f6e3e-113">Rules of Role Use</span></span>  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="f6e3e-114">用户、 角色和部门必须符合以下规则：</span><span class="sxs-lookup"><span data-stu-id="f6e3e-114">users, roles, and departments must conform to the following rules:</span></span>  
  
- <span data-ttu-id="f6e3e-115">修复后的消息的完整工作流是修复、 验证，然后批准消息。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-115">The full workflow for a repaired message is to repair, verify, and then approve the message.</span></span> <span data-ttu-id="f6e3e-116">创建消息的完整工作流是创建、 修复、 验证，然后批准消息。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-116">The full workflow for a created message is to create, repair, verify, and then approve the message.</span></span> <span data-ttu-id="f6e3e-117">验证和批准步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-117">The verification and approval steps are optional.</span></span>  
  
- <span data-ttu-id="f6e3e-118">部门的工作流必须以与创建角色或修复角色中。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-118">A department's workflow must begin with a create role or repair role.</span></span> <span data-ttu-id="f6e3e-119">如果工作流包括创建和修复步骤 （创建消息的工作流），创建步骤必须立即在修复步骤之前。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-119">If a workflow includes both create and repair steps (a workflow for a created message), the create step must come immediately before the repair step.</span></span>  
  
- <span data-ttu-id="f6e3e-120">用于创建消息的工作流必须包含一个且只有一个已创建的一项功能的角色。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-120">A workflow for a created message must contain one and only one role that has a capability of create.</span></span>  
  
- <span data-ttu-id="f6e3e-121">每个工作流必须包含一个且只有一个角色包含的修复功能。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-121">Each workflow must contain one and only one role that has a capability of repair.</span></span>  
  
- <span data-ttu-id="f6e3e-122">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户可以与多个角色相关联，但没有单个用户可以在单个工作流中执行多个步骤。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-122">An [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user can be associated with more than one role, but no single user can execute more than one step in a single workflow.</span></span> <span data-ttu-id="f6e3e-123">例如，如果用户 A 修复一条消息，并且用户 B 会验证消息，然后用户 A 和用户 B 都不可以批准消息。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-123">For example, if user A repairs a message and user B verifies the message, then neither user A nor user B can approve the message.</span></span>  
  
- <span data-ttu-id="f6e3e-124">没有相对于其他角色 RekeyVerify 或批准的功能与 RekeyVerify 或批准的功能具有角色的顺序进行检查。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-124">There is no check on the order of roles with the capability of RekeyVerify or Approve relative to other roles with the capability of RekeyVerify or Approve.</span></span>  
  
- <span data-ttu-id="f6e3e-125">如果你已经修复了消息验证再次失败，它将返回到 MRSR 站点文档库中的修复收件箱。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-125">If a message that you have already repaired fails validation again, it goes back into the repair inbox in the MRSR site document library.</span></span> <span data-ttu-id="f6e3e-126">在此情况下，（基于谁具有已执行工作流中的角色） 的验证和审批者角色上的上一限制不再适用。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-126">When this happens, the previous limitations on the verification and approver roles (based on who has already performed a role in the workflow) no longer apply.</span></span> <span data-ttu-id="f6e3e-127">例如，如果用户 A 修复一条消息，用户 B 会拒绝该消息中验证和用户 A 修复消息第二次，然后用户 B 以外的用户无法验证的消息。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-127">For example, if user A repairs a message, user B rejects the message in verification, and user A repairs the message a second time, then a user other than user B could verify the message.</span></span> <span data-ttu-id="f6e3e-128">如果是这样，用户 B 可以批准消息。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-128">If that is the case, then user B could approve the message.</span></span> <span data-ttu-id="f6e3e-129">另一个示例是，如果用户 A 创建一条消息，用户 B 会拒绝该消息中验证，并且用户 C 修复消息，然后用户 A 无法验证的消息。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-129">Another example is that if user A creates a message, user B rejects the message in verification, and user C repairs the message, then user A could verify the message.</span></span>  
  
- <span data-ttu-id="f6e3e-130">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]创建一条消息用户还可以修复该消息，如果它未通过验证。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-130">An [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user who creates a message can also repair that message if it fails validation.</span></span>  
  
- <span data-ttu-id="f6e3e-131">仅[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]与工作流关联的部门中的用户可以在工作流中执行一个步骤。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-131">Only [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users in the department associated with a workflow can perform a step in the workflow.</span></span> <span data-ttu-id="f6e3e-132">当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户提交一条消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]验证用户与消息关联在部门中具有的角色 （通过用户配置文件 （如果在部门不是默认值） 配置文件 web 客户端中）。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-132">When an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user submits a message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] verifies that the user has a role in the department associated with the message (through the User profiles (in case the department is not default) in Profile web client).</span></span>  
  
- <span data-ttu-id="f6e3e-133">管理员可以提供单个[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户在部门内的多个角色。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-133">An administrator can give a single [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user multiple roles within a department.</span></span> <span data-ttu-id="f6e3e-134">单个用户可以执行修复、 验证、 审批或创建过程中或这些角色，在上述任何一个工作流的限制的任何子集。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-134">A single user can perform repair, verification, approval, or creation, or any subset of those roles, subject to the limitations on any one workflow described above.</span></span>  
  
## <a name="certificates"></a><span data-ttu-id="f6e3e-135">证书</span><span class="sxs-lookup"><span data-stu-id="f6e3e-135">Certificates</span></span>  
 <span data-ttu-id="f6e3e-136">若要在本地计算机上的消息提交后修复、 验证、 审批或创建过程中，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户必须使用其自己的证书对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-136">To submit a message on your local computer after repair, verification, approval, or creation, the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user must sign the message with his or her certificate.</span></span> <span data-ttu-id="f6e3e-137">有关创建证书的详细信息，请参阅[安装证书](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-137">For more information about creating certificates, see [Installing Certificates](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md).</span></span>  
  
 <span data-ttu-id="f6e3e-138">若要能够修复、 验证、 审核或通过从远程客户端计算机访问 MRSR 站点创建一条消息，用户必须添加用户的证书的证书-当前用户/个人/证书存储区 （用户不具有其客户端计算机的是管理员才能执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-138">To be able to repair, verify, approve, or create a message by accessing the MRSR site from a remote client computer, the user must add his or her certificate in the Certificates - Current User/Personal/Certificates store of their client computer (the user does not have to be an administrator to do so).</span></span> <span data-ttu-id="f6e3e-139">此外，在服务器上的管理员必须添加用户的证书 （和任何其他用户从其客户端计算机访问服务器的） 证书 （本地计算机） / 其他人 / 证书存储在服务器上。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-139">In addition, an administrator on the server must add the user's certificate (and those of any other users who access the server from their client computer) to the Certificates (Local Computer)/Other People/Certificates store on the server.</span></span>  
  
 <span data-ttu-id="f6e3e-140">单个用户可能有多个分配的角色，并且执行所有这些角色时应使用相同的证书。</span><span class="sxs-lookup"><span data-stu-id="f6e3e-140">A single user might have several allotted roles, and should use the same certificate when performing any of those roles.</span></span>