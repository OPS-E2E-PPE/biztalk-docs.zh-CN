---
title: SWIFT 汇编程序 |Microsoft 文档
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
ms.openlocfilehash: 91d9411cce90079e8a84fc6919bd6ebf8b2b4371
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214429"
---
# <a name="swift-assembler"></a>SWIFT 汇编程序
出站发送管道处理所有消息传输的[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]（通过发送端口发送） 的应用程序。  
  
 与出站处理相关的逻辑执行阶段构成了 BizTalk 发送管道。 管道组件服务或实现的每个阶段。 具体而言，汇编程序服务中接收管道的装配阶段。 A4SWIFT 提供特定于 SWIFT 的出站消息处理自定义汇编程序组件中的功能。  
  
 SWIFT 汇编程序，一个自定义的平面文件的汇编程序，用于处理出站 SWIFT 消息，提供功能，并执行以下功能：  
  
-   动态发现消息类型，并解析文档架构  
  
-   将已分析的 XML 序列化到 SWIFT 平面文件  
  
 下图显示了 SWIFT 汇编程序数据流。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
 SWIFT 汇编程序有关的详细信息，请参阅[使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)