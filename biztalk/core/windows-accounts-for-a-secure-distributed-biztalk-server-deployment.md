---
title: Windows 帐户安全分布式的 BizTalk Server 部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493f0e9e095a5de8b1fc57eec658981ea3befa88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401569"
---
# <a name="windows-accounts-for-a-secure-distributed-biztalk-server-deployment"></a>Windows 帐户安全分布式 BizTalk Server 部署
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 本部分提供有关分布式 BizTalk Server 环境中创建 Windows 组和帐户的建议。 组和帐户名称是基于组和帐户的功能的建议。 您可以选择这些组和帐户的名称。 有关分布式 BizTalk Server 体系结构的详细信息，请参阅[大型分布式体系结构](../core/large-distributed-architecture.md)。  
  
## <a name="windows-groups-for-a-secure-distributed-biztalk-server-deployment"></a>Windows 组安全分布式 BizTalk Server 部署  
 以下列表介绍了建议的域管理员在数据层中的域控制器中创建的 Windows 组。  
  
- SSO Administrators  
  
- SSO 关联管理员  
  
- BizTalk Server Administrators  
  
- BizTalk Server Operators  
  
  有关 BizTalk Server 使用的 Windows 组的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
  除了以前的域组下, 表列出了特定于域管理员在数据层中的域控制器中创建的安全部署的其他组。  
  
|组名 （建议）|用途|  
|------------------------------|-------------|  
|处理 BizTalk 主机用户 1|用来处理消息的特定进程内主机的主机实例进行分组。 创建一个组的每个进程内主机在 BizTalk Server 环境中用于处理消息。|  
|BizTalk 发送主机用户 1|用于发送消息的特定进程内主机的主机实例的组。 为用于发送消息，BizTalk Server 环境中每个进程内主机创建一个组。|  
|BizTalk 接收主机用户 1|用来接收消息的特定进程内主机的主机实例的组。 为使用 BizTalk Server 环境中接收消息的每个进程内主机创建一个组。|  
|BizTalk 跟踪主机用户|用于专门进行跟踪的 BizTalk 主机组。|  
|BizTalk SOAP Users|用于 SOAP 适配器的独立主机的主机实例的组。|  
|BizTalk HTTP 用户|用于为 HTTP 适配器使用独立的主机的主机实例的组。|  
  
 域管理员必须在服务接口域的域控制器中创建以下组：  
  
-   BizTalk BAM 门户用户  
  
## <a name="windows-user-or-service-accounts-for-a-secure-distributed-biztalk-server-deployment"></a>Windows 用户或服务帐户的安全分布式的 BizTalk Server 部署  
 下表列出了建议域管理员创建的数据域的域控制器中使用的帐户。 域管理员必须确保帐户是所指定组的成员。  
  
 有关 BizTalk Server 使用的用户帐户的完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
|帐户名称 （示例）|类型|组的成员|  
|------------------------------|----------|---------------------|  
|SSO 管理员|“用户”|SSO Administrators|  
|SSO 服务|服务|SSO Administrators|  
|SSO 主密钥|服务|SSO Administrators|  
|BizTalk 管理员|“用户”|BizTalk 管理员<br /><br /> SSO 关联管理员|  
|BizTalk 操作员|“用户”|BizTalk 操作员|  
|BizTalk 处理 1|服务|处理 BizTalk 主机用户 1|  
|BizTalk 处理 2**注意：** 在您的环境中，可以为每个处理主机创建多个帐户。|服务|处理 BizTalk 主机用户 1|  
|BizTalk 跟踪|服务|BizTalk 跟踪主机用户|  
|SOAP 适配器|服务|BizTalk SOAP Users|  
|HTTP 适配器|服务|BizTalk HTTP 用户|  
|规则引擎更新服务|服务||  
|安装|“用户”|SSO Administrators （只用于配置主密钥服务器）<br /><br /> 本地管理员<br /><br /> sysadmin SQL Server 角色<br /><br /> OLAP 管理员|  
|BAM 应用程序池|服务|IIS_WPG|  
|BAM 管理|服务|IIS_WPG|  
|BAM 通知|服务|SQLServer2005NotificationServicesUser$\<**ComputerName**\>|  
  
 下表列出了建议使用域管理员在企业域一部分的域控制器中创建的帐户。  
  
|帐户名|类型|  
|------------------|----------|  
|SharePoint 管理员|“用户”|  
|SharePoint 站点凭据|“用户”|  
  
## <a name="see-also"></a>请参阅  
 [大型分布式体系结构](../core/large-distributed-architecture.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)