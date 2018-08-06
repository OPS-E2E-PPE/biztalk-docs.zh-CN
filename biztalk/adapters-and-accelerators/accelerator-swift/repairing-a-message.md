---
title: 修复消息 |Microsoft Docs
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
ms.openlocfilehash: f9edb8f9cc3c5db67e75ff47125e0d58891a5173
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992038"
---
# <a name="repairing-a-message"></a><span data-ttu-id="948ee-102">修复消息</span><span class="sxs-lookup"><span data-stu-id="948ee-102">Repairing a Message</span></span>
<span data-ttu-id="948ee-103">本部分介绍如何修复未通过验证的消息。</span><span class="sxs-lookup"><span data-stu-id="948ee-103">This section describes how to repair a message that has failed validation.</span></span>  

### <a name="to-repair-a-message"></a><span data-ttu-id="948ee-104">若要修复消息</span><span class="sxs-lookup"><span data-stu-id="948ee-104">To repair a message</span></span>  

1. <span data-ttu-id="948ee-105">在 Internet Explorer 中，打开你的 MRSR 站点置于 http://localhost/sites/bassite 。</span><span class="sxs-lookup"><span data-stu-id="948ee-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="948ee-106">在主页窗口中，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="948ee-106">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="948ee-107">在文档窗口中下,**文档库**，单击 **\<*部门名称*\>**_**Repairer**.</span><span class="sxs-lookup"><span data-stu-id="948ee-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>**_**Repairer**.</span></span>  

4. <span data-ttu-id="948ee-108">在中\<*部门名称*\>_Repair 窗口中，单击**收件箱**。</span><span class="sxs-lookup"><span data-stu-id="948ee-108">In the \<*Department name*\>_Repair window, click **Inbox**.</span></span>  

5. <span data-ttu-id="948ee-109">在收件箱窗口中，指向的消息的标题，单击消息标题右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。</span><span class="sxs-lookup"><span data-stu-id="948ee-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="948ee-110">SWIFT 加速器窗格中的[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，确保**错误**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="948ee-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, ensure that **Errors** is selected.</span></span> <span data-ttu-id="948ee-111">查看任何错误中所示**分析和 XML 验证错误**， **BRE 验证错误**，并**运行时错误**框。</span><span class="sxs-lookup"><span data-stu-id="948ee-111">Review any errors shown in the **Parse and XML Validation Errors**, **BRE Validation Errors**, and **Runtime Errors** boxes.</span></span>  

7. <span data-ttu-id="948ee-112">在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到的位置错误，并更正该错误。</span><span class="sxs-lookup"><span data-stu-id="948ee-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error, and correct the error.</span></span> <span data-ttu-id="948ee-113">如果 XML 验证错误，将以红色突出显示该错误。</span><span class="sxs-lookup"><span data-stu-id="948ee-113">If it is an XML validation error, the error will be highlighted in red.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="948ee-114">不中用红色突出显示 BRE 验证错误[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。</span><span class="sxs-lookup"><span data-stu-id="948ee-114">BRE validation errors will not be highlighted in red in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span> <span data-ttu-id="948ee-115">BRE 验证错误的详细信息，请参阅[SWIFT 错误代码](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="948ee-115">For more information about BRE validation errors, see [SWIFT Error Codes](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="948ee-116">如果错误发生在伴随下拉列表的字段，你将不能以查看导致了错误的原始值。</span><span class="sxs-lookup"><span data-stu-id="948ee-116">If the error occurs in a field that is accompanied by a drop-down list, you will not be able to see the original value that caused the error.</span></span> <span data-ttu-id="948ee-117">该字段将显示"选择"，而不是原始值。</span><span class="sxs-lookup"><span data-stu-id="948ee-117">The field will display "Select" instead of the original value.</span></span> <span data-ttu-id="948ee-118">从下拉列表中选择适当的值。</span><span class="sxs-lookup"><span data-stu-id="948ee-118">Select the appropriate value from the drop-down list.</span></span>  

8. <span data-ttu-id="948ee-119">若要确保将验证该消息，请单击**验证**当前角色中： 修复窗格中，然后依次**验证消息**。</span><span class="sxs-lookup"><span data-stu-id="948ee-119">To ensure that the message will validate, click **Validation** in the Current Role: Repair pane, and then click **Validate Message**.</span></span> <span data-ttu-id="948ee-120">验证是否显示结果窗格**该消息是否有效**。</span><span class="sxs-lookup"><span data-stu-id="948ee-120">Verify that the Results pane displays **The message is valid**.</span></span>  

