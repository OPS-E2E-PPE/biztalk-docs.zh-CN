---
title: "信封架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af296c30-95dc-4fef-9aa3-bea2f2cd8caf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9008e77e388a93b1750c9b9ba34679ed519db459
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="envelope-schemas"></a>信封架构

## <a name="overview"></a>概述
你可以在所有你可以创建针对业务文档的 XML 架构的相同方式创建信封架构。 你可以创建架构，从格式正确的 XML 信封实例消息，或从文档类型定义 (DTD) 或 XML 数据缩减 (XDR) 表示形式的信封架构。 或者，可以创建新的架构，或者结合其他架构。 因为信封架构是小得多，并且小于比大多数的业务文档架构复杂，通常多创建新的信封架构是可行的替代方案。  
  
 若要为信封架构中定义的架构，你需要设置**信封**属性**架构**的值的节点**是**。 在定义信封架构时，您应该指向的信封**正文 XPath**向父节点只包含\<任何\>子元素。 为了使 XML 汇编程序，若要使用信封的情况下，父节点不能包含任何其他元素。  
  
 当你将设置**信封**属性**是**，这意味着实际消息内容的 XML 实例消息 （称为消息的正文） 是否存在某个位置内根**记录**此架构，由指定的节点**正文 XPath**该节点的属性。 因此，您还必须根据不同条件设置其他属性：  
  
-   如果信封架构具有一个根，则必须设置**正文 XPath**该根的属性。  
  
-   如果信封架构具有多个根和**根引用**未设置属性，则必须设置**正文 XPath**所有根的属性。  
  
-   如果信封架构具有多个根和**根引用**属性时，必须设置**正文 XPath**属性的相应根**记录**节点。 你可以选择性地设置**正文 XPath**剩余的根的属性。  
  
-   无论是否信封架构具有单个根或多个根，设置**[根引用**属性不是必需。  

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
 [不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md)   
 [如何为包络线创建架构](../core/how-to-create-schemas-for-envelopes.md)