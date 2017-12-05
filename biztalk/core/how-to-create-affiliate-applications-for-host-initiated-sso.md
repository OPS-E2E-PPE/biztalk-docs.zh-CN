---
title: "如何创建关联应用程序为主机启动的 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], host initiated SSO
- creating, applications [SSO]
- host initiated SSO, creating affiliate applications
ms.assetid: 06202d21-055a-46bc-acff-da461f5673f1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8a5cf43cd1d6e455492a74985edb91f2cb0a94
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-affiliate-applications-for-host-initiated-sso"></a>如何创建关联应用程序为主机启动的 SSO
可以定义两种类型的应用程序：  
  
-   **单个**没有 Windows 用户和非 Windows 用户之间的 1 对 1 关系。  
  
-   **主机组**多个非 Windows 用户可以映射到相同的 Windows 帐户。  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元创建关联应用程序  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**Affiliate 应用程序**，然后单击**创建应用程序**以打开**企业单一登录在应用程序向导**。  
  
4.  使用该向导选择关联应用程序的属性。  
  
### <a name="to-create-an-individual-type-affiliate-application-using-the-command-line"></a>使用命令行创建“单项”类型的关联应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssomanage-createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
     以下显示了一个文件示例：  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_Host1">  
        <description>An Individual Type Affiliate Application for Host Initiated SSO</description>  
        <contact>someone@companyname.com</contact>  
        <appUserAccount>DomainName\AppUserGroup_HISSO</appUserAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags windowsInitiatedSSO="no" enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-a-host-group-type-affiliate-application-using-the-command-line"></a>使用命令行创建“主机组”类型的关联应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssomanage-createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
     以下显示了一个文件示例：  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_HostGroupApp1">  
        <description>A Group Type Affiliate Application for Host Initiated SSO associating multiple non-Windows user to a single Windows user account(DomainName\WindowsUserAccount1)</description>  
        <contact>someone@companyname.com</contact>  
        <windowsAccount>DomainName\WindowsUserAccount1</windowsAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags  enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-an-affiliate-application-supporting-both-windows-initiated-sso-and-host-initiated-sso-using-the-command-line"></a>使用命令行创建同时支持 Windows 启动的 SSO 和主机启动的 SSO 的关联应用程序  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行上，转至企业单一登录安装目录。 默认值是\<驱动器\>: \program Files\Enterprise 单一登录。  
  
4.  类型**ssomanage-createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
     以下显示了一个文件示例：  
  
    ```  
    <?xml version="1.0" ?>   
    - <SSO>  
    - <application name="SSOApp1">  
      <description>An Individual Type Affiliate Application for both Host Initiated SSO and Windows Initiated SSO</description>   
      <contact>someone@companyname.com</contact>   
      <appUserAccount>DomainName\AppUserGroup</appUserAccount>   
      <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>   
      <field ordinal="0" label="User ID" masked="no" />   
      <field ordinal="1" label="Password" masked="yes" />   
      <flags  enableApp="yes" />   
      </application>  
      </SSO>  
  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)