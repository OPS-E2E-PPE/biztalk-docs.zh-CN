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
ms.openlocfilehash: 77310b793b9dfccc85b0fc7898f6a02b69ea5688
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336695"
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a>如何管理用户映射的主机启动的 SSO
使用以下过程创建映射、 设置凭据，并启用或禁用映射。  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a>若要管理用户映射为主机启动的 SSO 使用 Mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  在作用域窗格中，单击**关联应用程序**。  
  
4.  在详细信息窗格中，右键单击关联应用程序，并选择相应的菜单项的操作。  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a>若要创建映射，在主机启动的 SSO 使用命令行  
  
1. 在 **“开始”** 菜单上，单击 **“运行”**。  
  
2. 在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3. 在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4. 类型**ssomanage – createmappings\<映射文件\>**，其中**映射文件 >** 是 xml 文件的名称。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
    示例映射文件如下所示：  
  
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
  
   验证密码功能可用于关联应用程序，时，必须设置凭据，如下所示：  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a>若要设置关联应用程序使用命令行的各个类型的凭据  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-setcredentials \<Windows 帐户名称\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a>为主机设置凭据组类型关联应用程序使用命令行  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-setcredentials\<外部帐户名\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>若要启用单个类型的映射的关联应用程序使用命令行  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-enablemapping \<Windows 帐户名称\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>若要禁用各个类型的关联映射使用命令行应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-disablemapping \<Windows 帐户名称\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a>若要启用主机组类型的映射的关联应用程序使用命令行  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-enablemapping\<外部帐户名\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>若要禁用各个类型的关联映射使用命令行应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage-disablemapping\<外部帐户名\>\<应用程序名称\>**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)