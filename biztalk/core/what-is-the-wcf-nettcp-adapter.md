---
title: 什么是 WCF-NetTcp 适配器？ | Microsoft Docs
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
ms.openlocfilehash: a741d3a4d7b7bcc80405d0fc25e37a31860523b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289405"
---
# <a name="what-is-the-wcf-nettcp-adapter"></a>什么是 WCF-NetTcp 适配器？
WCF-NetTcp 适配器在服务和客户端都是基于 WCF 的环境中提供连接的跨计算机或跨进程通信。 它提供了对 SOAP 安全性、可靠性和事务功能的完全访问权限。 此适配器使用 TCP 传输，消息采用二进制编码。  
  
 下表总结了 WCF-NetTcp 适配器的特征。  
  
|Description|特征|  
|-----------------|--------------------|  
|互操作性水平|.NET 配置文件|  
|消息编码|二进制|  
|边界|跨计算机或跨进程|  
|传输协议|TCP|  
|安全模式|无、消息、传输和 TransportWithMessageCredential。|  
|客户端身份验证机制|传输安全性和消息安全性|  
|是否支持 WS-ReliableMessaging|是|  
|是否支持 WS-AtomicTransaction|是|  
|支持单向消息传送|是|  
|支持双向消息传送|是|  
|接收适配器的主机类型|进程内|  
|发送适配器的主机类型|进程内|  
  
 WCF-NetTcp 适配器由两个适配器组成：一个接收适配器和一个发送适配器。  
  
 **WCF NetTcp 接收适配器**  
  
 您可使用 WCF-NetTcp 接收适配器通过 TCP 协议接收 WCF 服务请求。 使用 WCF-NetTcp 接收适配器的接收位置可以配置为单向或请求-响应（双向）。  
  
 **WCF NetTcp 发送适配器**  
  
 您可使用 WCF-NetTcp 发送适配器及 TCP 协议通过无类型约定调用 WCF 服务。  
  
 有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF NetTcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)