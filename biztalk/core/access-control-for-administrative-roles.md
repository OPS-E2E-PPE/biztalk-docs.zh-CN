---
title: 用于管理角色的访问控制 |Microsoft 文档
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
ms.openlocfilehash: dfc7b1891cd266457af97c18f2ad6220145e00ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225813"
---
# <a name="access-control-for-administrative-roles"></a>用于管理角色的访问控制
用户打开需要访问数据库或 Windows 资源的任何 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 工具时，使用该工具进行交互的用户必须具有相应的 SQL Server 和 Windows 用户权限，才能执行这些工具所支持的各种任务。  
  
 一个或多个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 工具可访问 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库。 因此，BizTalk Server 必须将每个数据库的某一级别的访问权限授予 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员。 此外，为安全起见，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员不应具有完成其工作所需权限之外的用户权限。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通过使用 SQL Server 数据库角色就可以满足这两个要求。 每当你创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]完成安装过程的数据库或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动创建该数据库中的这两个管理角色的 SQL Server 数据库角色。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]授予每个角色，以及分配给该角色，任何 SQL Server 登录名所需的 SQL Server 对象 （表、 视图、 存储的过程等） 在该数据库上执行管理任务上的管理员的最小用户权限。  
  
> [!NOTE]
>  还有一些管理任务需要 BizTalk 管理员具有比 SQL Server 角色所授予的权限更多的权限，例如创建主机实例。 有关这些其他权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，有两个管理角色：[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员，与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运算符。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员是高权限角色，有权访问配置数据和跟踪数据。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员是低权限角色，仅有权执行监视操作和排除故障操作。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员组：  
  
-   是无权访问消息数据的较低权限管理角色。  
  
-   使其成员能够监视 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是否发生错误，查询挂起的消息\实例，以及查看配置。  
  
-   防止成员更改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置。 例如，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员不能更改发送端口、接收位置、端口的筛选器，以及部署新项目。  
  
 首次安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，它会创建默认 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员角色。 默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将该角色称为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员，但您可以选择其他名称。  
  
 同样，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会在每个数据库中为每个主机的用户组创建一个 SQL Server 数据库角色，并将用户组执行该主机上的任务所需的最小用户权限授予此角色。 必须将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员添加到单一登录关联管理员组。 有关企业单一登录的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
> [!CAUTION]
>  BizTalk 管理员必须确保将在系统中部署的程序集的源是受信任的。 如果管理员部署的程序集包含不受信任的代码，则可能使 BizTalk 环境存在遭受攻击的危险。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不会强制对 BizTalk 引擎调用它们时，可以执行自定义代码组件的操作的任何限制。  
  
## <a name="see-also"></a>另请参阅  
 [访问控制和数据安全性](../core/access-control-and-data-security.md)   
 [BizTalk Server 中的 Windows 组和用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)