---
title: "XML 汇编程序管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: 3adfd603-0577-49c2-ae9d-445d62fed385
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22348b61ca32567190fa99e103fe536f5199af58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-assembler-pipeline-component"></a>XML 汇编程序管道组件
XML 组装器管道组件将 XML 序列化和组装合并到一个组件中。 其主要功能是将属性从消息上下文传输回信封和文档。  
  
 在接收一批消息形成交换后，在 XML 组装器组件中将会出现以下操作：  
  
1.  组装器通过使用指定的信封规范创建信封。  
  
2.  该组件通过使用预定义的 XPath（编码为与消息相关联的 XSD 架构中的批注）将内容属性放入消息实例中。  
  
3.  该组件将消息附加到信封。  
  
4.  该组件通过使用预定义的 XPath（编码为与信封相关联的 XSD 架构中的批注）将内容属性放入信封中。  
  
> [!NOTE]
>  XML 组装器管道组件不填充缺少的属性字段，但如果空元素字段为可选字段但不具有默认值或固定值，则将填充这些空元素字段。  
  
 有关配置 XML 汇编程序管道组件的信息，请参阅[如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XML 汇编程序管道组件中的字符编码](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [处理 XML 汇编程序管道组件中的说明](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [无法识别的消息中 XML 汇编程序管道组件](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML 信息集 XML 汇编程序管道组件中的元素](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML 汇编程序管道组件中的文档结构强制](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)