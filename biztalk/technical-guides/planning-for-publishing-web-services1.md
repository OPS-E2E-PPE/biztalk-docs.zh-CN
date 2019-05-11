---
title: 发布 web Services 规划 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b571c3aa-874b-43f7-af2e-5a71113a93dd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25ac0868660c5cff39f4879fe44738036dccca1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400699"
---
# <a name="planning-for-publishing-web-services"></a>规划发布 Web 服务
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为 Web 服务提供内置支持。 这样，您可以重用和聚合业务流程中的现有 Web 服务。  

## <a name="overview"></a>概述
 你还可以发布 （公开） 您的业务流程作为 Web 服务以单独的 Web 服务逻辑与业务流程逻辑，以便您可以更新或替换的业务逻辑，根据需要而无需涉及用于 Web 服务逻辑的代码。 此功能称为实现"模块化代码。" 一般情况下它被视为最佳做法来实现模块化代码，在可能的情况。 发布 Web 服务需要启用 Web 服务并为 Web 服务使用 BizTalk Web Services 发布向导发布的业务流程或架构。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 实现支持通过 SOAP 适配器使用的 Web 服务中的本地适配器。 本机适配器支持提供了可伸缩性、 容错能力和跟踪功能的 Web 服务，而无需编写一行代码。 有关 SOAP 适配器的详细信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。  
  
Web 服务的规划可以分为两类，用于发布 Web 服务和规划使用 Web 服务计划。 本主题介绍发布 Web 服务时应遵循的步骤。  
  
## <a name="enabling-web-services"></a>启用 Web Services  
 若要发布 Web 服务，必须配置 Internet 信息服务 (IIS)、 BizTalk Isolated Hosts 和 Windows 用户和组帐户。 本部分提供有关启用 web 服务的概述。 有关启用 Web services 的详细信息，请参阅 IIS 文档。  
  
### <a name="internet-information-services"></a>Internet Information Services
 可以将 Web 服务发布到了配置有 ASP.NET 的 IIS 的 Windows 系统。 在 IIS 中，所有 Web 服务在 ASP.NET 工作进程都运行。  
  
 IIS 使用应用程序池处理 Web 服务请求。 IIS 支持多个应用程序池，每个应用程序池进程可以在不同的用户上下文下运行。  
  
### <a name="biztalk-isolated-hosts"></a>BizTalk 独立主机主机  
 若要启用 Web 服务，必须创建至少一个独立的主机中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 独立主机是外部进程，如 ISAPI 扩展和 ASP.NET 进程的 BizTalk Server 不创建或控制。 这些类型的外部进程必须承载某些适配器，如 HTTP/S 和 SOAP。  
  
 BizTalk Server 配置管理器创建的 BizTalkServerIsolatedHost[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用作默认独立主机。 BizTalk Isolated Host Users 组是默认情况下与此主机关联的 Windows 组的名称。 有关主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
 一个独立的主机实例运行只有一个适配器。 如果用一个独立主机配置 HTTP 和 SOAP 适配器的接收处理程序，必须创建两个应用程序池，每个适配器的一个应用程序池。  
  
 例如，如果你打算配置两个独立主机，如下所示：  
  
|独立的主机名称|接收位置|  
|------------------------|-----------------------|  
|独立主机 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1**注意：****独立主机 1**用于 SOAP 和 HTTP 适配器的接收处理程序。|  
|独立的主机 2|HTTP_ReceiveLocation2|  
  
 你可以创建四个虚拟目录，每个接收位置，按如下所示：  
  
|接收位置|虚拟目录|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 然后必须创建至少三个应用程序池的虚拟目录，如下所示：  
  
> [!NOTE]  
>  必须为每个独立主机创建至少一个应用程序池。  
  
|虚拟目录|应用程序池|Description|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|因为所有接收位置都具有相同的独立主机 (独立主机 1) 和相同的协议，则不需要单独的应用程序池。|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|需要单独的应用程序池，因为接收位置从同一主机 (独立主机 1) 中的其他接收位置使用不同协议 (SOAP)。|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|需要单独的应用程序池，因为接收位置在独立主机 1 以外的主机下运行。|  
  
 创建应用程序池，请记住以下重要事项：  
  
-   必须将应用程序池的用户帐户添加到独立的主机的相应本地或域组。 请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
-   你需要匹配独立主机实例和相应的应用程序池根据上述表格之间的用户帐户。 有关独立主机实例和应用程序池的用户帐户之间的关系的详细信息，请参阅[如何更改服务帐户和密码](../core/how-to-change-service-accounts-and-passwords.md)。  
  
### <a name="database-access-for-single-server-installations"></a>单服务器安装的数据库访问  
 如果 BizTalk Server 和 BizTalk 管理数据库驻留在同一台服务器上，应设置 ASP.NET 工作进程或 IIS 应用程序池的用户上下文，为本地 ASPNET 用户帐户，或具有最低权限的本地或域用户帐户。  
  
### <a name="database-access-for-multiple-server-installations"></a>多个服务器安装的数据库访问  
 如果 BizTalk Server 和 BizTalk 管理数据库驻留在不同服务器上，应将 ASP.NET 工作进程或 IIS 应用程序池的用户上下文更改为域用户帐户。  
  
 当实现多服务器部署时，独立的主机 Windows 组必须存在 BizTalk 数据库服务器将要加入的域。  
  
### <a name="minimizing-account-privileges-and-user-rights"></a>帐户权限和用户权限降至最低  
 使用独立的主机以便运行在外部进程访问到所需的资源与 BizTalk Server 进行交互的最小数量的适配器。 对于更安全的部署，您应该为提供的用户上下文的外部进程最小特权。  
  
### <a name="security-recommendations-for-biztalk-web-services-publishing-wizard"></a>BizTalk Web Services 发布向导的安全建议  
 BizTalk Web Services 发布向导创建的虚拟目录将从父虚拟目录或网站继承访问控制列表 (ACL) 和身份验证要求。 如果父虚拟目录或网站允许匿名访问，BizTalk Web Services 发布向导将创建虚拟目录时删除该功能。  
  
### <a name="enabling-aspnet-40-for-published-web-services"></a>为已发布的 Web 服务启用 ASP.NET 4.0  
请参阅[如何能够为 ASP.NET 4.0 发布的 Web Services](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)。  
  
## <a name="using-the-biztalk-web-services-publishing-wizard"></a>使用 BizTalk Web Services 发布向导  
 有关业务流程发布为 Web 服务的详细信息，请参阅[业务流程发布为 Web 服务](../core/publishing-an-orchestration-as-a-web-service.md)。  
  
 为 Web 服务发布架构的详细信息，请参阅[将架构发布为 Web 服务](../core/publishing-schemas-as-a-web-service.md)。  
  
## <a name="planning-for-publishing-wcf-services"></a>规划发布 WCF 服务  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引入了 Windows Communication Foundation (WCF) 的内置支持。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使您可以重用和聚合业务流程中的所有现有 WCF 服务。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外实现 WCF 服务中的本地适配器的支持。 本机适配器支持提供了可伸缩性、 容错能力和跟踪功能为 WCF 服务，而无需编写代码。 有关 WCF 适配器的信息，请参阅[WCF 适配器](../core/wcf-adapters.md)。  
  
 有关规划中的 WCF 服务的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[发布 WCF 服务](../core/publishing-wcf-services.md)。  
  
## <a name="see-also"></a>请参阅  
 [规划使用 Web 服务](../technical-guides/planning-for-consuming-web-services.md)
