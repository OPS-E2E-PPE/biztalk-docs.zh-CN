---
title: "XML 信息在 XML 反汇编程序管道组件中设置元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], information set
- XML Disassembler [pipeline component], processing instructions
- pipeline components, XML Disassembler
ms.assetid: cc82344c-6c4b-4154-a662-0b7ae5caad30
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90b3140cbe23637160aafabdccb37104efd1d318
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a>XML 信息集 XML 反汇编程序管道组件中的元素
XML 拆装器按如下方式处理 XML 信息集合元素：  
  
|元素|Description|  
|-------------|-----------------|  
|comment|注释保留在文档中；但不保留 XML 信封中的任何注释。|  
|CDATA|CDATA 保留在文档中。 但不保留显示在文档外部（如信封中）的 CDATA 元素。|  
|处理指令|XML 拆装器保留显示在 XML 文档中或 XML 文档之前的处理指令。 不保留显示在 XML 文档之后或信封前后的处理指令。|  
|XML 声明|删除所有传入 XML 消息的 XML 声明元素。|  
  
## <a name="see-also"></a>另请参阅  
 [XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)