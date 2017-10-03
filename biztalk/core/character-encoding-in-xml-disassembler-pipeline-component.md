---
title: "XML 反汇编程序管道组件中的字符编码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], character encoding
- XMLNorm.SourceCharset property
ms.assetid: 37962bdc-cbcb-4559-9ae8-6c4be49b4822
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b0e307f2f608cde266e7a566fb3005bde048c31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a>XML 反汇编程序管道组件中的字符编码
XML 拆装器使用以下算法来确定用于处理传入消息的编码：  
  
1.  如果数据中存在字节顺序标记，则根据该标记确定编码信息。  
  
2.  否则为如果**IBaseMessagePart.Charset**属性设置，则使用此处指定该编码方式。  
  
3.  否则，如果 XML 文档中存在 XML 声明，则使用其中指定的编码（假设 XML 声明为 ANSI 格式）。  
  
4.  否则，将使用 UTF-8 编码。  
  
 对于上述情况 2、 3 和 4，，XML 反汇编程序确定的编码后，它将其保存在消息上下文中**XMLNorm.SourceCharset**属性。 由 XML 拆装器管道组件生成的消息始终使用 UTF-8 编码。 对于第 1 种情况，不保留从字节顺序标记确定的编码。  
  
## <a name="see-also"></a>另请参阅  
 [XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)