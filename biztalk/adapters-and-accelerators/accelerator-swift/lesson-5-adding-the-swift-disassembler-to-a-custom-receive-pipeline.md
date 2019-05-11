---
title: 第 5 课：将 SWIFT 反汇编程序添加到自定义接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, adding disassembler
- custom pipelines
- disassembler, custom pipelines
- disassembler, adding to pipelines
ms.assetid: 96e26d97-bfab-448f-b7b6-3bc2ec3ccebf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f37d8ff6369a030bf284584f19192f651cb08a2
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530288"
---
# <a name="lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline"></a><span data-ttu-id="aed0b-102">第 5 课：将 SWIFT 反汇编程序添加到自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="aed0b-102">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>
<span data-ttu-id="aed0b-103">在本课中，您将自定义 SWIFT 反汇编程序 (DASM) 添加到你的管道。</span><span class="sxs-lookup"><span data-stu-id="aed0b-103">In this lesson, you add the custom SWIFT disassembler (DASM) to your pipeline.</span></span> <span data-ttu-id="aed0b-104">DASM 管道组件是将分批消息划分为各个文档的管道组件。</span><span class="sxs-lookup"><span data-stu-id="aed0b-104">A DASM pipeline component is a pipeline component that divides messages in a batch into individual documents.</span></span>  
  
 <span data-ttu-id="aed0b-105">MicrosoftBizTalk 服务器中提供的 DASM 管道组件包括：</span><span class="sxs-lookup"><span data-stu-id="aed0b-105">The DASM pipeline components provided in MicrosoftBizTalk Server are:</span></span>  
  
- <span data-ttu-id="aed0b-106">平面文件拆装器</span><span class="sxs-lookup"><span data-stu-id="aed0b-106">Flat file disassembler</span></span>  
  
- <span data-ttu-id="aed0b-107">BizTalk 框架拆装器</span><span class="sxs-lookup"><span data-stu-id="aed0b-107">BizTalk Framework disassembler</span></span>  
  
- <span data-ttu-id="aed0b-108">XML 拆装器</span><span class="sxs-lookup"><span data-stu-id="aed0b-108">XML disassembler</span></span>  
  
  <span data-ttu-id="aed0b-109">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]添加其他的 SWIFT 反汇编程序。</span><span class="sxs-lookup"><span data-stu-id="aed0b-109">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] adds an additional SWIFT disassembler.</span></span>  
  
### <a name="to-add-the-swift-custom-disassembler-to-your-pipeline"></a><span data-ttu-id="aed0b-110">若要将 SWIFT 的自定义拆装器添加到你的管道</span><span class="sxs-lookup"><span data-stu-id="aed0b-110">To add the SWIFT custom disassembler to your pipeline</span></span>  
  
1. <span data-ttu-id="aed0b-111">从视图菜单中，单击**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="aed0b-111">From the View menu, click **Toolbox**.</span></span>  
  
2. <span data-ttu-id="aed0b-112">从**BizTalk 管道组件工具箱**，单击**SWIFT 反汇编程序**将其拖到**拖至此处**下面的框**拆装**阶段中的形状**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="aed0b-112">From the **BizTalk Pipeline Components Toolbox**, click **SWIFT Disassembler** and drag it to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="aed0b-113">将保留**SWIFT 反汇编程序**中所选的形状**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="aed0b-113">Leave the **SWIFT Disassembler** shape selected in the **BizTalk Pipeline Designer**.</span></span>  
  
3. <span data-ttu-id="aed0b-114">在中**属性**窗格中，选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**有关**SWIFT 标头架构**属性。</span><span class="sxs-lookup"><span data-stu-id="aed0b-114">In the **Properties** pane, select **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** for the **SWIFT Header Schema** property.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aed0b-115">不要混淆**SWIFT 标头架构**和消息标头架构。</span><span class="sxs-lookup"><span data-stu-id="aed0b-115">Do not confuse **SWIFT Header Schema** and Message Header Schema.</span></span> <span data-ttu-id="aed0b-116">必须设置**SWIFT 标头架构**步骤 3 中。</span><span class="sxs-lookup"><span data-stu-id="aed0b-116">You must set **SWIFT Header Schema** in step 3.</span></span>  
  
4. <span data-ttu-id="aed0b-117">在中**属性**窗格中，确保**BRE 验证**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="aed0b-117">In the **Properties** pane, ensure that the **BRE Validation** property is set to **True**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aed0b-118">本教程后面跟有解释的业务规则引擎 (BRE)。</span><span class="sxs-lookup"><span data-stu-id="aed0b-118">An explanation of the Business Rule Engine (BRE) follows later in this tutorial.</span></span>  
  
5. <span data-ttu-id="aed0b-119">在中**属性**窗格中，确保**XML 验证**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="aed0b-119">In the **Properties** pane, ensure that the **XML Validation** property is set to **True**.</span></span>  
  
6. <span data-ttu-id="aed0b-120">在中**属性**窗格中，确保**入站解除批处理**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="aed0b-120">In the **Properties** pane, ensure that the **Inbound Debatching** property is set to **False**.</span></span>  
  
7. <span data-ttu-id="aed0b-121">上**文件**菜单中，选择**全部保存**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="aed0b-121">On the **File** menu, select **Save All** to save your changes.</span></span>  
  
   <span data-ttu-id="aed0b-122">请继续执行[第 6 课：创建自定义发送管道](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="aed0b-122">Proceed to [Lesson 6: Creating a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md).</span></span>