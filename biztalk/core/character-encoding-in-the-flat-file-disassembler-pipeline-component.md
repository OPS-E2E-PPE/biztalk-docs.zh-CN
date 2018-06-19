---
title: 平面文件反汇编程序管道组件中的字符编码 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, Flat File Disassembler
- Flat File Disassembler [pipeline component], character encoding
ms.assetid: 0dbe24fb-c431-4edf-8aa9-4c040d6a7b32
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 839a3377f27417757e394c946fe96acc83752355
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231637"
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a>平面文件反汇编程序管道组件中的字符编码
平面文件拆装器组件使用以下算法来确定哪些编码要用于处理传入消息：  
  
1.  如果数据中存在字节顺序标记，则根据该标记确定编码信息。 此编码的信息不会保留反汇编程序 (即，不保存到**XMLNorm.SourceCharset**属性)。  
  
2.  否则为如果**IBaseMessagePart.Charset**属性设置，则使用此处指定该编码方式。  
  
3.  或者，如果标题或文档架构包含代码页信息，则使用该信息。  
  
4.  否则，将使用 UTF-8 编码。  
  
 于上述情况 2、 3 和 4，拆装器会将编码信息保存在消息上下文中**XMLNorm.SourceCharset**属性。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md)   
 [如何配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)