---
title: 配置 SWIFT 反汇编程序或汇编程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, disassembler
- disassembler, configuring
- configuring, assembler
ms.assetid: 56e421f2-0292-40af-b878-0cba1b034e19
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54efbf924add1b381d41e515c82de4e69ea80203
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378491"
---
# <a name="configuring-the-swift-disassembler-or-assembler"></a>配置 SWIFT 反汇编程序或汇编程序
将 SWIFT 反汇编程序或 SWIFT 汇编程序添加到自定义管道后，必须将其提供在特定方案 （如启用/禁用动态消息类型发现、 入站解除批处理、 XML 验证所需的功能配置业务规则引擎 (BRE) 验证等）。 在开发时编译和部署的自定义管道的调用它们之前，必须配置 SWIFT 反汇编程序和组装器。 若要配置 SWIFT 拆装器/组装器，在管道设计器中选择的组件和编辑属性窗口中的配置属性。  
  
 请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)完整的详细信息和每个配置属性，以及其他使用情况和配置信息的说明。  
  
 请参阅[SWIFT 汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)完整的详细信息和说明的编码字符集配置属性，以及其他使用情况和配置信息。  
  
> [!NOTE]
>  配置、 编译和部署自定义管道后，配置中的更改需要重新编译和重新部署自定义管道。  
  
 配置、 编译和部署自定义管道来处理 SWIFT 消息后，可以设置最多接收位置的使用自定义 SWIFT 接收管道和发送端口使用自定义 SWIFT 发送管道。 详细了解部署管道和配置接收端口、 接收位置和发送端口，请参阅[模块 4:创建 XML 接收和平面文件发送端口](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)，[模块 5:创建平面文件接收和 XML 发送端口](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)，和 BizTalk Server 帮助。  
  
 本部分包含：  
  
-   [配置 SWIFT 反汇编程序](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [配置 SWIFT 汇编程序](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a>请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)