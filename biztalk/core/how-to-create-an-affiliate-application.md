---
title: 如何创建关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], creating
- applications [SSO], creating
- creating, applications [SSO]
ms.assetid: d0967c4b-6201-416a-9d3a-23b5de5b83d6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8775ea82843641600c9156d79afab49e6cd7c634
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003102"
---
# <a name="how-to-create-an-affiliate-application"></a>如何创建关联应用程序
您可以使用 MMC 管理单元或此命令根据 XML 文件指定的内容创建一个或多个应用程序。 以下为 Windows 启动的 SSO 的 XML 文件示例：  
  
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
  
-   关联应用程序的名称  
  
-   与关联应用程序关联的字段  
  
-   关联应用程序类型（主机组、单项或配置存储）  
  
-   与 Affiliate Administrators 组相同的管理帐户。 （如果指定此标志，则将始终使用 Affiliate Administrators 组作为此关联应用程序的管理员帐户）  
  
> [!IMPORTANT]
>  通过将 allowLocalAccounts 标志设置为“是”，可以为管理帐户和用户帐户使用本地帐户。 不过，只能在单计算机环境中使用此标志。  
  
> [!IMPORTANT]
>  只有 SSO 管理员或 SSO 关联管理员才能执行此任务。  
  
 只有在创建关联应用程序后才能启用该应用程序。 有关详细信息，请参阅[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)。  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元创建关联应用程序  
  
1.  上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击**关联应用程序**，然后单击**创建应用程序**。  
  
4.  按照中的说明**企业单一登录应用程序向导**。  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a>使用命令行创建关联应用程序  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行上，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型 * * ssomanage – createapps *\<应用程序的文件名\>**<em>，其中 *\<应用程序文件的名称\></em>是 XML 文件。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)   
 [如何删除关联应用程序](../core/how-to-delete-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)