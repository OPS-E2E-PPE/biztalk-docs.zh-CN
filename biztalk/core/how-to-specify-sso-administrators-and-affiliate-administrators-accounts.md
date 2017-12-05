---
title: "如何指定 SSO Administrators 和 Affiliate Administrators 帐户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- enabling, SSO
- SSO, enabling
- disabling, SSO
- SSO, disabling
- managing [SSO], configuring administrator accounts
- managing [SSO], enabling
- managing [SSO], disabling
- SSO, administrator accounts
ms.assetid: 6c300e09-b781-45de-b2da-b1083164a1c0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c96e2d99bd6071098a65b3635bb466de44a455d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a>如何指定 SSO Administrators 和 Affiliate Administrators 帐户
企业单一登录 (SSO) 管理员和关联管理员帐户可以为主机组也可以为个人帐户。 必须首先创建这些帐户，然后才能配置 SSO 系统。  
  
 在使用域帐户时，必须将 SSO 管理员和 SSO 关联管理员帐户作为域控制器中的域全局安全组创建。 域管理员必须创建这些帐户。  
  
 必须在 SSO 数据库中指定单一登录管理员和关联管理员帐户。 必须首先禁用单一登录系统，然后才能用 SSO Administrators 组更新 SSO 数据库。  
  
 以下 XML 代码显示了用于更新 SSO 数据库的 XML 示例：  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  配置向导自动在 SSO 数据库中指定 SSO Administrators 和 SSO Affiliate Administrators 组。  
  
> [!NOTE]
>  如果未配置 SSO，用户应检查是否在混合模式域使用域本地帐户。  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>使用 MMC 管理单元禁用企业单一登录系统  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**禁用**。  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a>使用命令行禁用企业单一登录系统  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是\<*驱动器*\>: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage** –**disablesso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>使用 MMC 管理单元更新 SSO 数据库  
  
1.  上**启动**菜单上，单击**所有程序**， **Microsoft Enterprise 上单一登录**，，然后**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**更新**。  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a>使用命令行更新 SSO 数据库  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-updatedb *\<更新文件\>***，其中*\<更新文件\>*是路径和名称XML 文件。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>使用 MMC 管理单元启用企业单一登录系统  
  
1.  上**启动**菜单上，单击**所有程序**， **Microsoft Enterprise 上单一登录**，，然后**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**启用**。  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a>使用命令行启用企业单一登录系统  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-enablesso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 用户组](../core/sso-user-groups.md)