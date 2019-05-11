---
title: 使用分析和序列化引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78e0dcffd680136cd2a140f18787793b43a4913
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302987"
---
# <a name="using-the-parsing-and-serializing-engines"></a>使用解析和序列化引擎
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括解析和序列化引擎，以便简化解析和序列化平面文件文档的过程。  
  
 解析引擎是一个架构驱动的框架，可以解析为 XML 的许多不同的文档格式。 此外，该引擎具有明确定义的扩展模型，以使分析更简单的自定义格式。  
  
 对于复杂解析，则使用拆装器。 除了将本机格式转换为 XML，拆装器，还可以将单个文档到多个文档。  
  
 序列化引擎类似于解析引擎，只是它在相反方向工作。 解析引擎将本机格式转换为 XML，其中序列化引擎会将 XML 转换为本机格式。 并就像解析引擎使用拆装器相反，序列化引擎使用组装器。  
  
 本部分介绍如何执行字符编码、 解析和序列化基于 XML 架构定义语言 (XSD) 架构，并执行其他常见任务，使用解析引擎和序列化引擎 Api。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在管道组件中实现字符编码](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [使用架构](../core/using-schemas.md)  
  
-   [使用平面文件解析引擎](../core/using-the-flat-file-parsing-engine.md)  
  
-   [使用平面文件序列化引擎](../core/using-the-flat-file-serializing-engine.md)