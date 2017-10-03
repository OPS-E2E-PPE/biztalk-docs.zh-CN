---
title: "SSO 用户组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 949f3aa72771982321abf6904c43352b8821fc0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sso-user-groups"></a>SSO 用户组
若要配置和管理企业单一登录 (SSO) 系统，必须为其中每个角色创建某些 Windows 组和帐户。 在企业 sso 配置的访问帐户，你可以为每个这些角色指定多个帐户。 本部分介绍这些角色。  
  
> [!IMPORTANT]
>  强烈建议你配置 SSO 时使用域组。  
  
> [!NOTE]
>  出于安全考虑，SSO 系统不允许内置帐户。  
  
## <a name="single-sign-on-administrators"></a>单一登录管理员  
 SSO 管理员 SSO 系统中具有最高的级别的用户权限。 用户可以：  
  
-   创建和管理 SSO 数据库  
  
-   创建和管理主密钥  
  
-   启用和禁用 SSO 系统  
  
-   创建密码同步适配器  
  
-   启用和禁用 SSO 系统中的密码同步  
  
-   启用和禁用主机启动的 SSO  
  
-   执行所有管理任务  
  
 SSO administrators 帐户可以是 Windows 组帐户或个人帐户。 域或本地组或个人帐户，也可以是 SSO administrators 帐户。 时使用个人帐户，不能为其他个人帐户更改此帐户。 因此，建议不使用个人帐户。 只要原始帐户是新帐户的成员，可以更改此帐户为组帐户。  
  
> [!IMPORTANT]
>  运行企业单一登录服务的服务帐户必须是此帐户的成员。 若要保护你的环境，请确保没有其他服务正在使用的相同服务帐户。  
  
## <a name="single-sign-on-affiliate-administrators"></a>单一登录在分支机构管理员  
 SSO 关联管理员将定义 SSO 系统包含关联应用程序。 关联应用程序是表示使用 SSO 连接后端系统的逻辑实体。 SSO affiliate 管理员可以：  
  
-   创建、 管理和删除关联应用程序  
  
-   指定每个关联应用程序的应用程序管理员帐户  
  
-   执行应用程序管理员和应用程序用户可以的所有管理任务  
  
 SSO Affiliate Administrator 帐户可以是 Windows 组帐户或个人帐户。 域或本地组或帐户，也可以是 SSO Affiliate Administrator 帐户。  
  
## <a name="application-administrators"></a>应用程序管理员  
 没有每个关联应用程序的一个应用程序管理员组。  
  
 此组的成员可以：  
  
-   更改应用程序用户组帐户  
  
-   创建、 删除和管理特定的关联应用程序的所有用户的凭据映射  
  
-   设置的任何用户的凭据，在于特定关联应用程序用户组帐户  
  
-   执行应用程序用户可以的所有管理任务  
  
## <a name="application-users"></a>应用程序用户  
 没有为每个关联应用程序的一个应用程序用户组帐户。 此帐户包含一个企业单一登录的环境中的最终用户的列表。 此帐户的成员可以：  
  
-   查找关联应用程序在其凭据  
  
-   管理关联应用程序在其凭据映射  
  
> [!NOTE]
>  请记住要警惕，当将组分配。 它是有可能，例如，使用 BizTalk Server 安全用户组为 SSO 应用程序用户组。 执行此操作之前，请确保所有用户都需要将会提供给他们的所有访问。  
  
## <a name="see-also"></a>另请参阅  
 [如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md)   
 [如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [了解 SSO](../core/understanding-sso.md)