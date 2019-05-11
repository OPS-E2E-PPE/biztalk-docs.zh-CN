---
title: 创建管道项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b584e3ab-e824-4977-b4ed-4fc197a6cf7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f2e4ee625bd21dd16d58e5e75121de3a5c26308
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378454"
---
# <a name="creating-a-pipeline-project"></a>创建管道项目
若要创建管道项目：  
  
1.  在 Visual Studio 中，创建新的 BizTalk 项目。  
  
2.  将接收管道项和发送管道项添加到项目。  
  
3.  打开 ReceivePipeline.btp 文件。  
  
4.  在管道设计器中，打开工具箱。  
  
5.  右键单击**工具箱**图面，然后选择**选择项**。  
  
6.  在选择工具箱项窗口中，单击**管道组件**卡，并选择以下管道组件：  
  
    -   SwiftMXDisassembler  
  
    -   SwiftMXAssembler  
  
    -   Swift MXRR 编码器组件  
  
    -   Swift MXRR 解码器组件  
  
    -   Swift MXRR 相关参与方解析器组件  
  
7.  拖动**SwiftMXDisassembler**组件在接收管道中拆装器占位符。  
  
8.  在 SwiftMXDisassembler 组件属性中，设置**BRE 验证**属性设置为 TRUE 或 FALSE 具体取决于是否想要启用对传入的消息的业务规则验证。 设置**TransportHeaderRequired**属性设置为 TRUE 或 FALSE 具体取决于是否想要提供在消息的传输标头。  
  
9. 将 Swift MXRR 解码器和 Swift MXRR 相关参与方解析程序组件拖入解码器，并在接收管道的参与方解析程序占位符。  
  
10. 选择**MXRR 相关参与方解析程序**管道中。 在管道组件属性窗口中设置**启用 BAM 日志记录对帐**属性设置为 TRUE 或 FALSE，具体取决于是否想要启用的 SWIFT 响应对帐。  
  
11. 打开**SendPipeline.btp**文件，在管道设计器中，打开**工具箱**。  
  
12. 在工具箱中拖动**SwiftMXAssembler**组件到在发送管道的组装器占位符。  
  
13. 拖动**Swift MXRR 编码器**组件到发送管道的编码器占位符。  
  
14. 选择**MXRR 编码器参与方解析程序**在管道中，然后在管道组件属性窗口中，设置以下属性。  
  
15. 启用**BAM 日志记录对帐**为 TRUE 或 FALSE 具体取决于是否想要启用的 SWIFT 响应对帐。  
  
16. 设置**所需的 LAU**为 TRUE 或 FALSE 具体取决于是否必须启用消息在 SWIFT 联盟访问 (SAA) 的签名。  
  
17. 如果已启动所需属性已设置为 TRUE，然后提供 LAU 密钥第一部分和启动密钥第二部分 （值必须是相同的配置 SAA 时提供的。）  
  
18. 生成，然后部署该项目。