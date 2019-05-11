---
title: 定义路由和消息转换服务调用使用路线 |Microsoft Docs
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
ms.openlocfilehash: 0145bb07e700133be91878f040f5a3db4825db5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394681"
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a>定义路由和消息转换服务调用使用路线
在此用例，提交以进行处理的消息包含描述的服务执行，而其分辨率要求列表的路线 SOAP 标头。 具体而言，转换和路由服务定义，每个并选择性地要求通过通用描述、 发现和集成 (UDDI)、 业务规则引擎策略、 XML 路径语言 (XPath) 或静态查找解决方法。 可以通过在发布消息时将其他服务添加到路线扩展此用例。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供两种类型的路线接入： 支持单向通信和支持请求-响应方案。 动态解析机制信息可用于在路线中查找终结点或动态绑定到终结点，因为没有任何要求的 Microsoft BizTalk Server 以包含特定的终结点路由的详细信息。 图 1 显示了该过程的示意图。  
  
 ![定义路由服务调用](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3-DefiningRoutingServiceInvocation")  
  
 **图 1**  
  
 **定义路由和消息转换服务调用使用路线**  
  
 路线接入点示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何创建包含分辨率、 路由、 路线和服务调用的说明作为一系列定义的路线步骤如何[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和 BizTalk Server 将处理该消息使用发布-订阅的功能BizTalk Server。 单向和请求-响应示例包括在内。  
  
 有关详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。