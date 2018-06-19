---
title: 修复消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
ms.assetid: 3a61b73b-5433-4249-b580-6194ccb4aebc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4489e463257f811fe2c71efea49880940751c66a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25961555"
---
# <a name="repairing-a-message"></a><span data-ttu-id="ca157-102">修复消息</span><span class="sxs-lookup"><span data-stu-id="ca157-102">Repairing a Message</span></span>
<span data-ttu-id="ca157-103">本部分介绍如何修复未通过验证的消息。</span><span class="sxs-lookup"><span data-stu-id="ca157-103">This section describes how to repair a message that has failed validation.</span></span>  
  
### <a name="to-repair-a-message"></a><span data-ttu-id="ca157-104">若要修复一条消息</span><span class="sxs-lookup"><span data-stu-id="ca157-104">To repair a message</span></span>  
  
1.  <span data-ttu-id="ca157-105">在 Internet Explorer 中，打开 MRSR 网站http://localhost/sites/bassite。</span><span class="sxs-lookup"><span data-stu-id="ca157-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="ca157-106">在主页窗口中，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="ca157-106">In the Home window, click **Documents**.</span></span>  
  
3.  <span data-ttu-id="ca157-107">在文档窗口中，在**文档库**，单击 **\<*部门名称*\>**_**Repairer**.</span><span class="sxs-lookup"><span data-stu-id="ca157-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>**_**Repairer**.</span></span>  
  
4.  <span data-ttu-id="ca157-108">在\<*部门名称*\>_Repair 窗口中，单击**收件箱**。</span><span class="sxs-lookup"><span data-stu-id="ca157-108">In the \<*Department name*\>_Repair window, click **Inbox**.</span></span>  
  
5.  <span data-ttu-id="ca157-109">在收件箱窗口中，指向此消息的标题，单击消息标题中，右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。</span><span class="sxs-lookup"><span data-stu-id="ca157-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  
  
