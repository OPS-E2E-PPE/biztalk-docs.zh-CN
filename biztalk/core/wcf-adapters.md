---
title: WCF 适配器 |Microsoft Docs
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
ms.openlocfilehash: 716154cbc315c24f7a6a3cd65f9d26a7dfe2fa54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399423"
---
# <a name="wcf-adapters"></a>WCF 适配器

## <a name="overview"></a>概述
BizTalk 适配器的 Windows Communication Foundation (WCF) 允许[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与基于 WCF 的应用程序进行通信。 BizTalk WCF 适配器包括五个物理适配器，分别表示 WCF 预定义绑定 —**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**， **NetNamedPipeBinding**，并**NetMsmqBinding**。 预定义绑定的 WCF 适配器提供以便您可以轻松配置大多数应用程序要求所需的信息。  
  
 BizTalk WCF 适配器还包括两个适配器，您可以自由地配置 WCF 绑定和行为信息的接收位置和发送端口。  

## <a name="available-wcf-adapters"></a>可用的 WCF 适配器
    
- **Wcf-wshttp 适配器**。 提供对于 WS-* 标准的支持通过 HTTP 传输。 Wcf-wshttp 适配器实现了下列规范：WS 事务之间外部应用程序和 MessageBox 数据库和 Ws-security 的消息安全性和身份验证的事务交互。 传输协议是 HTTP 或 HTTPS，并且消息编码是文本或消息传输优化机制 (MTOM) 编码。  
  
- **Wcf-basichttp 适配器**。 与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务进行通信的基本配置文件 1.1。 传输协议是 HTTP 或 HTTPS，并且消息编码是文本编码。  
  
- **Wcf-nettcp 适配器**。 提供对于 WS-* 标准的支持通过 TCP 传输。 Wcf-nettcp 适配器提供了在 WCF 到 WCF 环境中有效的通信。 该适配器实现了下列规范：WS 事务之间外部应用程序和 MessageBox 数据库和 Ws-security 的消息安全性和身份验证的事务交互。 传输协议是 TCP，和消息编码是二进制编码。  
  
- **Wcf-netmsmq 适配器**。 通过利用机制来提供支持[!INCLUDE[btsCoName](../includes/btsconame-md.md)]消息队列 (MSMQ) 传输支持松散耦合应用程序、 故障隔离、 负载均衡，和断开连接操作。  
  
- **Wcf-netnamedpipe 适配器**。 提供了计算机上的跨进程通信的安全优化。 Wcf-netnamedpipe 适配器使用传输安全性保证传输安全，命名管道进行消息传递，并且包含二进制消息编码。  
  
- **WCF 自定义适配器**。 启用 WCF 扩展功能的使用。 该适配器，可以选择和配置 WCF 绑定和行为信息的接收位置和发送端口。  
  
- **Wcf-customisolated 适配器**。 允许通过 HTTP 传输使用 WCF 扩展功能。 该适配器，可以选择和配置 WCF 绑定和行为信息在独立主机中运行的接收位置。  
  
  此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供 BizTalk WCF 服务发布向导和 BizTalk WCF 服务使用向导。 若要创建和发布为 WCF 服务的 BizTalk 业务流程，并将架构发布为 WCF 服务，可以使用 BizTalk WCF 服务发布向导。 可以使用 BizTalk WCF 服务使用向导来生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，如业务流程和类型，以便 WCF 服务使用基于 WCF 服务的元数据文档。  
  
  本部分提供了资源，以帮助您配置和部署 WCF 适配器。  
  
## <a name="next"></a>Next 
  
-   [WCF 适配器概述](../core/what-are-the-wcf-adapters.md)  
  
-   [配置 WCF 适配器](../core/configuring-the-wcf-adapters.md)  
  
-   [Wcf-basichttp 适配器](../core/wcf-basichttp-adapter.md)  
  
-   [WCF-WSHttp 适配器](../core/wcf-wshttp-adapter.md)  
  
-   [WCF-NetTcp 适配器](../core/wcf-nettcp-adapter.md)  
  
-   [WCF-NetMsmq 适配器](../core/wcf-netmsmq-adapter.md)  
  
-   [WCF-NetNamedPipe 适配器](../core/wcf-netnamedpipe-adapter.md)  
  
-   [WCF-Custom 适配器](../core/wcf-custom-adapter.md)  
  
-   [WCF-CustomIsolated 适配器](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF 服务](../core/using-wcf-services.md)   