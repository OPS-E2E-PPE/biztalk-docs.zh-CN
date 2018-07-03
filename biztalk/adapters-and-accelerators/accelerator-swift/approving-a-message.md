---
title: 审核消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c565f40c6c455456101521414edf0c377411014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967102"
---
# <a name="approving-a-message"></a><span data-ttu-id="016e5-102">审核消息</span><span class="sxs-lookup"><span data-stu-id="016e5-102">Approving a Message</span></span>
<span data-ttu-id="016e5-103">本部分描述如何批准一条消息，已修复和验证。</span><span class="sxs-lookup"><span data-stu-id="016e5-103">This section describes how to approve a message that has been repaired and verified.</span></span>  

### <a name="to-approve-a-message"></a><span data-ttu-id="016e5-104">若要批准一条消息</span><span class="sxs-lookup"><span data-stu-id="016e5-104">To approve a message</span></span>  

1. <span data-ttu-id="016e5-105">在 Internet Explorer 中，打开你的 MRSR 站点置于http://localhost/sites/bassite。</span><span class="sxs-lookup"><span data-stu-id="016e5-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="016e5-106">在主页窗口中，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="016e5-106">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="016e5-107">在文档窗口中下,**文档库**，单击 **\<*部门名称*\>_Approver**。</span><span class="sxs-lookup"><span data-stu-id="016e5-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>_Approver**.</span></span>  

4. <span data-ttu-id="016e5-108">在中\<部门名称\>_Approver 窗口中，单击**收件箱**。</span><span class="sxs-lookup"><span data-stu-id="016e5-108">In the \<Department name\>_Approver window, click **Inbox**.</span></span>  

5. <span data-ttu-id="016e5-109">在收件箱窗口中，指向的消息的标题，单击消息标题右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。</span><span class="sxs-lookup"><span data-stu-id="016e5-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="016e5-110">SWIFT 加速器窗格中的[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**错误**。</span><span class="sxs-lookup"><span data-stu-id="016e5-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Errors**.</span></span> <span data-ttu-id="016e5-111">查看任何错误中所示**分析和 XML 验证错误**框中， **BRE 验证错误**框中，并且**运行时错误**框。</span><span class="sxs-lookup"><span data-stu-id="016e5-111">Review any errors shown in the **Parse and XML Validation Errors** box, the **BRE Validation Errors** box, and the **Runtime Errors** box.</span></span>  

7. <span data-ttu-id="016e5-112">在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到错误的位置并验证是否已更正错误。</span><span class="sxs-lookup"><span data-stu-id="016e5-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error and verify that the error has been corrected.</span></span> <span data-ttu-id="016e5-113">可以看到原始错误已通过单击**错误**中当前的角色： 批准窗格中，并在其中一个错误窗格中查看该错误。</span><span class="sxs-lookup"><span data-stu-id="016e5-113">You can see what the original error was by clicking **Errors** in the Current Role: Approve pane, and viewing the error in one of the error panes.</span></span> <span data-ttu-id="016e5-114">此外可以通过单击比较消息的修复和已修复版本**消息的详细信息**中当前的角色： 批准窗格。</span><span class="sxs-lookup"><span data-stu-id="016e5-114">You can also compare the unrepaired and repaired versions of the message by clicking **Message Details** in the Current Role: Approve pane.</span></span>  

8. <span data-ttu-id="016e5-115">若要确保将验证该消息，请单击**验证**当前角色中： 批准窗格中，然后依次**验证消息**。</span><span class="sxs-lookup"><span data-stu-id="016e5-115">To ensure that the message will validate, click **Validation** in the Current Role: Approve pane, and then click **Validate Message**.</span></span> <span data-ttu-id="016e5-116">验证结果窗格中显示消息**该消息是否有效**。</span><span class="sxs-lookup"><span data-stu-id="016e5-116">Verify that the Results pane displays the message **The message is valid**.</span></span>  

