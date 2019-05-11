---
title: 信封架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af296c30-95dc-4fef-9aa3-bea2f2cd8caf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d4637bbe0fcfecea0bf4c6e134eb131935315c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349526"
---
# <a name="envelope-schemas"></a>信封架构

## <a name="overview"></a>概述
可以在所有可以创建业务文档的 XML 架构的相同方式来创建一个信封架构。 从格式正确的 XML 信封实例消息，或从文档类型定义 (DTD)，可以创建一个架构或 XML 数据缩减 (XDR) 表示形式的信封架构。 或者，可以创建新的架构，可以结合其他架构。 信封架构是小得多，并且小于比大多数业务文档架构复杂一些，因为通常多创建新的信封架构是一个可行的替代。  
  
 若要将架构定义为信封架构，您需要设置**信封**的属性**架构**的值的节点**是**。 在定义信封架构时，您应该指向的信封**正文 XPath**向父节点只包含\<任何\>子元素。 为了使 XML 组装器，若要使用信封，父节点必须包含任何其他元素。  
  
 当您将设置**信封**属性设置为**是**，则意味着 XML 实例消息 （称为消息正文） 的实际消息内容是根内部的某个位置存在**记录**指定的此架构的节点**正文 XPath**该节点的属性。 因此，您还必须设置其他属性根据各种条件：  
  
-   如果信封架构具有一个根，则必须设置**正文 XPath**该根的属性。  
  
-   如果信封架构具有多个根和**根引用**属性未设置，则必须设置**正文 XPath**所有根的属性。  
  
-   如果信封架构具有多个根和**根引用**属性设置，则必须设置**正文 XPath**属性的相应根**记录**节点。 可以选择性地设置**正文 XPath**为其余根的属性。  
  
-   无论信封架构具有一个根还是多个根，设置 **[根引用**属性不是必需。  

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>请参阅  
 [不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md)   
 [如何为信封创建架构](../core/how-to-create-schemas-for-envelopes.md)