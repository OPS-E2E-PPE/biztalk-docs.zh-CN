---
title: Wcf-netnamedpipe 适配器是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, about WCF-NetNamedPipe adapters
ms.assetid: b9f84256-e49d-4ee2-b0fa-d3f692ade1d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01672c8babf30c99b8ba4d31069c836a46b18630
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242743"
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a>Wcf-netnamedpipe 适配器是什么？
Wcf-netnamedpipe 适配器服务和客户端是基于 WCF 的环境中的同一计算机上提供跨进程通信。 它提供对 SOAP 可靠性和事务功能的完全访问权限。 适配器使用命名的管道传输和消息采用二进制编码。 此适配器不能用在跨计算机通信。  
  
 下表总结了 Wcf-netnamedpipe 适配器的特征。  
  
|Description|特征|  
|-----------------|--------------------|  
|互操作性级别|.NET-Profile|  
|消息编码|Binary|  
|边界|跨进程|  
|传输协议|命名的管道|  
|安全模式|None 和传输|  
|客户端身份验证机制|传输安全和消息安全|  
|支持 WS-ReliableMessaging|否|  
|支持 WS-AtomicTransaction|是|  
|支持单向消息传送|是|  
|支持双向消息传送|是|  
|主机类型的接收适配器|进程内|  
|发送适配器的主机类型|进程内|  
  
 Wcf-netnamedpipe 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。  
  
 **Wcf-netnamedpipe 接收适配器**  
  
 使用 Wcf-netnamedpipe 接收适配器通过命名的管道传输协议接收 WCF 服务请求。 使用 Wcf-netnamedpipe 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。  
  
 **Wcf-netnamedpipe 发送适配器**  
  
 使用 Wcf-netnamedpipe 发送适配器通过无类型协定的 WCF 服务调用通过命名的管道传输。  
  
 有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 Wcf-netnamedpipe 适配器](../core/configuring-the-wcf-netnamedpipe-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)