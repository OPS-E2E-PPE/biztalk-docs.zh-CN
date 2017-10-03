---
title: "Ops 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67463adf4e1e960ab6608e67595a679804aa223e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-ops-adapter"></a>Ops 适配器
该解决方案设计为将存在问题的消息和错误传递（如果可能的话）给操作系统，由操作系统决定是修复错误还是终止订单。 Ops 适配器与新的错误报告功能配合使用可以处理许多这样的情况。  
  
 该解决方案将该适配器用在配置为使用新的错误报告功能的端口上。 当它收到错误时，适配器将调用两种方法，**初始化**和**执行**，在指定程序集中的类。 在该解决方案中，这些方法会将错误发送给正确的操作组。  
  
 该解决方案包含一个示例处理程序，当然，您也可以很容易地编写自己的处理程序，并在其他解决方案中使用该适配器。 有关新的错误报告功能的常规信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
> [!NOTE]
>  Ops 适配器是使用适配器框架构建的。 有关生成的框架的适配器的信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。  
  
 本部分介绍了该适配器的工作原理以及如何配置该适配器，并提供有关错误处理程序程序集的详细信息。 本部分最后介绍了实现详细信息，这些信息对于那些希望修改该适配器或者在其他应用程序中使用该适配器的用户将会非常有用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 Ops 适配器](../core/using-the-ops-adapter.md)  
  
-   [示例操作错误处理程序](../core/the-sample-operations-error-handler.md)  
  
-   [Ops 适配器实现详细信息](../core/ops-adapter-implementation-details.md)