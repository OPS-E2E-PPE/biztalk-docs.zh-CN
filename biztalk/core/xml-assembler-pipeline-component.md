---
title: XML 组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: 3adfd603-0577-49c2-ae9d-445d62fed385
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ed0d334539ae013a87d8caa293b55288e24becd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295603"
---
# <a name="xml-assembler-pipeline-component"></a>XML 组装器管道组件
XML 组装器管道组件将 XML 序列化和组装中有一个组件相结合。 其主要功能是将属性从消息上下文传输回信封和文档。  
  
 接收一批消息形成交换后，XML 组装器组件中执行以下操作：  
  
1.  在组装器通过使用指定的信封规范创建信封。  
  
2.  组件属性放入内容的消息实例通过使用预定义的 Xpath 编码为与消息关联的 XSD 架构中的批注。  
  
3.  该组件将消息附加到信封中。  
  
4.  该组件通过使用预定义的 Xpath 编码为与信封相关联的 XSD 架构中的批注在信封上将内容属性。  
  
> [!NOTE]
>  XML 组装器管道组件不会填充缺少的属性字段，但填充空元素字段时的字段是可选的但不是具有默认值或固定值。  
  
 有关配置 XML 组装器管道组件的信息，请参阅[如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XML 汇编程序管道组件中的字符编码](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML 汇编程序管道组件中的处理指令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML 汇编程序管道组件中无法识别的消息](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML 汇编程序管道组件中的 XML 信息集元素](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML 汇编程序管道组件中的文档结构强制规定](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)