---
title: Ops 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 052fff3518e3a302c6b632e9852a9d0c8f6b5ceb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277949"
---
# <a name="the-ops-adapter"></a>Ops 适配器
在解决方案的设计是传递，在可能的情况下，会出现问题的消息和错误给决定如何修复错误还是终止订单的操作系统。 Ops 适配器，结合新的错误报告功能，可处理许多这样的情况。  
  
 该解决方案使用该适配器端口配置为使用新的错误报告功能。 当它收到错误时，适配器调用两种方法**初始化**并**Execute**，指定程序集中的类上。 在解决方案中，这些方法将错误发送到正确的操作组。  
  
 该解决方案包含的示例处理程序，尽管您可以轻松地编写你自己和其他解决方案中使用的适配器。 有关新的错误报告功能的常规信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
> [!NOTE]
>  Ops 适配器是使用适配器框架生成的。 有关构建与框架的适配器的信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。  
  
 本部分介绍了该适配器的工作原理以及如何配置它，并提供处理程序程序集的错误详细信息。 本部分最后介绍会很有帮助的用户想要修改适配器或其他应用程序中使用它的实现详细信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 Ops 适配器](../core/using-the-ops-adapter.md)  
  
-   [操作错误处理程序示例](../core/the-sample-operations-error-handler.md)  
  
-   [Ops 适配器实施详细信息](../core/ops-adapter-implementation-details.md)