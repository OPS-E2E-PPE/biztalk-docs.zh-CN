---
title: "SSO 安全建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- Kerberos protocol, SSO
- deploying, SSO
- user accounts, SSO
- deploying, security
- SQL Server, SSO
- security, SSO
- SSO, Kerberos protocol
- SSO, auditing
- best practices, deploying
- SSO, Windows groups
- SSO, best practices
- SSO, perimeter network
- Windows groups, SSO
- SSO, SQL Server access
- best practices, security
- Master Secret server, clustering
- perimeter networks
- auditing [SSO]
- SSO, security
- SSO, user accounts
- Master Secret server, best practices
ms.assetid: 7ae922b4-fd48-41f4-aaab-419a5e22c753
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a86e669e603eaabf142ce446b8d7204a6cc0091
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sso-security-recommendations"></a>SSO 安全建议
利用企业单一登录 (SSO) 系统，用户只需使用一组凭据即可连接到不同的系统。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]利用的敏感信息的存储区作为 SSO 系统。 虽然只要安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 便会自动安装企业单一登录，但您也可以独立于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境将企业单一登录作为独立的组件进行安装。 有关企业单一登录的详细信息，请参阅[使用 SSO](../core/using-sso.md)。 建议遵循以下准则，以保护环境中企业单一登录 (SSO) 服务和资源的安全并对其进行部署。  
  
## <a name="general-deployment-recommendations-for-sso"></a>SSO 的一般性部署建议  
  
-   整个环境中必须只能有一个主密钥服务器和一个 SSO 数据库，即使您的环境中有多个 BizTalk 组。 在配置任何其他 BizTalk 和 SSO 服务器之前，必须先配置这两个服务器。  
  
-   您的环境中必须有一个时间服务器，以确保所有 SSO 服务器保持同步。 如果 SSO 服务器上的时钟不同步，可能会危及环境的安全。  
  
