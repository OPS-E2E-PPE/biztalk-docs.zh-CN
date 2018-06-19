---
title: SWIFT 反汇编程序 |Microsoft 文档
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
ms.openlocfilehash: ac0024abe862f777e7ee798991d97845ec5098a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214181"
---
# <a name="swift-disassembler"></a>SWIFT 反汇编程序
入站的接收管道处理所有消息提交到[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]（在接收位置接收） 的应用程序。  
  
 与 BizTalk 的入站的处理构成的逻辑执行阶段接收管道。 管道组件服务或实现的每个阶段。 具体而言，拆装器服务中接收管道的拆装阶段。 A4SWIFT 提供 SWIFT 特定消息处理自定义反汇编程序组件中的功能。  
  
 SWIFT 拆装器，自定义的平面文件拆装器，用于处理 SWIFT 的入站的消息和批处理，提供功能，并执行以下功能：  
  
-   动态发现消息类型，并解析文档架构  
  
-   为 XML 分析 SWIFT 平面文件  
  
-   调用验证读取器执行 XML （架构） 验证的 XML  
  
-   调用以执行 BRE 验证业务规则引擎 (BRE)  
  
-   将已分析的 XML 消息发布到 MessageBox 数据库使用提升的上下文属性和序列化的错误集合 XML  
  
-   处理并进行反汇编，入站的批处理  
  
 下图显示了 SWIFT 反汇编程序数据流。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
 SWIFT 反汇编程序有关的详细信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)