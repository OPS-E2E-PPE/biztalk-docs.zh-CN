---
title: XSD 角色 |Microsoft 文档
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
ms.openlocfilehash: 1ad2f99b60de5ebb2a3cd7e102a2f3f7b787d1ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268573"
---
# <a name="role-of-xsd"></a>XSD 的角色
XML 架构定义 (XSD) 语言提供了在 BizTalk 中定义的消息架构的基本语法。 尽管 BizTalk 编辑器和 BizTalk 映射器中的树视图使用了特定于 BizTalk 的记录和字段节点（在其他节点类型中）的图形化层次结构，并且每个树视图都具有自己的属性集，但此类层次结构将作为 XSD 进行构造和保存。 BizTalk 编辑器提供了只读的 XSD 视图，在其中您可以查看向树视图内的架构图形表示形式添加各节点或从其中删除各节点时以及更改与这些节点相关联的属性值时所构造的 XSD。 尽管通常无需了解 XSD 的详细信息即可使用 BizTalk 编辑器成功构造简单的架构，但是如果对在树视图中更改架构层次时所发生的 XSD 更改进行研究，就能了解如何使用 XSD。  
  
 使用 XSD 中的架构批注功能，以及 BizTalk Server 定义的扩展批注集，可以有效地将 XSD 扩展为支持表示诸如平面文件之类的非 XML 消息所需的语义。  
  
## <a name="see-also"></a>另请参阅  
 [在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)   
 [有关架构](../core/about-schemas.md)