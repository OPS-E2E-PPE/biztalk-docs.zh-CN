---
title: 将 SWIFT 管道组件添加到工具箱 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- toolbox, adding pipelines
- pipelines, adding to toolbox
ms.assetid: 3821c10e-ef9b-4657-b934-cff6d096f654
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4594b3ed3ca1c348a9d903217d165f8f9d2380d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378635"
---
# <a name="adding-swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="1d549-102">将 SWIFT 管道组件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="1d549-102">Adding SWIFT Pipeline Components to the Toolbox</span></span>
<span data-ttu-id="1d549-103">您必须添加到 SWIFT 管道组件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]工具箱中，以便您可以创建自定义管道使用这些组件。</span><span class="sxs-lookup"><span data-stu-id="1d549-103">You must add the SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox, so that you can create custom pipelines using these components.</span></span> <span data-ttu-id="1d549-104">这被必需的消息修复和新提交或 FIN 响应对帐创建管道。</span><span class="sxs-lookup"><span data-stu-id="1d549-104">This is required to create pipelines for either Message Repair and New Submission or FIN Response Reconciliation.</span></span>  
  
 <span data-ttu-id="1d549-105">**摘要**</span><span class="sxs-lookup"><span data-stu-id="1d549-105">**Summary**</span></span>  
  
 <span data-ttu-id="1d549-106">添加到以下 SWIFT 管道组件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]工具箱：</span><span class="sxs-lookup"><span data-stu-id="1d549-106">Add the following SWIFT pipeline components to the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Toolbox:</span></span>  
  
-   <span data-ttu-id="1d549-107">SWIFT 汇编程序 （用于消息修复和新提交或 FIN 响应对帐 (FRR)）</span><span class="sxs-lookup"><span data-stu-id="1d549-107">SWIFT Assembler (for Message Repair and New Submission or FIN Response Reconciliation (FRR))</span></span>  
  
-   <span data-ttu-id="1d549-108">SWIFT 反汇编程序 （用于消息修复和新提交或 FRR）</span><span class="sxs-lookup"><span data-stu-id="1d549-108">SWIFT Disassembler (for Message Repair and New Submission or FRR)</span></span>  
  
-   <span data-ttu-id="1d549-109">SWIFT 的 Frr 相关集冲突解决程序 （适用于 FRR)</span><span class="sxs-lookup"><span data-stu-id="1d549-109">SWIFT Frr Correlation Set Resolver (for FRR)</span></span>  
  
-   <span data-ttu-id="1d549-110">SWIFT 的 Frr MQSeries 解码器 （适用于 FRR)</span><span class="sxs-lookup"><span data-stu-id="1d549-110">SWIFT Frr MQSeries Decoder (for FRR)</span></span>  
  
-   <span data-ttu-id="1d549-111">（适用于 FRR) SWIFT 的 Frr MQSeries 发送组件</span><span class="sxs-lookup"><span data-stu-id="1d549-111">SWIFT Frr MQSeries Send Component (for FRR)</span></span>  
  
### <a name="to-add-a4swift-pipeline-components-to-the-toolbox"></a><span data-ttu-id="1d549-112">若要向工具箱添加 A4SWIFT 管道组件</span><span class="sxs-lookup"><span data-stu-id="1d549-112">To add A4SWIFT pipeline components to the toolbox</span></span>  
  
1.  <span data-ttu-id="1d549-113">在 Visual Studio 中，在**工具**菜单上，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="1d549-113">In Visual Studio, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
2.  <span data-ttu-id="1d549-114">在中**选择工具箱项**对话框中，在**BizTalk 管道组件**选项卡上，选择**SWIFT 汇编程序**和**SWIFT 反汇编程序**.</span><span class="sxs-lookup"><span data-stu-id="1d549-114">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Components** tab, select **SWIFT Assembler** and **SWIFT Disassembler**.</span></span> <span data-ttu-id="1d549-115">如果您将使用 FIN 响应对帐，选择**SWIFT Frr 相关设置解析程序**， **SWIFT 的 Frr MQSeries 解码器**，并**SWIFT 的 Frr MQSeries 发送组件**。</span><span class="sxs-lookup"><span data-stu-id="1d549-115">If you will be using FIN Response Reconciliation, select **SWIFT Frr Correlation Set Resolver**, **SWIFT Frr MQSeries Decoder**, and **SWIFT Frr MQSeries Send Component**.</span></span>  
  
3.  <span data-ttu-id="1d549-116">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1d549-116">Click **OK**.</span></span>