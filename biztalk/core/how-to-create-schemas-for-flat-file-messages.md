---
title: 如何创建平面文件消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48f2747b-7f26-4fb2-a855-523e093f3813
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58583037b8fae945dea07aa8af62e969b96e073f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249405"
---
# <a name="create-schemas-for-flat-file-messages"></a>创建架构的平面文件消息

## <a name="overview"></a>概述
创建 XML 消息架构中所述之后[创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)，使用**架构编辑器扩展**属性**架构**节点以启用平面文件扩展名。 启用平面文件扩展将向架构中的许多节点类型添加大量属性。 这些属性通常用于控制平面文件业务文档和其等效 XML 业务文档之间如何相互转换，它们的值在架构文件中存储为 XML 架构定义语言 (XSD) 批注。 要想正确使用这些属性，需要一些练习并且完全了解每个属性控制平面文件格式的哪些方面。 

有关概念和引用有关平面文件属性的信息，请参阅[注意事项时创建平面文件消息架构](../core/considerations-when-creating-flat-file-message-schemas.md)和**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
## <a name="see-also"></a>另请参阅  
-  [管理架构在项目中](../core/managing-schemas-within-projects.md)
-  这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]