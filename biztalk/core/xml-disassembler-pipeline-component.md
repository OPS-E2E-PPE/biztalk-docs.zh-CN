---
title: XML 拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], about XML Disassembler
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component]
ms.assetid: ef39b695-6ae7-401d-be1e-b066048c34e9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 634d007e2545dfd89457239fe4d05f86a1c90aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246379"
---
# <a name="xml-disassembler-pipeline-component"></a>XML 拆装器管道组件
XML 拆装器管道组件将 XML 解析功能和拆装到一个组件相结合。 其主要功能如下：  
  
- 删除信封。  
  
- 对交换进行拆装。  
  
- 升级的内容属性从交换级别和单个文档级别到消息上下文。  
  
  收到信封后，XML 拆装器组件执行下列操作：  
  
1. 使用以静态方式在设计时与组件关联的信封架构或动态确定在运行时从消息类型的信封架构，拆装器将对信封。 架构用于验证在信封解析过程的信封的结构。 如果未定义信封结构，它以递归方式找到通过使用根节点的命名空间和基名称查找架构。  
  
2. 拆装器组件将分析对信封内的每个文档。 对于每个文档，使用它自己获取复制升级从信封和文档本身的所有属性创建 BizTalk 消息对象。 该组件通过使用预定义的 Xpath 编码为与信封和消息相关联的 XSD 架构中的批注中提取内容属性从信封和消息实例。 信封架构，以及各文档架构相关联在管道设计器中的拆装器组件。  
  
   XML 拆装器只处理消息的正文部分中的数据。 因此，可以升级仅从正文部分的属性。 升级属性时，使用可提升的属性关联的字段中的日期时间值获取转换为 UTC。 非正文部分将复制到输出消息保持不变。  
  
> [!NOTE]
>  XML 拆装器管道组件当前强制转换为 UTC 的所有日期时间属性到达消息库之前。 BizTalk Server 使用 SQL 日期时间类型在内部，而不一定时间区域相关信息。 如果在业务流程中生成的日期时间属性，然后尝试将其用于与后续消息相关，它可能无法正常工作，因为 XML 拆装器管道组件将其转换为响应 UTC，并将 Microsoft SQL Server有没有办法识别为相同的原始和响应时间字段。 同样，查看消息事件和服务实例跟踪数据时可能会遇到差异。  
  
 有关配置 XML 拆装器管道组件的信息，请参阅[如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XML 反汇编程序管道组件中的 XML 信息集合元素](../core/xml-information-set-elements-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 反汇编程序管道组件中无法识别的消息](../core/unrecognized-messages-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 反汇编程序管道组件中的文档验证](../core/document-validation-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 反汇编程序管道组件中的文档结构强制规定](../core/document-structure-enforcement-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 反汇编程序管道组件中的字符编码](../core/character-encoding-in-xml-disassembler-pipeline-component.md)  
  
-   [演练：使用 XML 信封 （基础）](../core/walkthrough-using-xml-envelopes-basic.md)