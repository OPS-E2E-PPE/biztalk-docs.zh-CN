---
title: "处理未分析的消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unparsed messages
- messages, unparsed messages
ms.assetid: c6a67ff3-3295-489f-9d5f-fb35b2bf8b19
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b7683a598169b8ece75788584e8bb9b3c7f4861
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="handling-an-unparsed-message"></a><span data-ttu-id="ebae6-102">处理未分析的消息</span><span class="sxs-lookup"><span data-stu-id="ebae6-102">Handling an Unparsed Message</span></span>
<span data-ttu-id="ebae6-103">本部分介绍如何处理未分析的消息。</span><span class="sxs-lookup"><span data-stu-id="ebae6-103">This section describes how to handle an unparsed message.</span></span> <span data-ttu-id="ebae6-104">与不同的是未通过验证的消息，不能修复一条消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]无法分析。</span><span class="sxs-lookup"><span data-stu-id="ebae6-104">Unlike messages that fail validation, you cannot repair a message that [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] cannot parse.</span></span> <span data-ttu-id="ebae6-105">消息修复和新提交显示消息和分析错误的性质，并允许你打印消息或将其保存到本地文件。</span><span class="sxs-lookup"><span data-stu-id="ebae6-105">Message Repair and New Submission displays the message and the nature of the parsing error, and enables you to print the message or save it to a local file.</span></span> <span data-ttu-id="ebae6-106">然后，你可以警报将邮件发送给分析失败的特定性质的实体。</span><span class="sxs-lookup"><span data-stu-id="ebae6-106">You can then alert the entity that sent the message to the specific nature of the parsing failure.</span></span>  
  
### <a name="to-handle-an-unparsed-message"></a><span data-ttu-id="ebae6-107">以处理未分析的消息</span><span class="sxs-lookup"><span data-stu-id="ebae6-107">To handle an unparsed message</span></span>  
  
1.  <span data-ttu-id="ebae6-108">在 Internet Explorer 中，打开 http://localhost/sites/bassite MRSR 网站。</span><span class="sxs-lookup"><span data-stu-id="ebae6-108">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="ebae6-109">在主页窗口中，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-109">In the Home window, click **Documents**.</span></span>  
  
3.  <span data-ttu-id="ebae6-110">在文档窗口中，在**文档库**，单击**Unparsed**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-110">In the Documents window, under **Document Libraries**, click **Unparsed**.</span></span>  
  
4.  <span data-ttu-id="ebae6-111">在未分析的窗口中，单击**收件箱**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-111">In the Unparsed window, click **Inbox**.</span></span>  
  
5.  <span data-ttu-id="ebae6-112">在未分析的收件箱窗口中，依次指向未不分析，请单击邮件中，右侧的箭头，然后单击的消息**在 Microsoft Office InfoPath 中编辑**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-112">In the Unparsed Inbox window, point to the message that did not parse, click the arrow to the right of the message, and then click **Edit in Microsoft Office InfoPath**.</span></span>  
  
6.  <span data-ttu-id="ebae6-113">在 SWIFT 快捷键窗格中，单击**错误**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-113">In the SWIFT Accelerator pane, click **Errors**.</span></span>  
  
7.  <span data-ttu-id="ebae6-114">在分析和 XML 验证错误窗格中，读取了分析错误。</span><span class="sxs-lookup"><span data-stu-id="ebae6-114">In the Parse and XML Validation Errors pane, read the parse error.</span></span>  
  
8.  <span data-ttu-id="ebae6-115">在未分析消息窗格中，查看消息。</span><span class="sxs-lookup"><span data-stu-id="ebae6-115">In the Unparsed Message pane, review the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebae6-116">如果你想要在上打印消息，在未分析消息窗格中，**文件**菜单上，单击**打印**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-116">If you want to print the message, in the Unparsed Message pane, on the **File** menu, click **Print**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebae6-117">如果你想要将消息保存到本地文件，在未分析消息窗格中，在**文件**菜单上，单击**另存为**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-117">If you want to save the message to a local file, in the Unparsed Message pane, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="ebae6-118">在**另存为**对话框中，在**将保存在**下拉列表中，移动到你想要保存在中，该文件，然后单击的文件夹**确定**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-118">In the **Save As** dialog box, in the **Save in** drop-down list, move to the folder that you want to save the file in, and then click **OK**.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="ebae6-119">以 XML 格式保存消息。</span><span class="sxs-lookup"><span data-stu-id="ebae6-119"> saves the message in XML format.</span></span>  
  
9. <span data-ttu-id="ebae6-120">在未分析消息窗格中，进行必要的更改，然后单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-120">In the Unparsed Message pane, make the necessary changes, and then click **Submit**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebae6-121">无法验证您已修复未分析的消息。</span><span class="sxs-lookup"><span data-stu-id="ebae6-121">You cannot validate an unparsed message that you have repaired.</span></span>  
  
10. <span data-ttu-id="ebae6-122">在提交消息对话框中，单击**接受**要接受的更改提交修复后的消息，请单击**拒绝**以拒绝所做的更改，或单击**取消**取消提交并返回到窗体中。</span><span class="sxs-lookup"><span data-stu-id="ebae6-122">In the Submit Message dialog box, click **Accept** to submit the repaired message with changes accepted, click **Reject** to reject the changes, or click **Cancel** to cancel the submission and return to the form.</span></span>  
  
11. <span data-ttu-id="ebae6-123">如果你单击**接受**或**拒绝**在步骤 11 中，在数字签名向导页上，选择你想要使用表单 （为 repairer 创建的证书），进行签名的证书，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-123">If you clicked **Accept** or **Reject** in step 11, on the Digital Signature Wizard page, select the certificate that you want to use to sign the form (the certificate that you created for the repairer), and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebae6-124">若要验证其有效性的数字签名，请单击**数字签名**上**工具**菜单上，单击你想要验证，，然后单击的数字签名**查看签名的表单**.</span><span class="sxs-lookup"><span data-stu-id="ebae6-124">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebae6-125">执行任何角色的任何用户可以提交它们已修复未分析的消息。</span><span class="sxs-lookup"><span data-stu-id="ebae6-125">Any user performing any role can submit an unparsed message that they have repaired.</span></span>  
  
12. <span data-ttu-id="ebae6-126">在用于输入注释数字签名向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-126">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  
  
13. <span data-ttu-id="ebae6-127">在验证窗体数字签名向导页上，验证将对进行签名的消息正确。</span><span class="sxs-lookup"><span data-stu-id="ebae6-127">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="ebae6-128">单击**查看证书**如果你想要验证是否正在使用正确的签名。</span><span class="sxs-lookup"><span data-stu-id="ebae6-128">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="ebae6-129">单击**我已在签名之前验证此内容**，然后单击**登录**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-129">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
14. <span data-ttu-id="ebae6-130">在验证数字签名窗口中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-130">In the Verify Digital Signature window, click **Close**.</span></span>  
  
15. <span data-ttu-id="ebae6-131">在提交成功对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ebae6-131">In the Submission Success dialog box, click **OK**.</span></span>  
  
16. <span data-ttu-id="ebae6-132">关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。</span><span class="sxs-lookup"><span data-stu-id="ebae6-132">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>