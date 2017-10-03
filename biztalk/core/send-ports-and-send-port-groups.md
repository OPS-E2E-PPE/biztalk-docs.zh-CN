---
title: "发送端口和发送端口组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, states
- send port groups
- send port groups, states
- send ports, about send ports
- send ports
- send port groups, about send port groups
- states, send ports
ms.assetid: 274bdd27-9098-46a2-8762-8b57bbfc95b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e57e56d05cf3b1a98bba83d0df92d52f09c6eda5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="send-ports-and-send-port-groups"></a>发送端口和发送端口组
A*发送端口*是 Microsoft BizTalk Server 将消息发送到的位置或 BizTalk Server 从中接收消息。 它还提供 BizTalk Server 用于实现通信操作的技术。 端口名称唯一标识该位置。  
  
 只要向发送端口发送消息，就会创建一个新的发送端口服务实例。 此实例称为服务实例，也称为发送端口实例。  
  
> [!NOTE]
>  只能存在一个按序送达发送端口实例。  
  
 A*发送端口组*是可用于将同一条消息发送到多个目标中的一种配置 BizTalk Server 发送端口的命名的集合。  
  
 BizTalk Server 可直接将消息从接收位置路由至发送端口或发送端口组。 BizTalk Server 将把路由至发送端口组的消息发送到该组中的所有发送端口。  
  
 发送端口组中的成员发送端口按以下两种方式处理消息：  
  
-   以发送端口组成员的身份  
  
-   以 BizTalk Server 直接将消息路由至该发送端口的方式  
  
## <a name="send-port-and-send-port-group-states"></a>发送端口和发送端口组的状态  
 BizTalk 管理控制台按以下状态之一显示发送端口和发送端口组.：  
  
-   **绑定**。 使用 BizTalk Server 管理控制台，管理员可以将发送端口或发送端口组绑定到业务流程。 在 BizTalk Server 将消息路由至此发送端口或发送端口组之前，管理员必须登记和启动绑定的发送端口或发送端口组。  
  
-   **启动**。 对此发送端口或发送端口组的订阅已存在并处于活动状态。 当发送端口或发送端口组处于“已启动”状态时，BizTalk Server 将把消息送达该发送端口或发送端口组，然后由该发送端口或发送端口组来对这些消息进行处理。 在启动发送端口或发送端口组之前，管理员必须使用 BizTalk 管理控制台来登记绑定的发送端口或发送端口组。  
  
-   **停止**。 发送端口或发送端口组当前未运行。 如果在启动发送端口或发送端口组之后将其停止，则会在工作队列中继续进行处理。 BizTalk Server 将把路由至已停止的发送端口或发送端口组的所有新消息发送到正在运行发送处理程序的主机的挂起队列中。  
  
 下表显示了各种状态下可用的操作以及各操作的结果：  
  
||已绑定|已停止|Started|  
|------|-----------|-------------|-------------|  
|**登记**|已停止|不可用|不可用|  
|**开始**|Started|Started|不可用|  
|**停止**|不可用|不可用|已停止|  
|**取消登记**|不可用|已绑定|已绑定|  
  
 将发送端口的状态与其所属发送端口组的状态进行组合，可确定发送端口或发送端口组是否处理消息。  
  
 下表介绍了发送端口和发送端口组可能的状态组合：  
  
|消息发送方式|发送端口组的状态|发送端口的状态|结果|  
|------------------|------------------------------|------------------------|-------------|  
|直接发送到发送端口|任何状态|Started|消息已处理|  
|直接发送到发送端口|任何状态|已停止|消息被挂起|  
|通过发送端口组发送到发送端口|Started|Started|消息已处理|  
|通过发送端口组发送到发送端口|任何状态|已停止|消息被挂起|  
|通过发送端口组发送到发送端口|已停止|任何状态|消息被挂起|  
  
## <a name="see-also"></a>另请参阅  
 [项目](../core/artifacts.md)