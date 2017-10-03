---
title: "如何为策略配置事实检索器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, policies
- Business Rule Composer, facts
- policies, facts
ms.assetid: a7bcf3e5-3f28-4f0e-b112-8c97dee072a1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18572af1323de817b3c934866af917d2601332f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a>如何为策略配置事实检索器
您可以将不经常变化的事实存储起来，然后在主机应用程序的首次执行循环之前，可以从存储中检索这些事实，一次性地将它们提供给规则引擎进行缓存，以便在多个执行循环中重用这些事实。  
  
 可以通过两种方式将事实检索器与策略相关联。 你可以执行此操作使用业务规则编辑器或以编程方式使用**RuleSetExecutionConfiguration**对象。  
  
> [!NOTE]
>  一个策略版本只能关联一个事实检索器实现。  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a>在业务规则编辑器中将事实检索器与策略相关联  
  
1.  在“策略浏览器”窗口中，单击要关联事实检索器的策略版本。  
  
2.  在属性窗口中，单击**省略号**中的按钮 （…）**事实检索器**属性以浏览事实检索器对象的全局程序集缓存。  
  
    > [!IMPORTANT]
    >  **省略号**按钮 （…） 未显示直到您单击**事实检索器**属性窗口中的行。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)