---
title: 管理 BizTalk Server 安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- security, user accounts
- security, passwords
- certificates, security
- security, certificates
- security, BizTalk Server
- passwords, security
- user accounts, security
ms.assetid: adc89b0a-9846-4c99-b0fc-a32fc56ed769
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7486a23d5d606a1347c60b2971ebed66c354946
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000046"
---
# <a name="managing-biztalk-server-security"></a>管理 BizTalk Server 安全性
维持一个安全的 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境需要您对帐户、证书和密码进行管理。 为帮助确保由 BizTalk Server 处理的业务文档的安全性，BizTalk Server 管理员需要管理以下帐户和证书：  
  
- **BizTalk Server Administrators 组**。 对于通过 BizTalk 管理控制台或使用 Windows 管理规范 (WMI) 提供程序执行管理任务的用户，他们必须在 Microsoft SQL Server 和 Microsoft Windows 中获得适当的权限。 有关管理任务的权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
   有关将用户添加到 BizTalk Server Administrators 组或从 BizTalk Server Administrators 组中删除用户的信息，请参阅[如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md)。  
  
   有关企业单一登录的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
- **BizTalk Server Operators 组**。 BizTalk Server 操作员是只具有执行监控和故障排除操作的低权限角色。  
  
   BizTalk Server Operators 组的成员可以执行以下操作：  
  
  - 查看服务状态和消息流。  
  
  - 启动或停止应用程序。  
  
  - 启动或停止业务流程。  
  
  - 启动或停止发送端口和发送端口组。  
  
  - 启用或禁用接收位置。 在默认为 60 秒的下一缓存刷新间隔之前，更改不会生效。 缓存刷新间隔是在 BizTalk Server 组级别进行设置的。  
  
  - 终止和恢复服务实例。  
  
    BizTalk Server Operators 组的成员不能执行以下操作：  
  
  - 修改 BizTalk Server 的配置。  
  
  - 查看分类为个人身份信息 (PII) 的消息上下文属性或消息正文。  
  
  - 修改消息路由的过程（例如向正在运行的系统添加新的订阅或从中删除订阅），包括将消息发布到 BizTalk Server 运行时的能力。  
  
  > [!NOTE]
  >  如果某个用户既是 BizTalk Server Operators 组的成员，同时也是运行 BizTalk Server 的计算机的本地管理员，则该用户可以在这些计算机上访问 Operators 组中的角色可以访问的数据以外的数据。 有关详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
  > [!NOTE]
  >  如果要使作为 BizTalk Server Operators 组的成员的用户能够监控远程 BizTalk 服务器，则该用户必须同时是该远程计算机上本地 Administrators 组的成员。  
  
- **主机和服务帐户**。 创建主机及其关联的主机实例时，必须为主机提供 Windows 组并为每一个主机实例提供服务帐户凭据。 必须确保主机实例服务帐户是该主机的 Windows 组的成员。  
  
- **签名证书**。 签名证书（私钥证书）是为 BizTalk 组指定的。 它们是可选的，并且可以随时由 BizTalk Server 管理员进行更改。  
  
  有关 BizTalk Server 使用的 Windows 帐户的更完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)  
  
-   [管理证书的最佳做法](../core/best-practices-for-managing-certificates1.md)  
  
-   [管理 Windows 组和用户帐户](../core/managing-windows-groups-and-user-accounts.md)