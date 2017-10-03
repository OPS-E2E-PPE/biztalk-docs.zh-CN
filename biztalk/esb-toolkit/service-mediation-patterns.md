---
title: "服务中介模式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfda54db-75fa-4bc2-9f48-11d8b3cde65b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af76e6c123a3a273bc2e100b1008f40523762695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="service-mediation-patterns"></a>服务中介模式
## <a name="vetovetro"></a>否决/VETRO  
 VETRO 模式是一种常见的复合模式将时收到对消息执行的多个操作组合在一起。 术语 VETRO 是代表验证、 扩充、 转换、 路由、 操作的首字母缩写。 在[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，这些操作可以处理作为与接收位置关联的管道中的各个阶段。 有关如何实施其中每个阶段的详细信息，请参阅主要方案和开发任务。  
  
## <a name="request-response"></a>请求-响应  
 请求-响应模式定义请求服务或方发送消息，然后从目标服务中返回需要一答复消息的解决方案。 有关此模式的详细说明，请参阅[请求-答复](http://go.microsoft.com/fwlink/?LinkId=186849)([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849)) 上的企业集成模式站点。  
  
 有关如何实现此模式的详细信息，请参阅以下资源：  
  
-   [如何： 转换消息和使用请求-响应消息交换模式的服务终结点的路由](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
-   [安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)