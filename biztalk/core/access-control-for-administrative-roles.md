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
ms.openlocfilehash: 7999230f3ec0545d8cd15b66e1407148f080bb26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990310"
---
# <a name="access-control-for-administrative-roles"></a>管理角色的访问控制
用户打开需要访问数据库或 Windows 资源的任何 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 工具时，使用该工具进行交互的用户必须具有相应的 SQL Server 和 Windows 用户权限，才能执行这些工具所支持的各种任务。  
  
 一个或多个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 工具可访问 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库。 因此，BizTalk Server 必须将每个数据库的某一级别的访问权限授予 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员。 此外，为安全起见，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员不应具有完成其工作所需权限之外的用户权限。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通过使用 SQL Server 数据库角色就可以满足这两个要求。 每当您创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过安装的数据库或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会自动创建该数据库中的这两种管理角色的 SQL Server 数据库角色。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 授予每个角色，以及分配给该角色，任何 SQL Server 登录名的 SQL Server 对象 （表、 视图、 存储的过程等） 对该数据库执行管理任务上的管理员所需的最低用户权限。  
  
> [!NOTE]
>  还有一些管理任务需要 BizTalk 管理员具有比 SQL Server 角色所授予的权限更多的权限，例如创建主机实例。 有关这些额外权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，有两种管理角色：[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员，并且[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运算符。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员是高权限角色，有权访问配置数据和跟踪数据。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员是低权限角色，仅有权执行监视操作和排除故障操作。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员组：  
  
- 是无权访问消息数据的较低权限管理角色。  
  
- 使其成员能够监视 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是否发生错误，查询挂起的消息\实例，以及查看配置。  
  
- 防止成员更改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置。 例如，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员不能更改发送端口、接收位置、端口的筛选器，以及部署新项目。  
  
  首次安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，它会创建默认 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员角色。 默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将该角色称为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员，但您可以选择其他名称。  
  
  同样，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会在每个数据库中为每个主机的用户组创建一个 SQL Server 数据库角色，并将用户组执行该主机上的任务所需的最小用户权限授予此角色。 必须将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员添加到单一登录关联管理员组。 有关企业单一登录的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
> [!CAUTION]
>  BizTalk 管理员必须确保将在系统中部署的程序集的源是受信任的。 如果管理员部署的程序集包含不受信任的代码，则可能使 BizTalk 环境存在遭受攻击的危险。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不强制对自定义代码组件在 BizTalk 引擎调用这些时可以执行的操作的任何限制。  
  
## <a name="see-also"></a>请参阅  
 [访问控制和数据安全性](../core/access-control-and-data-security.md)   
 [BizTalk Server 中的 Windows 组和用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)