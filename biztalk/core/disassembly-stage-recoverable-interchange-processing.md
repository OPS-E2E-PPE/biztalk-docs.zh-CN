---
title: 反汇编阶段 （可恢复的交换处理） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 552b1e90-f75d-4713-8c7b-155a52819308
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81be8a4ca330c1ef48bbbb67a2de1b1c9d049f33
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530863"
---
# <a name="disassembly-stage-recoverable-interchange-processing"></a>反汇编阶段 （可恢复的交换处理）
在这两种模式中的拆装阶段处理交换：  
  
-   **标准模式。** 当接收管道的拆装器组件配置为执行标准拆装时，交换中包含的消息是提取、 由接收管道处理、 映射，并发布为事务性工作单元。 也就是说，整个交换和其包含的消息完全处理并发布到 MessageBox 数据库，或者交换被放置在挂起队列中。  
  
-   **可恢复模式。** 当接收管道的拆装器组件配置为执行**可恢复交换处理**，互相独立地提取交换中包含的消息。 已成功提取的消息传播进一步沿接收管道。 交换中标识，但未能成功提取的消息将放置在挂起队列中。  
  
## <a name="examples"></a>示例  
 以下示例说明了交换处理方案。  
  
### <a name="example-1"></a>示例 1  
 在此示例中，将标准提交以下伪交换的交换接收位置。 也就是说，在接收管道的拆装器组件配置为标准交换处理。  
  
```  
<Interchange>  
<Document1>...</Document1>  
<Document2 failure=”routing”>...</Document2>  
<Document3>...</Document3>  
<Document4 failure=”pipeline” recoverableError=”true”>...</Document4>  
<Document5>...</Document5>  
</Interchange>  
```  
  
 此交换包含五个消息时，所有这些拆装器已成功从提取交换。 它们进行处理，如下所示：  
  
- 第一，第二和第三个消息通过管道进行传播并准备好发布。  
  
- 第四个消息处理管道的拆装阶段失败。 这将导致已得到处理要回滚的所有消息和要作为可恢复挂起的原始交换消息。  
  
  提交的结果是：  
  
- 不发布任何内容。 原始交换被挂起，因为在标准交换处理的交换处理期间或之后在任何时刻失败的任何提取的消息会导致所有提取的消息被放弃和原始交换被放置在作为可恢复已挂起队列。  
  
### <a name="example-2"></a>示例 2  
 该示例与上面的示例中，使用相同的交换处理和传播方案，只不过拆装阶段配置为执行可恢复交换处理。  
  
 提交的结果是所有处理单个提取的消息，原始交换被放弃。 按如下所示处理各个消息：  
  
-   第一，第二和第三个消息通过管道进行传播并准备好发布。  
  
-   第四个消息拆装处理失败 （即后出现问题则将提取） 并已准备好将挂起。  
  
-   第五个消息通过管道进行传播，并已准备好发布。  
  
-   从交换中提取所有消息后，消息 1、 2、 3 和 5 将发布到 MessageBox 数据库中，并且消息 4 将放置在挂起队列。 消息 2 也将重定向到挂起队列由于路由失败的原因是没有匹配的订户。  
  
## <a name="configuring-recoverable-interchange-processing"></a>配置可恢复交换处理  
 可恢复交换处理是接收管道的拆装器组件的属性。 并非所有的拆装器组件允许您指定可恢复交换处理;例如，本机 BizTalk 框架拆装器不。 如果某一拆装器支持可恢复交换处理，则在管道设计器中指定此行为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到所设计的管道的拆装阶段添加拆装器组件时。 所选拆装器拖到管道的拆装阶段之后，设置可恢复交换处理属性为该拆装器组件的`true`。  
  
### <a name="party-resolution"></a>参与方解析  
 可恢复交换处理中成功提取的消息具有为相应父交换到达的接收端口配置的参与方根据标识其发送方。 如果从给定交换提取的任何消息的参与方解析失败，则认为参与方解析对于整个交换失败。  
  
### <a name="restrictions"></a>限制  
  
-   当交换在拆装器失败时，将挂起交换作为可恢复。 但是，如果管理性地恢复该交换，它将无法再次因为导致拆装失败的错误的类型是完全保持不变时恢复该交换的交换内容的结果。 此类失败的交换必须修改并重新提交通过接收位置。  
  
-   如果已成功提取来自交换随后的消息无法通过不匹配的订户由于消息传送传播，作为可恢复挂起消息。 如果路由失败的原因固定，可管理性地恢复此消息。  
  
-   拆装器组件将继续从交换拆装器组件中显示以下错误尽管中提取消息：  
  
    -   找不到架构  
  
    -   未解析的架构不明确问题 （即，多个架构相同的消息类型存在）  
  
    -   XML 验证失败  
  
    -   平面文件解析失败  
  
-   拆装器组件实现**不**继续从交换中提取消息，如果拆装器组件中出现以下错误：  
  
    -   文档数据不是格式正确 XML — 将导致 System.Xml.XmlReader 失败的任何文档属性  
  
## <a name="see-also"></a>请参阅  
 [如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)   
 [如何配置平面文件拆装器管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)