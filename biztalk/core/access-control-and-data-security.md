---
title: 访问控制和数据安全 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e34babf08ccc18d0e20165b5f3a39914ad7324e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362255"
---
# <a name="access-control-and-data-security"></a>访问控制和数据安全性
BizTalk Server 使用最低用户权限; 限制对其进程和数据库的访问您可以通过使用 Microsoft Windows Server 中的功能来帮助系统中的重要数据的安全。 出于安全原因，BizTalk Server Administrators 和 BizTalk 主机不应具有比执行其作业所需的更多的用户权限。  
  
 BizTalk 控制管理对使用 SQL 角色，从而控制数据通过工具或直接通过数据库访问的数据访问。 使用 Host User 组和帐户控制 BizTalk 主机访问数据。  
  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，有两种管理角色： BizTalk Server 管理器和 BizTalk Server 操作员。 无论，只要创建 BizTalk Server 数据库通过安装还是 BizTalk Server 管理控制台，BizTalk Server 会自动在该数据库中创建这两种管理角色的 SQL 角色。 BizTalk Server 授予每个角色，以及分配给该角色，任何 SQL Server 登录名的 SQL Server 对象 （表、 视图、 存储的过程等） 对该数据库执行管理任务上的管理员所需的最低用户权限。  
  
 BizTalk Server 管理员是高权限角色，有权访问配置数据和跟踪数据。 BizTalk Server 操作员是低权限角色，仅有权监视和故障排除操作。 这后一种角色可以查看服务状态和消息流和可以启动或停止应用程序以及终止和恢复服务实例，但不能更改配置或查看消息属性和内容。  
  
 同样，BizTalk Server 数据库中创建每个用户组的 SQL 角色的每个主机，并且授予此角色的用户组来执行该主机的任务所需的最低用户权限。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [组和服务帐户的访问控制](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [管理角色的访问控制](../core/access-control-for-administrative-roles.md)  
  
-   [对业务信息的访问控制](../core/access-control-to-business-information.md)  
  
-   [最低安全用户权限](../core/minimum-security-user-rights.md)