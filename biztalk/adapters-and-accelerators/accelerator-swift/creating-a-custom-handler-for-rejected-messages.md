---
title: 创建自定义处理程序被拒绝消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7fb2ebe02d4f64923239bb67aa3667ac4f3ff0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378501"
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a><span data-ttu-id="5500e-102">为已拒绝消息创建自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="5500e-102">Creating a Custom Handler for Rejected Messages</span></span>
<span data-ttu-id="5500e-103">如果在验证或审批阶段中，拒绝消息，则[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]该消息返回给工作流 （这在此情况下是始终修复，即使创建工作流中的第一个阶段） 定义的第一个阶段。</span><span class="sxs-lookup"><span data-stu-id="5500e-103">If you reject a message in the verification or approval stage, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] returns the message to the first stage defined for the workflow (which in this case is always repair, even if Create is the first stage in the workflow).</span></span> <span data-ttu-id="5500e-104">但是，如果工作流的第一个阶段会拒绝该消息，修复业务流程将消息发布到 MessageBox 与升级的属性，该值指示 MrsrRepair 业务流程已拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="5500e-104">However, if the first stage of the workflow rejects the message, the repair orchestration publishes the message to the MessageBox with promoted properties indicating that the MrsrRepair orchestration rejected the message.</span></span> <span data-ttu-id="5500e-105">若要处理这些消息，可以创建一个自定义处理程序 （业务流程），订阅这些升级的属性，并处理所需的消息。</span><span class="sxs-lookup"><span data-stu-id="5500e-105">To handle these messages, you can create a custom handler (orchestration) that subscribes to these promoted properties and processes the messages as required.</span></span>  
  
 <span data-ttu-id="5500e-106">一条消息失败 MrsrRepair 业务流程中存在多个原因。</span><span class="sxs-lookup"><span data-stu-id="5500e-106">A message can fail in the MrsrRepair orchestration for multiple reasons.</span></span> <span data-ttu-id="5500e-107">当它执行业务流程升级下表中的属性，并将这些属性分配值，或显示表的右侧列中的值之一。</span><span class="sxs-lookup"><span data-stu-id="5500e-107">When it does, the orchestration promotes the properties in the following table, and assigns these properties the value, or one of the values, shown in the right column of the table.</span></span>  
  
|<span data-ttu-id="5500e-108">属性</span><span class="sxs-lookup"><span data-stu-id="5500e-108">Property</span></span>|<span data-ttu-id="5500e-109">值</span><span class="sxs-lookup"><span data-stu-id="5500e-109">Values</span></span>|  
|--------------|------------|  
|<span data-ttu-id="5500e-110">BTS.Operation</span><span class="sxs-lookup"><span data-stu-id="5500e-110">BTS.Operation</span></span>|<span data-ttu-id="5500e-111">A4SWIFT_MRSRFailed</span><span class="sxs-lookup"><span data-stu-id="5500e-111">A4SWIFT_MRSRFailed</span></span>|  
|<span data-ttu-id="5500e-112">A4SWIFT_MRSRFailedReason</span><span class="sxs-lookup"><span data-stu-id="5500e-112">A4SWIFT_MRSRFailedReason</span></span>|<span data-ttu-id="5500e-113">超时</span><span class="sxs-lookup"><span data-stu-id="5500e-113">Timeout</span></span><br /><br /> <span data-ttu-id="5500e-114">已拒绝 （表示消息已被拒绝来自第一个阶段）</span><span class="sxs-lookup"><span data-stu-id="5500e-114">Rejected (means the message has been rejected from the first stage)</span></span><br /><br /> <span data-ttu-id="5500e-115">CantRepairInInfoPath</span><span class="sxs-lookup"><span data-stu-id="5500e-115">CantRepairInInfoPath</span></span>|  
|<span data-ttu-id="5500e-116">A4SWIFT_MRSRLastStage</span><span class="sxs-lookup"><span data-stu-id="5500e-116">A4SWIFT_MRSRLastStage</span></span>|<span data-ttu-id="5500e-117">\<消息已在失败之前的最后一个阶段 （角色） 的名称\></span><span class="sxs-lookup"><span data-stu-id="5500e-117">\<name of last stage (role) that the message was in before failing\></span></span>|  
|<span data-ttu-id="5500e-118">A4SWIFT_MRSRDepartment</span><span class="sxs-lookup"><span data-stu-id="5500e-118">A4SWIFT_MRSRDepartment</span></span>|<span data-ttu-id="5500e-119">\<系的名称\></span><span class="sxs-lookup"><span data-stu-id="5500e-119">\<name of department\></span></span>|