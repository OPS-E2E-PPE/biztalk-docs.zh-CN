---
title: 如何创建关联应用程序为主机启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], host initiated SSO
- creating, applications [SSO]
- host initiated SSO, creating affiliate applications
ms.assetid: 06202d21-055a-46bc-acff-da461f5673f1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d207766ce830da973a4767213810f07432c743fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339825"
---
# <a name="how-to-create-affiliate-applications-for-host-initiated-sso"></a>如何为主机启动的 SSO 创建关联应用程序
可以定义两种类型的应用程序：  
  
-   **单个**没有 Windows 用户和非 Windows 用户之间的一对一关系。  
  
-   **主机组**多个非 Windows 用户可以映射到相同的 Windows 帐户。  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a>若要创建关联应用程序使用 Mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**关联应用程序**，然后单击**创建应用程序**以打开**企业单一登录应用程序向导**。  
  
4.  使用向导选择关联应用程序的属性。  
  
### <a name="to-create-an-individual-type-affiliate-application-using-the-command-line"></a>创建单个类型关联应用程序使用命令行  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage – createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
     示例文件如下所示：  
  
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
  
### <a name="to-create-a-host-group-type-affiliate-application-using-the-command-line"></a>创建主机组类型关联应用程序使用命令行  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage – createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
     示例文件如下所示：  
  
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
  
### <a name="to-create-an-affiliate-application-supporting-both-windows-initiated-sso-and-host-initiated-sso-using-the-command-line"></a>若要创建附属机构支持这两个 Windows 应用程序启动的 SSO 和主机启动的 SSO 使用命令行  
  
1.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
2.  在中**运行**对话框中，键入**cmd**，然后单击**确定**。  
  
3.  在命令行中，转至企业单一登录安装目录。 默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
4.  类型**ssomanage – createapps \<AffApp.xml\>**，其中 AffApp.xml 是 xml 文件的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
     示例文件如下所示：  
  
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
  
## <a name="see-also"></a>请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)