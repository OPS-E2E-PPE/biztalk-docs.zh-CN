---
title: 定义路由和消息通过使用路线的多个业务流程的转换 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63141b83-798e-40d0-908d-6b7649923e69
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c5a87b06700794dca6c4aae9588c3068b98d995
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294013"
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a>定义路由和通过使用路线的多个业务流程的消息转换
在此用例，以进行处理的消息包含说明的服务执行，而其解析要求列表路线 SOAP 标头。 路线指定消息将传递在处理周期内的一个或多个 Microsoft BizTalk Server 业务流程。 （可选） 路线可以包含用来确定终结点或消息的转换要求的动态路由信息。 图 1 说明的过程的示意图。  
  
 ![定义路由多个业务流程](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3 DefiningRoutingMultipleOrchestrations")  
  
 **图 1**  
  
 **定义通过使用路线的多个业务流程的路由和消息转换**  
  
 附带路线入口示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何创建路线包含解析，路由，并作为一系列路线步骤定义服务调用说明如何[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和 BizTalk Server 将处理输入的消息。 单向请求响应示例中还包括。  
  
 有关详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。