---
title: "创建管道项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b584e3ab-e824-4977-b4ed-4fc197a6cf7a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eead267abbb990933e6fd3150d099d07b007526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-pipeline-project"></a>创建管道项目
若要创建管道项目：  
  
1.  在 Visual Studio 中，创建一个新的 BizTalk 项目。  
  
2.  将接收管道项和发送管道项添加到项目中。  
  
3.  打开 ReceivePipeline.btp 文件。  
  
4.  在管道设计器中，打开工具箱。  
  
5.  右键单击**工具箱**图面，，然后选择**选择项**。  
  
6.  在选择工具箱项窗口中，单击**管道组件**选项卡上，然后选择以下的管道组件：  
  
    -   SwiftMXDisassembler  
  
    -   SwiftMXAssembler  
  
    -   Swift MXRR 编码器组件  
  
    -   Swift MXRR 解码器组件  
  
    -   Swift MXRR 相关当事方冲突解决程序组件  
  
7.  拖动**SwiftMXDisassembler**组件到反汇编程序占位符接收管道中。  
  
8.  在 SwiftMXDisassembler 组件属性中，设置**BRE 验证**具体取决于是否想要对传入消息启用业务规则验证属性设置为 TRUE 或 FALSE。 设置**TransportHeaderRequired**具体取决于是否想要提供的消息中传输标头属性设置为 TRUE 或 FALSE。  
  
9. 将 Swift MXRR 解码器和 Swift MXRR 相关方冲突解决程序组件拖到解码器和方冲突解决程序占位符内接收管道。  
  
10. 选择**MXRR 相关方冲突解决程序**管道中。 在管道组件属性窗口中，设置**启用 BAM 日志记录对帐**属性设置为 TRUE 或 FALSE，具体取决于是否想要启用 SWIFT 响应的对帐。  
  
11. 打开**SendPipeline.btp**文件，在管道设计器中，打开**工具箱**。  
  
12. 在工具箱中，拖动**SwiftMXAssembler**到汇编程序占位符内发送管道组件。  
  
13. 拖动**Swift MXRR 编码器**组件发送管道的编码器占位符。  
  
14. 选择**MXRR 编码器方冲突解决程序**在管线中，然后在管道组件属性窗口中，设置以下属性。  
  
15. 启用**BAM 日志记录对帐**TRUE 或 FALSE，具体取决于是否想要启用 SWIFT 响应的对帐。  
  
16. 设置**所需的 LAU** TRUE 或 FALSE，具体取决于是否必须启用的消息在 SWIFT 联盟访问 (SAA) 的签名。  
  
17. 如果所需的 LAU 属性已设置为 TRUE，然后提供 LAU 密钥第一个部分和 LAU 密钥第二个部分 （值必须是相同的配置 SAA 时提供。）  
  
18. 生成然后部署项目。