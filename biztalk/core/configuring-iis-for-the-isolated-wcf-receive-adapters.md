---
title: 配置 IIS 的独立 WCF 接收适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- WCF services, receive adapters
- IIS, configuring [WCF receive adapters]
ms.assetid: 1c6f1561-a7ba-4eb0-8878-bf213ebcd6a6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1515a69ab6a9150668db4f3415f0483dd1ce4e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233365"
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a>配置 IIS 的独立 WCF 接收适配器
要使用 BizTalk WCF 服务发布向导发布 WCF 服务，您必须配置 Internet 信息服务 (IIS)、BizTalk 独立主机和 Windows 用户组帐户。 本部分介绍配置 IIS 以使用独立 WCF 接收适配器（如 WCF-BasicHttp 接收适配器、WCF-WSHttp 接收适配器和 WCF-CustomIsolated 适配器）发布 WCF 服务的相关问题。 有关承载在 IIS 中的 WCF 服务的常规信息，请参阅"在 IIS 上承载"网址[http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700)。  
  
## <a name="considerations-when-configuring-iis"></a>配置 IIS 的注意事项  
 **Internet Information Services 7.0 和 7.5**  
  
 您可以使用配置有 ASP.NET 4.0 的 IIS 7.0 和 7.5，通过独立的 WCF 接收适配器发布 WCF 服务。  
  
 IIS 7.0（适用于 Windows Server 2008 SP2）和 IIS 7.5（适用于 Windows Server 2008 R2）使用 IIS 应用程序池处理 Web 服务请求。 IIS 7.0 支持多个应用程序池。 每个应用程序池进程都可以在其他用户上下文中运行。  
  
 **隔离的 BizTalk 主机**  
  
 要在独立 WCF 接收适配器中承载 WCF 服务，必须在 BizTalk Server 中至少创建一个独立主机。 有关如何配置 BizTalk 隔离主机的详细信息，请参阅"BizTalk 隔离主机"中[启用 Web 服务](../core/enabling-web-services.md)。  
  
 **对于多个服务器安装的数据库访问**  
  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BizTalk 管理数据库驻留在不同服务器上，你应将 IIS 应用程序池的用户上下文更改为域用户帐户。  
  
 当实现多服务器部署时，独立主机 Windows 组必须存在于 BizTalk 数据库服务器所属的域中。  
  
 **将帐户特权和用户权限降至最低**  
  
 使用独立主机可为在外部进程中运行的适配器赋予访问与 BizTalk Server 交互所需的最小数量资源的权限。 为确保部署的安全，应为外部进程的用户上下文赋予最低权限。  
  
 **BizTalk Web 服务发布向导的安全建议**  
  
 BizTalk WCF 服务发布向导创建的虚拟目录将从其父虚拟目录或网站继承访问控制列表 (ACL)。  
  
## <a name="see-also"></a>另请参阅  
 [发布的 WCF 服务](../core/publishing-wcf-services.md)