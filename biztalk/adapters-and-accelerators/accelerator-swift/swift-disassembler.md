---
title: SWIFT 反汇编程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25c389e10a48287ef87495b32fe2d69644a8259e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010918"
---
# <a name="swift-disassembler"></a>SWIFT 反汇编程序
入站的接收管道处理所有消息提交到[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]（在接收位置收到） 的应用程序。  
  
 与 BizTalk 的入站的处理构成的逻辑执行阶段接收管道。 管道组件服务，或实现每个阶段。 具体而言，拆装器服务在接收管道的拆装阶段。 A4SWIFT 提供特定于 SWIFT 的消息处理中的自定义拆装器组件的功能。  
  
 SWIFT 反汇编程序，自定义的平面文件拆装器提供功能，用于处理入站 SWIFT 消息和批处理，并执行以下功能：  
  
- 动态发现消息类型和解析文档架构  
  
- 将 SWIFT 平面文件分析为 XML  
  
- 调用验证读取器执行 XML （架构） 验证 XML  
  
- 调用业务规则引擎 (BRE) 执行 BRE 验证  
  
- 将已分析的 XML 消息发布到 MessageBox 数据库使用已升级的上下文属性和序列化的错误集合 XML  
  
- 处理和反汇编入站的批处理  
  
  下图显示了 SWIFT 反汇编程序数据流。  
  
  ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
  SWIFT 反汇编程序有关的详细信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)