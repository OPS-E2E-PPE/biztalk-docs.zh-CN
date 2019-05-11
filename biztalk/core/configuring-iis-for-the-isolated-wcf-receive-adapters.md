---
title: 配置 IIS 以实现独立 WCF 接收适配器 |Microsoft Docs
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
ms.openlocfilehash: 477afeef37fdf62ecbbd5dc78d11bcf20b5fbd48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390915"
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a>配置 IIS 以实现独立 WCF 接收适配器
若要通过使用 BizTalk WCF 服务发布向导发布 WCF 服务，必须配置 Internet 信息服务 (IIS)、 biztalk 独立主机和 Windows 用户组帐户。 本部分讨论与 IIS 配置为发布的 WCF 服务通过独立 WCF 接收适配器，如 Wcf-basichttp 接收适配器相关的问题、 Wcf-wshttp 接收适配器和 Wcf-customisolated 适配器。 有关承载在 IIS 中的 WCF 服务的常规信息，请参阅"在 IIS 中承载"网址[ http://go.microsoft.com/fwlink/?LinkId=75700 ](http://go.microsoft.com/fwlink/?LinkId=75700)。  
  
## <a name="considerations-when-configuring-iis"></a>配置 IIS 时的注意事项  
 **Internet Information Services 7.0 和 7.5**  
  
 可以使用 IIS 7.0 和 7.5 配置有 ASP.NET 4.0 发布 WCF 服务通过独立 WCF 接收适配器。  
  
 IIS 7.0 （适用于 Windows Server 2008 SP2) 和 IIS 7.5 （适用于 Windows Server 2008 R2) 使用 IIS 应用程序池处理 Web 服务请求。 IIS 7.0 支持多个应用程序池。 每个应用程序池进程可以运行在不同用户上下文。  
  
 **Biztalk 独立主机**  
  
 若要承载 WCF 服务通过独立 WCF 接收适配器，则必须在 BizTalk Server 中创建至少一个独立的主机。 有关如何配置 biztalk 独立主机的详细信息，请参阅"BizTalk Isolated Hosts"中[启用 Web 服务](../core/enabling-web-services.md)。  
  
 **多个服务器安装的数据库访问**  
  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BizTalk 管理数据库驻留在不同服务器上，应将 IIS 应用程序池的用户上下文更改为域用户帐户。  
  
 当实现多服务器部署时，独立的主机 Windows 组必须存在 BizTalk 数据库服务器所属的域上。  
  
 **帐户权限和用户权限降至最低**  
  
 使用独立的主机以便运行在外部进程访问到所需的资源与 BizTalk Server 进行交互的最小数量的适配器。 为确保部署的您应该为提供的用户上下文的外部进程最小特权。  
  
 **BizTalk Web Services 发布向导的安全建议**  
  
 通过 BizTalk WCF 服务发布向导创建的虚拟目录从父虚拟目录或网站继承访问控制列表 (ACL)。  
  
## <a name="see-also"></a>请参阅  
 [发布 WCF 服务](../core/publishing-wcf-services.md)