---
title: "配置 SWIFT 反汇编程序或汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, disassembler
- disassembler, configuring
- configuring, assembler
ms.assetid: 56e421f2-0292-40af-b878-0cba1b034e19
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8920a8b74da14eeb8186d153444ced7c54d57724
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-the-swift-disassembler-or-assembler"></a>配置 SWIFT 反汇编程序或汇编程序
SWIFT 反汇编程序或 SWIFT 汇编程序添加自定义管道后，你必须将其配置为提供 （如启用/禁用动态消息类型发现、 入站 debatching、 XML 验证，在特定方案所需的功能业务规则引擎 (BRE) 验证和等等）。 必须在开发期间编译和部署自定义调用它们的管道之前配置的 SWIFT 反汇编程序和汇编程序。 若要配置 SWIFT 反汇编程序汇编程序，在管道设计器中选择的组件和编辑属性窗口中的配置属性。  
  
 请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)完整的详细信息和每个配置属性，以及其他使用情况和配置信息的说明。  
  
 请参阅[SWIFT 汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)完整的详细信息和说明的编码字符集配置属性，以及其他使用情况和配置信息。  
  
> [!NOTE]
>  配置、 编译和部署自定义管道后，配置中的更改需要重新编译和重新部署自定义的管道。  
  
 配置、 编译和部署自定义管道处理 SWIFT 消息后，你可以设置最多接收位置的使用自定义 SWIFT 接收管道，和发送端口使用自定义 SWIFT 发送管道。 接收端口的有关部署管道和配置的详细信息，接收位置，并发送端口，请参阅[模块 4： 创建 XML 接收和平面文件发送端口](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)，[模块 5： 创建接收平面文件和XML 发送端口](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)，和 BizTalk Server 帮助。  
  
 本部分包含：  
  
-   [配置 SWIFT 反汇编程序](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [配置 SWIFT 汇编程序](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a>另请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)