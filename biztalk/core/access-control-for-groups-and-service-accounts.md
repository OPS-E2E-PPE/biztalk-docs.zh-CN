---
title: "组和服务帐户的访问控制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- access control, service accounts
- user accounts, default accounts
- service accounts, security
- user accounts, unsupported
- access control, groups
- service accounts, access control
- groups, access control
- groups, security
ms.assetid: 411a7bfa-6675-4d09-9e37-83e2941df3c6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67bc5799d88c0dca876df463eb37d4af65ec84d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="access-control-for-groups-and-service-accounts"></a>组和服务帐户的访问控制
在用户创建服务帐户下运行每个 BizTalk 主机实例。 必须提供的服务帐户并且他们的密码时创建主机实例的计算机上。 BizTalk Server 然后确保帐户具有执行其作业通过将每个这些服务帐户添加到本地或域的 Windows 组，反过来，它将添加到 SQL Server 数据库角色特定于该主机所需的最小用户权限。  
  
 此方法提供了以下好处：  
  
-   你可以提供每个主机实例的服务不同的服务帐户，因而可能更改每个主机实例的密码，而无需使服务器脱机。 你可以执行滚动密码更新而不会中断服务。  
  
    > [!NOTE]
    >  不能使用相同的服务帐户的受信任的身份验证的主机和主机的不受信任的身份验证。  
  
-   如果你授予对本地资源的用户权限或 Microsoft SQL Server™ 级别的域组，你可以添加和减去而无需更改在 SQL Server，因此降低管理负担和总拥有成本中授予的用户权限的服务帐户。  
  
 若要确保服务帐户具有执行其作业所需的最小用户权限，BizTalk Server 创建的服务帐户的 SQL Server 数据库角色不在 BizTalk Server 的所有数据库上完全相同。 有关管理和跟踪数据库，所有主机实例服务帐户需要访问相同的 SQL Server 对象，因此将 BizTalk Server 创建一个名为 BTS_Host_User 的单个 SQL Server 数据库角色。 BizTalk 将添加到此 SQL Server 数据库角色的 BizTalk 主机创建的所有 Windows 组。  
  
 对于 MessageBox 数据库中，每个主机有一些专用于该主机的资源。 BizTalk Server 创建的 SQL Server 数据库角色，每个主机，名为 BTS_\<*主机名*> （_u)，并添加到其各自的 SQL Server 数据库角色的每个主机的 Windows 组，以阻止访问一台主机由另一个主机的资源。  
  
## <a name="accounts-not-supported-by-biztalk-server"></a>BizTalk Server 不支持的帐户  
 BizTalk Server 不支持使用任何以下内置 Windows 帐户：  
  
-   NT_AUTHORITY\NetworkService  
  
-   LocalSystem  
  
-   NT_AUTHORITY\LocalService  
  
## <a name="see-also"></a>另请参阅  
 [用于管理角色的访问控制](../core/access-control-for-administrative-roles.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [访问控制和数据安全](../core/access-control-and-data-security.md)