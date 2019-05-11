---
title: 如何配置主机要求启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service accounts, granting privileges [SSO]
- host initiated SSO, configuring
- domain function level [SSO]
- host initiated SSO, Transaction Integrator (TI)
- SPN [SSO]
- managing [SSO], granting TCB privileges
- Transaction Integrator (TI)
- host initiated SSO, SPN
- host initiated SSO, TCB privileges
- configuring, host initiated SSO
- creating, SPNs [SSO]
- TCB privileges [SSO]
- managing [SSO], host initiated
- host initiated SSO, domain function level
- service accounts, SSO
- SSO, host initiated
- managing [SSO], creating SPNs
- SSO, service accounts
ms.assetid: 91d77c9f-bab2-4f6e-8bce-e31c59cebb20
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3319c0d8157ebe0c71c36a2494b3bda641181c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341224"
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a>如何配置主机要求启动的 SSO
尽管企业 SSO 和主机启动的 SSO 的共同点某些方面，某些平台和 Active Directory 要求是唯一的以主机启动的 SSO。 本主题讨论了这些要求，并列出了检查或创建这些系统上的步骤。  
  
- 主机启动的 SSO 可仅在本机的 Windows Server 2008 域环境执行。  
  
- 将执行主机的 SSO 服务的服务帐户启动的 SSO 必须配置为具有 TCB 权限。 （你可以配置此域安全策略中的服务帐户。）  
  
  此外，某些要求是必需的使用主机启动的处理的事务集成器时。 TI 为 HIP 利用主机启动的 SSO 为非 Windows 用户实现单一登录。  
  
  例如，HIP 服务的 TI 的服务帐户在服务帐户 domainname\hipsvc 下运行。 此服务可承载的应用程序想要访问远程或本地资源在 Windows 上使用 Windows 帐户对应的非 Windows 帐户。  
  
  Domainname\hipsvc 帐户必须属于正在使用单一登录关联应用程序的应用程序管理员组帐户。  
  
  Domainname\hipsvc 帐户必须具有约束委托权限才能使用主机启动的单一登录。 这可以由域管理员在 Active Directory 中配置。 可以为已注册 Spn 的帐户配置委托。 约束的委派允许服务帐户来访问由管理员指定的组件。  
  
### <a name="to-check-your-domain-function-level"></a>若要检查域功能级别  
  
1.  在你**Active Directory 域和信任关系**MMC 管理单元中，右单击的节点**Active Directory 域和信任关系**，然后单击**提升林功能级别**。  
  
2.  验证功能级别是否**Windows Server 2008**。 如果不存在，请参阅 Active Directory 文档，然后再尝试更改该设置。  
  
### <a name="to-create-an-spn"></a>若要创建 SPN  
  
1. 下载**setspn**实用程序从以下位置： [ http://go.microsoft.com/fwlink/?LinkId=33178 ](http://go.microsoft.com/fwlink/?LinkId=33178)。  
  
2. 在 **“开始”** 菜单上，单击 **“运行”**。  
  
3. 在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
4. 在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
5. Type **setpsn -a hipsvc\computername.domain.com domain\hissvc**  
  
    其中**hipsvc\computername.domain.com**是将执行该操作和，运行的计算机的服务和**domain\hissvc**是 hipsvc 的服务帐户。  
  
   完成后，可以在此服务帐户 (domain\hissvc) 来访问网络中的相应资源的 Active Directory 中配置约束的委派。  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a>SSO 服务帐户授予 TCB 权限  
  
-   在你**域安全策略-本地策略-用户权限分配**，将 SSO 服务帐户添加到**充当操作系统的一部分**策略。  
  
     有关 Kerberos 协议转换和约束委派的详细信息，请转到[ http://go.microsoft.com/fwlink/?LinkId=195484 ](http://go.microsoft.com/fwlink/?LinkId=195484)。  
  
## <a name="see-also"></a>请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)