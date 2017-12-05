---
title: "步骤 3： 配置域控制器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, domain controller
- domain controller
ms.assetid: 1c513225-378b-4e57-ba29-7532b6cbcc9a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b2c89b3db94ce28376ab988a4342931c6d7dcad
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="step-3-configuring-the-domain-controller"></a>步骤 3： 配置域控制器
本部分介绍如何配置中的域控制器你[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]部署。 具体而言，本部分介绍如何安装和配置[!INCLUDE[btsAD](../../includes/btsad-md.md)]通过执行以下操作：  
  
-   安装 Active Directory 和 DNS  
  
-   创建所需的帐户  
  
-   加入域  
  
## <a name="installing-active-directory-and-dns"></a>安装 Active Directory 和 DNS  
 使用[!INCLUDE[btsAD](../../includes/btsad-md.md)]安装向导来简化配置域控制器的过程。 在安装 Active Directory 之后, 创建域名系统 (DNS) 反向查找区域。 然后创建并将主机添加到正向和反向查找区域。  
  
## <a name="creating-the-required-accounts"></a>创建所需的帐户  
 下表提供有关如何创建全局安全组的详细信息。 创建以下**全局安全**组和使用你自己的命名约定在域控制器上的用户。 以下示例使用为简单起见。 在列表中指定的成员添加到创建组。  
  
 创建组时，选择**全局**组作用域和**安全**组类型。  
  
|帐户或组名称|类型|Description|成员|  
|---------------------------|----------|-----------------|-------------|  
|管理员|用户|BizTalk 的所有计算机、 域控制器和运行 SQL Server 的所有计算机的本地管理帐户。<br /><br /> 这是用于安装应用程序的域用户帐户 (BizTalk Server 中， [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，和 SQL Server) 和在设计时为 A4SWIFT 配置 BizTalk 快捷键。 不需要具有域管理员特权才能执行 A4SWIFT 安装。 管理员用户帐户必须是域用户组、 域 BizTalk Server Administrators 组和本地管理员组的成员||  
|SQLSvc|用户|用于运行 SQL Server 服务帐户||  
|SSOSvc|用户|用于运行单一登录 (SSO) 服务帐户||  
|HostSvc|用户|用于运行 BizTalk 主机服务帐户||  
|IsolatedSvc|用户|运行隔离的 BizTalk 服务的帐户||  
|BAMSvc|用户|所需的 BAMPortal、 BAMAlerts，和 BAMTools BizTalk Server 配置||  
|BRESvc|用户|用于运行规则引擎更新服务帐户||  
|Domain Admins|域组|域管理员的全局域组帐户||  
|BizTalk Isolated Host Users|域组|独立 BizTalk 主机 （主机进程未运行在 BizTalk Server 中，如 HTTP 和 SOAP） 拥有访问权限的帐户的域全局组。|\<IsolatedSvc\>， \<HostSvc\>|  
|BizTalk Server Administrators|域组|已执行配置 Framework 向导中包括的管理任务以及管理 BizTalk Server 时需要的最低权限的域全局组帐户。|\<管理员\>|  
|BizTalk Application Users|域组|BizTalk 应用程序用户的全局域组帐户。|\<HostSvc\>|  
|BizTalk Server Operators|域组|具有执行所需的安装后运行 BizTalk Server 环境任务所需的最低权限的组。||  
|启用 SharePoint 的主机|域组|有权调用 Windows SharePoint Services 适配器 Web 服务的 Windows 组。|\<HostSvc\>|  
|SSO Administrators|域组|SSO administrators 的全局域组帐户。|\<管理员\>， \<SSOSvc\>|  
|SSO Affiliate Administrators|域组|全局域组帐户为 SSO affiliate 管理员|\<管理员\>|  
|A4SWIFT 用户|域组|已在 A4SWIFT 执行基本任务所需的最少特权的全局域组帐户。|\<HostSvc\>、 其他网络用户|  
|A4SWIFT 管理员|域组|具有管理 A4SWIFT 所需的最低权限的域全局组帐户。|\<管理员\>|  
  
> [!NOTE]
>  所有的组帐户应是全局安全帐户和非本地的域帐户。 如果使用本地域组帐户 （使用 net localgroup 创建），安装程序也为[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]无法验证特定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]域用户。  
  
## <a name="joining-the-domain"></a>加入域  
 在创建了域和域控制器已重新启动后，将每个服务器加入到域中。