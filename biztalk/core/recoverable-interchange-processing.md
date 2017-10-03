---
title: "可恢复的交换处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interchange processing [Messaging Engine], modes
- parties, party resolution
- Messaging Engine, examples
- messages, interchange modes
- interchange processing [Messaging Engine], examples
- Messaging Engine, Recoverable Interchange Processing property
- Messaging Engine, failures
- interchange processing [Messaging Engine], party resolution
- Messaging Engine, interchange processing
- disassembly stage, pipelines
- Recoverable Interchange Processing property
- Messaging Engine, interchange modes
- receive pipelines, disassembly stage
- interchange processing [Messaging Engine], failures
- interchange processing [Messaging Engine], restrictions
- System.Xml.XmlReader
- interchange modes [Messaging Engine]
ms.assetid: d9e366fe-b2a0-4f1a-b6b9-1264717e4731
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b341b3673cd7118d459197fecea1eca25efe4e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="recoverable-interchange-processing"></a>可恢复的交换处理
本部分讨论**可恢复的交换处理**功能，允许进行完全处理，即使在每个阶段的阶段以下一个或多个消息交换中的失败的交换：  
  
-   接收管道的拆装阶段  
  
-   接收管道的 XML 验证阶段  
  
-   接收端口的映射执行阶段  
  
 需要支持包含多个可标识消息的单个交换的处理时激发可恢复交换处理，以便有效消息通过消息传送路径传播，而无效消息被挂起。 使用标准交换处理，给定交换中存在的任何无效消息都会导致整个交换被挂起，即使交换中包含一个或多个有效消息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [反汇编阶段 （可恢复的交换处理）](../core/disassembly-stage-recoverable-interchange-processing.md)  
  
-   [XML 验证阶段 （可恢复的交换处理）](../core/xml-validation-stage-recoverable-interchange-processing.md)  
  
-   [映射阶段 （可恢复的交换处理）](../core/mapping-phase-recoverable-interchange-processing.md)