---
title: 第 2 步：添加适用于 v2.3.1 的通用架构 |Microsoft Docs
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
ms.openlocfilehash: 772b38911ee2f6896588909cb4ae9a6f33cb42b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288835"
---
# <a name="step-2-add-common-schemas-for-v231"></a><span data-ttu-id="49098-102">第 2 步：添加适用于 v2.3.1 的通用架构</span><span class="sxs-lookup"><span data-stu-id="49098-102">Step 2: Add Common Schemas for v2.3.1</span></span>
<span data-ttu-id="49098-103">在此步骤中，你创建基于 BTAHL7231Common 项目模板的新项目。</span><span class="sxs-lookup"><span data-stu-id="49098-103">In this step, you create a new project based on the BTAHL7231Common Project template.</span></span> <span data-ttu-id="49098-104">此模板包含的三个常见架构 （适用于数据类型、 段，以及表值） 的 Microsoft BizTalk Accelerator HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 用来验证适用于版本 v2.3.1 消息实例。</span><span class="sxs-lookup"><span data-stu-id="49098-104">This template contains the three common schemas (for data types, segments, and table values) that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses to validate v2.3.1 message instances.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="49098-105">HL7 适用于版本 v2.3.1 架构，包括将使用传入的批中的单个消息的架构与结合使用这些常见的架构 (ADT ^ A03)。</span><span class="sxs-lookup"><span data-stu-id="49098-105">uses these common schemas in conjunction with the HL7 v2.3.1 schemas, including the schema that you will use for the individual messages in the incoming batch (ADT^A03).</span></span>  
  
 <span data-ttu-id="49098-106">在此步骤结束时，对程序集分配强密钥和部署。</span><span class="sxs-lookup"><span data-stu-id="49098-106">At the end of the step, you assign a strong key to the assembly and deploy.</span></span> <span data-ttu-id="49098-107">不需要创建第二个强密钥;可以使用你在中创建的强密钥[步骤 1:添加标头及确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="49098-107">You do not have to create a second strong key; you can use the strong key that you created in [Step 1: Add Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md).</span></span>  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a><span data-ttu-id="49098-108">若要添加适用于版本 v2.3.1 的通用架构并将其部署该程序集</span><span class="sxs-lookup"><span data-stu-id="49098-108">To add v2.3.1 common schemas and deploy the assembly</span></span>  
  
1. <span data-ttu-id="49098-109">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="49098-109">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="49098-110">在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="49098-110">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="49098-111">在中**模板**部分中，选择**BTAHL7V231Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="49098-111">In the **Templates** section, select **BTAHL7V231Common Project**.</span></span>  
  
4. <span data-ttu-id="49098-112">在中**名称**框中，输入**BTAHL7V231Common 项目**作为项目名称。</span><span class="sxs-lookup"><span data-stu-id="49098-112">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5. <span data-ttu-id="49098-113">在中**解决方案**框中，选择**将添加到解决方案**。</span><span class="sxs-lookup"><span data-stu-id="49098-113">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6. <span data-ttu-id="49098-114">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="49098-114">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="49098-115">在解决方案资源管理器，在项目中包括三个架构 （datatypes_231.xsd、 segments_231.xsd 和 tablevalues_231.xsd）。</span><span class="sxs-lookup"><span data-stu-id="49098-115">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7. <span data-ttu-id="49098-116">在解决方案资源管理器中右键单击**BTAHL7V231Common 项目**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="49098-116">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="49098-117">在 BTAHL7V231Common 属性页对话框中，单击**签名**。</span><span class="sxs-lookup"><span data-stu-id="49098-117">On the BTAHL7V231Common Property Pages dialog box, click **Signing**.</span></span>  
  
9. <span data-ttu-id="49098-118">检查**为程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="49098-118">Check **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="49098-119">在选择强名称密钥文件下拉列表中，选择列表中。</span><span class="sxs-lookup"><span data-stu-id="49098-119">In Choose a strong name key file drop down list select.</span></span>  
  
11. <span data-ttu-id="49098-120">浏览到 **: \Batching 教程**，选择**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="49098-120">Browse to **:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="49098-121">右键单击**BTAHL7V231Common**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="49098-121">Right-click **BTAHL7V231Common**, and then click **Deploy**.</span></span> <span data-ttu-id="49098-122">请确保在输出窗口中将显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="49098-122">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49098-123">如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决您的架构。</span><span class="sxs-lookup"><span data-stu-id="49098-123">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
    <span data-ttu-id="49098-124">请继续执行[步骤 3:添加触发器事件 （消息） 架构](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="49098-124">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>