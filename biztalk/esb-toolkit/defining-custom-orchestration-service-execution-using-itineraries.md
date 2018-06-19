---
title: 定义自定义业务流程服务执行使用路线 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9336969db2c90168bf7c398276205043b06504ce
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007427"
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a>定义自定义业务流程服务执行使用路线
在此用例，以进行处理的消息包含说明的服务执行，而其解析要求列表路线 SOAP 标头。 路线指定一个或多个自定义业务流程或消息将传递在处理周期内的进程。 自定义业务流程具有完全控制路线及其消息上下文中公开的其他自定义属性。 （可选） 路线可以包含确定转换要求和消息的终结点的动态解析信息。 图 1 说明的过程的示意图。  
  
 ![定义自定义业务流程](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3 DefiningCustomOrchestration")  
  
 **图 1**  
  
 **定义自定义业务流程服务执行使用路线**  
  
 附带路线入口示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何创建包含解决方法、 路由和服务调用说明作为一系列路线定义 ESB 和 BizTalk Server 将如何处理输入的消息的步骤的路线。 单向请求响应示例中还包括。  
  
 有关详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。