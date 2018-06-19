---
title: 启用 Web 服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- hosts, isolated
- Web services, planning
- Web services, enabling
ms.assetid: 2a4681f6-9ded-423d-baa5-5831e6a85c61
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7cd0b1694422caf04285206f0bd7411ff5de20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242453"
---
# <a name="enabling-web-services"></a>启用 Web Services
若要发布 Web Services，必须配置 Internet 信息服务 (IIS)、BizTalk 独立主机以及 Windows 用户和组帐户。 本部分讨论如何启用 IIS 中的 Web 服务。 有关启用 Web 服务的详细信息，请参阅 IIS 文档。  
  
 **Internet Information Services**  
  
 可以将 Web 服务发布到了 IIS 和 ASP.NET 一起配置的 Windows 系统中。 对于每种服务器，所有 Web Services 都在 ASP.NET 工作进程中运行。  
  
 默认情况下，ASP.NET 工作进程使用本地 ASPNET 帐户。 IIS 使用用于处理 Web 服务请求的应用程序池。  
  
 **BizTalk 隔离主机**  
  
 若要启用 Web Services，必须在 BizTalk Server 中至少创建一个独立主机。 独立主机是指 BizTalk Server 不创建或控制的外部进程，如 ISAPI 扩展和 ASP.NET 进程。 这些类型的外部进程必须承载某些适配器，如 HTTP/S 和 SOAP。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置管理器创建 BizTalk 用作默认独立主机的 BizTalkServerIsolatedHost。 默认情况下，BizTalk Isolated Host Users 组是与此主机关联的 Windows 组的名称。 有关主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
 一个独立主机实例只能运行一个适配器。 如果用一个独立主机配置 HTTP 和 SOAP 适配器的接收处理程序，则必须创建两个应用程序池，每个适配器对应一个应用程序池。  
  
 例如，如果打算配置两个独立主机，如下所示：  
  
|独立主机名|接收位置|  
|------------------------|-----------------------|  
|独立主机 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1**注意：** **隔离主机 1**用于接收的 SOAP 和 HTTP 适配器处理程序。|  
|隔离的主机 2|HTTP_ReceiveLocation2|  
  
 你可以创建四个虚拟目录，每个接收位置对应一个，如下所示：  
  
|接收位置|虚拟目录|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 然后，必须至少为这些虚拟目录创建三个应用程序池，如下所示：  
  
> [!NOTE]
>  必须至少为每个独立主机创建一个应用程序池。  
  
|虚拟目录|应用程序池|Description|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|不需要单独的应用程序池，原因是所有接收位置都具有相同的独立主机（独立主机 1）和相同的协议。|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|需要单独的应用程序池，原因是此接收位置使用的协议 (SOAP) 与同一主机（独立主机 1）中其他接收位置使用的协议不同。|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|需要单独的应用程序池，原因是此接收位置在独立主机 1 以外的主机下运行。|  
  
> [!NOTE]
>  必须将应用程序池的用户帐户添加到独立主机的相应本地或域组中。 有关详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
> [!NOTE]
>  你需要根据上述表格在独立主机实例和相应的应用程序池之间匹配用户帐户。 有关独立的主机实例和应用程序池的用户帐户之间的关系的详细信息，请参阅[如何更改服务帐户和密码](../core/how-to-change-service-accounts-and-passwords.md)。  
  
 **对于单个服务器安装的数据库访问**  
  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BizTalk 管理数据库驻留在同一台服务器上，你应将 ASP.NET 工作进程或 IIS 应用程序池的用户上下文设置为本地 ASPNET 用户帐户或具有最低权限的本地或域用户帐户。  
  
 **对于多个服务器安装的数据库访问**  
  
 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BizTalk 管理数据库驻留在不同服务器上，你应将 ASP.NET 工作进程或 IIS 应用程序池的用户上下文更改为域用户帐户。  
  
 当实现多服务器部署时，独立主机 Windows 组必须存在于 BizTalk 数据库服务器所属的域上。  
  
 **将帐户特权和用户权限降至最低**  
  
 使用独立的主机提供对所需的资源与 BizTalk Server 进行交互的最少工作量在外部进程访问中运行的适配器。 为确保部署的安全，应为外部进程的用户上下文赋予最低权限。  
  
 **BizTalk Web 服务发布向导的安全建议**  
  
 BizTalk Web Services 发布向导创建的虚拟目录将从父虚拟目录或网站继承访问控制列表 (ACL) 和身份验证要求。 如果父虚拟目录或网站允许匿名访问，则 BizTalk Web Services 发布向导将在创建此虚拟目录时删除这一功能。  
  
 以下内容包含 [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)] 的安全说明和建议。  
  
## <a name="next"></a>Next
  
[如何对已发布的 Web 服务中启用 ASP.NET](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)