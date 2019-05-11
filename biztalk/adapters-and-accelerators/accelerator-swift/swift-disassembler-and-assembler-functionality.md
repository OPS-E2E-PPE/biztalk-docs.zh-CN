---
title: SWIFT 反汇编程序和汇编程序功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc3fa8b96b03d4bd3376f090e5e4436e70da945a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529813"
---
# <a name="swift-disassembler-and-assembler-functionality"></a>SWIFT 反汇编程序和汇编程序功能
SWIFT 反汇编程序可以执行以下任务中调用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道：  
  
- 动态地发现消息类型和解决文档架构。 这样的单个接收端口和管道来处理多个 SWIFT 消息类型。  
  
- 解析为 XML SWIFT 的平面文件。  
  
- 调用验证读取器以执行 XML （架构） 验证，例如数据类型有效性、 数据格式或长度一致性检查的 XML。  
  
- 调用业务规则引擎 (BRE)，以执行 BRE 验证，例如检查符合性的 SWIFT 网络规则或执行其他复杂的验证未实现架构。  
  
- 将已分析的 XML 消息发布到 MessageBox 数据库使用已升级的上下文属性和序列化的错误集合 XML （提供有关在分析或验证过程中遇到任何错误的信息）。  
  
  > [!NOTE]
  >  如果拆装器在分析过程中遇到致命故障，拆装器会将消息发布到 MessageBox 数据库中本机平面文件格式而不是 XML。  
  
- 按如下所示处理入站的批处理：  
  
  -   分析和保留批的信封 （批处理标头，批处理尾部）  
  
  -   分析并保留消息信封 （消息标头，消息尾部）  
  
  -   分析和单独验证批中的 SWIFT 消息  
  
  -   将 SWIFT 消息单独发布到 MessageBox 数据库  
  
  -   将整个入站的批处理发布到 MessageBox 数据库，作为单个消息 （输入的精确副本）  
  
  -   升级对排序或关联来自同一个批处理的消息批处理相关的上下文属性  
  
  SWIFT 汇编程序可以执行以下任务时在 BizTalk 发送管道中调用：  
  
- 动态地发现消息类型和解决文档架构。 这允许单个发送端口和管道来处理多个 SWIFT 消息类型。  
  
- 已分析的 XML 序列化为 SWIFT 的平面文件。  
  
## <a name="see-also"></a>请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)