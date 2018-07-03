---
title: BizTalk ESB 工具包消息生命周期 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f93a4ee2024fcb9cfaf65e7cf33922784a47030
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979134"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a>BizTalk ESB 工具包消息生命周期
下面是消息的来自外部系统开始并遍历 ESB 到达其最终目标的生命周期：  

1. 入口接收消息。 根据提交的参与方或客户端中，消息可能会也可能不包含定义该消息的处理指令的路线。  

2. ESB 管道组件将复制路线 （如果存在 SOAP 标头中） 到消息的上下文作为升级的属性。 如果没有路线的情况下收到消息时，可以配置特定的管道组件从一个数据库，具体取决于消息内容或上下文中，选择相应的路线，然后将路线复制到的消息上下文。 消息的生命周期的持续时间内，路线被保留在消息上下文中。  

3. 虽然仍在管道中，计算路线，并基于消息的路线服务能够处理该消息。 这些路线服务可能会转换该消息，或配置路由终结点。  

4. 将消息发布到 Microsoft BizTalk Server Messagebox 数据库。  

5. BizTalk Server 评估的升级的属性的消息和队列消息的一个或多个订阅服务器。  

6. 订阅者处理的消息使用典型的 BizTalk Server 机制。 订阅服务器可以是以下之一：  

   -   与直接绑定上配置的筛选器的 BizTalk Server 业务流程接收端口  

   -   动态的 BizTalk Server 发送端口，也称为 ESB 关闭接入点。 路线确定如何将配置端口以继续处理该消息。  

   作为通过路线接入点到达的消息的替代方法，BizTalk Server 业务流程还可以发布消息到 ESB 处理消息框：  

7. BizTalk Server 业务流程中创建一条消息。  

8. ESB 路线被填充消息的上下文。  

9. 通过直接绑定端口到 Messagebox 数据库中发布消息。
