---
title: "创建 FRR 接收管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad31a69d579cf2bbe9f646fc87be1bea9f561a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-pipeline"></a><span data-ttu-id="45cc0-102">创建 FRR 接收管道</span><span class="sxs-lookup"><span data-stu-id="45cc0-102">Creating the FRR Receive Pipeline</span></span>
<span data-ttu-id="45cc0-103">若要执行 FIN 响应对帐，必须创建包含 SWIFT FRR 解码器和 SWIFT FRR CorrelationSet 冲突解决程序管道组件，除了 SWIFT 反汇编程序接收管道。</span><span class="sxs-lookup"><span data-stu-id="45cc0-103">To perform FIN Response Reconciliation, you must create a receive pipeline that contains the SWIFT FRR Decoder and SWIFT FRR CorrelationSet Resolver pipeline components, in addition to the SWIFT disassembler.</span></span>  
  
 <span data-ttu-id="45cc0-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="45cc0-104">**Summary**</span></span>  
  
 <span data-ttu-id="45cc0-105">创建具有以下阶段属性接收管道：</span><span class="sxs-lookup"><span data-stu-id="45cc0-105">Create a receive pipeline with the following stages/properties:</span></span>  
  
|<span data-ttu-id="45cc0-106">阶段/属性</span><span class="sxs-lookup"><span data-stu-id="45cc0-106">Stage/Property</span></span>|<span data-ttu-id="45cc0-107">组件/设置</span><span class="sxs-lookup"><span data-stu-id="45cc0-107">Component/Setting</span></span>|  
|---------------------|------------------------|  
|<span data-ttu-id="45cc0-108">拆装阶段</span><span class="sxs-lookup"><span data-stu-id="45cc0-108">Disassemble stage</span></span>|<span data-ttu-id="45cc0-109">SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="45cc0-109">SWIFT Disassembler</span></span>|  
|<span data-ttu-id="45cc0-110">BRE 验证属性 （SWIFT 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="45cc0-110">BRE Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="45cc0-111">True</span><span class="sxs-lookup"><span data-stu-id="45cc0-111">True</span></span>|  
|<span data-ttu-id="45cc0-112">XML 验证属性 （SWIFT 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="45cc0-112">XML Validation property (SWIFT Disassembler)</span></span>|<span data-ttu-id="45cc0-113">True</span><span class="sxs-lookup"><span data-stu-id="45cc0-113">True</span></span>|  
|<span data-ttu-id="45cc0-114">SWIFT 标头架构属性 （SWIFT 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="45cc0-114">SWIFT Header Schema property (SWIFT Disassembler)</span></span>|<span data-ttu-id="45cc0-115">（无）</span><span class="sxs-lookup"><span data-stu-id="45cc0-115">(None)</span></span>|  
|<span data-ttu-id="45cc0-116">解码器阶段</span><span class="sxs-lookup"><span data-stu-id="45cc0-116">Decoder stage</span></span>|<span data-ttu-id="45cc0-117">SWIFT FRR MQSeries 解码器</span><span class="sxs-lookup"><span data-stu-id="45cc0-117">SWIFT FRR MQSeries Decoder</span></span>|  
|<span data-ttu-id="45cc0-118">当事方解析阶段</span><span class="sxs-lookup"><span data-stu-id="45cc0-118">Party Resolution stage</span></span>|<span data-ttu-id="45cc0-119">SWIFT FRR 关联集冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="45cc0-119">SWIFT FRR Correlation Set Resolver</span></span>|  
  
### <a name="to-create-a-custom-receive-pipeline-for-frr"></a><span data-ttu-id="45cc0-120">若要为 FRR 创建自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="45cc0-120">To create a custom receive pipeline for FRR</span></span>  
  
1.  <span data-ttu-id="45cc0-121">在解决方案资源管理器的 Visual Studio 中，右键单击项目包含你[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管道，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="45cc0-121">In Solution Explorer of Visual Studio, right-click the project containing your [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] pipelines, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="45cc0-122">在添加新项对话框中，单击**管道文件**在类别窗格中，然后选择**接收管道**在模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="45cc0-122">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** in the Templates pane.</span></span>  
  
3.  <span data-ttu-id="45cc0-123">在**名称**框中，键入接收管道的名称，如**FRRReceivePipeline.btp**。</span><span class="sxs-lookup"><span data-stu-id="45cc0-123">In the **Name** box, type a name for your receive pipeline, such as **FRRReceivePipeline.btp**.</span></span> <span data-ttu-id="45cc0-124">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="45cc0-124">Click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45cc0-125">在执行步骤 4 之前，你必须添加[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR 管道组件工具箱中所述[向工具箱添加 SWIFT 管道组件](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md)。</span><span class="sxs-lookup"><span data-stu-id="45cc0-125">Before you perform step 4, you must have added the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR pipeline components to the toolbox, as described in [Adding SWIFT Pipeline Components to the Toolbox](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md).</span></span>  
  
4.  <span data-ttu-id="45cc0-126">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**，然后单击**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="45cc0-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then click **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="45cc0-127">从 BizTalk 管道组件工具箱窗格中，将拖动**SWIFT 反汇编程序**到**拖至此处**下面框**拆卸**暂存管道设计器中的形状。</span><span class="sxs-lookup"><span data-stu-id="45cc0-127">From the BizTalk Pipeline Components Toolbox pane, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in Pipeline Designer.</span></span>  
  
6.  <span data-ttu-id="45cc0-128">与**SWIFT 反汇编程序组件**在管道设计器中，选择在**属性**，验证**BRE 验证**和**XML 验证**属性设置为**True**，和**SWIFT 标头架构**属性设置为**（无）**。</span><span class="sxs-lookup"><span data-stu-id="45cc0-128">With the **SWIFT Disassembler Component** selected in Pipeline Designer, in **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**, and the **SWIFT Header Schema** property is set to **(None)**.</span></span>  
  
7.  <span data-ttu-id="45cc0-129">在 BizTalk 管道组件工具箱中，拖动**SWIFT FRR MQSeries 解码器**到**拖至此处**下面框**解码器**暂存管道设计器中的形状。</span><span class="sxs-lookup"><span data-stu-id="45cc0-129">In the BizTalk Pipeline Components Toolbox, drag **SWIFT FRR MQSeries Decoder** to the **Drop Here** box below the **Decoder** stage shape in Pipeline Designer.</span></span>  
  
8.  <span data-ttu-id="45cc0-130">从 BizTalk 管道组件工具箱窗格中，将拖动**SWIFT FRR 相关设置解析程序**到**拖至此处**下面框**ResolveParty**阶段在管道中的形状设计器。</span><span class="sxs-lookup"><span data-stu-id="45cc0-130">From the BizTalk Pipeline Components Toolbox pane, drag **SWIFT FRR Correlation Set Resolver** to the **Drop Here** box below the **ResolveParty** stage shape in Pipeline Designer.</span></span>  
  
9. <span data-ttu-id="45cc0-131">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**文件**，然后单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="45cc0-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then click **Save All**.</span></span>