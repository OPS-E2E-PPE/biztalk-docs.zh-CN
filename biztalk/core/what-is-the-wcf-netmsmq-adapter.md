---
title: 什么是 Wcf-netmsmq 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6cfcba8858e894b83b5ec45fcd51406db93fcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242782"
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a>什么是 Wcf-netmsmq 适配器？
Wcf-netmsmq 适配器提供断开连接的跨计算机通信的服务和客户端都是基于 WCF 的环境中使用队列技术。 它使用消息队列 (MSMQ) 传输和消息采用二进制编码。  
  
 下表总结了 Wcf-netmsmq 适配器的特征。  
  
|Description|特征|  
|-----------------|--------------------|  
|互操作性级别|.NET-Profile|  
|消息编码|Binary|  
|边界|跨计算机|  
|传输协议|MSMQ|  
|安全模式|无、 消息、 传输，以及两者。|  
|客户端身份验证机制|传输安全和消息安全|  
|支持 WS-ReliableMessaging|不适用|  
|支持 WS-AtomicTransaction|是|  
|支持单向消息传送|是|  
|支持双向消息传送|否|  
|主机类型的接收适配器|进程内|  
|发送适配器的主机类型|进程内|  
  
> [!NOTE]
>  必须提前创建 Wcf-netmsmq 接收适配器提取消息的队列。 队列中的消息必须是基于; WCF否则，这些消息将发送到死信队列。  
  
 Wcf-netmsmq 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。  
  
 **Wcf-netmsmq 接收适配器**  
  
 使用 Wcf-netmsmq 接收适配器通过 MSMQ 接收 WCF 服务请求。 只能为使用 Wcf-netmsmq 接收适配器的接收位置配置为单向接收。  
  
 **Wcf-netmsmq 发送适配器**  
  
 使用 Wcf-netmsmq 发送适配器通过无类型协定的 WCF 服务调用通过 MSMQ。  
  
 有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 Wcf-netmsmq 适配器](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)