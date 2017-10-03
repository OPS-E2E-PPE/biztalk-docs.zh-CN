---
title: "Windows 组和 BizTalk Server 中的用户帐户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, BTS_ADMIN_USERS role [SQL Server database]
- MessageBox database, BTS_HOST_USERS role [SQL Server database]
- Rule Engine database, BTS_HOST_USERS role [SQL Server database]
- Management database, BTS_OPERATORS role [SQL Server database]
- BTS_HOST_USERS role [SQL Server database]
- NSSubscriberAdmin role [SQL Server database]
- Management database, tpm_user role [SQL Server database]
- SSO, securityadmin role [SQL Server database]
- IIS_WPG group
- BAM Notification service account
- EDI_ADMIN_USERS role [SQL Server database]
- Archive database [BAM], db_owner role [SQL Server database]
- Primary Import database [BAM], db_owner role [SQL Server database]
- Primary Import database [BAM], BAM_EVENT_WRITER role [SQL Server database]
- Notification Services Application database [BAM], db_owner role [SQL Server database]
- NSRunService role [SQL Server database]
- RE_HOST_USERS role [SQL Server database]
- MessageBox database, BTS_OPERATORS role [SQL Server database]
- Rule Engine database, RE_HOST_USERS role [SQL Server database]
- Windows groups, creating
- securityadmin role [SQL Server database]
- BizTalk Isolated Host Instance service account
- In-Process BizTalk Host groups
- Primary Import database [BAM], BTS_ADMIN_USERS role [SQL Server database]
- SSO Affiliate Administrators [Windows group]
- Star Schema database [BAM], db_owner role [SQL Server database]
- Notification Services Instance database [BAM], db_owner role [SQL Server database]
- MessageBox database, BTS_ADMIN_USERS role [SQL Server database]
- Rule Engine Update Service account
- Configuration Manager, creating user accounts
- SSO Administrators [Windows group]
- Rule Engine database, BTS_ADMIN_USERS role [SQL Server database]
- Tracking database, BTS_OPERATORS role [SQL Server database]
- Primary Import database [BAM], BAM_ManagementNSReader role [SQL Server database]
- Notification Services Instance database [BAM], role [SQL Server database]
- BizTalk Application Users [Windows group]
- user accounts, creating
- Rule Engine database, BTS_OPERATORS role [SQL Server database]
- STS_WPG group
- BAM_ManagementWS role [SQL Server database]
- BTS_OPERATORS role [SQL Server database]
- Tracking database, BTS_HOST_USERS role [SQL Server database]
- SSO, db_owner role [SQL Server database]
- Notification Services Application database [BAM], role [SQL Server database]
- OLAP Administrators
- BAM_EVENT_WRITER role [SQL Server database]
- Windows groups, group list
- tpm_user role [SQL Server database]
- BizTalk Host Instance service account
- Base DBI database, EDI_ADMIN_USERS role [SQL Server database]
- Primary Import database [BAM], role [SQL Server database]
- BizTalk SharePoint Adapter Enabled Hosts [Windows group]
- BAM Management Web service account
- db_owner role [SQL Server database]
- Management database, BTS_ADMIN_USERS role [SQL Server database]
- Configuration Manager, creating groups
- Management database, BTS_HOST_USERS role [SQL Server database]
- BizTalk Server Operators [Windows group]
- Base DBI database, BTS_OPERATORS role [SQL Server database]
- Enterprise Single Sign-On Service account
- NSAdmin role [SQL Server database]
- BAM_ManagementNSReader role [SQL Server database]
- Notification Services Application database [BAM], NSRunService role [SQL Server database]
- BTS_ADMIN_USERS role [SQL Server database]
- BizTalk Isolated Host Users [Windows group]
- Notification Services Instance database [BAM], NSAdmin role [SQL Server database]
- SQLServer2005NotificationServicesUser
- EDI Subsystem Users [Windows group]
- Primary Import database [BAM], BTS_HOST_USERS role [SQL Server database]
- BizTalk Server Administrators [Windows group]
- BAM Portal Users [Windows group]
- Notification Services Application database [BAM], NSAdmin role [SQL Server database]
ms.assetid: a01603bd-4105-4691-819d-de43b00b40f3
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f229c950c3f49eca80810e9702ce021f0e8579
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="windows-groups-and-user-accounts-in-biztalk-server"></a>BizTalk Server 中的 Windows 组和用户帐户
有关 BizTalk Server 本地和域组和用户帐户的信息。 如果在单台计算机上安装了 BizTalk Server 和所有必备软件，则默认情况下配置管理器将为你创建必需的 BizTalk 组帐户。 本部分中包含的信息适用于多计算机拓扑结构。  
  
