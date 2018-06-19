---
title: 定义路由和消息转换服务调用使用路线 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6f2448e-a5a7-496c-86d3-47f12e6f1251
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 975c830f73e0de362b25f312a8d41c4b15368cfd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294277"
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a>定义路由和转换消息的服务调用使用路线
在此用例，以进行处理的消息包含说明的服务执行，而其解析要求列表路线 SOAP 标头。 具体而言，转换和路由服务定义，每个 （可选） 需要通过通用描述、 发现和集成 (UDDI)、 业务规则引擎策略、 XML 路径语言 (XPath) 或静态查找解决方法。 可以通过在发布消息时将其他服务添加到路线扩展此用例。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供两种类型的路线上渐变： 那些支持单向通信和支持请求-响应方案。 因为动态解决机制可以使用中路线信息来查找终结点或动态绑定到终结点，则 Microsoft BizTalk Server 以包含特定的终结点路由的详细信息，不要求。 图 1 说明的过程的示意图。  
  
 ![定义路由服务调用](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3 DefiningRoutingServiceInvocation")  
  
 **图 1**  
  
 **定义路由和消息转换服务调用使用路线**  
  
 附带路线入口示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何创建路线包含解析，路由，并作为一系列路线步骤定义服务调用说明如何[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和 BizTalk Server 将处理该消息使用发布-订阅功能BizTalk Server。 单向请求响应示例中还包括。  
  
 有关详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。