---
title: 步骤 1： 添加标头及确认架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0712e2ee4498b8f6f2eb8cb9527aa8ee8e4582
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011296"
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="b26fd-102">步骤 1： 添加标头及确认架构</span><span class="sxs-lookup"><span data-stu-id="b26fd-102">Step 1: Add Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="b26fd-103">在此步骤中，你创建基于 BTAHL72XCommon 项目模板的新项目。</span><span class="sxs-lookup"><span data-stu-id="b26fd-103">In this step, you create a new project based on the BTAHL72XCommon Project template.</span></span> <span data-ttu-id="b26fd-104">此模板包含消息标头 (MSH_25_GLO_DEF.xsd) 和确认 (ACK_24_GLO_DEF.xsd) 的三个常见架构和 (ACK_25_GLO_DEF.xsd)。</span><span class="sxs-lookup"><span data-stu-id="b26fd-104">This template contains the three common schemas for message headers (MSH_25_GLO_DEF.xsd) and acknowledgments (ACK_24_GLO_DEF.xsd) and (ACK_25_GLO_DEF.xsd).</span></span> <span data-ttu-id="b26fd-105">您必须包括这些架构在项目中因此该 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 生成和/或正确验证消息标头和确认。</span><span class="sxs-lookup"><span data-stu-id="b26fd-105">You must include these schemas in a project so that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) builds and/or validates the message headers and acknowledgments correctly.</span></span> <span data-ttu-id="b26fd-106">此过程是通用于所有架构版本[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。</span><span class="sxs-lookup"><span data-stu-id="b26fd-106">This process is common across all schema versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
 <span data-ttu-id="b26fd-107">你还创建强密钥，将其分配给该程序集，并随后部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="b26fd-107">You also create a strong key, assign it to the assembly, and then deploy the assembly.</span></span> <span data-ttu-id="b26fd-108">强密钥提供安全和标识了程序集，并且部署所需的。</span><span class="sxs-lookup"><span data-stu-id="b26fd-108">The strong key provides security and identity to the assembly, and is necessary for deployment.</span></span> <span data-ttu-id="b26fd-109">在部署程序集时，它存储在配置数据库 （也称为 BizTalk 管理数据库） 和全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="b26fd-109">When you deploy the assembly, it is stored in the Configuration database (also known as the BizTalk Management database) and the global assembly cache (GAC).</span></span>  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a><span data-ttu-id="b26fd-110">若要创建项目并添加标头和确认架构</span><span class="sxs-lookup"><span data-stu-id="b26fd-110">To create the project and add header and acknowledgment schemas</span></span>  
  
1. <span data-ttu-id="b26fd-111">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-111">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="b26fd-112">在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后单击**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-112">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="b26fd-113">在中**模板**列表中，单击**BTAHL7V2XCommon 项目**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-113">In the **Templates** list, click **BTAHL7V2XCommon Project**.</span></span>  
  
4. <span data-ttu-id="b26fd-114">在中**名称**框中，键入**BTAHL7V2XCommon**作为项目名称。</span><span class="sxs-lookup"><span data-stu-id="b26fd-114">In the **Name** box, type **BTAHL7V2XCommon** as the project name.</span></span>  
  
5. <span data-ttu-id="b26fd-115">在中**位置**框中，浏览到**\<**<em>驱动器</em>**:\>\Batching 教程**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-115">In the **Location** box, browse to **\<**<em>drive</em>**:\>\Batching Tutorial**.</span></span>  
  
6. <span data-ttu-id="b26fd-116">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b26fd-116">Click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b26fd-117">在解决方案资源管理器，在项目中包括三个架构 （MSH_25_GLO_DEF.xsd、 ACK_24_GLO_DEF.xsd 和 ACK_25_GLO_DEF.xsd）。</span><span class="sxs-lookup"><span data-stu-id="b26fd-117">In Solution Explorer, three schemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd, and ACK_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="b26fd-118">若要对程序集分配强密钥并将其部署</span><span class="sxs-lookup"><span data-stu-id="b26fd-118">To assign a strong key to the assembly and deploy</span></span>  
  
1. <span data-ttu-id="b26fd-119">打开**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-119">Open **Visual Studio Command Prompt**.</span></span>  
  
2. <span data-ttu-id="b26fd-120">上[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符下，浏览到**\<**<em>驱动器</em>**\>: \Batching 教程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="b26fd-120">On the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the **\<**<em>drive</em>**\>:\Batching Tutorial** folder.</span></span>  
  
3. <span data-ttu-id="b26fd-121">在命令提示符处，键入**sn – k key.snk**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="b26fd-121">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="b26fd-122">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="b26fd-122">Ensure that a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b26fd-123">如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决您的程序集。</span><span class="sxs-lookup"><span data-stu-id="b26fd-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="b26fd-124">在解决方案资源管理器中右键单击**BTAHL7V2Xcommon 项目**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-124">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="b26fd-125">在中**BTAHL7V2XCommon 项目属性页**对话框中，单击**签名**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-125">In the **BTAHL7V2XCommon Project Property Page** dialog box, click **Signing**.</span></span>  
  
6. <span data-ttu-id="b26fd-126">检查**为程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="b26fd-126">Check **Sign the assembly** check box.</span></span>  
  
7. <span data-ttu-id="b26fd-127">在中**选择强名称**密钥文件下拉列表中，选择**\<浏览...\>**.</span><span class="sxs-lookup"><span data-stu-id="b26fd-127">In **Choose a Strong name** key file drop down list select **\<Browse…\>**.</span></span>  
  
8. <span data-ttu-id="b26fd-128">浏览到\<*驱动器*\>: \Batching 教程中，选择**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-128">Browse to \<*drive*\>:\Batching Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="b26fd-129">在 BTAHL7V2XCommon 项目属性页窗口中，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b26fd-129">In the BTAHL7V2XCommon Project Property Pages window, click **OK** to save your changes.</span></span>  
  
10. <span data-ttu-id="b26fd-130">在解决方案资源管理器中右键单击**BTAHL7V2Xcommon 项目**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="b26fd-130">In Solution Explorer, right-click **BTAHL7V2Xcommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="b26fd-131">请确保在输出窗口中将显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="b26fd-131">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b26fd-132">如果未显示正确的部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]若要排查部署问题。</span><span class="sxs-lookup"><span data-stu-id="b26fd-132">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
    <span data-ttu-id="b26fd-133">请继续执行[步骤 2： 添加适用于 v2.3.1 的通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)。</span><span class="sxs-lookup"><span data-stu-id="b26fd-133">Proceed to [Step 2: Add Common Schemas for v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).</span></span>