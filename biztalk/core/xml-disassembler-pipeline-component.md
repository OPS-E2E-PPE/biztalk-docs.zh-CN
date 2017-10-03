---
title: "XML 反汇编程序管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], about XML Disassembler
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component]
ms.assetid: ef39b695-6ae7-401d-be1e-b066048c34e9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3346cdbfeed14e933039d7866e174c833f17212e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-disassembler-pipeline-component"></a>XML 拆装器管道组件
XML 拆装器管道组件将 XML 解析功能和拆装功能组合到一个组件中。 该组件的主要功能如下：  
  
-   删除信封。  
  
-   对交换进行拆装。  
  
-   将内容属性从交换级别和单个文档级别升级到消息上下文。  
  
 收到信封后，在 XML 拆装器组件中将发生以下操作：  
  
1.  该拆装器通过使用在设计时与该组件关联的信封架构来静态地解析信封，或通过在运行时根据消息类型确定信封架构来动态地解析信封。 架构用于在信封解析过程中对信封的结构进行验证。 如果未定义信封结构，则可通过使用根节点的命名空间和基名称查找架构，从而以递归方式确定信封结构。  
  
2.  该拆装器组件将对信封内的每个文档进行解析。 对于每个文档，BizTalk 消息对象都使用其本身的上下文创建，从信封和文档本身升级的所有属性均是从此上下文中复制而来。 该组件通过使用预定义的 XPath（编码为与信封和消息相关联的 XSD 架构中的批注）从信封和消息实例中提取内容属性。 信封架构以及各文档架构均与管道设计器中的拆装器组件关联。  
  
 XML 拆装器只处理消息正文部分中的数据。 因此，只有正文部分的属性可以升级。 升级属性时，与可升级属性关联的字段中的日期时间值将转换为 UTC 格式。 非正文部分将不做更改直接复制到输出消息。  
  
> [!NOTE]
>  目前，XML 拆装器管道组件在日期时间属性到达消息库前将所有日期时间属性强制转换为 UTC 格式。 BizTalk Server 在内部使用不包含时区信息的 SQL 日期时间类型。 如果在业务流程中生成一个日期时间属性，然后尝试使用该属性以便与后续消息相关，则该属性可能无法正常工作，因为 XML 拆装器管道组件会在响应时将其转换为 UTC 格式，而 Microsoft SQL Server 却无法将原始时间字段和响应时间字段识别为相同字段。 同样，查看消息事件和服务实例跟踪数据时，也可能会遇到差异。  
  
 有关配置 XML 反汇编程序管道组件的信息，请参阅[如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XML 信息集 XML 反汇编程序管道组件中的元素](../core/xml-information-set-elements-in-the-xml-disassembler-pipeline-component.md)  
  
-   [无法识别的消息中 XML 反汇编程序管道组件](../core/unrecognized-messages-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 反汇编程序管道组件中的文档验证](../core/document-validation-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 反汇编程序管道组件中的文档结构强制](../core/document-structure-enforcement-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 反汇编程序管道组件中的字符编码](../core/character-encoding-in-xml-disassembler-pipeline-component.md)  
  
-   [演练： 使用 XML 信封 (Basic)](../core/walkthrough-using-xml-envelopes-basic.md)