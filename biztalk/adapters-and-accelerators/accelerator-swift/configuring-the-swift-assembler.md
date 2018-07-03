---
title: 配置 SWIFT 汇编程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50c58ad000e465949229400128ce4c47da40806e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993662"
---
# <a name="configuring-the-swift-assembler"></a>配置 SWIFT 汇编程序
SWIFT 汇编程序执行以下任务时调用在 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]发送管道：  
  
- 动态发现消息类型和解析文档架构  
  
- 将已分析的 XML 序列化到 SWIFT 的平面文件  
  
  你可以配置编码使用的字符集进行编码 （例如，若要使用 ASCII 或 Unicode 编码） 序列化的输出。  
  
  在开发期间使用 SWIFT 汇编程序的自定义发送管道配置 SWIFT 汇编程序。  
  
  BizTalk 管道设计器在开发时的自定义发送管道配置 SWIFT 汇编程序。  
  
  若要配置 SWIFT 汇编程序添加到自定义发送管道的组装阶段后，选择管道设计器画布上的 SWIFT 汇编程序组件。 SWIFT 汇编程序然后获得焦点，并可以设置其配置属性，使用 Microsoft 中的属性窗口[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。  
  
  有关可用的配置属性及其说明和使用情况详细信息的表，请参阅[SWIFT 汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)。  
  
  有关不同的情况下使用 SWIFT 汇编程序和设置配置属性的信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。  
  
  编译自定义管道二进制文件后，它以静态方式将配置设置写入到自定义管道。 因此，不能在部署过程中更改配置属性，或运行时。  
  
> [!NOTE]
>  配置、 编译和部署自定义管道后，在配置中的更改需要重新编译和重新部署的自定义管道。  
  
 有关创建、 生成和部署自定义管道的信息，请参阅 BizTalk Server 帮助。  
  
 本部分包含：  
  
-   [SWIFT 汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)