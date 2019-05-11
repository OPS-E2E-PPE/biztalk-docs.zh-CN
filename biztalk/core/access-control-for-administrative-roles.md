---
title: 用于管理角色的访问控制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- roles, administrative
- administrator accounts, administrative roles
- administrative roles
- access control, administrative roles
ms.assetid: 328e049b-921d-4057-85f0-7d008ec308bb
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b3fd5c38ea1ac46c54821b2dcd5ecd033d71ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362203"
---
# <a name="access-control-for-administrative-roles"></a>管理角色的访问控制
当用户在打开的任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要访问数据库或 Windows 资源的工具，该工具的交互式用户必须具有相应 SQL Server 和 Windows 用户权限，才能执行这些工具所支持的各种任务。  
  
 一个或多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]工具可访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 因此，BizTalk Server 必须授予某种级别的每个数据库的访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员。 此外，出于安全原因，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员不应具有权限的用户权限比实际所需执行其作业。 使用 SQL Server 数据库角色，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以满足这两个要求。 每当您创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过安装的数据库或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会自动创建该数据库中的这两种管理角色的 SQL Server 数据库角色。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 授予每个角色，以及分配给该角色，任何 SQL Server 登录名的 SQL Server 对象 （表、 视图、 存储的过程等） 对该数据库执行管理任务上的管理员所需的最低用户权限。  
  
> [!NOTE]
>  有一些需要 BizTalk 管理员具备更多权限的管理任务所授予通过 SQL Server 角色，例如创建主机实例。 有关这些额外权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，有两种管理角色：[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员，并且[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运算符。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员是高权限角色，有权访问配置数据和跟踪数据。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作员是低权限角色，仅有权监视和故障排除操作。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators 组：  
  
- 是较低权限管理角色，而无需对消息数据的访问。  
  
- 成员能够监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]错误，查询挂起的消息 \ 实例以及查看配置。  
  
- 防止成员更改[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。 例如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运算符不能更改发送端口、 接收位置、 端口的筛选器、 部署新项目。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建默认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员角色时，第一次安装产品。 默认情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将其称为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员，但您可以选择不同的名称。  
  
  同样，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库中创建每个用户组的 SQL Server 数据库角色的每个主机，并授予此角色的最小用户权限它需要要执行该主机的任务的用户组。 必须添加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到单一登录关联管理员组的管理员。 有关企业单一登录的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
> [!CAUTION]
>  BizTalk 管理员必须确保他们相信他们将在系统中部署的程序集的源。 如果他们部署，你不信任的代码的程序集，它们可能会公开到潜在攻击的 BizTalk 环境。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不强制对自定义代码组件在 BizTalk 引擎调用这些时可以执行的操作的任何限制。  
  
## <a name="see-also"></a>请参阅  
 [访问控制和数据安全性](../core/access-control-and-data-security.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)