---
title: "配置 SWIFT 汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e1309012abbaac27e2e0ae6ec9b35f37d88884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-swift-assembler"></a>配置 SWIFT 汇编程序
SWIFT 汇编程序将执行下列任务，在调用中时[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]发送管道：  
  
-   动态发现消息类型，并解析文档架构  
  
-   将已分析的 XML 序列化到 SWIFT 平面文件  
  
 你可以配置将用于编码 （例如，若要使用 ASCII 或 Unicode 编码） 序列化的输出的编码字符集。  
  
 在开发期间使用 SWIFT 汇编程序在自定义发送管道配置 SWIFT 汇编程序。  
  
 BizTalk 管道设计器配置的自定义发送管道的开发期间 SWIFT 汇编程序。  
  
 若要添加到自定义发送管道的组装阶段之后，请配置 SWIFT 汇编程序，选择管道设计器画布上的 SWIFT 汇编程序组件。 SWIFT 汇编程序然后接收焦点时，还可以设置其使用属性窗口中的配置属性[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。  
  
 有关可用的配置属性及其说明和用法的详细信息的表，请参阅[SWIFT 汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)。  
  
 有关为不同的方案使用 SWIFT 汇编程序和设置配置属性的信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。  
  
 编译该自定义管道二进制文件后，它将以静态方式向自定义管道将配置设置。 因此，你无法在部署过程中更改配置属性，或运行时间。  
  
> [!NOTE]
>  配置、 编译和部署自定义管道后，在配置中的更改需要重新编译和重新部署自定义的管道。  
  
 有关创建的信息，生成和部署自定义管道，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
 本部分包含：  
  
-   [SWIFT 汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)