---
title: "如何更新关联应用程序的属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], updating properties
- applications [SSO], properties
ms.assetid: b06eefdd-a5ca-4a32-93d7-72246e31a2e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef4a2fb99d423f7c7ccb08cec58c3c49928e1ed
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-update-the-properties-of-an-affiliate-application"></a>如何更新关联应用程序的属性
您可以使用 MMC 管理单元或此命令根据 XML 文件指定的内容更新一个或多个应用程序属性。 只有关联管理员才能执行此任务。 下面是一个示例 XML 文件，其中列出了可更新的字段：  
  
```  
<SSO>  
<application name="SSOApplication">  
<description>An SSO Application</description>  
<contact>someone@companyname.com</contact>  
<appUserAccount>DomainName\AppUserGroup</appUserAccount>  
<appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
<flags allowTickets="no" validateTickets="yes"  timeoutTickets="yes" enableApp="no" />  
</application>  
</SSO>  
  
```  
  
 创建关联应用程序后，将无法修改以下属性：  
  
-   关联应用程序的名称  
  
-   与关联应用程序关联的字段  
  
-   关联应用程序类型（主机组、单项或配置存储）  
  
-   与 Affiliate Administrators 组相同的管理帐户。 （如果指定此标志，则将始终使用 Affiliate Administrators 组作为此关联应用程序的管理员帐户）  
  
> [!IMPORTANT]
>  通过将 allowLocalAccounts 标志设置为“是”，可以为管理帐户和用户帐户使用本地帐户。 但是，你只可以在单计算机方案中使用此标志。  
  
> [!IMPORTANT]
>  只有 SSO 管理员、SSO 关联管理员或应用程序管理员才能执行此任务。  
  
> [!IMPORTANT]
>  只有 SSO 管理员才能修改票证标志（validateTickets 和 timeoutTickets）。  
  
> [!IMPORTANT]
>  只有 SSO 管理员或 SSO 关联管理员才能修改应用程序管理帐户。  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元更新关联应用程序的属性  
  
1.  上**启动**菜单上，单击**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击 affililate 应用程序，并依次**更新**。  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-command-line"></a>使用命令行更新关联应用程序的属性  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-updateapps\<应用程序文件名称\>**，其中应用程序文件名称是 XML 文件。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)