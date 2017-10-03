---
title: "什么是 WCF WSHttp 适配器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-WSHttp adapters, about WCF-WSHttp adapters
ms.assetid: 183a19e3-10b1-403f-b274-34a441e774d1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5d244dcfe26cf10bc4ae10c63374eef0824444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-wshttp-adapter"></a>什么是 WCF WSHttp 适配器？
借助 WCF-WSHttp 适配器，您可以通过以文本或消息传输优化机制 (MTOM) 编码的 HTTP 或 HTTPS 传输，与支持下一代 Web Services 标准的服务和客户端实现跨计算机通信。 WCF-WSHttp 适配器提供了对 SOAP 安全性、可靠性和事务功能的完全访问权限。  
  
 下表总结了 WCF-WSHttp 适配器的特征。  
  
|Description|特征|  
|-----------------|--------------------|  
|互操作性水平|WS-Profile|  
|消息编码|文本或 MTOM|  
|边界|跨计算机|  
|传输协议|HTTP 或 HTTPS|  
|安全模式|无、消息、传输和 TransportWithMessageCredential。|  
|客户端身份验证机制|传输安全性和消息安全性|  
|是否支持 WS-ReliableMessaging|是|  
|是否支持 WS-AtomicTransaction|是|  
|支持单向消息传送|是|  
|支持双向消息传送|是|  
|接收适配器的主机类型|隔离|  
|发送适配器的主机类型|进程内|  
  
 WCF-WSHttp 适配器由两个适配器组成：一个接收适配器和一个发送适配器。  
  
 **WCF WSHttp 接收适配器**  
  
 您可使用 WCF-WSHttp 接收适配器通过 HTTP 或 HTTPS 协议接收 WCF 服务请求。 使用 WCF-WSHttp 接收适配器的接收位置可以配置为单向或请求-响应（双向）。  
  
 **WCF WSHttp 发送适配器**  
  
 您可使用 WCF-WSHttp 发送适配器及 HTTP 或 HTTPS 协议通过无类型约定调用 WCF 服务。  
  
 有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF WSHttp 适配器](../core/configuring-the-wcf-wshttp-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)