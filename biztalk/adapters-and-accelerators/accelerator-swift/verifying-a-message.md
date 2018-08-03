---
title: 验证消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cdb64d95b970e8a1d526f3323cf2fcf0ae4d641
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012094"
---
# <a name="verifying-a-message"></a><span data-ttu-id="09cd7-102">验证消息</span><span class="sxs-lookup"><span data-stu-id="09cd7-102">Verifying a Message</span></span>
<span data-ttu-id="09cd7-103">本部分介绍如何验证已修复的消息。</span><span class="sxs-lookup"><span data-stu-id="09cd7-103">This section describes how to verify a message that has been repaired.</span></span>  

### <a name="to-verify-a-message"></a><span data-ttu-id="09cd7-104">若要验证消息</span><span class="sxs-lookup"><span data-stu-id="09cd7-104">To verify a message</span></span>  

1. <span data-ttu-id="09cd7-105">在 Internet Explorer 中，打开你的 MRSR 站点置于http://localhost/sites/bassite。</span><span class="sxs-lookup"><span data-stu-id="09cd7-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="09cd7-106">在主页窗口中，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-106">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="09cd7-107">在文档窗口中下,**文档库**，单击 **\<*部门名称*\>_Verifier**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>_Verifier**.</span></span>  

4. <span data-ttu-id="09cd7-108">在确认窗口中，单击**收件箱**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-108">In the Verify window, click **Inbox**.</span></span>  

5. <span data-ttu-id="09cd7-109">在验证收件箱窗口中，依次指向的消息的标题，请单击消息标题右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-109">In the Verify Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="09cd7-110">在中**文件下载**对话框中，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-110">In the **File Download** dialog box, click **Open**.</span></span>  

7. <span data-ttu-id="09cd7-111">中的当前角色： RekeyVerify 窗格[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**错误**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-111">In the Current Roles: RekeyVerify pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Errors**.</span></span> <span data-ttu-id="09cd7-112">查看任何错误中所示**分析和 XML 验证错误**框和**BRE 验证错误**框。</span><span class="sxs-lookup"><span data-stu-id="09cd7-112">Review any errors shown in the **Parse and XML Validation Errors** box and the **BRE Validation Errors** box.</span></span>  

8. <span data-ttu-id="09cd7-113">在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到错误的位置并验证是否已更正错误。</span><span class="sxs-lookup"><span data-stu-id="09cd7-113">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error and verify that the error has been corrected.</span></span> <span data-ttu-id="09cd7-114">可以看到原始错误已通过单击**错误**中当前的角色： RekeyVerify 窗格中，并在其中一个错误窗格中查看该错误。</span><span class="sxs-lookup"><span data-stu-id="09cd7-114">You can see what the original error was by clicking **Errors** in the Current Role: RekeyVerify pane, and viewing the error in one of the error panes.</span></span> <span data-ttu-id="09cd7-115">此外可以通过单击比较消息的修复和已修复版本**消息的详细信息**中当前的角色： RekeyVerify 窗格。</span><span class="sxs-lookup"><span data-stu-id="09cd7-115">You can also compare the unrepaired and repaired versions of the message by clicking **Message Details** in the Current Role: RekeyVerify pane.</span></span>  

9. <span data-ttu-id="09cd7-116">若要确保将验证该消息，请单击**验证**当前角色中： RekeyVerify 窗格中，然后单击**验证消息**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-116">To ensure that the message will validate, click **Validation** in the Current Role: RekeyVerify pane, and then click **Validate Message**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="09cd7-117">在当前角色中的消息验证下的结果窗格： RekeyVerify 窗格指示需要重新生成密钥的消息中的所有字段。</span><span class="sxs-lookup"><span data-stu-id="09cd7-117">The Results pane under Message Validation in the Current Role: RekeyVerify pane indicates all fields in the message that you need to rekey.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="09cd7-118"> 将标记中红色的星号消息窗格中的这些字段。</span><span class="sxs-lookup"><span data-stu-id="09cd7-118"> marks these fields in the Message pane with a red asterisk.</span></span>  

10. <span data-ttu-id="09cd7-119">在消息窗格 （指示在提交之前，必须重新生成数据） 以红色星号标记中的所有字段中重新生成数据。</span><span class="sxs-lookup"><span data-stu-id="09cd7-119">Rekey data into all fields in the Message pane marked with a red asterisk (indicating that the data must be rekeyed before submission).</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="09cd7-120">您可以通过单击所需的数据显示消息字段中重新生成密钥**消息的详细信息**中当前的角色： RekeyVerify 窗格中，并滚动到该字段的原始消息。</span><span class="sxs-lookup"><span data-stu-id="09cd7-120">You can display the data that you need to rekey into message fields by clicking **Message Details** in the Current Role: RekeyVerify pane, and scrolling through the original message to the field.</span></span> <span data-ttu-id="09cd7-121">这是 true，除非其中一个原始消息中的重新生成密钥字段中的验证错误时出现这种情况下您必须重新生成它时修复该字段。</span><span class="sxs-lookup"><span data-stu-id="09cd7-121">This is true unless there was a validation error in one of the rekey fields in the original message, in which case you have to repair the field when you rekey it.</span></span>  

11. <span data-ttu-id="09cd7-122">单击**验证**中**当前角色： RekeyVerify**窗格中，，然后单击**验证消息**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-122">Click **Validation** in the **Current Role: RekeyVerify** pane, and then click **Validate Message**.</span></span> <span data-ttu-id="09cd7-123">验证结果窗格中显示消息**该消息是否有效**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-123">Verify that the Results pane displays the message **The message is valid**.</span></span>  

12. <span data-ttu-id="09cd7-124">单击**提交**中[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口。</span><span class="sxs-lookup"><span data-stu-id="09cd7-124">Click **Submit** in the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="09cd7-125">当您单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。</span><span class="sxs-lookup"><span data-stu-id="09cd7-125">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="09cd7-126">如果验证不成功，必须修复验证错误，然后继续。</span><span class="sxs-lookup"><span data-stu-id="09cd7-126">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  

13. <span data-ttu-id="09cd7-127">在提交消息对话框中，单击**接受**可以将已验证的消息提交已接受的更改。</span><span class="sxs-lookup"><span data-stu-id="09cd7-127">In the Submit Message dialog box, click **Accept** to submit the verified message with changes accepted.</span></span> <span data-ttu-id="09cd7-128">单击**拒绝**可以将消息提交已拒绝的更改。</span><span class="sxs-lookup"><span data-stu-id="09cd7-128">Click **Reject** to submit the message with changes rejected.</span></span> <span data-ttu-id="09cd7-129">单击**取消**取消提交并返回到该表单。</span><span class="sxs-lookup"><span data-stu-id="09cd7-129">Click **Cancel** to cancel the submission and return to the form.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="09cd7-130">如果接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。</span><span class="sxs-lookup"><span data-stu-id="09cd7-130">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="09cd7-131">如果拒绝消息更改，则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]该消息返回给工作流的第一个阶段 （创建或修复） 并将重置修复工作流。</span><span class="sxs-lookup"><span data-stu-id="09cd7-131">If you reject the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] returns the message to the first stage of the workflow (create or repair) and resets the repair workflow.</span></span>  

