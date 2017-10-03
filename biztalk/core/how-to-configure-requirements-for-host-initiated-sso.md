---
title: "如何配置主机的要求启动的 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9f8a004c1883a05c3fcf60324f428144591cff4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a>如何配置主机启动的 SSO 的要求
尽管企业 SSO 和主机启动的 SSO 在某些方面有相同之处，但对于主机启动的 SSO，某些平台和 Active Directory 要求是其所独有的。 本主题将介绍这些要求，并列出在系统中检查或创建这些要求所需的步骤。  
  
-   主机启动的 SSO 只能在本地 Windows Server 2008 域环境中执行。  
  
-   必须将执行主机启动的 SSO 的 SSO 服务帐户配置为具有 TCB 权限。 （可在域安全策略中为服务帐户配置此权限。）  
  
 此外，在对主机启动的处理使用事务集成器时，必须满足某些要求。 HIP 的 TI 利用主机启动的 SSO 为非 Windows 用户实现单一登录。  
  
 例如，HIP 服务的 TI 的服务帐户在服务帐户 domainname\hipsvc 下运行。 此服务可承载要使用与非 Windows 帐户对应的 Windows 帐户访问 Windows 中远程或本地资源的应用程序。  
  
 domainname\hipsvc 帐户必须属于用于单一登录的关联应用程序的 Application Administrator 组帐户。  
  
 domainname\hipsvc 帐户必须具有约束委托权限才能使用主机启动的单一登录。 此权限可由 Active Directory 中的域管理员进行配置。 可以为已注册 SPN 的帐户配置委托。 使用约束委托，服务帐户可以只访问管理员指定的组件。  
  
### <a name="to-check-your-domain-function-level"></a>检查域功能级别  
  
1.  在你**Active Directory 域和信任关系**MMC 管理单元中，右单击节点**Active Directory 域和信任关系**，然后单击**提升林功能级别**。  
  
2.  验证的功能级别是否**Windows Server 2008**。 如果不是，请参阅 Active Directory 文档，然后尝试更改该设置。  
  
### <a name="to-create-an-spn"></a>要创建 SPN  
  
1.  下载**setspn**实用工具从以下位置： [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178)。  
  
2.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
3.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
4.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器 >: \program Files\Enterprise 单一登录。  
  
5.  类型**setpsn-a hipsvc\computername.domain.com domain\hissvc**  
  
     其中**hipsvc\computername.domain.com**是将执行该操作和的计算机运行的服务和**domain\hissvc**是 hipsvc 的服务帐户。  
  
 在执行此操作后，可以在 Active Directory 中为此服务帐户 (domain\hissvc) 配置约束委托以访问网络中的相应资源。  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a>为 SSO 服务帐户授予 TCB 权限  
  
-   在你**域安全策略的本地策略-用户权限分配**，SSO 服务将帐户添加到**充当操作系统的一部分**策略。  
  
     有关 Kerberos 协议转换和约束委派的详细信息，请转到[http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484)。  
  
## <a name="see-also"></a>另请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)