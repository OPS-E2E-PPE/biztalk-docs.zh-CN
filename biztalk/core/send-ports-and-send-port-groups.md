---
title: 发送端口和发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc8adf80d30be84236d0c4252f67257cfe92cbbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254521"
---
# <a name="send-ports-and-send-port-groups"></a>发送端口和发送端口组
一个*发送端口*是 Microsoft BizTalk Server 将消息发送到的位置，或从其 BizTalk Server 接收消息。 它还提供了 BizTalk Server 用于实现通信操作的技术。 该端口的名称唯一标识的位置。  
  
 创建一条消息发送到发送端口的发送端口服务的新实例的任何时间。 这称为服务实例，也称为发送端口实例。  
  
> [!NOTE]
>  只能有一个实例的按序送达发送端口。  
  
 一个*发送端口组*是 BizTalk Server 可用于将同一消息发送到多个目标中的一种配置的发送端口的命名的集合。  
  
 BizTalk Server 可以直接从消息路由接收到的发送端口，或发送端口组的位置。 BizTalk Server 将消息路由到该组中的发送端口的所有发送端口组。  
  
 发送端口的两种方式发送端口组处理消息的成员：  
  
-   为发送端口组的成员  
  
-   以 BizTalk Server 将消息路由至发送端口直接  
  
## <a name="send-port-and-send-port-group-states"></a>发送端口和发送端口组的状态  
 BizTalk 管理控制台中显示发送端口和发送端口组处于以下状态之一：  
  
- **绑定**。 使用 BizTalk Server 管理控制台，管理员将绑定的发送端口或业务流程向发送端口组。 BizTalk Server 将消息路由到此发送端口或发送端口组之前，管理员必须登记和启动绑定的发送端口或发送端口组。  
  
- **启动**。 为此发送端口或发送端口组的订阅存在并处于活动状态。 当发送端口或发送端口组处于启动状态时，BizTalk Server 将消息传送到发送端口或发送端口组，并发送端口或发送端口组处理订单。 开始发送端口或发送端口组之前，管理员必须使用 BizTalk 管理控制台来登记绑定的发送端口或发送端口组。  
  
- **停止**。 当前未运行的发送端口或发送端口组。 如果启动发送端口或发送端口组，然后停止了它在工作队列中继续进行处理。 BizTalk Server 发送路由到已停止的所有新消息的发送端口或发送端口组到主机的挂起队列的发送处理程序在何处运行。  
  
  下表显示了每个州和每个结果可用的操作。  
  
||绑定|已停止|Started|  
|------|-----------|-------------|-------------|  
|**登记**|已停止|不可用|不可用|  
|**开始**|Started|Started|不可用|  
|**停止**|不可用|不可用|已停止|  
|**取消登记**|不可用|绑定|绑定|  
  
 发送端口和它所属的发送端口组的组合的状态确定是否发送端口或发送端口组处理消息或不。  
  
 下表描述了可能的状态组合为发送端口和发送端口组。  
  
|发送消息|发送端口组的状态|发送端口的状态|结果|  
|------------------|------------------------------|------------------------|-------------|  
|直接向发送端口|任何状态|Started|处理消息|  
|直接向发送端口|任何状态|已停止|消息被挂起|  
|发送到发送端口通过发送端口组|Started|Started|处理消息|  
|发送到发送端口通过发送端口组|任何状态|已停止|消息被挂起|  
|发送到发送端口通过发送端口组|已停止|任何状态|消息被挂起|  
  
## <a name="see-also"></a>请参阅  
 [项目](../core/artifacts.md)