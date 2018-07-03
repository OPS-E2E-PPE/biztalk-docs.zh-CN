---
title: 平面文件拆装器管道组件中的字符编码 |Microsoft Docs
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
ms.openlocfilehash: d2a7ef27ec23fb7470aff74df2915150f892e07a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988806"
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a>平面文件拆装器管道组件中的字符编码
平面文件拆装器组件使用以下算法来确定哪些编码要用于处理传入消息：  
  
1. 如果数据中存在字节顺序标记，则根据该标记确定编码信息。 拆装器不保留此编码信息 (即，不保存到**XMLNorm.SourceCharset**属性)。  
  
2. 否则为如果**IBaseMessagePart.Charset**属性设置，则使用指定的编码。  
  
3. 或者，如果标题或文档架构包含代码页信息，则使用该信息。  
  
4. 否则，将使用 UTF-8 编码。  
  
   对于上述情况 2、 3 和 4，拆装器将编码信息保存消息上下文中**XMLNorm.SourceCharset**属性。  
  
## <a name="see-also"></a>请参阅  
 [平面文件拆装器管道组件](../core/flat-file-disassembler-pipeline-component.md)   
 [如何配置平面文件拆装器管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)