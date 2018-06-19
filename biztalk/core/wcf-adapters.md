---
title: WCF 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e64cd189-8805-4209-bd06-971363f38585
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb77124dbad631cd521a285ff4f036e0545ca819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290021"
---
# <a name="wcf-adapters"></a>WCF 适配器

## <a name="overview"></a>概述
用于 Windows Communication Foundation (WCF) 的 BizTalk 适配器允许 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与基于 WCF 的应用程序通信。 BizTalk WCF 适配器包括表示的预定义的 WCF 绑定的五个物理适配器-**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**， **NetNamedPipeBinding**，和**NetMsmqBinding**。 通过用于预定义绑定的 WCF 适配器，您可以轻松配置大多数应用程序要求的必需信息。  
  
 BizTalk WCF 适配器还包括用于随意配置接收位置和发送端口的 WCF 绑定和行为信息的两个适配器。  

## <a name="available-wcf-adapters"></a>可用 WCF 适配器
    
-   **WCF WSHttp 适配器**。 通过 HTTP 传输提供对于 WS-* 标准的支持。 WCF-WSHttp 适配器实现了下列规范：WS-Transaction（用来在外部应用程序和 MessageBox 数据库之间进行事务性交互）和 WS-Security（用来实现消息安全和身份验证）。 传输协议是 HTTP 或 HTTPS，消息编码是文本或消息传输优化机制 (MTOM) 编码。  
  
-   **WCF BasicHttp 适配器**。 与基于 ASMX 的 Web Services 以及符合 WS-I 基本配置文件 1.1 的客户端和其他服务进行通信。 传输协议是 HTTP 或 HTTPS，消息编码是文本编码。  
  
-   **WCF NetTcp 适配器**。 通过 TCP 传输提供对 WS-* 标准的支持。 WCF-NetTcp 适配器可在 WCF 到 WCF 环境中提供有效的通信。 适配器实现以下规范： 之间外部应用程序的 MessageBox 数据库和 Ws-security 消息安全性和身份验证的事务交互的 WS 事务。 传输为 TCP，和消息编码则是二进制编码。  
  
-   **WCF NetMsmq 适配器**。 使用 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] 消息队列 (MSMQ) 作为传输手段来提供队列支持，同时还提供对松散耦合应用程序、故障隔离、负载级别划分和脱机操作的支持。  
  
-   **WCF NetNamedPipe 适配器**。 对计算机上的跨进程通信提供了安全优化。 WCF-NetNamedPipe 适配器使用传输安全性保证传输安全，使用命名管道进行消息传送，并且使用二进制消息编码方式。  
  
-   **WCF 自定义适配器**。 允许使用 WCF 扩展功能。 用户使用此适配器可以为接收位置和发送端口选择并配置 WCF 绑定和行为信息。  
  
-   **WCF CustomIsolated 适配器**。 允许通过 HTTP 传输使用 WCF 扩展功能。 使用该适配器，可以为运行于独立主机上的接收位置选择和配置 WCF 绑定和行为信息。  
  
 此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供 BizTalk WCF 服务发布向导和 BizTalk WCF 服务使用向导。 可以使用 BizTalk WCF 服务发布向导创建 BizTalk 业务流程并将其发布为 WCF 服务，还可以将架构发布为 WCF 服务。 可以使用 BizTalk WCF 服务使用向导生成 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目，如业务流程和类型，以便基于 WCF 服务的元数据文档使用 WCF 服务。  
  
 本部分提供的资源有助于您配置和部署 WCF 适配器。  
  
## <a name="next"></a>Next 
  
-   [WCF 适配器有哪些？](../core/what-are-the-wcf-adapters.md)  
  
-   [配置 WCF 适配器](../core/configuring-the-wcf-adapters.md)  
  
-   [WCF-BasicHttp 适配器](../core/wcf-basichttp-adapter.md)  
  
-   [WCF WSHttp 适配器](../core/wcf-wshttp-adapter.md)  
  
-   [WCF NetTcp 适配器](../core/wcf-nettcp-adapter.md)  
  
-   [WCF NetMsmq 适配器](../core/wcf-netmsmq-adapter.md)  
  
-   [WCF NetNamedPipe 适配器](../core/wcf-netnamedpipe-adapter.md)  
  
-   [WCF 自定义适配器](../core/wcf-custom-adapter.md)  
  
-   [WCF CustomIsolated 适配器](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
 [使用 WCF 服务](../core/using-wcf-services.md)   