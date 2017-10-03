---
title: "访问控制和数据安全 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- access control, BizTalk Server Operator role
- databases, SQL roles
- access control, about access control
- BizTalk Server Administrator role
- databases, access control
- access control
- access control, BizTalk Server Administrator role
- access control, SQL roles
- user accounts, access control
- BizTalk Server Operator role
ms.assetid: f04fd4a3-0f8c-4170-934a-9cc77edd7f34
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11cb00eabf6110de78e2d194e0a25bfac6a3b6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="access-control-and-data-security"></a>访问控制和数据安全
BizTalk Server 通过使用最低用户权限来限制对其进程和数据库的访问；您可以使用 Microsoft Windows Server 中的功能来确保系统中重要数据的安全。 为安全起见，BizTalk Server 管理员和 BizTalk 主机所具有的用户权限不应高于执行其作业所需的权限。  
  
 BizTalk 使用 SQL 角色控制对数据的管理访问，因此可通过工具或直接通过数据库控制对数据的访问。 使用 Host User 组和帐户控制 BizTalk 主机对数据的访问。  
  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，有两个管理角色： BizTalk 服务器管理员和 BizTalk Server 运算符。 无论通过安装还是 BizTalk Server 管理控制台，只要创建 BizTalk Server 数据库，BizTalk Server 就会自动为该数据库中的这两种管理角色创建 SQL 角色。 BizTalk Server 会为每个角色以及分配给该角色的任何 SQL Server 登录帐户，授予管理员在该数据库中对 SQL Server 对象（表、视图和存储过程等）执行管理任务时所需的最低用户权限。  
  
 BizTalk Server 管理员是高权限角色，有权访问配置数据和跟踪数据。 BizTalk Server 操作员是低权限角色，仅有权执行监视操作和排除故障操作。 后一种角色可以查看服务状态和消息流，启动或停止应用程序，以及终止和恢复服务实例；但不能更改配置，也不能查看消息属性和内容。  
  
 同样，BizTalk Server 会在每个数据库中为每个主机的用户组创建一个 SQL 角色，并将用户组执行该主机上的任务所需的最低用户权限授予此角色。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BizTalk Server 中的 Windows 组和用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [组和服务帐户的访问控制](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [用于管理角色的访问控制](../core/access-control-for-administrative-roles.md)  
  
-   [对业务信息的访问控制](../core/access-control-to-business-information.md)  
  
-   [最低安全用户权限](../core/minimum-security-user-rights.md)