---
title: 如何创建关联应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3be483f8-2617-459e-9081-aab886c75d93
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5145111b2c585edab92cc10c3e3614e8bb91a85d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-create-an-affiliate-application"></a>如何创建关联应用程序
你可以使用 Mmc 管理单元或**createapps**命令以创建一个或多个应用程序，为指定的 XML 文件。 下面是示例 XML 文件的 Windows-Initiated 单一登录 (SSO):  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no" configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 创建关联应用程序后，将无法修改以下属性：  
  
-   关联应用程序的名称。  
  
-   关联应用程序与关联的字段。  
  
-   Affiliate 应用程序类型 （主机组、 个人或配置存储区）。  
  
-   与 Affiliate Administrators 组相同的管理帐户。 （指定此标志将始终使用分支机构的管理员组的管理员帐户作为此关联应用程序。）  
  
> [!IMPORTANT]
>  通过将 allowLocalAccounts 标志设置为“是”，可以为管理帐户和用户帐户使用本地帐户。 不过，只能在单计算机环境中使用此标志。  
  
> [!IMPORTANT]
>  只有 SSO 管理员或 SSO 关联管理员才能执行此任务。  
  
> [!NOTE]
>  如果你正在进行配置域控制器，并创建关联应用程序时，为应用程序管理员或应用程序的用户的域本地的作用域组指定，建议您启用本地帐户标记。 为此，请执行以下操作：  
  
-   在 MMC 管理单元中，在创建过程期间选择允许的访问帐户的本地帐户。  
  
-   从命令行中，指定 allowLocalAccounts = Affiliate 应用程序创建的 XML 文件中的是。  
  
 只有在创建关联应用程序后才能启用该应用程序。 有关详细信息，请参阅[如何启用 Affiliate 应用程序](../esso/how-to-enable-an-affiliate-application.md)。  
  
### <a name="to-create-an-affiliate-application-using-the-microsoft-management-console-mmc-snap-in"></a>若要创建使用 Microsoft 管理控制台 (MMC) 管理单元中的关联应用程序  
  
1.  单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**Affiliate 应用程序**，然后单击**新建**。  
  
4.  按照中的说明**创建新 Affiliate 应用程序**向导。  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a>使用命令行创建关联应用程序  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
3.  类型`ssomanage –createapps <application file name>`，其中*\<应用程序文件名称 >*是 XML 文件。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../esso/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../esso/how-to-enable-an-affiliate-application.md)   
 [如何删除关联应用程序](../esso/how-to-delete-an-affiliate-application.md)   
 [管理用户映射](../esso/managing-user-mappings.md)   
 [管理关联应用程序](../esso/managing-affiliate-applications.md)