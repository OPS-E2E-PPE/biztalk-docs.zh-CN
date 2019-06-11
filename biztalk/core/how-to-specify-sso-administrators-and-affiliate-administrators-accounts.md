---
title: 如何指定 SSO 管理员和关联管理员帐户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faff8a6a8b8b9a639c4e03c4c48c287835667238
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "65383851"
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a>如何指定 SSO 管理员和关联管理员帐户
企业单一登录 (SSO) 管理员和关联管理员帐户可以是主机组或个人帐户。 在配置 SSO 系统之前，必须创建这些帐户。  
  
 时使用域帐户，你必须创建的 SSO Administrators 和 SSO Affiliate Administrators 帐户为域全局安全组的域控制器中。 域管理员必须创建这些帐户。  
  
 必须在 SSO 数据库中指定的 Single Sign-on Administrators 和 Affiliate Administrators 帐户。 使用 SSO Administrators 组更新 SSO 数据库之前，必须禁用单一登录系统。  
  
 下面的 XML 代码显示更新 SSO 数据库的示例 XML:  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  配置向导自动指定 SSO 管理员和 SSO 关联管理员组在 SSO 数据库中。  
  
> [!NOTE]
>  如果 SSO 不进行配置，用户应检查是否正在混合模式域中使用域本地帐户。  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>若要禁用企业单一登录系统使用 Mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序”  、“Microsoft Enterprise Single Sign-On”  和“SSO 管理”  。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**禁用**。  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a>若要禁用企业单一登录系统使用命令行  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录 \<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage** –**disablesso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>使用 MMC 管理单元更新 SSO 数据库  
  
1.  上**启动**菜单上，单击**所有程序**， **Microsoft 企业单一登录**，然后**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**更新**。  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a>使用命令行更新 SSO 数据库  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行中，转至企业单一登录安装目录。 默认安装目录 *\<驱动器\>* : \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型 * * ssomanage – updatedb *\<更新文件\>**<em>，其中 *\<更新文件\></em>是路径和 XML 文件的名称。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>若要启用企业单一登录系统使用 Mmc 管理单元  
  
1.  上**启动**菜单上，单击**所有程序**， **Microsoft 企业单一登录**，然后**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**系统**，然后单击**启用**。  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a>若要启用企业单一登录系统使用命令行  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录 *\<驱动器\>* : \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage – enablesso**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [SSO 用户组](../core/sso-user-groups.md)