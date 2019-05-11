---
title: 定义路由和消息转换通过多个业务流程使用路线 |Microsoft Docs
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
ms.openlocfilehash: bb39d156827dd88d043c86cf3fa27cf82889d9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394656"
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a>定义路由和通过使用路线的多个业务流程的消息转换
在此用例，提交以进行处理的消息包含描述的服务执行，而其分辨率要求列表的路线 SOAP 标头。 路线指定通过该消息将直接处理周期内的一个或多个 Microsoft BizTalk Server 业务流程。 （可选） 路线可能包含用于确定终结点或转换要求消息的动态路由信息。 图 1 显示了该过程的示意图。  
  
 ![定义路由多业务流程](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3-DefiningRoutingMultipleOrchestrations")  
  
 **图 1**  
  
 **通过多个业务流程使用路线定义路由和消息转换**  
  
 路线接入点示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何创建包含分辨率、 路由、 路线和服务调用的说明作为一系列定义的路线步骤如何[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和 BizTalk Server 将处理输入的消息。 单向和请求-响应示例包括在内。  
  
 有关详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。