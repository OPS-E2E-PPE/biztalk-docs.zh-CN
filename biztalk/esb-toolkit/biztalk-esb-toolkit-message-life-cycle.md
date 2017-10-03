---
title: "BizTalk ESB 工具包消息生命周期 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cb15a4c87a497a5595327b65019ca95b3201664
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a>BizTalk ESB 工具包消息生命周期
下面是一条消息，来自外部系统，并通过 ESB 到达其最终目的地遍历生命周期：  
  
1.  入口接收的消息。 具体取决于正在提交方或客户端，消息可能会也可能不包含定义消息的处理说明路线。  
  
2.  ESB 管道组件将复制路线 （如果 SOAP 标头中存在） 到消息的上下文为提升的属性。 如果没有路线的情况下接收消息，则可以配置特定管道组件从一个数据库，具体取决于消息内容或上下文中，选择适当的路线，然后将路线复制到消息的上下文。 消息的有效期限的持续时间内，路线将保留在消息上下文中。  
  
3.  虽然路线计算仍在管道中，并且基于消息的路线服务能够处理该消息。 这些路线服务可能会转换消息，或配置路由的终结点。  
  
4.  消息发布到 Microsoft BizTalk Server 消息框数据库。  
  
5.  BizTalk Server 用于一个或多个订阅服务器，评估提升的属性的消息和队列的消息。  
  
6.  订阅服务器上处理使用典型的 BizTalk Server 机制的消息。 订阅服务器可以是以下方法之一：  
  
    -   使用筛选器直接绑定上配置 BizTalk Server 业务流程接收端口  
  
    -   动态的 BizTalk Server 发送端口，也称为 ESB 出口。 路线确定如何将配置端口以便继续处理消息。  
  
 作为消息到达通过路线入口的替代方法，BizTalk Server 业务流程可以还将消息发布到 ESB 处理此消息框：  
  
1.  在 BizTalk Server 业务流程中会创建消息。  
  
2.  消息的上下文被填充 ESB 路线。  
  
3.  通过直接绑定到消息框数据库端口发布消息。