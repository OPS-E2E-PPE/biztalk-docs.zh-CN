---
title: 如何为策略配置事实检索器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, policies
- Business Rule Composer, facts
- policies, facts
ms.assetid: a7bcf3e5-3f28-4f0e-b112-8c97dee072a1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7095ae5a03b6c3aec2d4f66db2563e7a6986fb39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342286"
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a>如何为策略配置事实检索器
可以存储的事实数据，通常情况下，不会更改之前在主机应用程序首次执行循环，然后, 您可以从存储中检索这些事实，一次将其呈现给规则引擎进行缓存，和多个执行循环中重复使用它们。  
  
 有两种方法将事实检索器与策略相关联。 您可以执行此操作使用业务规则编辑器或以编程方式使用**RuleSetExecutionConfiguration**对象。  
  
> [!NOTE]
>  只有一个事实检索器实现可以与策略版本相关联。  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a>要与业务规则编辑器中的策略关联的事实检索器  
  
1.  在策略浏览器窗口中，单击想要将事实检索器相关联的策略版本。  
  
2.  在属性窗口中，单击**省略号**中的按钮 （...）**事实检索器**以查找在事实检索器对象的全局程序集缓存中。  
  
    > [!IMPORTANT]
    >  **省略号**按钮 （...） 单击才会出现**事实检索器**属性窗口中的行。  
  
## <a name="see-also"></a>请参阅  
 [如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)