---
title: 组和服务帐户的访问控制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f3e34d34f9b6a79b1379c98aa362c266a52424c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362070"
---
# <a name="access-control-for-groups-and-service-accounts"></a>组和服务帐户的访问控制
每个 BizTalk 主机实例在用户创建服务帐户下运行。 必须提供的服务帐户并且他们的密码时创建主机实例的计算机上。 然后，BizTalk Server 可确保帐户具有完成其工作的每个这些服务帐户添加到本地或域 Windows 组，反过来，它将添加到 SQL Server 数据库角色特定于该主机所需的最低用户权限。  
  
 这种方法提供了以下好处：  
  
- 您可以为每个主机实例的服务不同的服务帐户，因此可以更改每个主机实例的密码，而无需使服务器脱机。 您可以执行密码滚动更新，而无需中断服务。  
  
  > [!NOTE]
  >  受信任验证主机和不受信任验证主机不能使用相同的服务帐户。  
  
- 如果你授予对本地资源用户权限或在 Microsoft SQL Server™ 级别的域组，可以添加和减去服务帐户，而无需更改的用户权限授予在 SQL Server 中，因此降低了管理负担和总拥有成本。  
  
  若要确保服务帐户具有完成其作业所需的最低用户权限，BizTalk Server 创建的服务帐户的 SQL Server 数据库角色不是在所有 BizTalk Server 数据库上完全相同。 有关管理和跟踪数据库，所有主机实例服务帐户需要访问相同的 SQL Server 对象，因此 BizTalk Server 创建名为 BTS_Host_User 的单个 SQL Server 数据库角色。 BizTalk 将添加到此 SQL Server 数据库角色的 BizTalk 主机创建的所有 Windows 组。  
  
  MessageBox 数据库中，对于每个主机具有一些专用于该主机的资源。 BizTalk Server 创建的 SQL Server 数据库角色，每个主机，名为 BTS_\<*主机名*\>用户 （_u)，并添加到其各自的 SQL Server 数据库角色的每个主机的 Windows 组，以阻止访问的一个通过另一台主机的主机资源。  
  
## <a name="accounts-not-supported-by-biztalk-server"></a>BizTalk Server 不支持的帐户  
 BizTalk Server 不支持使用任何以下内置 Windows 帐户：  
  
-   NT_AUTHORITY\NetworkService  
  
-   LocalSystem  
  
-   NT_AUTHORITY\LocalService  
  
## <a name="see-also"></a>请参阅  
 [管理角色的访问控制](../core/access-control-for-administrative-roles.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [访问控制和数据安全性](../core/access-control-and-data-security.md)