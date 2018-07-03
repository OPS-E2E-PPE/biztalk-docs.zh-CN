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
ms.openlocfilehash: e4459012155ca95166b6345ddad4390e78fce60c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984462"
---
# <a name="create-schemas-for-flat-file-messages"></a>为平面文件消息创建架构

## <a name="overview"></a>概述
在创建 XML 消息架构中所述[的 XML 消息创建架构](../core/how-to-create-schemas-for-xml-messages.md)，使用**架构编辑器扩展**属性**架构**节点以启用平面文件扩展。 启用平面文件扩展将向架构中的许多节点类型添加大量属性。 这些属性通常用于控制平面文件业务文档和其等效 XML 业务文档之间如何相互转换，它们的值在架构文件中存储为 XML 架构定义语言 (XSD) 批注。 要想正确使用这些属性，需要一些练习并且完全了解每个属性控制平面文件格式的哪些方面。 

有关概念和参考有关该平面文件属性的信息，请参阅[注意事项时创建平面文件消息架构](../core/considerations-when-creating-flat-file-message-schemas.md)并**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  

## <a name="see-also"></a>请参阅  
- [管理项目中的架构](../core/managing-schemas-within-projects.md)
- 这些属性的更多详细信息 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
