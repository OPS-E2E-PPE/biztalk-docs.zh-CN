---
title: 第 2 步：创建一个新项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- message enrichment tutorial, projects
ms.assetid: 6e994845-53b8-4de8-a64f-32d36f7b5412
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4147db9f24855a340ed616a794e2ee05822e24e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288765"
---
# <a name="step-2-create-a-new-project"></a><span data-ttu-id="31e52-102">第 2 步：创建一个新项目</span><span class="sxs-lookup"><span data-stu-id="31e52-102">Step 2: Create a New Project</span></span>
<span data-ttu-id="31e52-103">在此步骤中，您生成一个新的解决方案通过使用 Microsoft[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="31e52-103">In this step, you build a new solution by using the Microsoft [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] environment.</span></span> <span data-ttu-id="31e52-104">首先，您创建新项目 (BTAHL7V22Common) 包含三个常见 （适用于数据类型、 段，以及表值） 使用架构的 HL7 V2.2 架构，包括将用于传出的 HL7 消息架构。</span><span class="sxs-lookup"><span data-stu-id="31e52-104">First, you create a new project (BTAHL7V22Common) that contains the three common schemas (for data types, segments, and table values) that the HL7 V2.2 schemas use, including the schema that you will use for the outgoing HL7 message.</span></span> <span data-ttu-id="31e52-105">其次，将生成另一个新包含用于 HL7 消息 (MSH_25_GLO_DEF) 中的标头的通用标准架构的项目 (BTAHL7V2XCommon)。</span><span class="sxs-lookup"><span data-stu-id="31e52-105">Second, you build another new project (BTAHL7V2XCommon) that contains the common standard schema used for headers in HL7 messages (MSH_25_GLO_DEF).</span></span>  
  
### <a name="to-create-a-new-project"></a><span data-ttu-id="31e52-106">创建新项目的步骤</span><span class="sxs-lookup"><span data-stu-id="31e52-106">To create a new project</span></span>  
  
1. <span data-ttu-id="31e52-107">启动**Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="31e52-107">Start **Visual Studio**.</span></span>  
  
2. <span data-ttu-id="31e52-108">在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="31e52-108">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="31e52-109">在新建项目对话框中，展开**BizTalk 项目**文件夹，，然后单击**BTAHL7Projects**文件夹。</span><span class="sxs-lookup"><span data-stu-id="31e52-109">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  
  
4. <span data-ttu-id="31e52-110">在中**模板**窗格中，单击**BTAHL7V22Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="31e52-110">In the **Templates** pane, click **BTAHL7V22Common Project**.</span></span>  
  
5. <span data-ttu-id="31e52-111">在中**名称**字段中，键入**BTAHL7V22Common**作为项目名称。</span><span class="sxs-lookup"><span data-stu-id="31e52-111">In the **Name** field, type **BTAHL7V22Common** as the project name.</span></span>  
  
6. <span data-ttu-id="31e52-112">在中**位置**字段中，键入*\<驱动器\>* \* *:\Tutorial*\* 作为路径，然后单击**确定**打开新项目。</span><span class="sxs-lookup"><span data-stu-id="31e52-112">In the **Location** field, type *\<drive\>\*\*\*:\Tutorial*\* as the path, and then click **OK** to open the new project.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="31e52-113">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 添加到解决方案资源管理器的新项目具有三个常见的架构：</span><span class="sxs-lookup"><span data-stu-id="31e52-113">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) adds a new project to Solution Explorer with the three common schemas:</span></span>  
  
   - <span data-ttu-id="31e52-114">datatypes_22.xsd</span><span class="sxs-lookup"><span data-stu-id="31e52-114">datatypes_22.xsd</span></span>  
  
   - <span data-ttu-id="31e52-115">segments_22.xsd</span><span class="sxs-lookup"><span data-stu-id="31e52-115">segments_22.xsd</span></span>  
  
   - <span data-ttu-id="31e52-116">tablevalues_22.xsd</span><span class="sxs-lookup"><span data-stu-id="31e52-116">tablevalues_22.xsd</span></span>  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] <span data-ttu-id="31e52-117">创建项目文件夹和文件中\<*驱动器*\>: \Tutorial\BTAHL7V22Common 文件夹。</span><span class="sxs-lookup"><span data-stu-id="31e52-117">creates the project folder and files in the \<*drive*\>:\Tutorial\BTAHL7V22Common folder.</span></span>  
  
7. <span data-ttu-id="31e52-118">在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="31e52-118">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
8. <span data-ttu-id="31e52-119">在新建项目对话框中，展开**BizTalk 项目**文件夹，，然后单击**BTAHL7Projects**文件夹。</span><span class="sxs-lookup"><span data-stu-id="31e52-119">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  
  
9. <span data-ttu-id="31e52-120">在中**模板**窗格中，单击**BTAHL7V2XCommon 项目**。</span><span class="sxs-lookup"><span data-stu-id="31e52-120">In the **Templates** pane, click **BTAHL7V2XCommon Project**.</span></span>  
  
10. <span data-ttu-id="31e52-121">在中**名称**字段中，键入**BTAHL7V2XCommon**作为项目名称。</span><span class="sxs-lookup"><span data-stu-id="31e52-121">In the **Name** field, type **BTAHL7V2XCommon** as the project name.</span></span>  
  
11. <span data-ttu-id="31e52-122">在中**位置**字段中，键入*\<驱动器\>* \* *:\Tutorial*\* 作为路径。</span><span class="sxs-lookup"><span data-stu-id="31e52-122">In the **Location** field, type *\<drive\>\*\*\*:\Tutorial*\* as the path.</span></span>  
  
12. <span data-ttu-id="31e52-123">在中**解决方案**字段中，选择**将添加到解决方案**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="31e52-123">In the **Solution** field, select **Add to Solution**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="31e52-124">将新项目添加到解决方案资源管理器中，具有以下架构：</span><span class="sxs-lookup"><span data-stu-id="31e52-124">adds a new project to Solution Explorer with the following schemas:</span></span>  
  
    - <span data-ttu-id="31e52-125">ACK_24_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="31e52-125">ACK_24_GLO_DEF.xsd</span></span>  
  
    - <span data-ttu-id="31e52-126">ACK_25_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="31e52-126">ACK_25_GLO_DEF.xsd</span></span>  
  
    - <span data-ttu-id="31e52-127">MSH_25_GLO_DEF.xsd</span><span class="sxs-lookup"><span data-stu-id="31e52-127">MSH_25_GLO_DEF.xsd</span></span>  
  
      [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] <span data-ttu-id="31e52-128">创建项目文件夹和文件中**\<驱动器\>: \Tutorial\BTAHL7V22Common\BTAHL72XCommon**文件夹。</span><span class="sxs-lookup"><span data-stu-id="31e52-128">creates the project folder and files in the **\<drive\>:\Tutorial\BTAHL7V22Common\BTAHL72XCommon** folder.</span></span>  
  
    <span data-ttu-id="31e52-129">请继续执行[步骤 3:对程序集分配强名称](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)。</span><span class="sxs-lookup"><span data-stu-id="31e52-129">Proceed to [Step 3: Assign a Strong Name to the Assembly](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e52-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="31e52-130">See Also</span></span>  
 [<span data-ttu-id="31e52-131">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="31e52-131">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)