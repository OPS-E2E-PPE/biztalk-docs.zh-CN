---
title: SWIFT 汇编程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler
- send pipelines, messages
- messages, send pipelines
ms.assetid: 2a95c7d4-da10-4058-bc2c-3efc35958e14
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f89720a36c026fa0e8f02902a8fefb08fcebf9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973310"
---
# <a name="swift-assembler"></a>SWIFT 汇编程序
出站发送管道处理所有消息传送的[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]（通过发送端口发送） 的应用程序。  
  
 与出站处理相关的逻辑执行阶段组成 BizTalk 发送管道。 管道组件服务，或实现每个阶段。 特别是，则组装器服务在接收管道的组装阶段。 A4SWIFT 提供特定于 SWIFT 的出站消息处理中的自定义组装器组件的功能。  
  
 SWIFT 汇编程序，自定义的平面文件组装器处理出站 SWIFT 消息，提供功能，并执行以下功能：  
  
- 动态发现消息类型和解析文档架构  
  
- 将已分析的 XML 序列化到 SWIFT 的平面文件  
  
  下图显示了 SWIFT 汇编程序数据流。  
  
  ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
  SWIFT 汇编程序的详细信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)