-   假设您的整个环境中只有一个主密钥服务器，建议为该主密钥服务器使用主动-被动群集配置。 有关群集的主密钥服务器的详细信息，请参阅[如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。  
  
-   主密钥服务器存放 SSO 系统用于对 SSO 数据库中的信息进行加密的加密密钥。 建议不要在此计算机上安装或配置任何其他产品或服务。  
  
    > [!NOTE]
    >  安装和配置主密钥服务器的计算机不必是服务器。  
  
-   主密钥服务器应能够访问可移动媒体或 NTFS 文件系统文件夹，以便备份和还原主密钥。 如果使用可移动媒体，请确保采取适当的措施来保护可移动媒体。 如果将主密钥备份到 NTFS 文件系统，请确保对文件和文件夹进行保护。 只有 SSO 管理员才能访问该文件。  
  
-   一旦主密钥服务器生成主密钥，应立即备份主密钥。 这样，当主密钥服务器发生故障时，就可以对 SSO 数据库中的数据进行恢复。 有关备份主密钥的详细信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。  
  
-   应定期（例如，每月一次）备份当前密钥或生成新密钥。 如果没有密钥，将无法从 SSO 数据库检索信息。 有关备份和还原主密钥的详细信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。  
  
## <a name="security-recommendations-for-sso-groups-and-accounts"></a>SSO 组和帐户的安全建议  
  
-   建议使用 Windows 组，而不要使用单个用户帐户，特别是对于 SSO Administrators 和 SSO Affiliate Administrators 组。 这些组在任何时候都必须至少具有两个组成员用户帐户。  
  
-   SSO 运行时服务帐户和 SSO 管理员用户帐户应为不同的帐户，即使它们是同一 SSO Administrators 组的成员。 执行管理任务（例如生成和备份密钥）的 SSO 管理员用户必须为 Windows 管理员，而 SSO 运行时服务帐户不必为 Windows 管理员。  
  
    > [!IMPORTANT]
    >  Windows 管理员用户权限不能取代 SSO 管理员的用户权限。 若要执行任何 SSO 管理级别的任务，即使您已经是 Windows 管理员，也必须为 SSO Administrators 组的成员。  
  
-   如果使用 SSO 票证功能，则必须使用处理域（SSO 服务器所在的域）中的计算机能够识别的域帐户。  
  
-   建议为与主密钥服务器相应的 SSO 服务使用唯一的服务帐户。  
  
-   SSO 管理员帐户是 SSO 系统中具有很高权限的帐户，该帐户同时也是包含 SSO 数据库的 SQL Server 的 SQL Server 管理员帐户。 应为 SSO 管理员使用专用帐户，并且不应将这些帐户用于任何其他用途。 应将 SSO Administrators 组的成员身份限制为仅负责运行和维护 SSO 系统的帐户。  
  
-   必须手动将 BizTalk Administrators 组添加到 SSO Affiliate Administrators 组中，以便 BizTalk 管理员可以利用 SSO 系统将适配器的配置信息保存到 SSO 数据库中。 只有管理适配器的 BizTalk 管理员需要为 SSO Affiliate Administrators 组的成员。 BizTalk 管理员不需要为 SSO 管理员。  
  
## <a name="security-recommendations-for-an-sso-deployment"></a>SSO 部署的安全建议  
  
-   如果您的网络支持 Kerberos 验证，则应注册所有 SSO 服务器。 如果在主密钥服务器与 SSO 数据库之间使用 Kerberos 验证，则必须在该 SSO 数据库所在的 SQL Server 上配置服务主体名称 (SPN)。 有关配置服务主体名称的详细信息，请参阅 Microsoft 下载网站，网址[http://go.microsoft.com/fwlink/?LinkId=195797](http://go.microsoft.com/fwlink/?LinkId=195797)。  
  
-   在运行 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 时，如果主密钥服务器位于与其他 SSO 服务器和 SSO 数据库不同的域中，则必须对主密钥服务器、SSO 服务器（处理域中的处理计算机）和 SSO 数据库禁用 RPC 安全性（用于计算机之间的数据事务处理协调器 (DTC) 验证）。 RPC 安全性是 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 和 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 中的一项 DTC 功能。 当禁用 RPC 安全性后，RPC 调用的 DTC 身份验证安全级别将恢复为 Microsoft Windows Server 2003 中可用的级别。  
  
-   SSO 管理员应定期监视主密钥服务器和 SSO 服务器中的事件日志，以查看 SSO 审核事件。  
  
-   除防火墙之外，建议在所有 SSO 服务器和 SSO 数据库之间使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL)。 有关 SSL 的详细信息，请参阅在 Microsoft 帮助和支持网站[http://go.microsoft.com/fwlink/?LinkId=195798](http://go.microsoft.com/fwlink/?LinkId=195798)。 有关所有 SSO 服务器与 SSO 数据库之间使用 SSL 的详细信息，请参阅[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)。  
  
## <a name="perimeter-network"></a>外围网络  
 在运行 Internet 信息服务 (IIS) 和企业单一登录时，请遵循以下建议：  
  
-   如果 IIS 位于外围网络（也称为外围安全区域、DMZ 和外围子网）中，应在防火墙后面提供另一台 IIS 服务器以连接到 SSO 系统。  
  
-   不要打开 IIS 上的远程过程调用 (RPC) 端口。  
  
## <a name="sql-server-access"></a>SQL Server 访问  
 所有 SSO 服务器都需要访问 SQL Server SSO 数据库。 有关如何为安全的 SQL Server 数据库的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=33175](http://go.microsoft.com/fwlink/?LinkId=33175)。  
  
 建议使用安全套接字层 (SSL) 和/或 Internet 协议安全性 (IPSec) 来保护 SSO 服务器和 SSO 数据库之间的数据传输的安全。 有关使用 SSL 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=195798](http://go.microsoft.com/fwlink/?LinkId=195798)。  
  
 若要仅为 SSO 服务器和 SSO 数据库之间的连接启用 SSL，可以使用 ssoconfig 实用工具在每个 SSO 服务器上设置 SSL 支持。 此选项允许 SSO 在访问 SSO 数据库时始终使用 SSL。 有关详细信息，请参阅[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)。  
  
## <a name="strong-passwords"></a>强密码  
 为所有帐户使用强密码非常重要，特别是对于作为 SSO Administrators 组成员的帐户，因为这些用户对整个 SSO 系统具有控制权。  
  
## <a name="sso-administrator-accounts"></a>SSO 管理员帐户  
 建议为在不同计算机上运行的 SSO 服务使用不同的服务帐户。 对于 SSO 服务，不要使用执行管理操作（例如生成和备份密钥）的 SSO 管理员帐户。 虽然 SSO 服务帐户不应为该计算机的本地管理员，但对于某些操作，执行管理操作的 SSO 管理员必须为该计算机的本地管理员。  
  
## <a name="master-secret-server"></a>主密钥服务器  
 强烈建议保护主密钥服务器的安全并锁定该服务器。 不应使用此服务器作为处理服务器。 此服务器的唯一用途应为存放主密钥。 应确保此计算机的物理安全性，只有 SSO 管理员才可以访问此计算机。  
  
## <a name="kerberos"></a>Kerberos  
 SSO 支持 Kerberos，建议为 SSO 设置 Kerberos。 若要为 SSO 设置 Kerberos，必须为 SSO 服务注册安全主体名称 (SPN)。 默认情况下，在设置 Kerberos 时，SSO 使用该 SPN 来验证使用 SSO 服务的组件。 建议在 SSO 管理辅助服务和 SSO 服务器之间设置 Kerberos 验证。 也可以在 SSO 服务器之间以及 SSO 服务器和 SSO 数据库所在的 SQL Server 之间使用 Kerberos 验证。  
  
 若要设置和验证 Kerberos，请使用 setspn 和 kerbtray 实用工具。 有关这些实用工具的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178)。  
  
## <a name="delegation"></a>委派  
 在使用 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 时，可以使用约束委托，但建议不要使用委托来执行单一登录管理员的任务。 同样，建议不要将其他任务或用户权限委托给单一登录管理员。  
  
## <a name="auditing"></a>审核  
 审核是跟踪环境中的信息的关键机制。 企业单一登录 (SSO) 将对 SSO 数据库中执行的所有操作进行审核。 SSO 使用数据库自身的事件日志和审核日志。 SSO 为单一登录服务器提供了两种审核级别：  
  
-   成功审核级别审核成功的操作  
  
-   失败审核级别审核失败的操作  
  
 SSO 管理员可以设置适合其公司策略的成功和失败审核级别。  
  
 您可以将成功和失败审核设置为以下级别之一：  
  
 0 = 无。 此级别不发出任何审核消息  
  
 1 = 低  
  
 2 = 中等  
  
 3 = 高。 此级别发出尽可能多的审核消息  
  
 正审核的默认值为 0 （无）、 和负审核的默认值为 1 （低）。 根据 SSO 系统所需的审核级别，您可能需要更改这些值。  
  
> [!IMPORTANT]
>  企业单一登录审核发出由单一登录服务生成的消息。 这不是安全审核，SSO 系统不会将该信息保存在事件日志的安全日志中。 SSO 系统将 SSO 审核消息直接保存到应用程序事件日志中。  
  
### <a name="database-level-auditing"></a>数据库级别的审核  
 对于数据库级别的审核，SSO 系统在数据库的审核表中跟踪对 SSO 数据库执行的操作。 这些审核表的大小在 SSO 系统级别上进行定义。 您可以对已删除的关联应用程序、已删除的映射和所执行的凭据查找进行审核。 默认情况下，审核表大小设置为 1,000 个条目。 SSO 管理员可以更改此大小以符合其公司策略。  
  
## <a name="using-sso-accounts"></a>使用 SSO 帐户  
 本节包含在企业单一登录 (SSO) 系统中使用域和本地组以及个人帐户时的最佳实践。  
  
### <a name="domain-windows-groups-and-accounts"></a>域 Windows 组和帐户  
 在使用域 Windows 组时，请考虑以下建议：  
  
-   使用域组和域帐户。  
  
-   使用 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 时，可将 ENTSSO 服务帐户配置为以 Network Service 帐户运行。 不过，出于安全方面的原因建议不使用该配置，因为将来需要授予 Network Service 帐户 SSO 管理员权限。 建议您为 ENTSSO 服务帐户使用唯一的域服务帐户。  
  
-   为 SSO 管理员使用域组。 不应将个人域帐户指定为 SSO 管理员，因为无法将此帐户从一个个人帐户更改为另一个个人帐户。  
  
-   虽然可以将个人域帐户指定为 SSO 关联管理员，但还是应使用域组。  
  
-   虽然可以将个人域帐户指定为应用程序管理员，但还是应使用域组。  
  
-   必须为应用程序用户帐户使用域组。 SSO 应用程序用户帐户不支持个人帐户。  
  
-   可以为这些 SSO 访问帐户中的每一个访问帐户指定多个帐户。  
  
## <a name="see-also"></a>另请参阅  
 [企业单一登录服务器的端口](../core/ports-for-the-enterprise-single-sign-on-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)