---
title: 步骤 2： 添加常见架构 v2.3.1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da98fe6c-4776-4cb8-8454-af3128dea4ab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba84c9f45c477aefe7615eca906c40014b06bd04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206509"
---
# <a name="step-2-add-common-schemas-for-v231"></a><span data-ttu-id="c6ec6-102">步骤 2： 添加常见 v2.3.1 架构</span><span class="sxs-lookup"><span data-stu-id="c6ec6-102">Step 2: Add Common Schemas for v2.3.1</span></span>
<span data-ttu-id="c6ec6-103">在此步骤中，你可以创建基于 BTAHL7231Common 项目模板的新项目。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-103">In this step, you create a new project based on the BTAHL7231Common Project template.</span></span> <span data-ttu-id="c6ec6-104">此模板包含三个常见的架构 （适用于数据类型、 线段和表值）， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 用于验证 v2.3.1 消息实例。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-104">This template contains the three common schemas (for data types, segments, and table values) that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses to validate v2.3.1 message instances.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="c6ec6-105">HL7 v2.3.1 架构，包括将使用传入的批处理中的单个消息的架构与结合使用这些常见的架构 (ADT ^ A03)。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-105"> uses these common schemas in conjunction with the HL7 v2.3.1 schemas, including the schema that you will use for the individual messages in the incoming batch (ADT^A03).</span></span>  
  
 <span data-ttu-id="c6ec6-106">在步骤结束时，你的程序集分配强密钥，并部署。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-106">At the end of the step, you assign a strong key to the assembly and deploy.</span></span> <span data-ttu-id="c6ec6-107">无需创建第二个强密钥;你可以使用你在中创建的强密钥[步骤 1： 添加标头和确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-107">You do not have to create a second strong key; you can use the strong key that you created in [Step 1: Add Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).</span></span>  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a><span data-ttu-id="c6ec6-108">若要添加 v2.3.1 公共架构和部署程序集</span><span class="sxs-lookup"><span data-stu-id="c6ec6-108">To add v2.3.1 common schemas and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="c6ec6-109">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-109">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="c6ec6-110">在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-110">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="c6ec6-111">在**模板**部分中，选择**BTAHL7V231Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-111">In the **Templates** section, select **BTAHL7V231Common Project**.</span></span>  
  
4.  <span data-ttu-id="c6ec6-112">在**名称**框中，输入**BTAHL7V231Common 项目**作为项目名称。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-112">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5.  <span data-ttu-id="c6ec6-113">在**解决方案**框中，选择**将添加到解决方案**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-113">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="c6ec6-114">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-114">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6ec6-115">在解决方案资源管理器，三个架构 （datatypes_231.xsd、 segments_231.xsd 和 tablevalues_231.xsd） 包含在项目中。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-115">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7.  <span data-ttu-id="c6ec6-116">在解决方案资源管理器，右键单击**BTAHL7V231Common 项目**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-116">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="c6ec6-117">在 BTAHL7V231Common 属性页对话框中，单击**签名**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-117">On the BTAHL7V231Common Property Pages dialog box, click **Signing**.</span></span>  
  
9. <span data-ttu-id="c6ec6-118">检查**对程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-118">Check **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="c6ec6-119">在选择强名称密钥文件下拉列表中，选择列表中。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-119">In Choose a strong name key file drop down list select.</span></span>  
  
11. <span data-ttu-id="c6ec6-120">浏览到 **: \Batching 教程**，选择**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-120">Browse to **:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="c6ec6-121">右键单击**BTAHL7V231Common**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-121">Right-click **BTAHL7V231Common**, and then click **Deploy**.</span></span> <span data-ttu-id="c6ec6-122">确保输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-122">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6ec6-123">如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="c6ec6-124">继续执行[步骤 3： 添加触发器事件 （消息） 架构](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="c6ec6-124">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>