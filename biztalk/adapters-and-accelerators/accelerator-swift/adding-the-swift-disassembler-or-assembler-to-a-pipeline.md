---
title: 将 SWIFT 反汇编程序或汇编程序添加到管道 |Microsoft Docs
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
ms.openlocfilehash: 0efb67e403ebffe87924f236ae69bfd0e6108d09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378805"
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a>将 SWIFT 反汇编程序或汇编程序添加到管道
您可以使用 BizTalk 管道设计器与 Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]创建自定义 BizTalk 接收和发送管道。 SWIFT 反汇编程序可用于自定义接收管道中的"拆装"阶段。 同样，您可以在自定义发送管道中的"组装"阶段使用 SWIFT 汇编程序。 若要调用的 SWIFT 反汇编程序或组装器管道设计器工具箱中，您将拆装器或组装器拖到相应的管道阶段在管道设计器画布上。 有关调用拆装器或组装器的分步说明，请参阅[模块 3:添加管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)在端到端教程。 有关使用管道项目或有关在管道设计器的详细信息，请参阅 BizTalk Server 帮助。  
  
 SWIFT 反汇编程序按照设计，需要为的"拆装"阶段*最终*调用接收管道阶段。 使用任何后续阶段将导致意外行为 （不调用随后的阶段，此类的拆装器或删除它之前填充名称并将消息发布到 MessageBox 之前升级上下文属性的拆装器数据库）。 同样，SWIFT 汇编程序需要"组装"阶段*第一个*发送管道阶段。 使用任何上述阶段可能会影响通过 SWIFT 汇编程序的动态消息类型发现。  
  
 手动必须将 SWIFT 反汇编程序和汇编程序添加到管道设计器工具箱第一次使用它们。 中详细介绍了执行此操作的分步说明[模块 3:添加管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)在端到端教程。 组件将继续显示在工具箱中手动添加后 (直到手动删除或卸载[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)])。  
  
## <a name="see-also"></a>请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)