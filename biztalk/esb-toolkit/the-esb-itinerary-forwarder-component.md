---
title: ESB 路线转发器组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 607cc8a0-4964-4751-baca-c3329983c98b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e23368b1d74a2842659332d2c545b93e24386455
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399791"
---
# <a name="the-esb-itinerary-forwarder-component"></a>ESB 路线转发器组件
路线必须按顺序调用多个 Web 服务时，使用 ESB 路线转发器组件。 可以使用该组件在接收管道与双向关闭接入点在响应端相关联。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装**路线转发器**组件的 BizTalk Server 管道组件文件夹中。  
  
## <a name="how-it-works"></a>其工作原理  
 当 Microsoft BizTalk 收到任何消息通过双向接收端口将消息发布到 Messagebox 数据库，创建实例订阅。 此订阅都包含**EpmRRCorrelationToken**升级的属性和一个**RouteDirectToTP**升级的属性。 当订阅服务器 （业务流程或双向发送端口） 返回的响应消息时，这些升级的属性与订阅匹配，并通过接收端口的发送管道立即返回响应。  
  
 ESB 路线转发器应在响应管道中为双向，关闭 ramp 其中关闭负载增加正在调用的请求-响应 Web 服务。 该组件会影响通过更改典型 BizTalk 进程**RouteDirectToTP**升级的属性为 False，因此可确保对发起将不返回响应接收端口。 达到路线的最后一步后， **RouteDirectToTP**属性更改回**True**，因此将结果返回到起始负载增加。  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a>使用 ESB 路线转发器组件  
 将 ESB ItineraryForwarder 组件添加到接收管道，然后使用双向关闭接入点的响应部分使用管道。 创建路线的链接多个 Web 服务，带有或不使用转换路线服务之前或在服务之间。 有关如何使用 ESB 路线转发器组件的示例，请参阅[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。