---
title: "ESB 路线的转发器组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 607cc8a0-4964-4751-baca-c3329983c98b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61643423021701186745ab4275520cb14d3ceca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-itinerary-forwarder-component"></a>ESB 路线的转发器组件
一条路线必须按顺序调用多个 Web 服务时使用 ESB 路线转发器组件。 可以使用组件在收到与双向出口响应端关联的管道。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装**路线转发器**组件 BizTalk Server 管道组件文件夹中。  
  
## <a name="how-it-works"></a>它是如何工作  
 当 Microsoft BizTalk 接收任何消息通过双向接收端口，如消息发布到消息框数据库，创建一个实例订阅。 此订阅组成**EpmRRCorrelationToken**升级的属性和**RouteDirectToTP**提升属性。 在订阅服务器 （业务流程或双向发送端口） 返回响应消息时，这些提升的属性与订阅匹配，并通过发送管道的接收端口立即返回响应。  
  
 ESB 路线转发器应在响应管道中用于双向，关闭提升关闭负载增加其中调用请求-响应 Web 服务。 组件干扰典型 BizTalk 过程通过更改**RouteDirectToTP**提升的属性为 False，从而确保响应将不返回给启动接收端口。 达到路线的最后一步后， **RouteDirectToTP**属性更改回**True**，因此将结果返回到启动负载增加。  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a>使用 ESB 路线的转发器组件  
 将 ESB ItineraryForwarder 组件添加到接收管道，然后使用双向，关闭提升的响应部分使用管道。 创建一条路线的链接多个 Web 服务，带有或不使用转换路线服务之前或在服务之间。 有关如何使用 ESB 路线转发器组件的示例，请参阅[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。