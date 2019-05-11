---
title: SSO 用户组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- groups, SSO
- user accounts, administrators
- service accounts, SSO
- SSO, user groups
- SSO, service accounts
- SSO, administrator accounts
ms.assetid: e279001e-c724-4a2d-8939-0ba9dd08a19c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd38c0417c84f7130a40f54fb684b01b6b853623
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398952"
---
# <a name="sso-user-groups"></a>SSO 用户组
若要配置和管理企业单一登录 (SSO) 系统，必须为每个角色创建特定的 Windows 组和帐户。 在企业 SSO 中配置访问帐户，可以为每个角色指定多个帐户。 本部分介绍这些角色。  
  
> [!IMPORTANT]
>  强烈建议配置 SSO 时使用域组。  
  
> [!NOTE]
>  出于安全目的，SSO 系统不允许内置帐户。  
  
## <a name="single-sign-on-administrators"></a>单一登录管理员  
 SSO 管理员在 SSO 系统中具有最高的级别的用户权限。 他们可以：  
  
- 创建和管理 SSO 数据库  
  
- 创建和管理主密钥  
  
- 启用和禁用 SSO 系统  
  
- 创建密码同步适配器  
  
- 启用和禁用 SSO 系统中的密码同步  
  
- 启用和禁用主机启动的 SSO  
  
- 执行所有管理任务  
  
  SSO 管理员帐户可以是 Windows 组帐户或个人帐户。 域或本地组或个人帐户，也可以是 SSO 管理员帐户。 如果使用个人帐户，则无法更改此帐户到另一个个人帐户。 因此，建议不使用个人帐户。 只要原始帐户是新帐户的成员，您可以更改此帐户为组帐户。  
  
> [!IMPORTANT]
>  运行企业单一登录服务的服务帐户必须是此帐户的成员。 若要保护你的环境，请确保没有其他服务使用相同的服务帐户。  
  
## <a name="single-sign-on-affiliate-administrators"></a>单一登录关联管理员  
 SSO 关联管理员定义 SSO 系统包含的关联应用程序。 关联应用程序是表示使用 SSO 连接在后端系统的逻辑实体。 SSO 关联管理员可以：  
  
- 创建、 管理和删除关联应用程序  
  
- 指定每个关联应用程序的应用程序管理员帐户  
  
- 执行所有的应用程序管理员和应用程序用户可以管理任务  
  
  SSO 关联管理员帐户可以是 Windows 组帐户或个人帐户。 SSO 关联管理员帐户也可以是域或本地组或帐户。  
  
## <a name="application-administrators"></a>应用程序管理员  
 没有每个关联应用程序的一个应用程序管理员组。  
  
 此组的成员可以：  
  
-   更改应用程序用户组帐户  
  
-   创建、 删除和管理的特定关联应用程序的所有用户的凭据映射  
  
-   为任何用户设置凭据，特定关联应用程序用户组帐户  
  
-   执行应用程序用户的所有管理任务  
  
## <a name="application-users"></a>应用程序用户  
 有了一个应用程序用户组帐户的每个关联应用程序。 此帐户包含企业单一登录的环境中的最终用户的列表。 此帐户的成员可以：  
  
-   查找凭据，关联应用程序  
  
-   管理关联应用程序中的其凭据映射  
  
> [!NOTE]
>  请记住将组分配时要警惕。 它是有可能，例如，使用 BizTalk Server 安全用户组为 SSO 应用程序用户组。 执行此操作之前，请确保所有用户都需要然后将提供给他们的所有访问。  
  
## <a name="see-also"></a>请参阅  
 [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)   
 [如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [了解 SSO](../core/understanding-sso.md)