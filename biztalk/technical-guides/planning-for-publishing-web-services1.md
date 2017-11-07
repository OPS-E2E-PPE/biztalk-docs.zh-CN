---
title: "发布 web 服务规划 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b571c3aa-874b-43f7-af2e-5a71113a93dd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34539704a0725a96464fae03226fb88cdd6660c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="planning-for-publishing-web-services"></a>规划发布 Web 服务
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 Web 服务提供内置支持。 它使你重复使用并聚合中你的业务流程将现有的 Web 服务。  

## <a name="overview"></a>概述
 你也可以发布 （公开） 作为 Web 服务来分隔 Web 你业务流程服务从业务过程逻辑，这使您能够更新或替换的业务逻辑，而无需触摸用 Web 服务逻辑的代码所需的逻辑。 此功能称为实现"模块化的代码"。 一般情况下它被视为最佳做法尽可能实现模块化代码。 发布 Web 服务需要启用 Web 服务并将其作为 Web 服务使用 BizTalk Web 服务发布向导发布了业务流程或架构。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现支持通过 SOAP 适配器使用的 Web 服务中的本机适配器。 本机适配器支持为 Web Services 提供了可伸缩性、容错功能和跟踪功能，且无需为此编写代码。 有关 SOAP 适配器的详细信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。  
  
规划 Web 服务可以划分为两个类别，规划用于发布 Web 服务和规划使用 Web 服务。 本主题介绍发布 Web 服务时应遵循的步骤。  
  
## <a name="enabling-web-services"></a>启用 Web Services  
 若要发布 Web Services，必须配置 Internet 信息服务 (IIS)、BizTalk 独立主机以及 Windows 用户和组帐户。 本部分提供有关启用 web 服务的概述。 有关启用 Web 服务的详细信息，请参阅 IIS 文档。  
  
### <a name="internet-information-services"></a>Internet Information Services
 可以将 Web 服务发布到了 IIS 和 ASP.NET 一起配置的 Windows 系统中。 在 IIS 中，所有 Web 服务在 ASP.NET 工作进程中都运行。  
  
 IIS 使用用于处理 Web 服务请求的应用程序池。 IIS 支持多个应用程序池，每个应用程序池进程可以在不同用户上下文下运行。  
  
### <a name="biztalk-isolated-hosts"></a>BizTalk 隔离主机  
 若要启用 Web 服务，必须创建中的至少一个独立主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 隔离的主机表示外部进程，如 ISAPI 扩展和 BizTalk 服务器不会创建或控制的 ASP.NET 进程。 这些类型的外部进程必须承载某些适配器，如 HTTP/S 和 SOAP。  
  
 BizTalk Server 配置管理器创建的 BizTalkServerIsolatedHost[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用作为默认的独立主机。 默认情况下，BizTalk Isolated Host Users 组是与此主机关联的 Windows 组的名称。 有关主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
 一个独立主机实例只能运行一个适配器。 如果用一个独立主机配置 HTTP 和 SOAP 适配器的接收处理程序，则必须创建两个应用程序池，每个适配器对应一个应用程序池。  
  
 例如，如果你打算将两个独立的主机，配置，如下所示：  
  
|独立的主机名|接收位置|  
|------------------------|-----------------------|  
|独立主机 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1**注意：** **隔离主机 1**用于接收的 SOAP 和 HTTP 适配器处理程序。|  
|隔离的主机 2|HTTP_ReceiveLocation2|  
  
 你可以创建四个虚拟目录，一个用于每个接收位置，如下所示：  
  
|接收位置|虚拟目录|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 然后必须创建虚拟目录的至少三个应用程序的池，如下所示：  
  
> [!NOTE]  
>  必须至少为每个独立主机创建一个应用程序池。  
  
|虚拟目录|应用程序池|Description|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|不需要单独的应用程序池，原因是所有接收位置都具有相同的独立主机（独立主机 1）和相同的协议。|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|需要单独的应用程序池，原因是此接收位置使用的协议 (SOAP) 与同一主机（独立主机 1）中其他接收位置使用的协议不同。|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|需要单独的应用程序池，原因是此接收位置在独立主机 1 以外的主机下运行。|  
  
 创建应用程序池，请记住以下重要事项：  
  
-   必须将应用程序池的用户帐户添加到独立主机的相应本地或域组中。 请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
-   你需要根据上述表格在独立主机实例和相应的应用程序池之间匹配用户帐户。 有关独立的主机实例和应用程序池的用户帐户之间的关系的详细信息，请参阅[如何更改服务帐户和密码](../core/how-to-change-service-accounts-and-passwords.md)。  
  
### <a name="database-access-for-single-server-installations"></a>对于单个服务器安装的数据库访问  
 如果 BizTalk Server 和 BizTalk 管理数据库驻留在同一台服务器上，应将设置 ASP.NET 工作进程或 IIS 应用程序池的用户上下文，为本地 ASPNET 用户帐户，或具有最低权限的本地或域用户帐户。  
  
### <a name="database-access-for-multiple-server-installations"></a>对于多个服务器安装的数据库访问  
 如果 BizTalk Server 和 BizTalk 管理数据库驻留在不同服务器上，你应将 ASP.NET 工作进程或 IIS 应用程序池的用户上下文更改为域用户帐户。  
  
 在实施多服务器部署时，独立的主机 Windows 组必须存在 BizTalk 数据库服务器所属的域。  
  
### <a name="minimizing-account-privileges-and-user-rights"></a>将帐户特权和用户权限降至最低  
 使用独立主机可为在外部进程中运行的适配器赋予访问与 BizTalk Server 交互所需的最小数量资源的权限。 对于更安全的部署，你应为外部进程最小权限提供的用户上下文。  
  
### <a name="security-recommendations-for-biztalk-web-services-publishing-wizard"></a>发布向导的 BizTalk Web 服务的安全建议  
 BizTalk Web Services 发布向导创建的虚拟目录将从父虚拟目录或网站继承访问控制列表 (ACL) 和身份验证要求。 如果父虚拟目录或网站允许匿名访问，则 BizTalk Web Services 发布向导将在创建此虚拟目录时删除这一功能。  
  
### <a name="enabling-aspnet-40-for-published-web-services"></a>为发布的 Web 服务中启用 ASP.NET 4.0  
请参阅[如何启用 ASP.NET 4.0 for 发布 Web 服务](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)。  
  
## <a name="using-the-biztalk-web-services-publishing-wizard"></a>使用发布向导的 BizTalk Web 服务  
 有关发布作为 Web 服务业务流程的详细信息，请参阅[发布作为 Web 服务业务流程](../core/publishing-an-orchestration-as-a-web-service.md)。  
  
 作为 Web 服务发布的架构的详细信息，请参阅[作为 Web 服务的发布架构](../core/publishing-schemas-as-a-web-service.md)。  
  
## <a name="planning-for-publishing-wcf-services"></a>规划发布 WCF 服务  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引入了内置支持 Windows Communication Foundation (WCF)。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可重复使用和聚合你业务流程中的所有现有 WCF 服务。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 WCF 服务还实现对本机适配器的支持。 本地适配器支持为 WCF 服务提供了可伸缩性、容错功能和跟踪功能，且用户无需为此编写代码。 有关 WCF 适配器的信息，请参阅[WCF 适配器](../core/wcf-adapters.md)。  
  
 有关规划中的 WCF 服务的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[发布 WCF 服务](../core/publishing-wcf-services.md)。  
  
## <a name="see-also"></a>另请参阅  
 [规划使用 Web 服务](../technical-guides/planning-for-consuming-web-services.md)
