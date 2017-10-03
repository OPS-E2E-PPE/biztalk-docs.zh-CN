---
title: "过程管理器逻辑 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 6b69fc71-0f01-4513-9361-d7787d0cde6d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e562362fec8e13589f1860e74024ffe70dad1c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="process-manager-logic"></a>过程管理器逻辑
本部分介绍如何进程管理器中， **OrderManager**业务流程、 进程订单。 此外，还介绍了各个订单消息中的关键字段，以及新订单和更新的订单通过该业务流程的过程。  
  
 **OrderManager** orchestration 协调从属业务流程来处理订单。 你可以添加、 删除或修改这些阶段，而无需更改**OrderManager**。 **OrderManager**由.NET 类定义的自定义消息都可通过协调大部分。 在解决方案中的所有消息的列表，请参阅[业务流程管理解决方案的消息引用](../core/message-reference-for-the-business-process-management-solution.md)。 有关定义使用.NET 类的消息类型的信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
> [!NOTE]
>  由于的大小和作用域**OrderManager**，你可能想要阅读这些部分中，特别是第二个，与 Microsoft Visual Studio 中打开业务流程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [关键信息和字段](../core/key-messages-and-fields.md)  
  
-   [顺序流通过进程管理器](../core/order-flow-through-the-process-manager.md)