14. <span data-ttu-id="09cd7-132">在用于选择证书来签署该窗体数字签名向导页上，选择你想要用于登录窗体 （为验证程序创建的证书），该证书，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-132">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the verifier), and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="09cd7-133">若要验证数字签名的有效性，请单击**数字签名**上**工具**菜单中，单击你想要验证，，然后单击的数字签名**查看签名窗体**.</span><span class="sxs-lookup"><span data-stu-id="09cd7-133">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span> <span data-ttu-id="09cd7-134">如果需要添加此角色的另一个签名，此，请在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="09cd7-134">If you need to add another signature for this role, do so in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console.</span></span>  

15. <span data-ttu-id="09cd7-135">在用于输入注释数字签名向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-135">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  

16. <span data-ttu-id="09cd7-136">在验证窗体数字签名向导页上，验证签名的消息正确。</span><span class="sxs-lookup"><span data-stu-id="09cd7-136">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="09cd7-137">单击**查看证书**如果你想要验证是否使用正确的签名。</span><span class="sxs-lookup"><span data-stu-id="09cd7-137">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="09cd7-138">单击**我已在签名之前验证此内容**，然后单击**登录**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-138">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

17. <span data-ttu-id="09cd7-139">在验证数字签名窗口中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-139">In the Verify Digital Signature window, click **Close**.</span></span>  

18. <span data-ttu-id="09cd7-140">在提交成功对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-140">In the Submission Success dialog box, click **OK**.</span></span>  

19. <span data-ttu-id="09cd7-141">关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。</span><span class="sxs-lookup"><span data-stu-id="09cd7-141">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  

20. <span data-ttu-id="09cd7-142">在 MRSR 站点中，单击**文档和列表**。</span><span class="sxs-lookup"><span data-stu-id="09cd7-142">In MRSR site, click **Documents and Lists**.</span></span> <span data-ttu-id="09cd7-143">如果单击了**Accept**为接受步骤 13 中的更改，请确认\<部门名称\>_Approve 文档库中包含的消息，只需修改。</span><span class="sxs-lookup"><span data-stu-id="09cd7-143">If you clicked **Accept** to accept the changes in step 13, verify that the \<Department name\>_Approve document library contains the message that was just modified.</span></span> <span data-ttu-id="09cd7-144">如果已打开文档和列表窗口，单击**刷新**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="09cd7-144">If you already had the Documents and Lists window open, click **Refresh** on the **View** menu.</span></span> <span data-ttu-id="09cd7-145">如果单击了**拒绝**为拒绝步骤 13 中的更改，请确认*\<计算机名称\>*_Outbox 文档库中包含的消息，只需修改。</span><span class="sxs-lookup"><span data-stu-id="09cd7-145">If you clicked **Reject** to reject the changes in step 13, verify that the *\<computer name\>*_Outbox document library contains the message that was just modified.</span></span>
