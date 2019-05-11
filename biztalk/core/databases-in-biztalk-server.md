---
title: 在 BizTalk Server 中的数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM]
- Archive database [BAM]
- Analysis database [BAM]
- Windows SharePoint Services, content database
- Windows SharePoint Services, configuration database
- TPM database
- BizTalk Server, databases
- Notification Services Instance database [BAM]
- Star Schema database [BAM]
- Primary Import database [BAM]
- Rule Engine database
- databases, BizTalk Server
- SSO database
- Tracking Analysis Server database [BAM]
- Management database
- Tracking database
- MessageBox database
ms.assetid: bb504a26-cae6-4f2a-9b86-3554ef8f6045
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9abdbb476639b17fec4dc43dec5ddc5863e18a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389763"
---
# <a name="databases-in-biztalk-server"></a>在 BizTalk Server 中的数据库
Microsoft BizTalk Server 在 SQL Server 中安装多个数据库。 本主题介绍这些数据库，并在这些数据库使用的 SQL 逻辑组。  

## <a name="database-descriptions"></a>数据库说明
下表描述了典型使用特性进行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
BizTalk Server 运行时操作通常使用前四个数据库：BizTalk Server 管理数据库、 MessageBox 数据库、 跟踪数据库和 SSO 数据库。 根据您使用的 BizTalk Server 功能，您可能部分或所有其他数据库表中。  
  
|“数据库”|默认数据库名称|Description|  
|--------------|---------------------------|-----------------|  
|BAM 分析|BAMAnalysis|此数据库包含业务活动监视 (BAM) OLAP 多维数据集以进行联机和脱机分析。|  
|BAM 存档|BAMArchive|此数据库存档旧的业务活动数据。 创建 BAM 存档数据库以最大程度减少 BAM 主导入数据库中的业务活动数据的累计。|  
|BAM Notification Services 应用程序数据库|BAMAlertsApplication|此数据库包含 BAM 通知的警报信息。 例如，在创建警报使用 BAM 门户时，会将条目插入在指定与警报相关，以及其他支持的数据项的警报的条件和事件的数据库中。|  
|BAM 通知服务实例数据库|BAMAlertsNSMain|此数据库包含指定 notification services 如何连接到 BAM 监视的系统的实例信息。|  
|BAM 主导入数据库|BAMPrimaryImport|这是 BAM 从中收集原始跟踪数据的数据库。|  
|BAM 星型架构|BAMStarSchema|此数据库包含中间临时表、 和的度量值和维度表。|  
|BizTalk 管理数据库|BizTalkMgmtDb|此数据库是 BizTalk Server 的所有实例的中央元信息存储区。|  
|BizTalk MessageBox 数据库|BizTalkMsgBoxDb|BizTalk Server 引擎使用此数据库的路由、 排队、 实例管理和各种其他任务。|  
|BizTalk 跟踪数据库|BizTalkDTADb|此数据库存储运行状况监视 BizTalk Server 跟踪引擎所跟踪的数据。|  
|规则引擎数据库|BizTalkRuleEngineDb|此数据库是存储库：<br /><br /> -策略，这是一组相关的规则。<br />-词汇，即是规则中的数据引用的用户友好的特定于域的名称的集合。|  
|SSO 数据库|SSODB|此企业单一登录数据库安全地存储配置信息的接收位置。|  
|Windows SharePoint Services 配置数据库|*用户定义*|此数据库包含所有服务器的全局设置。|  
|Windows SharePoint Services 内容数据库|*用户定义*|此数据库包含的所有站点内容，如列表项和文档。|  

## <a name="database-login-accounts"></a>数据库登录帐户

[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建 SQL 登录组，并将它们映射到 SQL Server 角色和下表中列出的数据库角色：  
  
|Group|Description|SQL Server 角色或数据库角色|  
|-----------|-----------------|----------------------------------------|  
|BizTalk Application Users|包含能够访问进程内 BizTalk 主机（BizTalk Server 中的主机进程 BTSNTSvc.exe）的所有帐户。  在你的环境中每个进程内主机将使用一个 BizTalk 主机组。|以下数据库中的 BTS_HOST_USERS SQL Server 数据库角色：<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> BAMPrimaryImport 中的 BAM_EVENT_WRITER SQL Server 数据库角色|  
|BizTalk Isolated Host Users|包含能够访问独立 BizTalk 主机的所有帐户。 在你的环境中每个独立主机将使用一个 BizTalk 独立主机组。|以下数据库中的 BTS_HOST_USERS SQL Server 数据库角色：<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport|  
|BizTalk Server Administrators|包含所有将执行以下操作的 BizTalk Server 管理员：部署解决方案、管理应用程序并解决消息处理过程中的问题。|以下数据库中的 BTS_ADMIN_USERS SQL Server 数据库角色：<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> 以下数据库中的 db_owner SQL Server 数据库角色：<br /><br /> BAMStarSchema<br /><br /> BAMPrimaryImport<br /><br /> BAMArchive<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> 以下数据库中的 NSAdmin SQL Server 数据库角色：<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BizTalkDTADb<br /><br /> BizTalkMgmtDb<br /><br /> BAMAnalysis OLAP 数据库宿主计算机上的 OLAP 管理员。|  
|BizTalk Server Operators|具有只能执行监视和故障排除操作的低权限角色。<br /><br /> 不包含服务帐户|以下数据库中的 BTS_OPERATORS SQL Server 数据库角色：<br /><br /> BizTalkDTADb<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb|  
|SSO Administrators|企业单一登录 (SSO) 服务的顶级管理员。<br /><br /> 所包含的用于运行 BizTalk 配置的用户帐户必须属于该组。<br /><br /> 包含企业单一登录服务帐户，以及需要能够配置和管理 BizTalk Server 和 SSO 的所有用户/组。|SSO 的 db_owner SQL Server 数据库角色<br /><br /> SSO 所在的 SQL Server 的 securityadmin SQL Server 角色|  

[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建 SQL 登录帐户，并将它们映射到下表中列出的 SQL Server 数据库角色：  
  
|用户帐户|Description|SQL 数据库角色|  
|------------------|-----------------|------------------------|  
|规则引擎更新服务|用于运行规则引擎更新服务的用户帐户。|BizTalkRuleEngineDb 中的 RE_HOST_USERS SQL Server 数据库角色|  
|BAM Notification Services 用户|用于运行 BAM Notification Services 的用户帐户。|以下数据库中的 NSRunService SQL Server 数据库角色：<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMPrimaryImport 的 BAM_ManagementNSReader SQL Server 数据库角色|  
|BAM 管理 Web Services 用户|用于运行 BAM 管理 Web Services 的用户帐户。|以下数据库中的 NSSubscriberAdmin SQL Server 数据库角色：<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMPrimaryImport 的 BAM_ManagementWS SQL Server 数据库角色|  
  
  
## <a name="see-also"></a>请参阅  
 [数据库结构和作业](../core/database-structure-and-jobs.md)   
 [MessageBox 数据库](../core/the-messagebox-database.md)   
 [维护 BizTalk Server](../technical-guides/maintaining-biztalk-server-databases.md)   
 [缩放你的解决方案](../core/scaling-your-solutions.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [如何更改服务帐户和密码](../core/how-to-change-service-accounts-and-passwords.md)