9. <span data-ttu-id="948ee-121">在中[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="948ee-121">In the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="948ee-122">当您单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。</span><span class="sxs-lookup"><span data-stu-id="948ee-122">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="948ee-123">如果验证不成功，必须修复验证错误，然后继续。</span><span class="sxs-lookup"><span data-stu-id="948ee-123">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  

10. <span data-ttu-id="948ee-124">在提交消息对话框中，单击**Accept**若要接受的更改提交修复后的消息，请单击**拒绝**以拒绝所做的更改，或单击**取消**取消提交和返回到该窗体中。</span><span class="sxs-lookup"><span data-stu-id="948ee-124">In the Submit Message dialog box, click **Accept** to submit the repaired message with changes accepted, click **Reject** to reject the changes, or click **Cancel** to cancel the submission and return to the form.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="948ee-125">如果接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。</span><span class="sxs-lookup"><span data-stu-id="948ee-125">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="948ee-126">如果在修复阶段中，拒绝消息更改，则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到 MessageBox，并发布到事件查看器读取的错误"无法重置到工作流中的第一个阶段。"。</span><span class="sxs-lookup"><span data-stu-id="948ee-126">If you reject the message changes in the repair stage, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the MessageBox, and posts to the Event Viewer an error that reads "Could not reset to the first stage in the workflow.".</span></span>  

11. <span data-ttu-id="948ee-127">如果单击了**Accept**或**拒绝**在步骤 10 中，在**数字签名向导**页上，选择你想要用于登录窗体的证书 (证书，对于创建 repairer），然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="948ee-127">If you clicked **Accept** or **Reject** in step 10, on the **Digital Signature Wizard** page, select the certificate that you want to use to sign the form (the certificate that you created for the repairer), and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="948ee-128">若要验证数字签名的有效性，请单击**数字签名**上**工具**菜单中，单击你想要验证，，然后单击的数字签名**查看签名窗体**.</span><span class="sxs-lookup"><span data-stu-id="948ee-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  

12. <span data-ttu-id="948ee-129">在输入的注释为数字签名向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="948ee-129">On the Digital Signature Wizard page for entering a comment, click **Finish**.</span></span>  

13. <span data-ttu-id="948ee-130">在验证窗体数字签名向导页上，验证签名的消息和您的签名正确。</span><span class="sxs-lookup"><span data-stu-id="948ee-130">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing and your signature are correct.</span></span> <span data-ttu-id="948ee-131">单击**我已在签名之前验证此内容**，然后单击**登录**。</span><span class="sxs-lookup"><span data-stu-id="948ee-131">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

14. <span data-ttu-id="948ee-132">在验证数字签名窗口中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="948ee-132">In the Verify Digital Signature window, click **Close**.</span></span>  

15. <span data-ttu-id="948ee-133">在提交成功对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="948ee-133">In the Submission Success dialog box, click **OK**.</span></span>  

16. <span data-ttu-id="948ee-134">关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。</span><span class="sxs-lookup"><span data-stu-id="948ee-134">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  

17. <span data-ttu-id="948ee-135">在 MRSR 站点中，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="948ee-135">In MRSR site, click **Documents**.</span></span> <span data-ttu-id="948ee-136">如果单击了**Accept**为接受步骤 11 中的更改，请确认*\<部门名称\>*_ReKeyVerify 文档库中包含的消息，只需修复。</span><span class="sxs-lookup"><span data-stu-id="948ee-136">If you clicked **Accept** to accept the changes in step 11, verify that the *\<Department name\>*_ReKeyVerify document library contains the message that you just repaired.</span></span> <span data-ttu-id="948ee-137">如果单击了**拒绝**要拒绝步骤 11 中的更改，请验证 A4SWIFT_Outbox 文档库包含刚刚修改的消息。</span><span class="sxs-lookup"><span data-stu-id="948ee-137">If you clicked **Reject** to reject the changes in step 11, verify that the A4SWIFT_Outbox document library contains the message that was just modified.</span></span>
