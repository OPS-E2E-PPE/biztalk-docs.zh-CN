---
title: 服务介质模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfda54db-75fa-4bc2-9f48-11d8b3cde65b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b11d58393ea90f840a1193106c4c01376a5c1a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268941"
---
# <a name="service-mediation-patterns"></a>服务介质模式
## <a name="vetovetro"></a>VETO/VETRO  
 VETRO 模式是一种常见的复合模式结合了多个消息收到后执行的操作。 术语 VETRO 是代表验证、 扩充、 转换、 路由、 操作的首字母缩写。 在[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，可以作为与接收位置关联的管道中的各个阶段处理这些操作。 有关如何实现每个阶段的详细信息，请参阅主要方案和开发任务。  
  
## <a name="request-response"></a>请求-响应  
 请求-响应模式定义会将请求服务或参与方发送消息，并返回预期的答复消息，从目标服务的解决方案。 此模式的详细说明，请参阅[请求-答复](http://go.microsoft.com/fwlink/?LinkId=186849)([http://go.microsoft.com/fwlink/?LinkId=186849](http://go.microsoft.com/fwlink/?LinkId=186849)) 企业集成模式站点上。  
  
 有关如何实现此模式的详细信息，请参阅以下资源：  
  
-   [如何：转换消息并使用请求-响应消息交换模式的服务终结点的路由](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
-   [安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)