> [!IMPORTANT]
>  BizTalk Server 只有在单计算机配置中才支持本地组和本地用户帐户。 BizTalk Server 在单计算机配置和多计算机配置中都支持域组和域用户帐户。 如果你的 BizTalk Server 配置使用域组，则在配置 BizTalk Server 前必须先手动创建这些组。 配置管理器无法创建域组。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-create-windows-group-and-user-accounts-in-biztalk-server"></a>在 BizTalk Server 中创建 Windows 组和用户帐户  
  
1.  使用 Active Directory 中，从**启动**菜单上，指向**程序**，指向**管理工具**，然后选择**Active Directory 用户和计算机**。  
  
2.  在 Active Directory 用户和计算机窗口中，右键单击底部的右窗格中，或右键单击**用户**的左窗格中的导航树中的文件夹。  
  
3.  选择**新建**，然后选择**组**或**用户**。  
  
4.  输入下表中概述的组和用户信息。  
  
 下表列出了 BizTalk Server 使用的 Windows 组和他们的成员。 它还给出了这些组的 SQL Server 角色或数据库角色。  
  
|分组|组的说明|成员身份|SQL Server 角色或数据库角色|  
|-----------|-----------------------|----------------|----------------------------------------|  
|SSO Administrators|企业单一登录 (SSO) 服务的管理员。|包含企业单一登录服务的服务帐户。<br /><br /> 包含配置和管理 BizTalk Server 和 SSO 服务所需的用户/组。<br /><br /> 包含在配置 SSO 主密钥服务器时用于运行 BizTalk 配置管理器的帐户。|SSO 的 db_owner SQL Server 数据库角色<br /><br /> SSO 所在的 SQL Server 的 securityadmin SQL Server 角色|  
|SSO Affiliate Administrators|某些 SSO 关联应用程序的管理员。<br /><br /> 可以创建/删除 SSO 关联应用程序、 管理用户的映射，并设置应用程序用户的关联的凭据|不包含服务帐户。<br /><br /> 包含 BizTalk Server 管理员使用的帐户。||  
|BizTalk Server Administrators|具有执行管理任务所需的最低权限。<br /><br /> 可以部署解决方案，管理应用程序并解决在消息处理过程中出现的问题。<br /><br /> 若要执行关于适配器、接收处理程序、发送处理程序和接收位置的管理任务，则必须将 BizTalk Server Administrators 的成员添加到 Single Sign-On Affiliate Administrators 中。<br /><br /> 有关详细信息，请参阅[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)。|包含配置和管理 BizTalk Server 所需的用户/组。|以下数据库中的 BTS_ADMIN_USERS SQL Server 数据库角色：<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> 以下数据库中的 db_owner SQL Server 数据库角色：<br /><br /> BAMStarSchema<br /><br /> BAMPrimaryImport<br /><br /> BAMArchive<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> 以下数据库中的 NSAdmin SQL Server 数据库角色：<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMAnalysis OLAP 数据库宿主计算机上的 OLAP 管理员。|  
|BizTalk Server Operators|具有只能执行监视和故障排除操作的低权限角色。<br /><br /> 有关详细信息，请参阅[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)|包含将监视解决方案的用户/组。<br /><br /> 不包含服务帐户。|以下数据库中的 BTS_OPERATORS SQL Server 数据库角色：<br /><br /> BizTalkDTADb<br /><br /> BizTalkEDIDb<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb|  
|BizTalk Application Users|由配置管理器创建的首个进程内 BizTalk 主机组的默认名称。<br /><br /> 在你的环境中每个进程内主机将使用一个 BizTalk 主机组。<br /><br /> 包含能够访问进程内 BizTalk 主机（BizTalk Server 中的主机进程 BTSNTSvc.exe）的帐户。|包含 BizTalk 主机组所属主机中，BizTalk 进程内主机实例的服务帐户。|以下数据库中的 BTS_HOST_USERS SQL Server 数据库角色：<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> BAMPrimaryImport 中的 BAM_EVENT_WRITER SQL Server 数据库角色|  
|BizTalk Isolated Host Users|由配置管理器创建的首个独立 BizTalk 主机组的默认名称。 独立 BizTalk 主机指不在 BizTalk Server 上运行的 BizTalk 主机，例如 HTTP 和 SOAP。<br /><br /> 在你的环境中每个独立主机将使用一个 BizTalk 独立主机组。|包含独立 BizTalk 主机组所属主机中，BizTalk 独立主机实例的服务帐户。|以下数据库中的 BTS_HOST_USERS SQL Server 数据库角色：<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport|  
|BAM Portal Users|能够访问 BAM 门户网站。|默认情况下，此角色使用 Everyone 组。<br /><br /> 不包含服务帐户。||  
|BizTalk SharePoint Adapter Enabled Hosts|能够访问 Windows SharePoint Services 适配器 Web Services|包含可以调用 SharePoint 适配器的 BizTalk 主机实例的服务帐户。||  
|BizTalk B2B Operators 组|减轻管理员执行所有参与方管理操作责任的新 BizTalk 角色。 使用此角色，与该角色关联的 Windows 用户可以执行所有参与方管理操作。|包含的用户/组必须能够配置和管理 BizTalk Server TPM 数据以及监视解决方案。|在以下数据库 BTS_OPERATORS SQL Server 数据库角色： BizTalkDTADb、 BizTalkMgmtDb、 BizTalkMsgBoxDb、 BizTalkRuleEngineDb 和 BAMPrimaryImport|  
  
 下表列出了 BizTalk Server 所使用的 Windows 用户帐户或服务帐户以及组从属关系。 它还给出了这些帐户的 SQL Server 角色或数据库角色。  
  