6.  <span data-ttu-id="ca157-110">在 SWIFT 快捷键窗格中的[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，确保**错误**选择。</span><span class="sxs-lookup"><span data-stu-id="ca157-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, ensure that **Errors** is selected.</span></span> <span data-ttu-id="ca157-111">查看中显示任何错误**Parse 和 XML 验证错误**， **BRE 验证错误**，和**运行时错误**框。</span><span class="sxs-lookup"><span data-stu-id="ca157-111">Review any errors shown in the **Parse and XML Validation Errors**, **BRE Validation Errors**, and **Runtime Errors** boxes.</span></span>  
  
7.  <span data-ttu-id="ca157-112">在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到的位置错误，并更正错误。</span><span class="sxs-lookup"><span data-stu-id="ca157-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error, and correct the error.</span></span> <span data-ttu-id="ca157-113">如果这是 XML 验证错误，将以红色突出显示错误。</span><span class="sxs-lookup"><span data-stu-id="ca157-113">If it is an XML validation error, the error will be highlighted in red.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca157-114">未在中以红色突出显示 BRE 验证错误[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。</span><span class="sxs-lookup"><span data-stu-id="ca157-114">BRE validation errors will not be highlighted in red in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span> <span data-ttu-id="ca157-115">有关 BRE 验证错误的详细信息，请参阅[SWIFT 错误代码](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="ca157-115">For more information about BRE validation errors, see [SWIFT Error Codes](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca157-116">如果错误发生在字段伴随下拉列表中，你将不能以查看导致错误的原始值。</span><span class="sxs-lookup"><span data-stu-id="ca157-116">If the error occurs in a field that is accompanied by a drop-down list, you will not be able to see the original value that caused the error.</span></span> <span data-ttu-id="ca157-117">该字段将显示"选择"，而不是原始值。</span><span class="sxs-lookup"><span data-stu-id="ca157-117">The field will display "Select" instead of the original value.</span></span> <span data-ttu-id="ca157-118">从下拉列表中选择适当的值。</span><span class="sxs-lookup"><span data-stu-id="ca157-118">Select the appropriate value from the drop-down list.</span></span>  
  
8.  <span data-ttu-id="ca157-119">若要确保将验证消息，请单击**验证**中当前的角色： 修复窗格中，并依次**Validate 消息**。</span><span class="sxs-lookup"><span data-stu-id="ca157-119">To ensure that the message will validate, click **Validation** in the Current Role: Repair pane, and then click **Validate Message**.</span></span> <span data-ttu-id="ca157-120">验证结果窗格中显示**消息无效**。</span><span class="sxs-lookup"><span data-stu-id="ca157-120">Verify that the Results pane displays **The message is valid**.</span></span>  
  
9. <span data-ttu-id="ca157-121">在[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="ca157-121">In the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca157-122">当你单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。</span><span class="sxs-lookup"><span data-stu-id="ca157-122">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="ca157-123">如果未成功验证，则必须修复验证错误，然后继续。</span><span class="sxs-lookup"><span data-stu-id="ca157-123">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  
  
10. <span data-ttu-id="ca157-124">在提交消息对话框中，单击**接受**要接受的更改提交修复后的消息，请单击**拒绝**以拒绝所做的更改，或单击**取消**取消提交并返回到窗体中。</span><span class="sxs-lookup"><span data-stu-id="ca157-124">In the Submit Message dialog box, click **Accept** to submit the repaired message with changes accepted, click **Reject** to reject the changes, or click **Cancel** to cancel the submission and return to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca157-125">如果你接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。</span><span class="sxs-lookup"><span data-stu-id="ca157-125">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca157-126">如果您在修复阶段中，拒绝消息更改[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到 MessageBox，并发送到事件查看器读取错误"无法重置到工作流中的第一个阶段。"。</span><span class="sxs-lookup"><span data-stu-id="ca157-126">If you reject the message changes in the repair stage, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the MessageBox, and posts to the Event Viewer an error that reads "Could not reset to the first stage in the workflow.".</span></span>  
  
11. <span data-ttu-id="ca157-127">如果你单击**接受**或**拒绝**在步骤 10 中，在**数字签名向导**页上，选择你想要用于对表单进行签名的证书 (证书你为创建 repairer），然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ca157-127">If you clicked **Accept** or **Reject** in step 10, on the **Digital Signature Wizard** page, select the certificate that you want to use to sign the form (the certificate that you created for the repairer), and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca157-128">若要验证其有效性的数字签名，请单击**数字签名**上**工具**菜单上，单击你想要验证，，然后单击的数字签名**查看签名的表单**.</span><span class="sxs-lookup"><span data-stu-id="ca157-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  
  
12. <span data-ttu-id="ca157-129">在用于输入注释数字签名向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="ca157-129">On the Digital Signature Wizard page for entering a comment, click **Finish**.</span></span>  
  
13. <span data-ttu-id="ca157-130">在验证窗体数字签名向导页上，验证将对进行签名的消息和签名正确。</span><span class="sxs-lookup"><span data-stu-id="ca157-130">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing and your signature are correct.</span></span> <span data-ttu-id="ca157-131">单击**我已在签名之前验证此内容**，然后单击**登录**。</span><span class="sxs-lookup"><span data-stu-id="ca157-131">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
14. <span data-ttu-id="ca157-132">在验证数字签名窗口中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="ca157-132">In the Verify Digital Signature window, click **Close**.</span></span>  
  
15. <span data-ttu-id="ca157-133">在提交成功对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca157-133">In the Submission Success dialog box, click **OK**.</span></span>  
  
16. <span data-ttu-id="ca157-134">关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。</span><span class="sxs-lookup"><span data-stu-id="ca157-134">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  
  
17. <span data-ttu-id="ca157-135">在 MRSR 站点中，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="ca157-135">In MRSR site, click **Documents**.</span></span> <span data-ttu-id="ca157-136">如果你单击**接受**若要接受步骤 11 中的更改，请确认*\<部门名称\>*_ReKeyVerify 文档库包含仅修复的消息。</span><span class="sxs-lookup"><span data-stu-id="ca157-136">If you clicked **Accept** to accept the changes in step 11, verify that the *\<Department name\>*_ReKeyVerify document library contains the message that you just repaired.</span></span> <span data-ttu-id="ca157-137">如果你单击**拒绝**若要拒绝步骤 11 中的更改，请验证 A4SWIFT_Outbox 文档库包含刚刚修改的消息。</span><span class="sxs-lookup"><span data-stu-id="ca157-137">If you clicked **Reject** to reject the changes in step 11, verify that the A4SWIFT_Outbox document library contains the message that was just modified.</span></span>