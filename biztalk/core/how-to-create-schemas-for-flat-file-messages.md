---
title: 如何为平面文件消息创建架构 |Microsoft Docs
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
ms.openlocfilehash: bd17aca790648b39d3219bb9816115645abe0855
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385438"
---
# <a name="create-schemas-for-flat-file-messages"></a>为平面文件消息创建架构

## <a name="overview"></a>概述
在创建 XML 消息架构中所述[的 XML 消息创建架构](../core/how-to-create-schemas-for-xml-messages.md)，使用**架构编辑器扩展**属性**架构**节点以启用平面文件扩展。 启用平面文件扩展到多个架构中的节点类型添加大量属性。 这些属性通常用于控制平面文件业务文档如何转换到和从其等效 XML 业务文档，并将它们的值存储为 XML 架构定义语言 (XSD) 批注中的架构文件。 正确使用这些属性需要一些练习并且完全了解这些方面的平面文件格式它们每个控制。 

有关概念和参考有关该平面文件属性的信息，请参阅[注意事项时创建平面文件消息架构](../core/considerations-when-creating-flat-file-message-schemas.md)并**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  

## <a name="see-also"></a>请参阅  
- [管理项目中的架构](../core/managing-schemas-within-projects.md)
- 这些属性的更多详细信息 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
