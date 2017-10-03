---
title: "管道添加 SWIFT 反汇编程序或汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, adding assembler
- assembler, adding to pipelines
- pipelines, adding disassembler
- disassembler, adding to pipelines
ms.assetid: f39eb340-fe58-4c8f-b3f2-f7686a245095
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a6a8e45d8f11e6dad977e42c6e9272e9b594e83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a>管道添加 SWIFT 反汇编程序或汇编程序
可以使用与 BizTalk 管道设计[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]创建自定义 BizTalk 接收和发送管道。 SWIFT 反汇编程序可用于在自定义接收管道中的"反汇编"阶段。 同样，你可以在自定义发送管道中的"汇编"阶段使用 SWIFT 汇编程序。 若要调用的 SWIFT 反汇编程序或从管道设计器工具箱的汇编程序，您将拆装器或汇编程序拖到相应的管道阶段管道设计器画布上。 有关调用反汇编程序集的分步说明，请参阅[模块 3： 添加的管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)在端到端教程。 有关使用管道项目或有关管道设计器的详细信息，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
 按照设计，SWIFT 反汇编程序需要"反汇编"阶段，以将*最终*调用接收管道的阶段。 使用任何后续阶段将导致意外行为 （反汇编不调用后续阶段的程序或删除上下文属性，它具有之前填充，并在发布到 MessageBox 消息之前提升反汇编程序数据库）。 同样，SWIFT 汇编程序需要"汇编"阶段，以将*第一个*发送管道的阶段。 使用任何前面阶段可能会影响由 SWIFT 汇编程序动态消息类型发现。  
  
 你必须手动 SWIFT 反汇编程序和添加汇编程序到管道设计器工具箱第一次使用它们。 中详细介绍了执行此操作的分步说明[模块 3： 添加的管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)在端到端教程。 组件将继续出现在工具箱中，一旦你手动将它们添加 (直到你手动将其删除或卸载[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)])。  
  
## <a name="see-also"></a>另请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)