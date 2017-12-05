---
title: "创建自定义处理程序拒绝消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa02ad0fcb0236ec879e43b44a891fcdf591beb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a><span data-ttu-id="ee4d9-102">为被拒绝的邮件创建自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="ee4d9-102">Creating a Custom Handler for Rejected Messages</span></span>
<span data-ttu-id="ee4d9-103">如果在验证或批准阶段中，拒绝消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将消息返回至工作流 （这在此情况下是始终修复，即使创建该工作流中的第一个阶段） 定义的第一个阶段。</span><span class="sxs-lookup"><span data-stu-id="ee4d9-103">If you reject a message in the verification or approval stage, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] returns the message to the first stage defined for the workflow (which in this case is always repair, even if Create is the first stage in the workflow).</span></span> <span data-ttu-id="ee4d9-104">但是，如果工作流的第一个阶段会拒绝该消息，修复业务流程将发布消息到 MessageBox 具有提升的属性，该值指示 MrsrRepair 业务流程已拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="ee4d9-104">However, if the first stage of the workflow rejects the message, the repair orchestration publishes the message to the MessageBox with promoted properties indicating that the MrsrRepair orchestration rejected the message.</span></span> <span data-ttu-id="ee4d9-105">若要处理这些消息，你可以创建自定义处理 （业务流程） 来订阅这些提升的属性并处理所需的消息。</span><span class="sxs-lookup"><span data-stu-id="ee4d9-105">To handle these messages, you can create a custom handler (orchestration) that subscribes to these promoted properties and processes the messages as required.</span></span>  
  
 <span data-ttu-id="ee4d9-106">MrsrRepair 业务流程中有多个原因情况下，一条消息可能会失败。</span><span class="sxs-lookup"><span data-stu-id="ee4d9-106">A message can fail in the MrsrRepair orchestration for multiple reasons.</span></span> <span data-ttu-id="ee4d9-107">不，业务流程提升下表中的属性，并将这些属性分配值，或表的右侧列中显示的值之一。</span><span class="sxs-lookup"><span data-stu-id="ee4d9-107">When it does, the orchestration promotes the properties in the following table, and assigns these properties the value, or one of the values, shown in the right column of the table.</span></span>  
  
|<span data-ttu-id="ee4d9-108">属性</span><span class="sxs-lookup"><span data-stu-id="ee4d9-108">Property</span></span>|<span data-ttu-id="ee4d9-109">值</span><span class="sxs-lookup"><span data-stu-id="ee4d9-109">Values</span></span>|  
|--------------|------------|  
|<span data-ttu-id="ee4d9-110">BTS。操作</span><span class="sxs-lookup"><span data-stu-id="ee4d9-110">BTS.Operation</span></span>|<span data-ttu-id="ee4d9-111">A4SWIFT_MRSRFailed</span><span class="sxs-lookup"><span data-stu-id="ee4d9-111">A4SWIFT_MRSRFailed</span></span>|  
|<span data-ttu-id="ee4d9-112">A4SWIFT_MRSRFailedReason</span><span class="sxs-lookup"><span data-stu-id="ee4d9-112">A4SWIFT_MRSRFailedReason</span></span>|<span data-ttu-id="ee4d9-113">超时</span><span class="sxs-lookup"><span data-stu-id="ee4d9-113">Timeout</span></span><br /><br /> <span data-ttu-id="ee4d9-114">被拒绝 （表示消息已被拒绝来自第一个阶段）</span><span class="sxs-lookup"><span data-stu-id="ee4d9-114">Rejected (means the message has been rejected from the first stage)</span></span><br /><br /> <span data-ttu-id="ee4d9-115">CantRepairInInfoPath</span><span class="sxs-lookup"><span data-stu-id="ee4d9-115">CantRepairInInfoPath</span></span>|  
|<span data-ttu-id="ee4d9-116">A4SWIFT_MRSRLastStage</span><span class="sxs-lookup"><span data-stu-id="ee4d9-116">A4SWIFT_MRSRLastStage</span></span>|<span data-ttu-id="ee4d9-117">\<消息在失败之前已在最后一个阶段 （角色） 的名称\></span><span class="sxs-lookup"><span data-stu-id="ee4d9-117">\<name of last stage (role) that the message was in before failing\></span></span>|  
|<span data-ttu-id="ee4d9-118">A4SWIFT_MRSRDepartment</span><span class="sxs-lookup"><span data-stu-id="ee4d9-118">A4SWIFT_MRSRDepartment</span></span>|<span data-ttu-id="ee4d9-119">\<部门的名称\></span><span class="sxs-lookup"><span data-stu-id="ee4d9-119">\<name of department\></span></span>|