---
title: 步骤 7：配置 BizTalk HTTP 前端服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, HTTP servers
- HTTP server, configuring
ms.assetid: 6b7e0b48-bb20-42f4-84a5-092ff3a02741
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038f20096247e952b10d95c6823cb0749d3b1a71
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377022"
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a>步骤 7：配置 BizTalk HTTP 前端服务器
此部分指导配置中的 Web 服务器在[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]部署。  
  
> [!NOTE]
>  在单台计算机部署中，此计算机是作为一个执行消息传送和处理在同一台计算机。  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a>若要配置 BizTalk HTTP 前端服务器  
  
1. 安装 Internet 信息服务 (IIS) 和 ASP.NET。  
  
2. 打开 IIS 管理器，然后选择**Web 服务扩展**。 确保 ASP.NET v1.1 和 ASP.NET 2.0 版设置为**允许**。  
  
3. 絋粄**消息队列**服务 (MSMQ) 与**路由支持**从添加/删除安装[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]下应用程序服务器/消息队列的组件。  
  
4. 确保启用了网络 DTC 访问中添加/删除[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]类别下的应用程序服务器组件。 已启用网络 DTC 客户端访问在[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前面步骤中的计算机。  
  
5. 你的部署中实现安全套接字层 (SSL) 协议，如中所述[支持安全套接字层 (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)。  
  
6. 安装和配置 Windows SharePoint Services 3.0 SP1。  
  
7. 安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]中所述[安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)。  
  
   本部分包含：  
  
-   [支持安全套接字层 (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [安装和配置 BizTalk HTTP 前端服务器](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [在 HTTP 前端服务器上安装和配置 BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)