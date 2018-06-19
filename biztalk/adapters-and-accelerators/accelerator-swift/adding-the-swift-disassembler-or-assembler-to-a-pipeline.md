---
title: 管道添加 SWIFT 反汇编程序或汇编程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, adding assembler
- assembler, adding to pipelines
- pipelines, adding disassembler
- disassembler, adding to pipelines
ms.assetid: f39eb340-fe58-4c8f-b3f2-f7686a245095
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0648e6c51d83a95fb24b36d872e06e157480c5fb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005246"
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a><span data-ttu-id="7abe8-102">管道添加 SWIFT 反汇编程序或汇编程序</span><span class="sxs-lookup"><span data-stu-id="7abe8-102">Adding the SWIFT Disassembler or Assembler to a Pipeline</span></span>
<span data-ttu-id="7abe8-103">可以使用与 BizTalk 管道设计[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]创建自定义 BizTalk 接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="7abe8-103">You can use BizTalk Pipeline Designer with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create custom BizTalk receive and send pipelines.</span></span> <span data-ttu-id="7abe8-104">SWIFT 反汇编程序可用于在自定义接收管道中的"反汇编"阶段。</span><span class="sxs-lookup"><span data-stu-id="7abe8-104">You can use the SWIFT disassembler for the "disassemble" stage in a custom receive pipeline.</span></span> <span data-ttu-id="7abe8-105">同样，你可以在自定义发送管道中的"汇编"阶段使用 SWIFT 汇编程序。</span><span class="sxs-lookup"><span data-stu-id="7abe8-105">Similarly, you can use the SWIFT assembler for the "assemble" stage in a custom send pipeline.</span></span> <span data-ttu-id="7abe8-106">若要调用的 SWIFT 反汇编程序或从管道设计器工具箱的汇编程序，您将拆装器或汇编程序拖到相应的管道阶段管道设计器画布上。</span><span class="sxs-lookup"><span data-stu-id="7abe8-106">To invoke the SWIFT disassembler or assembler from the Pipeline Designer toolbox, you drag the disassembler or assembler onto the corresponding pipeline stage on the Pipeline Designer canvas.</span></span> <span data-ttu-id="7abe8-107">有关调用反汇编程序集的分步说明，请参阅[模块 3： 添加的管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)在端到端教程。</span><span class="sxs-lookup"><span data-stu-id="7abe8-107">For step-by-step instructions about invoking the disassembler or assembler, see [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) in the End-to-End Tutorial.</span></span> <span data-ttu-id="7abe8-108">有关使用管道项目或有关管道设计器的详细信息，请参阅 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="7abe8-108">For more information about the Pipeline Designer or working with pipeline projects, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="7abe8-109">按照设计，SWIFT 反汇编程序需要"反汇编"阶段，以将*最终*调用接收管道的阶段。</span><span class="sxs-lookup"><span data-stu-id="7abe8-109">By design, the SWIFT disassembler expects the "disassemble" stage to be the *final* stage of the receive pipeline that is invoked.</span></span> <span data-ttu-id="7abe8-110">使用任何后续阶段将导致意外行为 （反汇编不调用后续阶段的程序或删除上下文属性，它具有之前填充，并在发布到 MessageBox 消息之前提升反汇编程序数据库）。</span><span class="sxs-lookup"><span data-stu-id="7abe8-110">Using any subsequent stages will result in unexpected behavior (such the disassembler not invoking subsequent stages, or the disassembler removing context properties that it had previously populated and promoted before publishing the message to the MessageBox database).</span></span> <span data-ttu-id="7abe8-111">同样，SWIFT 汇编程序需要"汇编"阶段，以将*第一个*发送管道的阶段。</span><span class="sxs-lookup"><span data-stu-id="7abe8-111">Similarly, the SWIFT assembler expects the "assemble" stage to be the *first* stage of the send pipeline.</span></span> <span data-ttu-id="7abe8-112">使用任何前面阶段可能会影响由 SWIFT 汇编程序动态消息类型发现。</span><span class="sxs-lookup"><span data-stu-id="7abe8-112">Using any preceding stages may impair dynamic message type discovery by the SWIFT assembler.</span></span>  
  
 <span data-ttu-id="7abe8-113">你必须手动 SWIFT 反汇编程序和添加汇编程序到管道设计器工具箱第一次使用它们。</span><span class="sxs-lookup"><span data-stu-id="7abe8-113">You must manually add the SWIFT disassembler and assembler to the Pipeline Designer toolbox the first time you use them.</span></span> <span data-ttu-id="7abe8-114">中详细介绍了执行此操作的分步说明[模块 3： 添加的管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)在端到端教程。</span><span class="sxs-lookup"><span data-stu-id="7abe8-114">Step-by-step instructions for doing this are detailed in [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) in the End-to-End Tutorial.</span></span> <span data-ttu-id="7abe8-115">组件将继续出现在工具箱中，一旦你手动将它们添加 (直到你手动将其删除或卸载[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="7abe8-115">The components will continue to appear in the toolbox once you manually add them (until you manually remove them or until you uninstall [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abe8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7abe8-116">See Also</span></span>  
 [<span data-ttu-id="7abe8-117">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="7abe8-117">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)