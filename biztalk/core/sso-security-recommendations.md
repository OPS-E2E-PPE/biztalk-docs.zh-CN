---
title: SSO 安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7fa15b272aef5da2eba1fea53c690fadc60b143
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395456"
---
# <a name="sso-security-recommendations"></a>SSO 安全建议
使用企业单一登录 (SSO) 系统中，用户可以通过使用只有一组凭据连接到不同的系统。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 利用 SSO 系统来存储敏感信息。 尽管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会自动安装时安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时，您还可以安装企业单一登录作为独立组件，独立于你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 有关企业单一登录的详细信息，请参阅[使用 SSO](../core/using-sso.md)。 建议您遵循这些准则以保护和部署的企业单一登录 (SSO) 服务和你的环境中的资源。  
  
## <a name="general-deployment-recommendations-for-sso"></a>SSO 的一般性部署建议  
  
-   必须有一个主密钥服务器和一个 SSO 数据库在整个环境中，即使你的环境中有多个 BizTalk 组。 必须配置这些两个服务器之前配置任何其他 BizTalk 和 SSO 服务器。  
  
-   在您的环境以确保所有 SSO 服务器保持都同步，必须具有的时间服务器。 如果 SSO 服务器上的时钟不同步，可能危及您的环境的安全。  
  
