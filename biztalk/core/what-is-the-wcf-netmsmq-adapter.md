---
title: 什么是 WCF-NetMsmq 适配器？ | Microsoft Docs
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
ms.openlocfilehash: 1008cc7178c38532f1781890080eacf4b5dfb56c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289429"
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a>什么是 WCF-NetMsmq 适配器？
WCF-NetMsmq 适配器提供断开连接的跨计算机通信，方式是通过在服务和客户端都是基于 WCF 的环境中使用队列技术。 它使用消息队列 (MSMQ) 传输，而且消息采用二进制编码。  
  
 下表总结了 WCF-NetMsmq 适配器的特征。  
  
|Description|特征|  
|-----------------|--------------------|  
|互操作性水平|.NET 配置文件|  
|消息编码|二进制|  
|边界|跨计算机|  
|传输协议|MSMQ|  
|安全模式|无、消息、传输或两者。|  
|客户端身份验证机制|传输安全性和消息安全性|  
|是否支持 WS-ReliableMessaging|不适用|  
|是否支持 WS-AtomicTransaction|是|  
|支持单向消息传送|是|  
|支持双向消息传送|是|  
|接收适配器的主机类型|进程内|  
|发送适配器的主机类型|进程内|  
  
> [!NOTE]
>  必须提前创建 WCF-NetMsmq 接收适配器从其提取消息的队列。 队列中的消息必须基于 WCF；否则，这些消息将被发送到死信队列。  
  
 WCF NetMsmq 适配器包含两个适配器-接收适配器和一个发送适配器。  
  
 **WCF NetMsmq 接收适配器**  
  
 您可以使用 WCF-NetMsmq 接收适配器在 MSMQ 上接收 WCF 服务请求。 使用 WCF-NetMsmq 接收适配器的接收位置只能配置为单向接收。  
  
 **WCF NetMsmq 发送适配器**  
  
 您可以使用 WCF-NetMsmq 发送适配器在 MSMQ 上通过无类型的协定调用 WCF 服务。  
  
 有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF NetMsmq 适配器](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)