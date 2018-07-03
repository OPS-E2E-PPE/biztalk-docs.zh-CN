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
ms.openlocfilehash: 0ca8b90765b2b00803f5b8eb6a22c59ed6b43776
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966110"
---
# <a name="disassembly-stage-recoverable-interchange-processing"></a>拆装阶段（可恢复交换处理）
在这两种模式中的拆装阶段处理交换：  
  
-   **标准模式。** 如果接收管道的拆装器组件配置为执行标准拆装，交换中包含的消息将被提取、由接收管道处理、映射并发布为工作的事务单元。 也就是说，整个交换和其包含的消息被完全处理并发布到 MessageBox 数据库中，或者交换被放置在挂起队列中。  
  
-   **可恢复模式。** 当接收管道的拆装器组件配置为执行**可恢复交换处理**，互相独立地提取交换中包含的消息。 成功提取的消息随后将向下传播到接收管道。 在交换内找出、但未能成功提取的消息将放置在挂起队列中。  
  
## <a name="examples"></a>示例  
 以下示例说明了几个交换处理方案：  
  
### <a name="example-1"></a>示例 1  
 在此示例中，在标准交换接收位置上提交以下伪交换。 即接收管道中的拆装器组件配置用于标准交换处理。  
  
```  
<Interchange>  
<Document1>...</Document1>  
<Document2 failure=”routing”>...</Document2>  
<Document3>...</Document3>  
<Document4 failure=”pipeline” recoverableError=”true”>...</Document4>  
<Document5>...</Document5>  
</Interchange>  
```  
  
 此交换包含五个消息，全都是拆装器从交换成功提取的消息。 按如下方式处理这些消息：  
  
- 第一个、第二个和第三个消息通过管道进行传播，并且可发布。  
  
- 第四个消息在管道的拆装阶段处理失败。 这将导致已处理的所有消息回滚，原始交换消息作为可恢复的消息挂起。  
  
  提交的结果为：  
  
- 不发布任何内容。 原始交换被挂起，因为在标准交换处理中，在交换处理期间或之后的任何时刻失败的任何提取消息都将导致所有提取的消息被放弃，并且原始交换作为可恢复的交换放置在挂起队列中。  
  
### <a name="example-2"></a>示例 2  
 该示例使用与上例相同的交换处理和传播方案，除了拆装阶段配置为执行可恢复交换处理。  
  
 提交的结果为：单个提取的消息都被处理，原始交换被放弃。 按如下所示处理各个消息：  
  
-   第一个、第二个和第三个消息通过管道进行传播，并且可发布。  
  
-   第四个消息拆装处理失败（即提取该消息后出错），并且可挂起。  
  
-   第五个消息通过管道进行传播，并且可发布。  
  
-   在从交换中提取了所有消息后，消息 1、2、3 和 5 将发布到 MessageBox 数据库中，消息 4 将放置在挂起队列。 消息 2 也将重定向到挂起队列，因为路由由于没有匹配的订户而失败。  
  
## <a name="configuring-recoverable-interchange-processing"></a>配置可恢复的交换处理  
 可恢复的交换处理是接收管道的拆装器组件的一个属性。 并非所有的拆装器组件都允许您指定可恢复的交换处理；例如，本地 BizTalk 框架拆装器就不允许。 如果某一拆装器支持可恢复交换处理，则在管道设计器中指定此行为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到所设计的管道的拆装阶段添加拆装器组件时。 所选拆装器拖到管道的拆装阶段之后，设置可恢复交换处理属性为该拆装器组件的`true`。  
  
### <a name="party-resolution"></a>参与方解析  
 在可恢复的交换处理中成功提取的消息将根据为相应父交换到达的接收端口配置的参与方来标识其发送方。 如果参与方解析对于从给定交换提取的任何消息失败，则认为参与方解析对于整个交换失败。  
  
### <a name="restrictions"></a>限制  
  
-   当某个交换在拆装器中失败时，该交换将作为可恢复交换被挂起。 但是，如果管理性地恢复该交换，它将再次失败，因为导致拆装失败的这些类型的错误只是交换内容的结果，其在恢复交换时将保持相同。 必须修改此类失败的交换，并通过接收位置重新提交相应交换。  
  
-   如果从交换成功提取的消息随后由于不匹配的订户无法通过消息传送传播，则该将消息作为可恢复消息挂起。 如果解决了导致路由失败的问题，则可以管理性地恢复此消息。  
  
-   即使拆装器组件中出现以下错误，拆装器组件也将继续从交换中提取消息：  
  
    -   找不到架构  
  
    -   未解决架构不明确问题（即，对于同一消息类型存在多个架构）  
  
    -   XML 验证失败  
  
    -   平面文件解析失败  
  
-   拆装器组件实现**不**继续从交换中提取消息，如果拆装器组件中出现以下错误：  
  
    -   文档数据不是格式正确的 XML—将导致 System.Xml.XmlReader 失败的任何文档属性  
  
## <a name="see-also"></a>请参阅  
 [如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)   
 [如何配置平面文件拆装器管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)