9. <span data-ttu-id="016e5-117">如果已对该文档中的更改批准[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="016e5-117">If you approve of the changes that have been made to the document, in the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="016e5-118">当您单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。</span><span class="sxs-lookup"><span data-stu-id="016e5-118">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="016e5-119">如果验证不成功，必须修复验证错误，然后继续。</span><span class="sxs-lookup"><span data-stu-id="016e5-119">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  

10. <span data-ttu-id="016e5-120">在提交消息对话框中，单击**接受**提交已批准的消息与接受更改。</span><span class="sxs-lookup"><span data-stu-id="016e5-120">In the Submit Message dialog box, click **Accept** to submit the approved message with changes accepted.</span></span> <span data-ttu-id="016e5-121">单击**拒绝**可以将消息提交已拒绝的更改。</span><span class="sxs-lookup"><span data-stu-id="016e5-121">Click **Reject** to submit the message with changes rejected.</span></span> <span data-ttu-id="016e5-122">单击**取消**取消提交并返回到该表单。</span><span class="sxs-lookup"><span data-stu-id="016e5-122">Click **Cancel** to cancel the submission and return to the form.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="016e5-123">如果接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。</span><span class="sxs-lookup"><span data-stu-id="016e5-123">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="016e5-124">如果拒绝消息更改，则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]该消息返回给工作流的第一个阶段 （创建或修复） 并将重置修复工作流。</span><span class="sxs-lookup"><span data-stu-id="016e5-124">If you reject the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] returns the message to the first stage of the workflow (create or repair) and resets the repair workflow.</span></span>  

11. <span data-ttu-id="016e5-125">在用于选择证书来签署该窗体数字签名向导页上，选择你想要使用表单 （为审批者创建的证书） 进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="016e5-125">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the approver).</span></span> <span data-ttu-id="016e5-126">单击**查看证书**如果你想要验证是否使用正确的签名。</span><span class="sxs-lookup"><span data-stu-id="016e5-126">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="016e5-127">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="016e5-127">Click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="016e5-128">若要验证数字签名的有效性，请单击**数字签名**上**工具**菜单中，单击你想要验证，，然后单击的数字签名**查看签名窗体**.</span><span class="sxs-lookup"><span data-stu-id="016e5-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span> <span data-ttu-id="016e5-129">您还可以查看哪些角色已签名的表单之前 （窗体进行签名者必须一次每个工作流） 通过单击**数字签名**上**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="016e5-129">You can also see which roles have signed the form previously (a form can only be signed by a person once per workflow) by clicking **Digital Signatures** on the **Tools** menu.</span></span> <span data-ttu-id="016e5-130">如果需要添加此角色的另一个签名，此，请在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="016e5-130">If you need to add another signature for this role, do so in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console.</span></span>  

12. <span data-ttu-id="016e5-131">在用于输入注释数字签名向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="016e5-131">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  

13. <span data-ttu-id="016e5-132">在验证窗体数字签名向导页上，验证签名的消息正确。</span><span class="sxs-lookup"><span data-stu-id="016e5-132">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="016e5-133">单击**查看证书**如果你想要验证是否使用正确的签名。</span><span class="sxs-lookup"><span data-stu-id="016e5-133">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="016e5-134">单击**我已在签名之前验证此内容**，然后单击**登录**。</span><span class="sxs-lookup"><span data-stu-id="016e5-134">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

14. <span data-ttu-id="016e5-135">在验证数字签名窗口中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="016e5-135">In the Verify Digital Signature window, click **Close**.</span></span>  

15. <span data-ttu-id="016e5-136">在提交成功对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="016e5-136">In the Submission Success dialog box, click **OK**.</span></span>  

16. <span data-ttu-id="016e5-137">关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。</span><span class="sxs-lookup"><span data-stu-id="016e5-137">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  

17. <span data-ttu-id="016e5-138">在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，打开设置以接收所发送的消息的文件夹。</span><span class="sxs-lookup"><span data-stu-id="016e5-138">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, open the folder that you set up to receive sent messages.</span></span> <span data-ttu-id="016e5-139">验证该文件夹包含已批准的消息。</span><span class="sxs-lookup"><span data-stu-id="016e5-139">Verify that the folder contains the approved message.</span></span> <span data-ttu-id="016e5-140">若要验证已修复消息的文本编辑器中打开的邮件。</span><span class="sxs-lookup"><span data-stu-id="016e5-140">Open the message in a text editor to verify that the message has been repaired.</span></span>
