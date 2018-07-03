---
title: 如何管理用户映射的主机启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, host initiated SSO
- host initiated SSO, user maps
ms.assetid: 6b05249e-da35-475b-9c23-5eb556013d57
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad232bf81fff96e6cabf367e9c591d02d4296151
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006702"
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a>如何管理用户映射的主机启动的 SSO
通过以下步骤可以创建映射、设置凭据以及启用或禁用映射。  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a>使用 MMC 管理单元为主机启动的 SSO 管理用户映射  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  在作用域窗格中，单击**关联应用程序**。  
  
4.  在详细信息窗格中，右键单击相应的关联应用程序，然后选择适当的操作菜单项。  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a>使用命令行在主机启动的 SSO 中创建映射  
  
1. 在 **“开始”** 菜单上，单击 **“运行”**。  
  
2. 在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3. 在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4. 类型**ssomanage – createmappings\<映射文件\>**，其中**映射文件 >** 是 xml 文件的名称。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
    下面是一个映射文件的示例：  
  
   ```  
   <SSO>  
     <mapping>  
       <windowsDomain>DomainName</windowsDomain>  
       <windowsUserId>UserA</windowsUserId>  
       <externalApplication>SSOApplication</externalApplication>  
   <externalUserId>ExternalUserID that corresponds to UserA</externalUserId>  
     </mapping>  
   </SSO>  
  
   ```  
  
   如果为关联应用程序启用了“验证密码”功能，则需要设置凭据，步骤如下：  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a>使用命令行为“单项”类型的关联应用程序设置凭据  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-setcredentials \<Windows 帐户名称\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a>使用命令行为“主机组”类型的关联应用程序设置凭据  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-setcredentials\<外部帐户名\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>使用命令行为“ 单项” 类型的关联应用程序启用映射  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-enablemapping \<Windows 帐户名称\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>使用命令行为“单项”类型的关联应用程序禁用映射  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-disablemapping \<Windows 帐户名称\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a>使用命令行为“主机组”类型的关联应用程序启用映射  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-enablemapping\<外部帐户名\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>使用命令行为“单项”类型的关联应用程序禁用映射  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-disablemapping\<外部帐户名\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)