|用户|用户说明|组从属关系|SQL Server 角色或数据库角色|  
|----------|----------------------|-----------------------|----------------------------------------|  
|企业单一登录服务|用于运行企业单一登录服务（该服务访问 SSO 数据库）的服务帐户。|SSO Administrators||  
|BizTalk 主机实例帐户|用于运行 BizTalk 进程内主机实例（即访问进程内 BizTalk 主机实例 BTNTSVC 的实例）的服务帐户。|BizTalk Application Users<br /><br /> SSO Affiliate Administrators||  
|BizTalk 独立主机实例帐户|用于运行 BizTalk 独立主机实例 (HTTP/SOAP) 的服务帐户。|BizTalk Isolated Host Users<br /><br /> SSO Affiliate Administrators<br /><br /> IIS_WPG||  
|规则引擎更新服务|用于运行规则引擎更新服务收到的规则引擎数据库通知部署/取消部署策略的服务帐户。||BizTalkRuleEngineDb 中的 RE_HOST_USERS SQL Server 数据库角色|  
|BAM Notification Services 用户|用于运行 BAM Notification Services（该服务访问 BAM 数据库）的服务帐户。|SQLServer2008NotificationServicesUser$\<**ComputerName**>|以下数据库中的 NSRunService SQL Server 数据库角色：<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMPrimaryImport 的 BAM_ManagementNSReader SQL Server 角色|  
|BAM 管理 Web Services 用户|访问各种 BAM 资源的 BAM 管理 Web Services (BAMManagementService) 的用户帐户。 BAM 门户带有登录 BAM 门户以管理警报、 XML 和 BAM 视图获取 BAM 定义用户凭据的调用 BAMManagementService|IIS_WPG|以下数据库中的 NSSubscriberAdmin SQL Server 数据库角色：<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMPrimaryImport 的 BAM_ManagementWS SQL Server 角色|  
|BAM 应用程序池帐户|BAM 门户网站宿主 BAMAppPool 的应用程序池帐户。|IIS_WPG||  
  
## <a name="in-this-section"></a>本节内容  
  
-   [本地组](../core/local-groups.md)  
  
-   [域组](../core/domain-groups.md)