---
title: "文档中的 XML 汇编程序管道组件的结构强制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46dbc613439b24403c66c345b9023151b409213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a>XML 汇编程序管道组件中的文档结构强制
如果在 XML 组装器中显式引用文档或信封架构，则 XML 组装器可确保仅处理消息类型与所引用的架构相应的文档。 不会对其他所有文档进行处理，即使可能已为这些文档部署了架构也是如此。  
  
> [!NOTE]
>  信封架构仅取自第一条消息。 信封的属性始终取自第一条消息。  
  
## <a name="see-also"></a>另请参阅  
 [XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)