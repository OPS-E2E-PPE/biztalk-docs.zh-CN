---
title: ESB JMS 编码器和解码器组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e5591c2-d2ca-4168-8026-059fe51dd588
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7c1be49757872021ab19b419eb0042261a76e15
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399778"
---
# <a name="the-esb-jms-encoder-and-decoder-components"></a>ESB JMS 编码器和解码器组件
一些集成的解决方案涉及到 Java 消息服务 (JMS) 和 SOAP 消息发送到或从 IBM WebSphere MQ;[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括两个 JMS 管道组件在这些情况下使用的托管代码编写的。 组件读取或写入 MQ 消息标头使用与消息关联的上下文属性的值的 JMS 部分。 目前，有 60 多个不同类型的 JMS 标头中与 WebSphere MQ Series 系统; 结合使用ESB JMS 组件仅使用 MQRFH2 标头。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心 BizTalk Server 管道组件文件夹中安装 JMS 编码器和 JMS 解码器组件。  
  
## <a name="how-it-works"></a>其工作原理  
 JMS 管道组件检查消息标头和仅对具有的消息**MQMD_Format**标头设置为**RFH (MQRFH2)**。 但是，即使设置此属性，组件会检查以确认它们符合为 IBM RFH2 格式的标头。 如果标头不符合此格式，组件会生成分析错误，指示**MQMD_Format**参数设置为**RFH (MQRFH2)**，但不是符合的标头的结构RFH2 标准。 如果入站的消息标头分析失败，解码器组件允许消息传递，但它名为消息上下文属性设置**MQRFH2_ParseError**到**True**。  
  
 **MQRFH2**与 JMS 组件部署在 BizTalk 属性架构公开所有 MQRFH2 标头属性。 在降级的传入消息的标头，从标头的数据驻留在 XML 文档存储在**MQRFH2_NameValueData**消息上下文属性。 编码器调整的长度**NameValueData**文件夹，以确保它是正确的长度。 若要了解这些标头和影响的使用情况，在更改值时，查看相应的 IBM 文档。  
  
## <a name="using-the-jms-encoder-and-decoder-components"></a>使用 JMS 编码器和解码器组件  
 若要使用的 JMS 编码器和解码器组件，开发人员将它们添加到 BizTalk 应用程序中的管道。 为发送管道，JMS 编码器组件应位于编码阶段。 接收管道，JMS 解码器组件应驻留在解码阶段中。 JMS 组件将不安装任何其他阶段的管道中。  
  
 JMS 编码器组件的编码阶段在安装时，读取的值中将 JMS **MQRFH2**标头和写入 （升级） 到消息上下文属性。 在解码阶段安装时，读取 JMS 解码器组件 （将降级） 的上下文属性值，并将其插入到 JMS **MQRFH2**标头。 这意味着所有 MQ 标头值都为上下文属性在管道中消息的形式提供。  
  
 若要检测和管理标头分析错误，开发人员可以添加代码来检查的值**MQRFH2_ParseError**属性。 它们可以实现订阅失败消息的恢复过程，也可以指定发送端口的筛选**MQRFH2_ParseError**属性将该消息保存。 使用 JMS 消息的订阅服务器应包含指定的值的筛选器条件**False**有关**MQRFH2_ParseError**属性来防止订阅者接收消息失败分析过程的标头。  
  
 开发人员还可以更新上下文属性值 (例如，更改**MQRFH2_Encoding**属性值)，并且该组件将反映的 MQ 消息标头中的这些更改，以使它们设置消息到达时其最终目标。 该组件会自动将忽略无效的值，并设置"安全"默认值必需的标头会缺失。 例如，如果开发人员指定的值无效**MQRFH2_Encoding**属性，出站消息将具有**MQRFH2_Encoding**标头设置为**未知**. 如果开发人员从上下文属性中删除一个值，但**MQMD_Format**属性仍设置为**RFH**，该组件将添加包含默认值，根据 IBM 规范的标头。  
  
 有关如何使用这些组件的示例，请参阅[安装和运行 JMS MQRFH2 组件示例](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)。