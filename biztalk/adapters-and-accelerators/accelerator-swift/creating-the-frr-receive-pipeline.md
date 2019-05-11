---
title: 创建 FRR 接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f82aef718422dc00c80d9f22343873780380a801
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378323"
---
# <a name="creating-the-frr-receive-pipeline"></a><span data-ttu-id="f414f-102">创建 FRR 接收管道</span><span class="sxs-lookup"><span data-stu-id="f414f-102">Creating the FRR Receive Pipeline</span></span>
<span data-ttu-id="f414f-103">若要执行 FIN 响应对帐，必须创建包含 SWIFT 的 FRR 解码器和 SWIFT FRR CorrelationSet 冲突解决程序除了 SWIFT 反汇编程序管道组件的接收管道。</span><span class="sxs-lookup"><span data-stu-id="f414f-103">To perform FIN Response Reconciliation, you must create a receive pipeline that contains the SWIFT FRR Decoder and SWIFT FRR CorrelationSet Resolver pipeline components, in addition to the SWIFT disassembler.</span></span>  

 <span data-ttu-id="f414f-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="f414f-104">**Summary**</span></span>  

 <span data-ttu-id="f414f-105">创建一个接收管道具有以下阶段属性：</span><span class="sxs-lookup"><span data-stu-id="f414f-105">Create a receive pipeline with the following stages/properties:</span></span>  

|<span data-ttu-id="f414f-106">阶段/属性</span><span class="sxs-lookup"><span data-stu-id="f414f-106">Stage/Property</span></span>|<span data-ttu-id="f414f-107">组件/设置</span><span class="sxs-lookup"><span data-stu-id="f414f-107">Component/Setting</span></span>|  
|---------------------|------------------------|  
|<span data-ttu-id="f414f-108">拆装阶段</span><span class="sxs-lookup"><span data-stu-id="f414f-108">Disassemble stage</span></span>|<span data-ttu-id="f414f-109">SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="f414f-109">SWIFT Disassembler</span></span>|  
|<span data-ttu-id="f414f-110">BRE 验证属性 （SWIFT 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="f414f-110">BRE Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="f414f-111">True</span><span class="sxs-lookup"><span data-stu-id="f414f-111">True</span></span>|  
|<span data-ttu-id="f414f-112">XML 验证属性 （SWIFT 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="f414f-112">XML Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="f414f-113">True</span><span class="sxs-lookup"><span data-stu-id="f414f-113">True</span></span>|  
|<span data-ttu-id="f414f-114">SWIFT 标头架构属性 （SWIFT 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="f414f-114">SWIFT Header Schema property (SWIFT Disassembler)</span></span>|<span data-ttu-id="f414f-115">（无）</span><span class="sxs-lookup"><span data-stu-id="f414f-115">(None)</span></span>|  
|<span data-ttu-id="f414f-116">解码器阶段</span><span class="sxs-lookup"><span data-stu-id="f414f-116">Decoder stage</span></span>|<span data-ttu-id="f414f-117">SWIFT 的 FRR MQSeries 解码器</span><span class="sxs-lookup"><span data-stu-id="f414f-117">SWIFT FRR MQSeries Decoder</span></span>|  
|<span data-ttu-id="f414f-118">参与方解析阶段</span><span class="sxs-lookup"><span data-stu-id="f414f-118">Party Resolution stage</span></span>|<span data-ttu-id="f414f-119">SWIFT 的 FRR 相关集冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="f414f-119">SWIFT FRR Correlation Set Resolver</span></span>|  

### <a name="to-create-a-custom-receive-pipeline-for-frr"></a><span data-ttu-id="f414f-120">若要为 FRR 创建自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="f414f-120">To create a custom receive pipeline for FRR</span></span>  

1. <span data-ttu-id="f414f-121">在解决方案资源管理器的 Visual Studio 中，右键单击项目包含你[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管道中，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="f414f-121">In Solution Explorer of Visual Studio, right-click the project containing your [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] pipelines, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="f414f-122">在添加新项对话框中，单击**管道文件**在类别窗格中，然后选择**接收管道**模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="f414f-122">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** in the Templates pane.</span></span>  

3. <span data-ttu-id="f414f-123">在中**名称**框中，键入你的接收管道的名称，如**FRRReceivePipeline.btp**。</span><span class="sxs-lookup"><span data-stu-id="f414f-123">In the **Name** box, type a name for your receive pipeline, such as **FRRReceivePipeline.btp**.</span></span> <span data-ttu-id="f414f-124">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="f414f-124">Click **Add**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f414f-125">在执行步骤 4 之前，您必须添加[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR 管道组件工具箱中所述[到工具箱中添加 SWIFT 管道组件](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f414f-125">Before you perform step 4, you must have added the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR pipeline components to the toolbox, as described in [Adding SWIFT Pipeline Components to the Toolbox](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).</span></span>  

4. <span data-ttu-id="f414f-126">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**，然后单击**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="f414f-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then click **Toolbox**.</span></span>  

5. <span data-ttu-id="f414f-127">通过 BizTalk 管道组件工具箱窗格中，将**SWIFT 反汇编程序**到**在此处放置**下面的框**拆装**阶段在管道设计器中的形状。</span><span class="sxs-lookup"><span data-stu-id="f414f-127">From the BizTalk Pipeline Components Toolbox pane, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in Pipeline Designer.</span></span>  

6. <span data-ttu-id="f414f-128">与**SWIFT 拆装器组件**中在管道设计器中，选择**属性**，验证**BRE 验证**和**XML 验证**属性设置为**True**，和**SWIFT 标头架构**属性设置为 **（无）**。</span><span class="sxs-lookup"><span data-stu-id="f414f-128">With the **SWIFT Disassembler Component** selected in Pipeline Designer, in **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**, and the **SWIFT Header Schema** property is set to **(None)**.</span></span>  

7. <span data-ttu-id="f414f-129">在 BizTalk 管道组件工具箱拖动**SWIFT 的 FRR MQSeries 解码器**到**在此处放置**下面的框**解码器**阶段在管道设计器中的形状。</span><span class="sxs-lookup"><span data-stu-id="f414f-129">In the BizTalk Pipeline Components Toolbox, drag **SWIFT FRR MQSeries Decoder** to the **Drop Here** box below the **Decoder** stage shape in Pipeline Designer.</span></span>  

8. <span data-ttu-id="f414f-130">通过 BizTalk 管道组件工具箱窗格中，将**SWIFT FRR 相关设置解析程序**到**在此处放置**下面的框**解析参与方**阶段管道中的形状设计器。</span><span class="sxs-lookup"><span data-stu-id="f414f-130">From the BizTalk Pipeline Components Toolbox pane, drag **SWIFT FRR Correlation Set Resolver** to the **Drop Here** box below the **ResolveParty** stage shape in Pipeline Designer.</span></span>  

9. <span data-ttu-id="f414f-131">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**文件**，然后单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="f414f-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then click **Save All**.</span></span>
