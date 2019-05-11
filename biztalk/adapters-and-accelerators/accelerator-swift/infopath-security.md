---
title: InfoPath 安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, InfoPath forms
- InfoPath forms, security
ms.assetid: 6ed7b5cc-9801-45a5-8fdb-e5d56dd36435
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2797cd51e6e013feb6c273b3aace8a007d71a4eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377397"
---
# <a name="infopath-security"></a><span data-ttu-id="2c7a4-102">InfoPath 安全性</span><span class="sxs-lookup"><span data-stu-id="2c7a4-102">InfoPath Security</span></span>
<span data-ttu-id="2c7a4-103">Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年会使用 XML 签名来让你使用的数字证书对表单进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-103">Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 uses XML Signatures to let you digitally sign a form using a digital certificate.</span></span> <span data-ttu-id="2c7a4-104">XML 签名定义一个标准的基于 XML 的数字签名，用来帮助保护在 XML 文档中包含的数据。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-104">XML Signatures defines a standard for XML-based digital signatures that you use to help secure the data contained in XML documents.</span></span> <span data-ttu-id="2c7a4-105">XML 签名是受 World Wide Web 联合会 (W3C) 标准。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-105">XML Signatures is a standard governed by the World Wide Web Consortium (W3C).</span></span>  
  
 <span data-ttu-id="2c7a4-106">数字签名是宏或文档上的身份验证了电子、 基于加密的、 安全戳。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-106">A digital signature is an electronic, encryption-based, secure stamp of authentication on a macro or document.</span></span> <span data-ttu-id="2c7a4-107">进行数字签名时[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，通过在窗体输入的 XML 实例"标记"使用数字签名 (签名公共密钥和签名的数据摘要写入到 XML 中的专用节点)。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-107">When digitally signing an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, the XML instance entered through the form is "stamped" with a digital signature (the signature public key and signed data digest is written to a dedicated node in the XML).</span></span> <span data-ttu-id="2c7a4-108">此签名确认 XML 文档来源于签名者，而不更改。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-108">This signature confirms that the XML document originated from the signer and has not been altered.</span></span> [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] <span data-ttu-id="2c7a4-109">提供可验证、 否认签名、 部分签名、 cosigning 和副署通过增强的数字签名的支持。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-109">provides verifiable, non-repudiable signing, partial signing, cosigning and countersigning through enhanced digital signature support.</span></span>  
  
 <span data-ttu-id="2c7a4-110">SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]使用提供的 A4SWIFT FormGenerator 实用工具生成的窗体使用数字签名的 countersigning 方法以便 countersigners 以彼此堆叠的签名。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-110">The SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms generated with the FormGenerator utility provided by A4SWIFT use the countersigning method of digital signing to let signatures of countersigners to be stacked on top of each other.</span></span> <span data-ttu-id="2c7a4-111">此 countersigning 签名堆栈模型的创建或编辑 SWIFT 消息、 条消息由一个或多个审阅者和审批者审阅和批准和最后在工作流中的所有阶段后才提交该消息面向人员的过程具有已注销。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-111">This countersigning signature stack models the human-oriented process of creating or editing a SWIFT message, having the message reviewed and approved by one or more reviewers and approvers, and finally submitting that message only after all stages in a workflow have signed off.</span></span>  
  
 <span data-ttu-id="2c7a4-112">Repairers、 审阅者或审批者而不考虑是否批准或拒绝它对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-112">Repairers, reviewers, or approvers sign the message regardless of whether they approve or reject it.</span></span> <span data-ttu-id="2c7a4-113">签名表示响应的真实性，并不一定表示"已接受"决策。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-113">The signature signifies authenticity of the response and does not necessarily signify an "accepted" decision.</span></span>  
  
 <span data-ttu-id="2c7a4-114">当[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]提交窗体时，它会检查消息的有效性，签名窗体用户属于正确的角色。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-114">When the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form is submitted, it checks messages for validity and that the user signing the form is in the correct role.</span></span>  
  
 <span data-ttu-id="2c7a4-115">如果消息被拒绝在任何阶段 （除了修复） 工作流中，则将消息发送回修复阶段。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-115">If the message is rejected at any stage in a workflow (besides repair), the message is sent back to the repair stage.</span></span> <span data-ttu-id="2c7a4-116">如果消息被拒绝在 repairer 或创建者阶段，消息修复和新提交具有将消息标记为已拒绝的特定属性将消息发送回消息修复和新提交业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-116">If the message is rejected at the repairer or creator stage, Message Repair and New Submission sends the message back to the Message Repair and New Submission orchestration instance with specific properties marking the message as rejected.</span></span>  
  
 <span data-ttu-id="2c7a4-117">本部分介绍如何消息修复和新提交处理的数字签名为角色定义的功能。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-117">This section describes how Message Repair and New Submission handles the digital signatures based on the capabilities defined for a role.</span></span> <span data-ttu-id="2c7a4-118">角色和功能的组合称为"阶段"工作流中。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-118">The role and capability combination is called a "stage" in the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c7a4-119">"创建"角色是跨所有部门限于单一的创建者。</span><span class="sxs-lookup"><span data-stu-id="2c7a4-119">The "create" role is limited to a single creator across all departments.</span></span>  
  
 <span data-ttu-id="2c7a4-120">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="2c7a4-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="2c7a4-121">创建和修复阶段</span><span class="sxs-lookup"><span data-stu-id="2c7a4-121">Create and Repair Stages</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [<span data-ttu-id="2c7a4-122">重新生成密钥验证阶段</span><span class="sxs-lookup"><span data-stu-id="2c7a4-122">Rekey Verification Stage</span></span>](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [<span data-ttu-id="2c7a4-123">审批阶段</span><span class="sxs-lookup"><span data-stu-id="2c7a4-123">Approval Stage</span></span>](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [<span data-ttu-id="2c7a4-124">分发数字证书</span><span class="sxs-lookup"><span data-stu-id="2c7a4-124">Distributing Digital Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)