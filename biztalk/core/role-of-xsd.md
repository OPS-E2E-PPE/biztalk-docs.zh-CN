---
title: XSD 的角色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fe08f6b-563f-4bae-a5be-551e487b2a6d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6cb9a975f137263265051be0235f33d35bd4a41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303533"
---
# <a name="role-of-xsd"></a>XSD 的角色
XML 架构定义 (XSD) 语言提供了 BizTalk 中定义的消息架构的基本语法。 尽管 BizTalk 编辑器和 BizTalk 映射器中的树视图使用特定于 BizTalk 的图形化层次结构的记录和字段节点 （在其他类型的节点），每个都具有其自己的属性集，此类层次结构构造和保存为 XSD。 BizTalk 编辑器提供了可以在其中查看添加或删除的架构树视图中的图形表示形式中各个节点，并且如属性的值与这些节点时所构造的 XSD 的只读的 XSD 视图更改。 尽管通常不需了解 XSD 成功构造简单的架构使用 BizTalk 编辑器的详细信息，如果您研究一下发生的 XSD 更改，当更改架构层次结构树视图中，您将了解如何使用 XSD。  
  
 在 XSD 中，通过广泛的 BizTalk Server 定义的批注的架构批注功能有效地将 XSD 扩展为支持用于表示诸如平面文件之类的非 XML 消息所需的语义。  
  
## <a name="see-also"></a>请参阅  
 [在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)   
 [关于架构](../core/about-schemas.md)