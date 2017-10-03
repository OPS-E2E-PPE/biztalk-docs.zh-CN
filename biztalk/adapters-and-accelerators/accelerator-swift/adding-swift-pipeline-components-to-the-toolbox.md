---
title: "将 SWIFT 管道组件添加到工具箱 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbox, adding pipelines
- pipelines, adding to toolbox
ms.assetid: 3821c10e-ef9b-4657-b934-cff6d096f654
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaef345994a1d849e09025d9ad1bb0f133c1b224
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="8381b-102">将 SWIFT 管道组件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="8381b-102">Adding SWIFT Pipeline Components to the Toolbox</span></span>
<span data-ttu-id="8381b-103">你必须添加到 SWIFT 管道组件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]工具箱中，以便你可以创建自定义管线，使用这些组件。</span><span class="sxs-lookup"><span data-stu-id="8381b-103">You must add the SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox, so that you can create custom pipelines using these components.</span></span> <span data-ttu-id="8381b-104">这是为消息修复和新提交或 FIN 响应对帐创建管道所需的。</span><span class="sxs-lookup"><span data-stu-id="8381b-104">This is required to create pipelines for either Message Repair and New Submission or FIN Response Reconciliation.</span></span>  
  
 <span data-ttu-id="8381b-105">**摘要**</span><span class="sxs-lookup"><span data-stu-id="8381b-105">**Summary**</span></span>  
  
 <span data-ttu-id="8381b-106">添加到以下 SWIFT 管道组件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]工具箱：</span><span class="sxs-lookup"><span data-stu-id="8381b-106">Add the following SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox:</span></span>  
  
-   <span data-ttu-id="8381b-107">SWIFT 汇编程序 （用于消息修复和新提交或 FIN 响应对帐 (FRR)）</span><span class="sxs-lookup"><span data-stu-id="8381b-107">SWIFT Assembler (for Message Repair and New Submission or FIN Response Reconciliation (FRR))</span></span>  
  
-   <span data-ttu-id="8381b-108">SWIFT 反汇编程序 （用于消息修复和新提交或 FRR）</span><span class="sxs-lookup"><span data-stu-id="8381b-108">SWIFT Disassembler (for Message Repair and New Submission or FRR)</span></span>  
  
-   <span data-ttu-id="8381b-109">SWIFT Frr 相关设置 （对于 FRR) 的解析程序</span><span class="sxs-lookup"><span data-stu-id="8381b-109">SWIFT Frr Correlation Set Resolver (for FRR)</span></span>  
  
-   <span data-ttu-id="8381b-110">SWIFT Frr MQSeries 解码器 （FRR)</span><span class="sxs-lookup"><span data-stu-id="8381b-110">SWIFT Frr MQSeries Decoder (for FRR)</span></span>  
  
-   <span data-ttu-id="8381b-111">SWIFT Frr MQSeries 发送组件 （用于 FRR)</span><span class="sxs-lookup"><span data-stu-id="8381b-111">SWIFT Frr MQSeries Send Component (for FRR)</span></span>  
  
### <a name="to-add-a4swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="8381b-112">将 A4SWIFT 管道组件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="8381b-112">To add A4SWIFT pipeline components to the toolbox</span></span>  
  
1.  <span data-ttu-id="8381b-113">在 Visual Studio 中，在**工具**菜单上，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="8381b-113">In Visual Studio, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
2.  <span data-ttu-id="8381b-114">在**选择工具箱项**对话框中，在**BizTalk 管道组件**选项卡上，选择**SWIFT 汇编程序**和**SWIFT 反汇编程序**.</span><span class="sxs-lookup"><span data-stu-id="8381b-114">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Components** tab, select **SWIFT Assembler** and **SWIFT Disassembler**.</span></span> <span data-ttu-id="8381b-115">如果你将使用 FIN 响应对帐，选择**SWIFT Frr 相关设置解析程序**， **SWIFT Frr MQSeries 解码器**，和**SWIFT Frr MQSeries 发送组件**。</span><span class="sxs-lookup"><span data-stu-id="8381b-115">If you will be using FIN Response Reconciliation, select **SWIFT Frr Correlation Set Resolver**, **SWIFT Frr MQSeries Decoder**, and **SWIFT Frr MQSeries Send Component**.</span></span>  
  
3.  <span data-ttu-id="8381b-116">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8381b-116">Click **OK**.</span></span>