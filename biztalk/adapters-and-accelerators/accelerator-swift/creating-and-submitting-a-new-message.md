---
title: "创建和提交新消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- submitting, messages
- messages, submitting
- messages, creating
ms.assetid: 88b7a2d3-44a4-44e4-ba8c-527c10290925
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42cd2a82fe0ecde75446e68f9f58e17f103e5efa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-submitting-a-new-message"></a><span data-ttu-id="abda4-102">创建和提交新消息</span><span class="sxs-lookup"><span data-stu-id="abda4-102">Creating and Submitting a New Message</span></span>
<span data-ttu-id="abda4-103">本部分介绍如何将提交一条新消息。</span><span class="sxs-lookup"><span data-stu-id="abda4-103">This section describes how to submit a new message.</span></span> <span data-ttu-id="abda4-104">作为提供修复后的消息，一条新消息必须先验证并批准以外的消息创建者的人员。</span><span class="sxs-lookup"><span data-stu-id="abda4-104">As with a repaired message, a new message must be verified and approved by people other than the message creator.</span></span>  
  
 <span data-ttu-id="abda4-105">若要提交新消息，你必须将上载到新 SWIFT 消息文档库你想要提交的消息的类型的消息模板文件。</span><span class="sxs-lookup"><span data-stu-id="abda4-105">To submit a new message, you must upload into the New SWIFT Messages document library a message template file for the type of message that you want to submit.</span></span> <span data-ttu-id="abda4-106">你可以手动上载单个消息模板，也可以上载使用 FormPublish 工具的所有消息模板。</span><span class="sxs-lookup"><span data-stu-id="abda4-106">You can upload a single message template manually, or you can upload all message templates using the FormPublish tool.</span></span>  
  
### <a name="to-upload-a-single-message-template-into-the-new-document-library"></a><span data-ttu-id="abda4-107">若要将单个消息模板上载到新的文档库</span><span class="sxs-lookup"><span data-stu-id="abda4-107">To upload a single message template into the new document library</span></span>  
  
1.  <span data-ttu-id="abda4-108">请参阅部分[窗体生成器实用程序生成 MT/MX InfoPath 窗体](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md)有关的说明。</span><span class="sxs-lookup"><span data-stu-id="abda4-108">Refer to the section [Form Generator Utility to Generate MT/MX InfoPath Forms](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md) for instructions.</span></span>  
  
### <a name="to-create-and-submit-a-new-message"></a><span data-ttu-id="abda4-109">若要创建并提交一条新消息</span><span class="sxs-lookup"><span data-stu-id="abda4-109">To create and submit a new message</span></span>  
  
1.  <span data-ttu-id="abda4-110">在 Internet Explorer 中，打开 http://localhost/sites/bassite MRSR 网站。</span><span class="sxs-lookup"><span data-stu-id="abda4-110">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="abda4-111">单击**文档**，然后单击**新 SWIFT 消息**。</span><span class="sxs-lookup"><span data-stu-id="abda4-111">Click **Documents**, and then click **New SWIFT Messages**.</span></span>  
  
3.  <span data-ttu-id="abda4-112">在新 SWIFT 消息页上，双击包含想要创建的消息类型的类别的名称。</span><span class="sxs-lookup"><span data-stu-id="abda4-112">On the New SWIFT Messages page, double-click the name of the category containing the type of the message that you would like to create.</span></span>  
  
4.  <span data-ttu-id="abda4-113">单击你想要创建的消息的表单模板。</span><span class="sxs-lookup"><span data-stu-id="abda4-113">Click the form template for the message that you want to create.</span></span>  
  
5.  <span data-ttu-id="abda4-114">在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]2007年窗口中的，消息中窗体中，类型 （作为用星号表示） 的所有必填的字段和任何可选字段，你想要使用的消息数据。</span><span class="sxs-lookup"><span data-stu-id="abda4-114">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, in the message form, type message data for all required fields (as denoted by an asterisk) and any optional fields you want to use.</span></span>  
  
6.  <span data-ttu-id="abda4-115">若要查找 BIC、 当前的角色中： 创建窗格中，请单击**BIC 查找**。</span><span class="sxs-lookup"><span data-stu-id="abda4-115">To look up a BIC, in the Current Role: Create pane, click **BIC Lookup**.</span></span>  
  
7.  <span data-ttu-id="abda4-116">键入金融机构、 bank 代码和国家/地区的名称，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="abda4-116">Type the name of the financial institution, the bank code, and the country/region, and then click **Search**.</span></span>  
  
8.  <span data-ttu-id="abda4-117">从 BIC 查找窗格中，将 BIC 复制到消息窗体中的相应的银行代码字段。</span><span class="sxs-lookup"><span data-stu-id="abda4-117">From the BIC Lookup pane, copy the BIC into the appropriate bank code field in the message form.</span></span>  
  
9. <span data-ttu-id="abda4-118">在当前角色： 创建窗格中，请单击**验证**，然后单击**Validate 消息**。</span><span class="sxs-lookup"><span data-stu-id="abda4-118">In the Current Role: Create pane, click **Validation**, and then click **Validate Message**.</span></span>  
  
10. <span data-ttu-id="abda4-119">在结果窗格中的当前角色： 创建窗格中，确定需要在消息中修复的错误。</span><span class="sxs-lookup"><span data-stu-id="abda4-119">In the Results pane of the Current Role: Create pane, determine the errors that you need to fix in the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="abda4-120">如果您没有固定的所有验证错误消息中，你仅可以提交一条新消息。</span><span class="sxs-lookup"><span data-stu-id="abda4-120">You can only submit a new message if you have fixed all validation errors in the message.</span></span>  
  
11. <span data-ttu-id="abda4-121">从窗口顶部标准工具栏中，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="abda4-121">From the Standard toolbar at the top of the window, click **Submit**.</span></span>  
  
12. <span data-ttu-id="abda4-122">在用于选择要对表单进行签名的证书数字签名向导页上，选择你想要使用表单 （你创建的创建者的证书） 进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="abda4-122">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the creator).</span></span> <span data-ttu-id="abda4-123">单击**查看证书**如果你想要验证是否正在使用正确的签名。</span><span class="sxs-lookup"><span data-stu-id="abda4-123">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="abda4-124">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="abda4-124">Click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="abda4-125">若要验证其有效性的数字签名，请单击**数字签名**上**工具**菜单上，单击你想要验证，，然后单击的数字签名**查看签名的表单**.</span><span class="sxs-lookup"><span data-stu-id="abda4-125">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  
  
13. <span data-ttu-id="abda4-126">在用于输入注释数字签名向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="abda4-126">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  
  
14. <span data-ttu-id="abda4-127">在验证窗体数字签名向导页上，验证将对进行签名的消息正确。</span><span class="sxs-lookup"><span data-stu-id="abda4-127">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="abda4-128">单击**查看证书**如果你想要验证是否正在使用正确的签名。</span><span class="sxs-lookup"><span data-stu-id="abda4-128">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="abda4-129">单击**我已在签名之前验证此内容**，然后单击**登录**。</span><span class="sxs-lookup"><span data-stu-id="abda4-129">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
15. <span data-ttu-id="abda4-130">在验证数字签名窗口中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="abda4-130">In the Verify Digital Signature window, click **Close**.</span></span>  
  
16. <span data-ttu-id="abda4-131">在提交成功对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="abda4-131">In the Submission Success dialog box, click **OK**.</span></span>  
  
17. <span data-ttu-id="abda4-132">关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。</span><span class="sxs-lookup"><span data-stu-id="abda4-132">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>