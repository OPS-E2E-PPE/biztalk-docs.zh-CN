---
title: "部署 A4SWIFT 信封架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8811f1dd056ca5a4ea4582d593af30e2ffc879f
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="deploying-a4swift-envelope-schemas"></a><span data-ttu-id="d27d6-102">部署 A4SWIFT 信封架构</span><span class="sxs-lookup"><span data-stu-id="d27d6-102">Deploying A4SWIFT Envelope Schemas</span></span>
<span data-ttu-id="d27d6-103">每当你设置消息修复和新提交时，架构项目中必须包含信封架构。</span><span class="sxs-lookup"><span data-stu-id="d27d6-103">You must include envelope schemas in schema projects whenever you set up Message Repair and New Submission.</span></span> <span data-ttu-id="d27d6-104">信封架构，如 EnvelopeMT103.xsd，需要将写入到 MRSR 站点。</span><span class="sxs-lookup"><span data-stu-id="d27d6-104">An envelope schema, such as EnvelopeMT103.xsd, is required to write to MRSR site.</span></span>  
  
 <span data-ttu-id="d27d6-105">**摘要**</span><span class="sxs-lookup"><span data-stu-id="d27d6-105">**Summary**</span></span>  
  
 <span data-ttu-id="d27d6-106">向你的项目，添加信封架构，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d27d6-106">Add envelope schemas to your project, as follows:</span></span>  
  
-   <span data-ttu-id="d27d6-107">在 Visual Studio 中，包含你的消息架构的项目将添加到每个消息架构信封架构。</span><span class="sxs-lookup"><span data-stu-id="d27d6-107">In Visual Studio, to the project that contains your message schemas, add an envelope schema for each message schema.</span></span>  
  
-   <span data-ttu-id="d27d6-108">将对 RuntimeSchemas.dll 的引用添加到任何包含一个或多个信封架构的项目。</span><span class="sxs-lookup"><span data-stu-id="d27d6-108">Add a reference to RuntimeSchemas.dll to any project that contains one or more envelope schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d27d6-109">添加对 RuntimeSchemas.dll 的引用所需[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]项目仅在有消息修复和新提交到该项目添加信封架构时。</span><span class="sxs-lookup"><span data-stu-id="d27d6-109">Adding a reference to RuntimeSchemas.dll is required for an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] project only when you have added an envelope schema for Message Repair and New Submission to the project.</span></span>  
  
-   <span data-ttu-id="d27d6-110">将未分析消息信封架构 (EnvelopeUnparsedMessage.xsd) 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="d27d6-110">Add the Unparsed Message envelope schema (EnvelopeUnparsedMessage.xsd) to the project.</span></span>  
  
### <a name="to-add-a-swift-envelope-schema"></a><span data-ttu-id="d27d6-111">若要添加 SWIFT 信封架构</span><span class="sxs-lookup"><span data-stu-id="d27d6-111">To add a SWIFT envelope schema</span></span>  
  
1.  <span data-ttu-id="d27d6-112">在解决方案资源管理器的 Visual Studio 中，打开架构项目。</span><span class="sxs-lookup"><span data-stu-id="d27d6-112">In Solution Explorer of Visual Studio, open your schemas project.</span></span>  
  
2.  <span data-ttu-id="d27d6-113">右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-113">Right-click **References**, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="d27d6-114">在添加引用对话框中，单击**浏览**标记。</span><span class="sxs-lookup"><span data-stu-id="d27d6-114">In the Add Reference dialog box, click the **Browse** tag.</span></span>  
  
4.  <span data-ttu-id="d27d6-115">在选择组件对话框中，打开**查找**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d27d6-115">In the Select Component dialog box, open the **Look in** drop-down list.</span></span> <span data-ttu-id="d27d6-116">将移动到 ***\<驱动器\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\Assemblies**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-116">Move to ***\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\Assemblies**.</span></span> <span data-ttu-id="d27d6-117">选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**从列表中的程序集，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-117">Select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** from the list of assemblies, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="d27d6-118">在**添加引用**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-118">In the **Add Reference** dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="d27d6-119">右键单击你的项目，指向**添加**，然后单击**添加现有项**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-119">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
7.  <span data-ttu-id="d27d6-120">在添加现有项对话框中，在**查找**下拉列表框中，移动到**\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Categoryn\MTxxx**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-120">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Categoryn\MTxxx**.</span></span> <span data-ttu-id="d27d6-121">例如，选择信封架构， **EnvelopeMT103.xsd**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-121">Select the envelope schema, for example, **EnvelopeMT103.xsd**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="d27d6-122">在添加现有项对话框中，在**查找**下拉列表框中，移动到。</span><span class="sxs-lookup"><span data-stu-id="d27d6-122">In the Add Existing Item dialog box, in the **Look in** drop-down box, move to.</span></span> <span data-ttu-id="d27d6-123">选择信封架构，例如，EnvelopeMT103.xsd，，然后单击添加。</span><span class="sxs-lookup"><span data-stu-id="d27d6-123">Select the envelope schema, for example, EnvelopeMT103.xsd, and then click Add.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d27d6-124">A4SWIFT 将添加你的项目，信封架构，如解决方案资源管理器中所示。</span><span class="sxs-lookup"><span data-stu-id="d27d6-124">A4SWIFT adds the envelope schema for your project, as shown in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="d27d6-125">在解决方案资源管理器，右键单击你的项目，指向**添加**，然后单击**添加现有项**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-125">In Solution Explorer, right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
9. <span data-ttu-id="d27d6-126">如果在使用添加现有项对话框中中的消息修复和新提交功能**查找**下拉列表框中，移动到 **\<*驱动器*\>: \Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Unparsed 消息**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-126">If using the Message Repair and New Submission feature, in the Add Existing Item dialog box, in the **Look in** drop-down box, move to **\<*drive*\>:\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Unparsed Message**.</span></span> <span data-ttu-id="d27d6-127">选择**EnvelopeUnparsedMessage.xsd**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-127">Select **EnvelopeUnparsedMessage.xsd**, and then click **Add**.</span></span>  
  
10. <span data-ttu-id="d27d6-128">在解决方案资源管理器，右键单击项目名称，然后单击 **生成**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-128">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
11. <span data-ttu-id="d27d6-129">在解决方案资源管理器，右键单击项目名称，然后单击 **部署**。</span><span class="sxs-lookup"><span data-stu-id="d27d6-129">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>