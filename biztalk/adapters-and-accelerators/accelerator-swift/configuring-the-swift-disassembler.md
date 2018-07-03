---
title: 配置 SWIFT 反汇编程序 |Microsoft Docs
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
ms.openlocfilehash: 5ad88310f5bbf600edd576bc0bc17c64fe3ecbea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001462"
---
# <a name="configuring-the-swift-disassembler"></a>配置 SWIFT 反汇编程序
SWIFT 反汇编程序 (DASM) 执行以下任务时调用在 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道：  
  
- 动态发现消息类型和解析文档架构  
  
- 将 SWIFT 平面文件分析为 XML  
  
- 调用验证读取器执行 XML （架构） 验证 XML  
  
- 调用业务规则引擎 (BRE) 执行 BRE 验证  
  
- 将已分析的 XML 消息发布到 MessageBox 数据库使用已升级的上下文属性和序列化的错误集合 XML  
  
- 进程的入站的批处理  
  
  你可以配置以满足用户方案的特定要求上面所列的功能和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]解决方案。  
  
  BizTalk 管道设计器在开发时的自定义接收管道配置 SWIFT 反汇编程序。  
  
  若要配置 SWIFT 反汇编程序添加到自定义接收管道的拆装阶段之后，选择 BizTalk 管道设计器画布上的 SWIFT 反汇编程序组件。 SWIFT 反汇编程序然后接收焦点，并可以设置其配置属性，使用 Microsoft 中的属性窗口[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。  
  
  有关可用的配置属性及其说明和使用情况详细信息的表，请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)。  
  
  有关不同的情况下使用 SWIFT 反汇编程序和设置配置属性的信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。  
  
  当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]编译二进制文件，以静态方式配置设置写入到自定义管道的自定义管道。 因此，不能在部署过程中更改配置属性，或运行时。  
  
> [!NOTE]
>  配置、 编译和部署自定义管道后，在配置中的更改需要重新编译和重新部署的自定义管道。  
  
 有关创建、 生成和部署自定义管道的信息，请参阅 BizTalk Server 帮助。  
  
 本部分包含：  
  
-   [SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)