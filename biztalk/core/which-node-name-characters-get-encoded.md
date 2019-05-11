---
title: 该节点名称字符进行编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a581d2-48fa-4c36-b5c2-fe87c328a7f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810476ccd640b33ecf5996bc351947a8bceb0ad4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394787"
---
# <a name="which-node-name-characters-get-encoded"></a>节点名称字符进行编码
XML 将置于可在 XML 名称，例如元素的名称，包括一些特殊限制 XML 名称的第一个字符的字符的一些限制。 确定允许哪些字符以及排除合法 XML 名称中使用哪些字符概念的目标是：  
  
- 如果适用，是包含而非排除，以便新的文字系统可以以 Unicode 进行编码一样容纳。  
  
- 排除可能或者用作分隔符的字符，以便 XML 名称可以更轻松地将显示在非 XML 分隔的上下文。  
  
  下表显示了可以在 XML 名称中，在任何位置在名称中，或位于第一个以外的任何位置使用的字符。 某些允许的字符不在名称中的第一个字符。 带引号的原义字符，并且范围显示在方括号内。  
  
|名称中的位置|允许的字符|  
|----------------------|------------------------|  
|任何位置|["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]|  
|除第一个任何位置|"-"，"。"，["0"-"9"]，0x00B7、 [0x0300-0x036F] [0x203F-0x2040]|  
  
 在英语中的元素或属性名称 （架构树视图中的节点名称） 的最佳做法可归纳如下：  
  
-   使用字母数字字符，但不要以数字开头的名称。  
  
-   使用下划线 (_)、 连字符 （-）、 句点 （.） 和中间点 （配置）。  
  
-   不要使用空格。  
  
-   自然语言中使用有意义的词或词组。  
  
## <a name="see-also"></a>请参阅  
 [节点名称属性](../core/node-name-property.md)   
 [如何对节点名称字符进行编码](../core/how-node-name-characters-get-encoded.md)