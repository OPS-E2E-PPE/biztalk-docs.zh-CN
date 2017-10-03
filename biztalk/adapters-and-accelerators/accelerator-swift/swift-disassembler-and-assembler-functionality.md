---
title: "SWIFT 反汇编程序和汇编程序功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0109979fbb9bf61fc0e1be833061b2a15b470690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler-and-assembler-functionality"></a>SWIFT 反汇编程序和汇编程序功能
SWIFT 反汇编程序可以执行以下任务中调用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道：  
  
-   动态发现消息类型和解决文档架构。 这使单个接收端口和管道来处理多个 SWIFT 消息类型。  
  
-   为 XML 分析 SWIFT 平面文件。  
  
-   调用验证读取器以执行 XML （架构） 验证，例如数据类型有效性、 数据格式或长度一致性检查的 XML。  
  
-   调用以执行 BRE 验证，例如检查符合 SWIFT 网络规则或执行其他复杂的验证架构不实现业务规则引擎 (BRE)。  
  
-   将已分析的 XML 消息发布到 MessageBox 数据库使用提升的上下文属性和序列化的错误集合 XML （提供有关在分析或验证过程中遇到任何错误的信息）。  
  
    > [!NOTE]
    >  如果反汇编程序在分析过程中遇到严重故障，拆装器将将消息发布到 MessageBox 数据库在本机平面文件格式，而不是 XML。  
  
-   处理入站的批处理，如下所示：  
  
    -   分析并保留批处理信封 （批处理标头，批处理尾）  
  
    -   分析并保留消息信封 （消息标头、 消息尾部）  
  
    -   分析和单独验证 SWIFT 批处理中的消息  
  
    -   单独将 SWIFT 消息发布到 MessageBox 数据库  
  
    -   将整个的入站的批处理发布到 MessageBox 数据库中，为一条消息 （输入的准确副本）  
  
    -   提升排序或关联从同一个批处理发出的消息的批处理相关的上下文属性  
  
 SWIFT 汇编程序可以执行以下任务时 BizTalk 发送管道中进行调用：  
  
-   动态发现消息类型和解决的文档架构。 这样，一个发送端口和管道来处理多个 SWIFT 消息类型。  
  
-   已分析的 XML 序列化为 SWIFT 平面文件。  
  
## <a name="see-also"></a>另请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)