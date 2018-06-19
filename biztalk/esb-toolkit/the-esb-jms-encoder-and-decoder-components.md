---
title: ESB JMS 编码器和解码器组件 |Microsoft 文档
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
ms.openlocfilehash: 9f39f4ab1b0650a8ad6fa1ff35d62b4807995237
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295677"
---
# <a name="the-esb-jms-encoder-and-decoder-components"></a>ESB JMS 编码器和解码器组件
某些集成解决方案涉及到 Java 消息服务 (JMS) 和 SOAP 消息发送到数据库或从 IBM WebSphere MQ;[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括用在这些情况下使用的托管代码编写的两个 JMS 管道组件。 组件读取或写入 MQ 消息标头使用与消息关联的上下文属性的值的 JMS 部分。 目前，有 60 多个不同类型的 JMS 中与 WebSphere MQ 系列系统; 一起使用的标头ESB JMS 组件只使用 MQRFH2 标头。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装 BizTalk Server 管道组件文件夹中的 JMS 编码器和 JMS 解码器组件。  
  
## <a name="how-it-works"></a>它是如何工作  
 JMS 管道组件检查消息头，并仅对消息进行操作**MQMD_Format**标头设置为**RFH (MQRFH2)**。 但是，即使设置此属性，组件会检查以确认它们符合 IBM RFH2 格式的标头。 如果标头不符合此格式，组件都会生成分析错误，该值指示**MQMD_Format**参数设置为**RFH (MQRFH2)**，但不是符合的标头结构RFH2 标准。 如果分析的入站的消息标头失败，解码器组件允许消息传递，但它将设置一个名为消息上下文属性**MQRFH2_ParseError**到**True**。  
  
 **MQRFH2**属性架构部署在 BizTalk 通过 JMS 组件公开的所有 MQRFH2 标头属性。 在降级传入消息的标头，标头中的数据将驻留在 XML 文档存储在**MQRFH2_NameValueData**消息上下文属性。 编码器调整的长度**NameValueData**文件夹以确保它是正确的长度。 若要了解使用这些标头，以及影响在更改值时，查看相应的 IBM 文档。  
  
## <a name="using-the-jms-encoder-and-decoder-components"></a>使用 JMS 编码器和解码器组件  
 若要使用的 JMS 编码器和解码器组件，开发人员将它们添加到 BizTalk 应用程序中的管道。 发送管道，JMS 编码器组件应驻留在编码阶段。 接收管道，JMS 解码器组件应驻留在解码阶段。 JMS 组件将不安装任何其他阶段的管道中。  
  
 JMS 编码器组件安装在编码阶段中，当读取 JMS 中的值**MQRFH2**标头和写入 （提升） 消息上下文属性中。 JMS 解码器组件安装在解码阶段中，当读取 （将降级） 的上下文属性值，并将其插入到 JMS **MQRFH2**标头。 这意味着所有 MQ 标头值都是可用作管道中消息的上下文属性。  
  
 若要检测和管理标头分析错误，开发人员可以包括检查的值的代码**MQRFH2_ParseError**属性。 它们可以实现订阅失败的消息的恢复进程或指定对筛选发送端口**MQRFH2_ParseError**属性将该消息保存。 使用 JMS 消息的订阅服务器应包括指定的值的筛选器条件**False**为**MQRFH2_ParseError**属性来阻止订阅服务器接收消息失败分析进程的标头。  
  
 开发人员还可以更新的上下文属性值 (例如，更改**MQRFH2_Encoding**属性值)，该组件将反映 MQ 消息标头中的这些更改，以便它们设置消息到达时其最终目标。 该组件会自动将忽略无效的值，并设置"安全"默认值缺少必需的标头在哪里。 例如，如果开发人员已指定的值无效**MQRFH2_Encoding**属性，出站消息将具有**MQRFH2_Encoding**标头设置为**未知**. 如果开发人员从上下文属性中删除一个值，但**MQMD_Format**属性仍将设置为**RFH**，该组件将添加包含默认值，根据 IBM 规范的标头。  
  
 有关如何使用这些组件的示例，请参阅[安装和运行 JMS MQRFH2 组件示例](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)。