-   假设在整个环境中只有一个主密钥服务器，建议使用主动-被动群集配置主密钥服务器。 有关群集主密钥服务器的详细信息，请参阅[如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。  
  
-   主密钥服务器存放 SSO 系统用来加密 SSO 数据库中的信息的加密密钥。 建议您不要安装或配置此计算机上的任何其他产品或服务。  
  
    > [!NOTE]
    >  安装和配置主密钥服务器的计算机没有为服务器。  
  
-   主密钥服务器应该有权访问可移动媒体或 NTFS 文件系统文件夹，以便备份和还原主密钥。 如果你使用可移动媒体，请确保采取适当的措施来保护可移动媒体。 如果为 NTFS 文件系统进行备份主密钥，请确保保护文件和文件夹。 只有 SSO 管理员应有权访问此文件。  
  
-   一旦主密钥服务器生成它，您应备份主密钥。 这是，使主服务器发生故障的事件中，则可以恢复 SSO 数据库中的数据。 有关备份主密钥的详细信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。  
  
-   备份当前密钥或生成新密钥定期进行，例如，每隔一个月。 如果没有密钥，无法从 SSO 数据库中检索信息。 有关备份和还原主密钥的详细信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。  
  
## <a name="security-recommendations-for-sso-groups-and-accounts"></a>SSO 组和帐户的安全建议  
  
-   建议使用 Windows 组和非单个用户帐户，特别是对于 SSO 管理员和 SSO 关联管理员组。 在任何时候，这些组必须为组的成员具有至少两个用户帐户。  
  
-   SSO 运行时服务帐户和 SSO 管理员用户帐户应为不同的帐户，即使它们是相同的 SSO Administrators 组的成员。 执行管理任务，例如生成和备份密钥的 SSO 管理员用户必须是 Windows 管理员，而 SSO 运行时服务帐户不需要是 Windows 管理员。  
  
    > [!IMPORTANT]
    >  Windows 管理员用户权限不能取代 SSO 管理员的用户权限。 若要执行任何 SSO 管理级别的任务必须是 SSO administrators 组的成员，即使您已经是 Windows 管理员。  
  
-   如果你使用 SSO 票证功能，必须使用处理域 （SSO 服务器所在的域） 中的计算机识别的域帐户。  
  
-   建议使用唯一的服务帐户的主密钥服务器到相应的 SSO 服务。  
  
-   SSO 管理员帐户在 SSO 系统中，这也是包含 SSO 数据库的 SQL server 的 SQL Server 管理员帐户是高特权的帐户。 应为 SSO 管理员专用帐户，并不应使用这些帐户用于任何其他目的。 应仅向这些帐户负责运行和维护 SSO 系统的 SSO administrators 组的成员身份进行限制。  
  
-   以便 BizTalk 管理员可以利用 SSO 系统，SSO 数据库中保存适配器的配置信息，必须手动将 BizTalk administrators 组添加到 SSO Affiliate Administrators 组。 管理适配器的 BizTalk 管理员需要为 SSO Affiliate Administrators 组的成员。 BizTalk 管理员不需要为 SSO 管理员。  
  
## <a name="security-recommendations-for-an-sso-deployment"></a>SSO 部署的安全建议  
  
- 如果你的网络支持 Kerberos 身份验证，则应注册所有 SSO 服务器。 使用主密钥服务器和 SSO 数据库之间的 Kerberos 身份验证时，你必须配置 SSO 数据库所在的 SQL server 上的服务主体名称 (SPN)。 有关配置服务主体名称的详细信息，请参阅 Microsoft 下载网站，网址[ http://go.microsoft.com/fwlink/?LinkId=195797 ](http://go.microsoft.com/fwlink/?LinkId=195797)。  
  
- 运行时[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，如果主密钥服务器位于不同的域从其他 SSO 服务器和 SSO 数据库，则必须禁用 RPC 安全性 （用于计算机之间的数据事务处理协调器 (DTC) 验证) 在主密钥服务器、 SSO 服务器 （处理在处理域中的计算机） 和 SSO 数据库。 RPC 安全性是一项 DTC 功能[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]和[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 当禁用 RPC 安全性后时，RPC 调用的 DTC 身份验证安全级别将恢复为 Microsoft Windows Server 2003 中可用。  
  
- SSO 管理员应定期监视主密钥服务器和 SSO 服务器中的事件日志，查看 SSO 审核事件。  
  
- 除防火墙之外，建议所有 SSO 服务器和 SSO 数据库之间使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL)。 有关 SSL 的详细信息，请参阅 Microsoft 帮助和支持网站上的[ http://go.microsoft.com/fwlink/?LinkId=195798 ](http://go.microsoft.com/fwlink/?LinkId=195798)。 有关所有 SSO 服务器和 SSO 数据库之间使用 SSL 的详细信息，请参阅[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)。  
  
## <a name="perimeter-network"></a>外围网络  
 当运行 Internet 信息服务 (IIS) 和企业单一登录，请遵循以下建议：  
  
-   如果 IIS 位于外围网络 （也称为 DMZ、 外围安全区域和外围子网） 中，提供要连接到 SSO 系统在防火墙后面的另一台 IIS 服务器。  
  
-   不要打开 IIS 上的远程过程调用 (RPC) 端口。  
  
## <a name="sql-server-access"></a>SQL Server Access  
 所有 SSO 服务器都访问 SQL Server SSO 数据库。 有关如何对保护 SQL Server 数据库的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=33175 ](http://go.microsoft.com/fwlink/?LinkId=33175)。  
  
 建议使用安全套接字层 (SSL) 和/或 Internet 协议安全 (IPSec) 来保护 SSO 服务器和 SSO 数据库之间的数据传输。 有关使用 SSL 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=195798 ](http://go.microsoft.com/fwlink/?LinkId=195798)。  
  
 若要为仅 SSO 服务器和 SSO 数据库之间的连接启用 SSL，可以使用 ssoconfig 实用工具每个 SSO 服务器上设置 SSL 支持。 此选项允许 SSO 在访问 SSO 数据库时始终使用 SSL。 有关详细信息，请参阅[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)。  
  
## <a name="strong-passwords"></a>强密码  
 它是对所有帐户，尤其是 SSO Administrators 组的成员，因为这些用户可以控制整个 SSO 系统的帐户使用强密码非常重要。  
  
## <a name="sso-administrator-accounts"></a>SSO 管理员帐户  
 建议在不同计算机上运行的 SSO 服务使用不同的服务帐户。 不应使用执行管理操作，例如生成和备份密钥用于 SSO 服务的 SSO 管理员帐户。 SSO 服务帐户不应在该计算机上的本地管理员，而执行管理操作的 SSO 管理员必须是对于某些操作的计算机上的本地管理员。  
  
## <a name="master-secret-server"></a>主密钥服务器  
 强烈建议您保护和锁定在主密钥服务器。 不应为处理服务器使用此服务器。 此服务器的唯一用途应为存放主密钥。 您应确保此计算机，只有 SSO 管理员的物理安全性应具有访问这台计算机。  
  
## <a name="kerberos"></a>Kerberos  
 SSO 支持 Kerberos，建议为 SSO 设置 Kerberos。 若要设置 SSO 使用 Kerberos，必须注册安全主体名称 (SPN) 的 SSO 服务。 默认情况下，在设置 Kerberos 时，SSO 使用该 SPN 进行身份验证使用 SSO 服务的组件。 建议设置 SSO 管理辅助服务和 SSO 服务器之间的 Kerberos 身份验证。 您还可以使用 Kerberos 验证 SSO 服务器和 SSO 数据库所在的 SQL server 之间以及 SSO 服务器之间。  
  
 若要设置和验证 Kerberos，则使用 setspn 和 kerbtray 实用工具。 有关这些实用工具的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=33178 ](http://go.microsoft.com/fwlink/?LinkId=33178)。  
  
## <a name="delegation"></a>委派  
 使用时[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，可以使用约束的委派，但建议，则不要使用委托来执行单一登录管理员的任务。 同样，建议不委派的其他任务或对单一登录管理员的用户权限。  
  
## <a name="auditing"></a>审核  
 审核是跟踪你环境中的信息的关键机制。 企业单一登录 (SSO) 在 SSO 数据库中执行的所有操作进行都审核。 SSO 使用事件日志和数据库本身的审核日志。 SSO 提供了两种审核级别的单一登录服务器：  
  
- 成功审核级别审核成功的操作  
  
- 失败审核级别审核失败的操作，  
  
  SSO 管理员可以设置适合其公司策略的成功和失败审核级别。  
  
  可以将成功和失败审核设置为以下级别之一：  
  
  0 = 无。 此级别不发出任何审核消息  
  
  1 = 低  
  
  2 = 中等  
  
  3 = 高。 此级别不发出多尽可能的审核消息  
  
  正审核的默认值为 0 （无）、 和失败审核的默认值为 1 （低）。 您可能想要更改这些值，具体取决于的审核级别所需的 SSO 系统。  
  
> [!IMPORTANT]
>  企业单一登录审核发出由单一登录服务生成的消息。 这不是安全审核，SSO 系统不会保存在安全日志中的事件日志的信息。 SSO 系统将保存 SSO 审核消息直接到应用程序事件日志。  
  
### <a name="database-level-auditing"></a>数据库级审核  
 对于数据库级别审核，SSO 系统跟踪数据库中的审核表中的 SSO 数据库上执行的操作。 这些大小审核表在 SSO 系统级别上定义。 您可以审核将被删除的关联应用程序、 已删除的映射和凭据查找进行执行。 默认情况下，审核大小设置为 1,000 个条目。 SSO 管理员可以更改此大小以符合其公司策略。  
  
## <a name="using-sso-accounts"></a>使用 SSO 帐户  
 本部分包含企业单一登录 (SSO) 系统中使用域和本地组和单个帐户时的最佳做法。  
  
### <a name="domain-windows-groups-and-accounts"></a>域 Windows 组和帐户  
 当使用域 Windows 组时，以下建议适用：  
  
- 使用域组和域帐户。  
  
- 使用时[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]ENTSSO 服务帐户可以配置为在 Network Service 帐户下运行。 但是，这不是建议出于安全原因，作为网络服务帐户将需要指定 SSO 管理员权限。 建议改为 ENTSSO 服务帐户使用唯一的域服务帐户。  
  
- 为 SSO 管理员使用域组。 因为无法将此帐户从一个个人帐户更改为其他个人帐户，不应为 SSO 管理员中，指定将个人域帐户。  
  
- 尽管您可以指定为 SSO 关联管理员将个人域帐户，应使用域组。  
  
- 尽管可以将个人域帐户指定为应用程序管理员，应使用域组。  
  
- 为应用程序用户帐户，必须使用域组。 SSO 应用程序用户帐户不支持个人帐户。  
  
- 可以为每个这些 SSO 访问帐户指定多个帐户。  
  
## <a name="see-also"></a>请参阅  
 [用于企业单一登录服务器的端口](../core/ports-for-the-enterprise-single-sign-on-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)