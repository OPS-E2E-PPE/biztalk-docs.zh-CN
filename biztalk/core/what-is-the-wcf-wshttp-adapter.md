---
title: Wcf-wshttp 适配器是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, about WCF-WSHttp adapters
ms.assetid: 183a19e3-10b1-403f-b274-34a441e774d1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3d82d26e03163d856bc4ce9d0cc8d948d07e54a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242800"
---
# <a name="what-is-the-wcf-wshttp-adapter"></a>Wcf-wshttp 适配器是什么？
可以使用 Wcf-wshttp 适配器实现跨计算机通信服务和客户端，可以了解下一代 Web 服务标准，与文本或消息传输优化机制 （使用 HTTP 或 HTTPS 传输MTOM) 编码。 Wcf-wshttp 适配器提供了对 SOAP 安全性、 可靠性和事务功能完全访问权限。  
  
 下表总结了 Wcf-wshttp 适配器的特征。  
  
|Description|特征|  
|-----------------|--------------------|  
|互操作性级别|WS-Profile|  
|消息编码|文本或 MTOM|  
|边界|跨计算机|  
|传输协议|HTTP 或 HTTPS|  
|安全模式|无、 消息、 传输和 TransportWithMessageCredential。|  
|客户端身份验证机制|传输安全和消息安全|  
|支持 WS-ReliableMessaging|否|  
|支持 WS-AtomicTransaction|是|  
|支持单向消息传送|是|  
|支持双向消息传送|是|  
|主机类型的接收适配器|隔离|  
|发送适配器的主机类型|进程内|  
  
 Wcf-wshttp 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。  
  
 **Wcf-wshttp 接收适配器**  
  
 使用 Wcf-wshttp 接收适配器接收通过 HTTP 或 HTTPS 协议的 WCF 服务请求。 使用 Wcf-wshttp 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。  
  
 **Wcf-wshttp 发送适配器**  
  
 使用 Wcf-wshttp 发送适配器来调用通过使用 HTTP 或 HTTPS 协议通过无类型协定的 WCF 服务。  
  
 有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 Wcf-wshttp 适配器](../core/configuring-the-wcf-wshttp-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)