---
title: 什么是 Wcf-nettcp 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, about WCF-NetTcp adapters
ms.assetid: 94dc24df-19a1-4701-9012-59d05b0c8abd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da209ab45dbb9458cd6be0d2e988fac7ea9270f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242858"
---
# <a name="what-is-the-wcf-nettcp-adapter"></a>什么是 Wcf-nettcp 适配器？
Wcf-nettcp 适配器提供了服务和客户端是基于 WCF 的环境中已连接的跨计算机或跨进程通信。 它提供了 SOAP 安全性、 可靠性和事务功能的完全访问权限。 此适配器使用 TCP 传输和消息采用二进制编码。  
  
 下表总结了 Wcf-nettcp 适配器的特征。  
  
|Description|特征|  
|-----------------|--------------------|  
|互操作性级别|.NET-Profile|  
|消息编码|Binary|  
|边界|跨计算机或跨进程|  
|传输协议|TCP|  
|安全模式|无、 消息、 传输和 TransportWithMessageCredential。|  
|客户端身份验证机制|传输安全和消息安全|  
|支持 WS-ReliableMessaging|否|  
|支持 WS-AtomicTransaction|是|  
|支持单向消息传送|是|  
|支持双向消息传送|是|  
|主机类型的接收适配器|进程内|  
|发送适配器的主机类型|进程内|  
  
 Wcf-nettcp 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。  
  
 **Wcf-nettcp 接收适配器**  
  
 使用 Wcf-nettcp 接收适配器接收通过 TCP 协议的 WCF 服务请求。 使用 Wcf-nettcp 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。  
  
 **Wcf-nettcp 发送适配器**  
  
 使用 Wcf-nettcp 发送适配器通过无类型协定的 WCF 服务调用使用 TCP 协议。  
  
 有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 Wcf-nettcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)