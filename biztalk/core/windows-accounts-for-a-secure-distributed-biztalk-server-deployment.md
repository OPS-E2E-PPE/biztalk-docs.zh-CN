---
title: "Windows 帐户对于安全的分布式的 BizTalk 服务器部署 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, Windows groups
- user accounts, naming conventions
- user accounts
- access control, Windows groups
- security, access control
- architecture, security
- security, Windows accounts
- administrator accounts
- user accounts, administrators
- architecture, large distributions
ms.assetid: 2a0893ef-8bfb-481b-b024-7f7d6e2a6f09
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04c7e6e28cc0deb83eaa7868c6c4ee17da8bc563
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="windows-accounts-for-a-secure-distributed-biztalk-server-deployment"></a>Windows 帐户，可以一种安全的分布式 BizTalk Server 部署
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 本部分提供有关在分布式 BizTalk Server 环境中创建 Windows 组和帐户的建议。 组名和帐户名暗示了组和帐户的功能。 您可以选择这些组和帐户的名称。 有关分布式 BizTalk Server 体系结构的详细信息，请参阅[大型分布式体系结构](../core/large-distributed-architecture.md)。  
  
## <a name="windows-groups-for-a-secure-distributed-biztalk-server-deployment"></a>安全分布式 BizTalk Server 部署的 Windows 组  
 下面列出了建议域管理员在域控制器的数据层创建的 Windows 组：  
  
-   SSO Administrators  
  
-   SSO Affiliate Administrators  
  
-   BizTalk Server Administrators  
  
-   BizTalk Server Operators  
  
 有关 BizTalk Server 使用的 Windows 组的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
 除了上述域组之外，下表还列出了其他专用于确保部署安全的组，域管理员也可以在域控制器的数据层创建这些组：  
  
|组名（建议）|用途|  
|------------------------------|-------------|  
|BizTalk Processing Host Users 1|用于特定进程内主机（用来处理消息）的实例的组。 在 BizTalk Server 环境中将为用于处理消息的每个进程内主机创建一个组。|  
|BizTalk Send Host Users 1|用于特定进程内主机（用来发送消息）的实例的组。 在 BizTalk Server 环境中将为用于发送消息的每个进程内主机创建一个组。|  
|BizTalk Receive Host Users 1|用于特定进程内主机（用来接收消息）的实例的组。 在 BizTalk Server 环境中将为用于接收消息的每个进程内主机创建一个组。|  
|BizTalk Tracking Host Users|用于专门进行跟踪的 BizTalk 主机的组。|  
|BizTalk SOAP Users |用于为 SOAP 适配器使用的独立主机的实例的组。|  
|BizTalk HTTP Users|用于为 HTTP 适配器使用的独立主机的实例的组。|  
  
 域管理员必须在服务接口域的域控制器中创建以下组：  
  
-   BizTalk BAM Portal Users  
  
## <a name="windows-user-or-service-accounts-for-a-secure-distributed-biztalk-server-deployment"></a>安全分布式 BizTalk Server 部署的 Windows 用户或服务帐户  
 下表列出了建议域管理员在数据域的域控制器中创建的帐户。 域管理员必须确保这些帐户是所指定组的成员。  
  
 有关 BizTalk Server 使用的用户帐户的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
|帐户名（示例）|类型|所属的组|  
|------------------------------|----------|---------------------|  
|SSO administrator|用户|SSO Administrators|  
|SSO service|服务|SSO Administrators|  
|SSO master secret|服务|SSO Administrators|  
|BizTalk administrator|用户|BizTalk Administrators<br /><br /> SSO Affiliate Administrators|  
|BizTalk operator|用户|BizTalk Operators|  
|BizTalk Processing 1|服务|BizTalk Processing Host Users 1|  
|BizTalk 处理 2**注意：**可以在你的环境中对于每个处理主机创建多个帐户。|服务|BizTalk Processing Host Users 1|  
|BizTalk Tracking|服务|BizTalk Tracking Host Users|  
|SOAP 适配器|服务|BizTalk SOAP Users |  
|HTTP 适配器|服务|BizTalk HTTP Users|  
|规则引擎更新服务|服务||  
|安装|用户|SSO Administrators（只用于配置主密钥服务器）<br /><br /> 本地管理员<br /><br /> sysadmin SQL Server 角色<br /><br /> OLAP Administrator|  
|BAM Application pool|服务|IIS_WPG|  
|BAM Management|服务|IIS_WPG|  
|BAM Notification|服务|SQLServer2005NotificationServicesUser$\<**ComputerName**\>|  
  
 下表列出了建议域管理员在公司域的域控制器中创建的帐户：  
  
|帐户名|类型|  
|------------------|----------|  
|SharePoint administrator|用户|  
|SharePoint Site credential|用户|  
  
## <a name="see-also"></a>另请参阅  
 [大型分布式体系结构](../core/large-distributed-architecture.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)