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
ms.openlocfilehash: 61612cced50d634f3ca4d71b5e29ebd3c1781009
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531152"
---
# <a name="managing-biztalk-server-security"></a>管理 BizTalk Server 安全性
维护一个安全的 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境需要管理帐户、 证书和密码。 为帮助确保由 BizTalk Server 处理的业务文档的安全性，BizTalk Server 管理员管理以下帐户和证书：  
  
- **BizTalk Server Administrators 组**。 对于执行管理任务通过 BizTalk 管理控制台或通过使用 Microsoft Windows Management Instrumentation (WMI) 提供程序的用户，他们必须获得 Microsoft SQL Server 和 Microsoft Windows 中适当的权限。 有关管理任务的权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
   有关将用户添加到 BizTalk Server Administrators 组或从 BizTalk Server Administrators 组中删除用户的信息，请参阅[如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md)。  
  
   有关企业单一登录的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
- **BizTalk Server Operators 组**。 BizTalk Server 操作员是仅有权访问监视和故障排除操作的低权限的角色。  
  
   BizTalk Server Operators 组的成员可以执行以下操作：  
  
  - 查看服务状态和消息流。  
  
  - 启动或停止应用程序。  
  
  - 启动或停止业务流程。  
  
  - 启动或停止发送端口或发送端口组。  
  
  - 启用或禁用接收位置。 更改不会生效直到下一步的缓存刷新间隔为 60 秒，这是默认设置。 在 BizTalk Server 组级别设置缓存刷新间隔。  
  
  - 终止和恢复服务实例。  
  
    BizTalk Server Operators 组的成员不能执行以下操作：  
  
  - 修改 BizTalk Server 的配置。  
  
  - 查看被归类为个人身份信息 (PII) 或消息正文的消息上下文属性。  
  
  - 修改消息路由，例如删除或将新的订阅添加到正在运行的系统，包括能够将消息发布到 BizTalk Server 运行时的过程。  
  
  > [!NOTE]
  >  如果 BizTalk Server Operators 组的成员的用户也是运行 BizTalk Server 的计算机上的本地管理员，此用户可以访问这些计算机上的操作员组的角色之外的数据。 有关详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
  > [!NOTE]
  >  如果你想要允许的用户是要监控远程 BizTalk 服务器的 BizTalk Server Operators 组的成员，此用户还必须是远程计算机上的本地管理员组的成员。  
  
- **主机和服务帐户**。 创建主机和其关联的主机实例时，必须提供主机和每个主机实例服务帐户凭据的 Windows 组。 您必须确保主机实例服务帐户是主机 Windows 组的成员。  
  
- **签名证书**。 为 BizTalk 组指定签名证书 （私钥证书）。 这些是可选的可以由 BizTalk Server 管理员随时更改。  
  
  有关 BizTalk Server 使用的 Windows 帐户的更完整信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)  
  
-   [管理证书的最佳做法](../core/best-practices-for-managing-certificates1.md)  
  
-   [管理 Windows 组和用户帐户](../core/managing-windows-groups-and-user-accounts.md)