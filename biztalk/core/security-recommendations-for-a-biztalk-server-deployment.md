---
title: "BizTalk Server 部署的安全建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fad4f4a734f396b3ffec726b65fe19d62ee0f5ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-recommendations-for-a-biztalk-server-deployment"></a>BizTalk Server 部署的安全建议
本部分包含了对确保 Microsoft BizTalk Server 环境安全的与功能无关的高级建议。  
  
## <a name="topology-level-recommendations"></a>拓扑结构级建议  
 **使用通道级加密。** 默认情况下，BizTalk Server 中各个组件之间的网络数据流是明文形式传输的。 如果在消息从一台计算机传递到另一台计算机时存在对数据进行探查或篡改的问题，则建议使用通道级加密，例如 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL)。 尽管默认情况下 BizTalk Server 不配置通道级加密，但 BizTalk Server 不会将诸如加密密钥和密码等关键数据以明文形式放置在网络上。 通过使用主密钥服务器提供的主密钥（加密密钥）以加密的形式存储敏感信息，SSO 数据库可以管理这些敏感信息。 默认情况下，SSO 数据库将以加密的形式接收、存储和发送敏感信息。  
  
 有关 SSL 的详细信息，请参阅[http://go.microsoft.com/fwlink/p/?LinkId=189708](http://go.microsoft.com/fwlink/p/?LinkId=189708)。  
  
 **帮助确保服务器的物理安全性。** 你还必须考虑服务器、设备、网络、电缆、电源和其他组件的物理安全。 应当将你的计算机置于安全环境中，并且限制对包含重要业务信息（例如数据库）的计算机的访问。  
  
 **仅安装你将使用的组件。** 如果需要在你的环境（外围网络中的计算机，或者运行 HTTP 和 SOAP 适配器的计算机）中安装 Internet 信息服务 (IIS)，你不需要安装 IIS 的文件传输协议 (FTP)、WebDAV 和简单邮件传输协议 (SMTP) 子组件。 同样，请确保仅安装和配置你的环境所需的 BizTalk Server 功能。 例如，仅当要使用 BizTalk 消息队列适配器时，才对其进行配置。 这样将有助于减小你的环境中潜在的攻击面。  
  
如果使用 Internet Explorer，我们建议你打开的 Internet Explorer 增强的安全性。  
  
 **安装 service pack 和更新**。 我们建议始终具有的所有服务器上安装最新的产品服务包和 Microsoft 更新[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]资源，包括[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]。  
  
 **无法用明文脚本或绑定文件中保存密码。** 应当将脚本保存在使用加强的任意访问控制列表 (DACL) 的位置中，以便只有 BizTalk Server 管理员才有权查看、修改和运行这些脚本。 如果脚本和绑定文件需要密码，请确保在使用这些脚本进行配置或部署后立即屏蔽密码。 不要将密码以明文形式存放在这些文件中。  
  
 **使用强大的自由访问控制列表 (Dacl)。** 确保仅将对资源的访问权限授予使用该资源的用户和帐户，并且授予这些用户和帐户执行其任务所需的最低权限。 将配置脚本放置在使用 DACL 并且只有 BizTalk Server 管理员才能访问的位置中，并且不要将明文密码放置在这些脚本中。 确保 BizTalk Server 使用的所有服务帐户的临时目录都具有 DACL，以便只有相应的服务帐户和 BizTalk 管理员才有权对其进行访问。  
  
 如果具有自定义适配器，则建议你将适配器扩展组件存储在使用加强的 DACL 的位置中，以便只有 BizTalk Server 管理员才对这些组件具有写权限。  
  
 **不要将 BizTalk 服务器放在外围网络中。** 不管你的公司大小如何，如果将 BizTalk Server 放置在外围网络中，则这些服务器可能会受到来自 Internet 的直接攻击和来自外围网络中可能受到威胁的其他服务器的攻击。 由于 BizTalk Server 与数据域中的 Microsoft SQL Server 数据库进行通信，因此恶意用户可能会利用受到威胁的 BizTalk Server 来篡改重要的业务处理数据和配置数据。  
  
## <a name="biztalk-server-groups-and-accounts"></a>BizTalk Server 组和帐户  
 **使用最小权限和用户权限的帐户。** BizTalk Server 系统中的所有帐户应只具有执行其任务所需的最低用户权限。 例如，在处理服务器中使用的服务帐户不应具有 BizTalk Server、SQL Server 或 Windows Server 中的管理用户权限。 有关最低安全权限和用户权限帐户需要在 BizTalk Server 中执行某项任务的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。 关于组和 BizTalk Server 使用的帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
 **为不同的功能中使用不同的帐户。** 为保护 BizTalk Server 环境的安全，建议为你的环境中运行的每个主机实例创建不同的服务帐户。 这样还可以在密码更新期间提供更佳的可用性。 我们建议服务帐户不是 BizTalk Server 的多个 Windows 组的成员。  
  
 此外，建议你为每个 BizTalk 主机使用不同的 Windows 组，并建议不要将属于一个组的服务帐户作为另一个主机的 Windows 组的成员。 这样可以为每个 BizTalk 主机提供加强的安全隔离。  
  
 建议你创建一个仅用于跟踪主机的 Windows 组，并使用此组中的服务帐户来跟踪主机实例。 不要将此服务帐户用于其他任何服务，也不要使用 BizTalk 管理员帐户来跟踪主机实例。  
  
 **使用不同的主机为不同的功能。** 建议你创建一个仅用于跟踪的主机。 配置为“主机跟踪”的主机具有对 MessageBox 数据库中跟踪表的读取权限和写入权限，以及对跟踪数据库中的表的访问权限。 因此，在作为跟踪宿主的主机中运行的所有对象都具有对这些表的读取权限和写入权限。 为阻止对用户项（例如管道和业务流程）中可能敏感的跟踪数据的访问，建议你创建一个专用于跟踪的主机，该主机不处理、发送或接收消息。  
  
 此外，建议对于处理、接收和发送消息分别使用不同的主机。 然后，可以隔离需要访问你的公司的专用证书的服务帐户。 使用这些帐户运行的代码越少，则通过漏洞危及帐户安全的可能性越小，从而，可以降低危及专用证书安全的风险。  
  
 **定期更改密码。** 你必须定期更改服务帐户的密码。 如果具有主机实例的多个服务帐户，则必须更改其中每个服务帐户的密码。  
  
> [!CAUTION]
>  必须在 BizTalk 管理控制台中更改主机实例的服务帐户密码。 如果在计算机管理控制台中更改主机实例的服务帐户密码，则可能会导致配置问题。  
  
 **限制 BizTalk 管理员组成员资格。** BizTalk Server 管理员具有跨 BizTalk Server 环境的用户权限，包括对大多数加密或未加密数据的访问权限。 因此，如果由于 BizTalk 管理员的错误而导致配置不正确，则可能会出现严重的安全漏洞。 如果 BizTalk 管理员误操作，则可能会对系统造成极大的损害，包括对客户数据的保密性、完整性和可用性的完全破坏。  
  
 如果开发人员将业务流程直接部署到生产环境中的计算机上，则域管理员必须向开发人员授予 BizTalk 管理员用户权限。 出于上述原因，建议不要执行此操作。  
  
 **限制到 COM + 管理员组的成员身份。** 出于各种结构上的原因，COM+ 管理员在一些 BizTalk Server 组件中具有与管理员相同的用户权限。 实际上，你必须假定计算机上的 COM+ 管理员也是 BizTalk 管理员，并应在 BizTalk 生产服务器中限制此组的成员身份。  
  
 **仅授权用户访问运行他们需要访问的服务的计算机。** 并非所有帐户都需要对所有计算机的权限。 BizTalk 主机实例将敏感信息存放在内存中。 这些信息可能是诸如密码或业务信息之类的关键数据。 应在这些计算机上设置十分严格的本地用户策略。 例如，仅将这些计算机上的本地登录权限授予需要该权限以维护部署的个人。 这样可以缓解由于访问交换文件和崩溃转储而导致的威胁。  
  
 **限制权限的 Power Users 组中，或将其删除。** Power Users 组的默认权限可以为此组成员授予修改计算机范围的设置（包括在全局程序集缓存 (GAC) 中注册的 BizTalk 程序集）的用户权限。 每台计算机都具有包含一个或多个应用程序共享的程序集的 GAC。 建议从 Power Users 组中删除更改程序集的权限，或者从生产 BizTalk Server 中删除 Power Users 组。  
  
 
## <a name="see-also"></a>另请参阅  
 [组和服务帐户的访问控制](../core/access-control-for-groups-and-service-accounts.md)   
 [用于管理角色的访问控制](../core/access-control-for-administrative-roles.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)   
 [Planning for Security](../core/planning-for-security.md)