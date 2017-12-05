---
title: "步骤 1： 创建和部署标头和确认架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, header schemas
- header schemas
ms.assetid: 3ff013a4-6c67-4bac-be97-81b2dc5b6119
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9ffa8ab8d80a8b2da172378349eb9761a728fb7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-create-and-deploy-header-and-acknowledgment-schemas"></a><span data-ttu-id="67b8e-102">步骤 1： 创建和部署标头和确认架构</span><span class="sxs-lookup"><span data-stu-id="67b8e-102">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="67b8e-103">使用标头架构来验证消息实例的标头 （MSH 段）。</span><span class="sxs-lookup"><span data-stu-id="67b8e-103">You use the header schema to validate the header (MSH segment) of the message instance.</span></span> <span data-ttu-id="67b8e-104">确认架构用于生成消息实例确认。</span><span class="sxs-lookup"><span data-stu-id="67b8e-104">You use the acknowledgment schema to generate the acknowledgment for the message instance.</span></span> <span data-ttu-id="67b8e-105">此过程能够在之间通用的所有架构版本[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。</span><span class="sxs-lookup"><span data-stu-id="67b8e-105">This process is common across all schemas versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a><span data-ttu-id="67b8e-106">若要创建的标头和确认的架构</span><span class="sxs-lookup"><span data-stu-id="67b8e-106">To create the header and acknowledgment schemas</span></span>  
  
1.  <span data-ttu-id="67b8e-107">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="67b8e-108">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="67b8e-109">在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-109">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
4.  <span data-ttu-id="67b8e-110">在模板部分中，选择**BTAHL7V2XCommon 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-110">In the Templates section, select **BTAHL7V2XCommon Project**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="67b8e-111">在解决方案资源管理器，请注意，在项目中包含的三个架构 （ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd 和 MSH_25_GLO_DEF.xsd）。</span><span class="sxs-lookup"><span data-stu-id="67b8e-111">In Solution Explorer, notice that the three schemas (ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd, and MSH_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="67b8e-112">步骤 1A： 向程序集分配强密钥和部署</span><span class="sxs-lookup"><span data-stu-id="67b8e-112">Step 1A: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="67b8e-113">使用以下过程向程序集分配强密钥，然后将部署程序集。</span><span class="sxs-lookup"><span data-stu-id="67b8e-113">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="67b8e-114">分配一个强密钥和部署程序集</span><span class="sxs-lookup"><span data-stu-id="67b8e-114">To assign a strong key and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="67b8e-115">启动**Visual Studio 2012 的命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-115">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="67b8e-116">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符处，浏览到\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>Accelerator for HL7 \SDK\端到端教程文件夹。</span><span class="sxs-lookup"><span data-stu-id="67b8e-116">At the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for HL7 \SDK\End-to-End Tutorial folder.</span></span>  
  
3.  <span data-ttu-id="67b8e-117">在命令提示符处，键入**sn-k key.snk**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="67b8e-117">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="67b8e-118">确保以下成功消息显示在输出窗口，然后关闭命令窗口。</span><span class="sxs-lookup"><span data-stu-id="67b8e-118">Ensure the following success message appears in the output window, and then close the command window.</span></span>  
  
     <span data-ttu-id="67b8e-119">**"密钥对写入到命名为 key.snk。"**</span><span class="sxs-lookup"><span data-stu-id="67b8e-119">**"Key pair written to key.snk."**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67b8e-120">如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]进行故障排除程序集。</span><span class="sxs-lookup"><span data-stu-id="67b8e-120">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4.  <span data-ttu-id="67b8e-121">在解决方案资源管理器，右键单击**BTAHL7V2XCommon Project1**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-121">In Solution Explorer, right-click **BTAHL7V2XCommon Project1**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="67b8e-122">在 BTAHL7V2XCommon Project1 属性页页上，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-122">On the BTAHL7V2XCommon Project1 Property Pages page, click **Assembly**.</span></span>  
  
6.  <span data-ttu-id="67b8e-123">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="67b8e-123">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
7.  <span data-ttu-id="67b8e-124">在程序集密钥文件对话框中，浏览到\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>HL7\SDK\End 端到端的快捷键教程，选择**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-124">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="67b8e-125">在 BTAHL7V2XCommon 项目属性页上，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="67b8e-125">On the BTAHL7V2XCommon Project Property page, click **OK** to save your changes.</span></span>  
  
9. <span data-ttu-id="67b8e-126">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]中**解决方案资源管理器**，右键单击**BTAHL7V2XCommon 项目**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="67b8e-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in **Solution Explorer**, right-click **BTAHL7V2XCommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="67b8e-127">确保输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="67b8e-127">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67b8e-128">如果未显示正确部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来排查你的部署。</span><span class="sxs-lookup"><span data-stu-id="67b8e-128">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
 <span data-ttu-id="67b8e-129">继续执行[步骤 2： 为 V2.3.1 创建通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)。</span><span class="sxs-lookup"><span data-stu-id="67b8e-129">Proceed to [Step 2: Create Common Schemas for V2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md).</span></span>