---
title: 进程管理器逻辑 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 6b69fc71-0f01-4513-9361-d7787d0cde6d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9894c2201ab9a96559188fd102ec585fafd5afd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396674"
---
# <a name="process-manager-logic"></a>进程管理器逻辑
本部分介绍了如何流程管理器**OrderManager**业务流程、 进程订单。 它描述了各个订单消息中的键字段，并遵循新的和更新订单通过业务流程。  
  
 **OrderManager**业务流程协调从属业务流程以处理订单。 可以添加、 删除或修改这些阶段，而无需更改**OrderManager**。 **OrderManager**进行许多协调处理由.NET 类定义的自定义消息。 在解决方案中的所有消息的列表，请参阅[业务流程管理解决方案的消息引用](../core/message-reference-for-the-business-process-management-solution.md)。 有关定义消息类型使用.NET 类的信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
> [!NOTE]
>  由于大小和范围**OrderManager**，可能需要阅读这些部分中，尤其是第二个，与在 Microsoft Visual Studio 中打开业务流程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [主要消息和字段](../core/key-messages-and-fields.md)  
  
-   [通过进程管理器的订单流](../core/order-flow-through-the-process-manager.md)