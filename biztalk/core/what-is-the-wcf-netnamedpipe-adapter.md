---
title: WCF-NetNamedPipe 适配器概述 | Microsoft Docs
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
ms.openlocfilehash: 43c73a670139690c4a27d4784c6ad23225492f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289245"
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a>WCF-NetNamedPipe 适配器概述
WCF-NetNamedPipe 适配器在服务和客户端都是基于 WCF 的环境中的同一计算机上提供跨进程通信。 它提供了对 SOAP 可靠性和事务功能的完全访问。 适配器使用命名管道传输，消息采用二进制编码。 此适配器无法用于计算机间的通信。  
  
 下表总结了 WCF-NetNamedPipe 适配器的特征。  
  
|Description|特征|  
|-----------------|--------------------|  
|互操作性水平|.NET 配置文件|  
|消息编码|二进制|  
|边界|跨进程|  
|传输协议|命名的管道|  
|安全模式|“无”和“传输”|  
|客户端身份验证机制|传输安全性和消息安全性|  
|是否支持 WS-ReliableMessaging|是|  
|是否支持 WS-AtomicTransaction|是|  
|支持单向消息传送|是|  
|支持双向消息传送|是|  
|接收适配器的主机类型|进程内|  
|发送适配器的主机类型|进程内|  
  
 WCF-NetNamedPipe 适配器由两个适配器组成：一个接收适配器和一个发送适配器。  
  
 **WCF NetNamedPipe 接收适配器**  
  
 您可以使用 WCF-NetNamedPipe 接收适配器通过命名管道传输来接收 WCF 服务请求。 使用 WCF-NetNamedPipe 接收适配器的接收位置可以配置为单向或请求-响应（双向）。  
  
 **WCF NetNamedPipe 发送适配器**  
  
 借助命名管道传输，您可以使用 WCF-NetNamedPipe 发送适配器通过无类型约定调用 WCF 服务。  
  
 有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF NetNamedPipe 适配器](../core/configuring-the-wcf-netnamedpipe-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)