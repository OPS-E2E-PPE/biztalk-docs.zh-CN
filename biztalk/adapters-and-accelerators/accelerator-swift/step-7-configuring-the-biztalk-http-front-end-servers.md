---
title: 步骤 7： 配置 BizTalk HTTP 前端服务器 |Microsoft 文档
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
ms.openlocfilehash: 5840099816149265711744373e08d3a9a9d91cd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22213933"
---
# <a name="step-7-configuring-the-biztalk-http-front-end-servers"></a>步骤 7： 配置 BizTalk HTTP 前端服务器
本部分提供有关配置 Web 服务器中的准则你[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]部署。  
  
> [!NOTE]
>  在单台计算机部署中，此计算机是同一台计算机作为一个执行消息传送和处理。  
  
### <a name="to-configure-the-biztalk-http-front-end-servers"></a>若要配置 BizTalk HTTP 前端服务器  
  
1.  安装 Internet 信息服务 (IIS) 和 ASP.NET。  
  
2.  打开 IIS 管理器，然后选择**Web 服务扩展**。 确保 ASP.NET 1.1 版和 ASP.NET 2.0 版设置为**允许**。  
  
3.  确保**消息队列**与服务 (MSMQ)**路由支持**从添加/删除安装[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]下应用程序服务器/消息队列的组件。  
  
4.  确保启用了网络 DTC 访问中添加/删除[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]应用程序服务器类别下的组件。 在上启用网络 DTC 客户端访问[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前面步骤中的计算机。  
  
5.  在你部署中，实现安全套接字层 (SSL) 协议中所述[支持安全套接字层 (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)。  
  
6.  安装和配置 Windows SharePoint Services 3.0 SP1。  
  
7.  安装和配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]中所述[安装和配置 BizTalk Accelerator for HTTP 前端服务器上的 SWIFT](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)。  
  
 本部分包含：  
  
-   [支持安全套接字层 (SSL)](../../adapters-and-accelerators/accelerator-swift/supporting-secure-sockets-layer-ssl.md)  
  
-   [安装和配置 BizTalk HTTP 前端服务器](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-http-front-end-servers.md)  
  
-   [安装和配置 BizTalk Accelerator for SWIFT HTTP 前端服务器上](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-http-front-end-servers.md)