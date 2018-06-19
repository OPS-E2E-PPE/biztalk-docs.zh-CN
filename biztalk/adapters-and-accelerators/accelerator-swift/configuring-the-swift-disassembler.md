---
title: 配置 SWIFT 反汇编程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26147924950a73b0f654531e9e0eff8e5ac82541
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005358"
---
# <a name="configuring-the-swift-disassembler"></a>配置 SWIFT 反汇编程序
SWIFT 反汇编程序 (DASM) 将执行下列任务，在调用中时[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道：  
  
-   动态发现消息类型，并解析文档架构  
  
-   为 XML 分析 SWIFT 平面文件  
  
-   调用验证读取器执行 XML （架构） 验证的 XML  
  
-   调用以执行 BRE 验证业务规则引擎 (BRE)  
  
-   将已分析的 XML 消息发布到 MessageBox 数据库使用提升的上下文属性和序列化的错误集合 XML  
  
-   进程入站的批处理  
  
 你可以配置上面列出的、 以满足用户方案的特定要求的功能和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]解决方案。  
  
 BizTalk 管道设计器配置的自定义接收管道的开发期间 SWIFT 反汇编程序。  
  
 若要添加到自定义接收管道的拆装阶段之后，请配置 SWIFT 反汇编程序，选择 BizTalk 管道设计器画布上的 SWIFT 反汇编程序组件。 SWIFT 反汇编程序然后接收到焦点并可以设置使用内的属性窗口其配置属性[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。  
  
 有关可用的配置属性及其说明和用法的详细信息的表，请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)。  
  
 有关为不同的方案使用 SWIFT 反汇编程序和设置配置属性的信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。  
  
 当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]编译二进制文件，以静态方式的配置设置写入到自定义管道自定义的管道。 因此，你无法在部署过程中更改配置属性，或运行时间。  
  
> [!NOTE]
>  配置、 编译和部署自定义管道后，在配置中的更改需要重新编译和重新部署自定义的管道。  
  
 有关创建、 构建和部署自定义管道的信息，请参阅 BizTalk Server 帮助。  
  
 本部分包含：  
  
-   [SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)