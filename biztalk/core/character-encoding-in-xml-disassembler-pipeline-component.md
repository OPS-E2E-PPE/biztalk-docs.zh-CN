---
title: XML 拆装器管道组件中的字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], character encoding
- XMLNorm.SourceCharset property
ms.assetid: 37962bdc-cbcb-4559-9ae8-6c4be49b4822
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d299ac6a1261160cbd3844c3f0201e55affa5655
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391668"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a>XML 拆装器管道组件中的字符编码
XML 拆装器使用以下算法来确定要用于处理传入消息使用的编码：  
  
1. 如果数据中存在字节顺序标记，它从确定编码信息。  
  
2. 否则为如果**IBaseMessagePart.Charset**属性设置，则使用指定的编码。  
  
3. 或者如果 XML 文档中存在 XML 声明，则指定的编码则使用，提供的 XML 声明为 ANSI。  
  
4. 否则，使用 utf-8 编码。  
  
   对于上述情况下，2、 3 和 4 中，XML 拆装器将确定编码后，它将其保存的消息上下文中**XMLNorm.SourceCharset**属性。 消息始终由 XML 拆装器管道组件使用 utf-8 编码。 针对情况 1，不保留从字节顺序标记确定的编码。  
  
## <a name="see-also"></a>请参阅  
 [XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)