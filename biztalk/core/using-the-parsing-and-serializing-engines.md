---
title: "使用的分析和序列化引擎 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e820b2dce1257ec948aa214c9fdf1d43a6a7152
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-parsing-and-serializing-engines"></a>使用了分析和序列化引擎
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括分析和序列化引擎来简化分析和序列化平面文件文档的过程。  
  
 解析引擎是一个架构驱动的框架，可以将许多不同的文档格式解析为 XML。 此外，该引擎还具有明确定义的扩展模型，以便简化对自定义格式的解析。  
  
 对于复杂解析，需使用拆装器。 除了将本地格式转换为 XML 外，拆装器还可以将单个文档划分为多个文档。  
  
 序列化引擎类似于解析引擎，只是它以相反方向工作。 解析引擎将本地格式转换为 XML，而序列化引擎则将 XML 转换为本地格式。 此外，与解析引擎使用拆装器相反，序列化引擎使用组装器。  
  
 本部分论述如何基于 XML 架构定义语言 (XSD) 架构执行字符编码、解析和序列化，以及使用解析引擎和序列化引擎 API 执行其他常见任务。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [实现管道组件中的字符编码](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [使用架构](../core/using-schemas.md)  
  
-   [使用平面文件分析引擎](../core/using-the-flat-file-parsing-engine.md)  
  
-   [使用序列化引擎的平面文件](../core/using-the-flat-file-serializing-engine.md)