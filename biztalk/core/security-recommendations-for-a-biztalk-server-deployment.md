---
title: BizTalk Server 部署的安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, security
- Windows Server 2003 Security Configuration Wizard (SCW)
- user accounts, security
- permissions
- access control
- security, deploying
- channel level encryption
- security, permissions
ms.assetid: 033fff11-d989-46ba-83ed-5063f7cd7818
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5513670afcdd6568f224d4f2fb79fedb721b02cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279954"
---
# <a name="security-recommendations-for-a-biztalk-server-deployment"></a>BizTalk Server 部署的安全建议
本部分包含高级、 不可知的功能来保护你的 Microsoft BizTalk Server 环境的建议。  
  
## <a name="topology-level-recommendations"></a>拓扑结构级建议  
 **使用通道级加密。** 默认情况下，BizTalk Server 中的各种组件之间的网络数据流是明文形式传输。 当探查或篡改的数据，如消息需要传输从一台计算机向另一个问题，我们建议使用通道级加密，如 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL)。 默认情况下，BizTalk Server 不会配置通道级加密，而 BizTalk Server 不会将关键数据，如加密密钥和密码在网络上的清除文本。 SSO 数据库通过将其以加密形式存储通过使用主密钥 （加密密钥） 由主密钥服务器提供管理敏感信息。 默认情况下，SSO 数据库接收、 存储和加密的形式发送敏感信息。  
  
 有关 SSL 的详细信息，请参阅[ http://go.microsoft.com/fwlink/p/?LinkId=189708 ](http://go.microsoft.com/fwlink/p/?LinkId=189708)。  
  
 **帮助确保服务器的物理安全性。** 您还必须考虑到这一点的服务器、 设备、 网络、 电缆、 电源和其他组件的物理安全性。 应在安全环境中，将你的计算机，并限制对包含业务关键信息，例如数据库的计算机的访问。  
  
 **仅安装将使用的组件。** 如果需要在你的环境 （在外围网络中或在运行 HTTP 和 SOAP 适配器的计算机的计算机） 中安装 Internet 信息服务 (IIS)，不需要安装文件传输协议 (FTP)、 WebDAV 和简单邮件传输协议 (SMTP) 的 IIS 子组件。 同样，确保仅安装和配置 BizTalk Server 功能所需的环境。 如果你使用例如，仅配置 BizTalk 消息队列适配器。 这有助于降低您的环境中潜在的攻击面。  
  
如果使用 Internet Explorer，我们建议您打开的 Internet Explorer 增强的安全性。  
  
 **安装 service pack 和更新**。 我们建议您始终具有的所有服务器上安装最新的产品 service pack 和 Microsoft 更新[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]资源，包括[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]。  
  
 **不在脚本或绑定文件中的明文形式保存密码。** 您应将脚本保存在位置具有加强的任意访问控制列表 (Dacl)，以便只有 BizTalk Server 管理员才有权查看、 修改和运行这些脚本。 在脚本和绑定文件需要密码，确保你使用的脚本进行配置或部署时，就立即屏蔽密码。 不要将密码以在这些文件中以明文形式。  
  
 **使用加强的任意访问控制列表 (Dacl)。** 确保只向用户和帐户使用它，资源提供访问权限，并且您向为他们提供最少的权限可以执行其任务。 将配置脚本放置在向 BizTalk Server 管理员使用的 Dacl 的位置并不将明文密码放置在脚本中。 确保 BizTalk Server 使用的所有服务帐户的临时目录都具有 Dacl，以便只有该服务帐户和 BizTalk 管理员有权访问它。  
  
 如果具有自定义适配器时，我们建议您将适配器扩展组件都存储在使用加强的 Dacl 的位置，以便只有 BizTalk Server 管理员才具有写权限与这些组件。  
  
 **未将 BizTalk 服务器放在外围网络。** 无论你的公司规模大小，将 BizTalk Server 放置在外围网络中公开服务器，到这两个来自 Internet 的直接攻击和可能会受到在外围网络中的其他服务器的攻击。 BizTalk Server 与数据域中的 Microsoft SQL Server 数据库进行通信，因为恶意用户可能会利用受到威胁的 BizTalk Server 来篡改重要的业务处理数据和配置数据。  
  
## <a name="biztalk-server-groups-and-accounts"></a>BizTalk Server 组和帐户  
 **使用具有最小权限和用户权限的帐户。** BizTalk Server 系统中的所有帐户应都具有执行其任务所需的最低用户权限。 例如，在处理服务器中使用的服务帐户不应该在 BizTalk Server、 SQL Server 或 Windows Server 中的管理用户权限。 有关最低安全权限和用户权限的帐户必须在 BizTalk Server 中执行的任务的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。 关于组和 BizTalk Server 使用的帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
 **为不同功能使用不同的帐户。** 为保护 BizTalk Server 环境的安全性，我们建议为每个环境中运行的主机实例创建不同的服务帐户。 这还会分配为提高可用性在密码更新过程。 我们建议一个服务帐户不是为 BizTalk Server 的多个 Windows 组的成员。  
  
 此外，我们建议你为每个 BizTalk 主机使用不同的 Windows 组和一个组的成员的服务帐户不是另一台主机的 Windows 组的成员。 这提供了强大的安全隔离每个 BizTalk 主机。  
  
 我们建议仅用于跟踪主机中，创建 Windows 组并对其进行跟踪，此组中使用的服务帐户的主机实例。 请不要将此服务帐户用于任何其他服务，也不使用 BizTalk 管理员帐户的跟踪主机实例。  
  
 **为不同功能使用不同的主机。** 我们建议创建一个仅用于跟踪主机。 配置为"主机跟踪"的主机具有读取和写入 MessageBox 数据库中的跟踪表的访问权限以及对跟踪数据库中的表的访问。 因此，承载还跟踪的主机中运行的所有对象都具有读取和写入到这些表的访问权限。 若要从用户的项，例如管道和业务流程阻止对可能敏感的跟踪数据的访问，建议创建专用的主机，用于跟踪，则不处理、 发送或接收消息。  
  
 此外，我们建议你使用不同的主机的处理、 接收和发送消息。 然后，可以隔离需要访问私有证书为你的公司的服务帐户。 您有这些帐户运行的代码更少、 越低可能会危及帐户通过漏洞，从而降低危及专用证书的风险。  
  
 **定期更改密码。** 必须定期更改服务帐户的密码。 如果主机实例的具有多个服务帐户，必须为每个这些服务帐户更改密码。  
  
> [!CAUTION]
>  必须更改 BizTalk 管理控制台中的主机实例的服务帐户的密码。 更改计算机管理控制台中的主机实例服务帐户的密码可能会导致配置问题。  
  
 **限制 BizTalk Administrators 组的成员身份。** BizTalk Server 管理员具有用户权限该范围内跨 BizTalk Server 环境，包括对大多数加密或未加密的数据的访问。 因此，由 BizTalk 管理员错误导致的配置不正确可以公开严重的安全漏洞。 如果 BizTalk 管理员误可以执行到系统，包括完整的保密性、 完整性和可用性的客户数据安全威胁的损害。  
  
 在其中开发人员直接将部署业务流程到生产环境中的计算机的情况下，域管理员必须向开发人员授予 BizTalk 管理员用户权限。 建议不要前面所述的原因。  
  
 **限制 COM + Administrators 组的成员身份。** 由于各种体系结构的原因，COM + 管理员以管理员身份在多个 BizTalk Server 组件中具有用户权限。 所有的实用的角度而言，您必须假定计算机上的 COM + 管理员也是 BizTalk 管理员，并应限制在 BizTalk 生产服务器中此组的成员身份。  
  
 **仅授权用户访问他们需要访问的服务运行的计算机。** 并非所有的帐户需要对所有计算机的权限。 BizTalk 主机实例在内存中保留敏感信息。 这些可能是密码或业务信息之类的关键数据。 应在这些计算机上设置非常严格的本地用户策略。 例如，仅授予给需要它们来维护部署的个人的这些计算机上的本地登录权限。 这样可降低到交换文件和崩溃转储导致访问的威胁。  
  
 **限制 Power Users 组的权限，或将其删除。** 此组的用户权限的 Power Users 组授予成员的默认权限修改计算机范围的设置，包括 BizTalk 程序集在全局程序集缓存 (GAC) 中注册。 每台计算机具有 GAC 中，其中包含一个或多个应用程序共享的程序集。 我们建议您删除更改程序集从 Power Users 组的权限或从生产 BizTalk Server 中删除 Power Users 组。  
  
 
## <a name="see-also"></a>请参阅  
 [组和服务帐户的访问控制](../core/access-control-for-groups-and-service-accounts.md)   
 [管理角色的访问控制](../core/access-control-for-administrative-roles.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)   
 [规划安全性](../core/planning-for-security.md)