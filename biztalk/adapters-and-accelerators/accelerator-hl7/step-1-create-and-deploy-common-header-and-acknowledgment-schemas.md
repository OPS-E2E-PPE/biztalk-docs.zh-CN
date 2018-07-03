---
title: 步骤 1： 创建和部署通用标头及确认架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, headers
ms.assetid: e0f11f58-9a8c-4567-a537-3d182fa7dce2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 988c2922d09412aa248c08c36e727709d45e5a66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989262"
---
# <a name="step-1-create-and-deploy-common-header-and-acknowledgment-schemas"></a><span data-ttu-id="0c085-102">步骤 1： 创建和部署通用标头及确认架构</span><span class="sxs-lookup"><span data-stu-id="0c085-102">Step 1: Create and Deploy Common Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="0c085-103">使用标头架构来验证消息实例的标头 （MSH 段）。</span><span class="sxs-lookup"><span data-stu-id="0c085-103">You use the header schema to validate the header (MSH segment) of the message instance.</span></span> <span data-ttu-id="0c085-104">使用确认架构生成的确认消息实例。</span><span class="sxs-lookup"><span data-stu-id="0c085-104">You use the acknowledgment schema to generate the acknowledgment for the message instance.</span></span> <span data-ttu-id="0c085-105">此过程是通用于所有 HL7 架构版本。</span><span class="sxs-lookup"><span data-stu-id="0c085-105">This process is common across all HL7 schema versions.</span></span>  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a><span data-ttu-id="0c085-106">若要创建的标头和确认架构</span><span class="sxs-lookup"><span data-stu-id="0c085-106">To create the header and acknowledgment schemas</span></span>  
  
1. <span data-ttu-id="0c085-107">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="0c085-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2. <span data-ttu-id="0c085-108">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="0c085-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="0c085-109">在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="0c085-109">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
4. <span data-ttu-id="0c085-110">在中**模板**列表中，选择**BTAHL7V2XCommon 项目**。</span><span class="sxs-lookup"><span data-stu-id="0c085-110">In the **Templates** list, select **BTAHL7V2XCommon Project**.</span></span>  
  
5. <span data-ttu-id="0c085-111">在中**名称**字段中，键入**Interrogative_2XSchemas**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0c085-111">In the **Name** field, type **Interrogative_2XSchemas**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="0c085-112">在解决方案资源管理器，请注意，在项目中包含三个架构 （ACK_24_GLO_DEF.xsd、 ACK_25_GLO_DEF.xsd 和 MSH_25_GLO_DEF.xsd）。</span><span class="sxs-lookup"><span data-stu-id="0c085-112">In Solution Explorer, notice that three schemas (ACK_24_GLO_DEF.xsd, ACK_25_GLO_DEF.xsd, and MSH_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
    <span data-ttu-id="0c085-113">Visual Studio 保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="0c085-113">Leave Visual Studio open.</span></span>  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="0c085-114">步骤 1A： 对程序集分配强密钥并将其部署</span><span class="sxs-lookup"><span data-stu-id="0c085-114">Step 1A: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="0c085-115">使用以下过程来对程序集分配强密钥并随后部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="0c085-115">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="0c085-116">若要分配一个强密钥并将其部署该程序集</span><span class="sxs-lookup"><span data-stu-id="0c085-116">To assign a strong key and deploy the assembly</span></span>  
  
1. <span data-ttu-id="0c085-117">启动**Visual Studio 2012 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="0c085-117">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2. <span data-ttu-id="0c085-118">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符下，将目录切换到\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\Interrogative 的快捷键Tutorial 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c085-118">At the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, change your directory to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder.</span></span>  
  
3. <span data-ttu-id="0c085-119">在命令提示符处，键入**sn – k key.snk**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="0c085-119">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="0c085-120">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="0c085-120">Ensure that a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0c085-121">如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决您的程序集。</span><span class="sxs-lookup"><span data-stu-id="0c085-121">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="0c085-122">在解决方案资源管理器中右键单击**Interrogative_2XSchemas**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0c085-122">In Solution Explorer, right-click **Interrogative_2XSchemas** project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="0c085-123">在 Interrogative_2XSchemas 属性页对话框中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="0c085-123">In the Interrogative_2XSchemas Property Pages dialog box, click **Assembly**.</span></span>  
  
6. <span data-ttu-id="0c085-124">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="0c085-124">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7. <span data-ttu-id="0c085-125">在程序集密钥文件对话框中，浏览到\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator HL7\SDK\Interrogative 教程中，单击**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="0c085-125">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
8. <span data-ttu-id="0c085-126">在 Interrogative_2XSchemas 属性页对话框中，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="0c085-126">In the Interrogative_2XSchemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
9. <span data-ttu-id="0c085-127">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**Interrogative_2XSchemas**项目，然后依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="0c085-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **Interrogative_2XSchemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="0c085-128">请确保在输出窗口中将显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="0c085-128">Ensure a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0c085-129">如果未显示正确的部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]若要排查部署问题。</span><span class="sxs-lookup"><span data-stu-id="0c085-129">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
   <span data-ttu-id="0c085-130">请继续执行[步骤 2： 创建适用于 V2.4 的通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)。</span><span class="sxs-lookup"><span data-stu-id="0c085-130">Proceed to [Step 2: Create Common Schemas for V2.4](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md).</span></span>