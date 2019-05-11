---
title: 如何更新关联应用程序的属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], updating properties
- applications [SSO], properties
ms.assetid: b06eefdd-a5ca-4a32-93d7-72246e31a2e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c50664fcf9e87ed6980a031fed980bf1e01301
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333659"
---
# <a name="how-to-update-the-properties-of-an-affiliate-application"></a>如何更新关联应用程序的属性
可以使用 MMC 管理单元或此命令更新一个或多个应用程序属性，指定的 XML 文件。 必须是关联管理员才能执行此任务。 下面是示例 XML 文件，其中列出了可更新的字段。  
  
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
  
 创建关联应用程序后，无法修改以下属性：  
  
-   关联应用程序的名称  
  
-   与关联应用程序关联的字段  
  
-   关联应用程序类型 （主机组、 单项或配置存储区）  
  
-   相同与 affiliate administrators 组的管理帐户。 （指定此标志将始终使用 affiliate administrators 组的管理员帐户作为此关联应用程序）  
  
> [!IMPORTANT]
>  可以通过此 allowLocalAccounts 标志设置为是使用管理帐户的本地帐户和用户帐户。 但是，仅可以在单计算机方案中使用此标志。  
  
> [!IMPORTANT]
>  必须是 SSO 管理员、 SSO 关联管理员或应用程序管理员才能执行此任务。  
  
> [!IMPORTANT]
>  必须是 SSO 管理员才能修改票证标志 （validateTickets 和 timeoutTickets）。  
  
> [!IMPORTANT]
>  您必须是 SSO 管理员或 SSO 关联管理员才能修改应用程序管理帐户。  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-mmc-snap-in"></a>若要更新的关联应用程序使用 Mmc 管理单元属性  
  
1.  上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击关联应用程序，然后依次**更新**。  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-command-line"></a>若要更新的关联应用程序使用命令行属性  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage – updateapps\<应用程序文件名\>**，其中应用程序文件名称是 XML 文件。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)