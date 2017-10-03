---
title: "如何显示的 SSO 数据库信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO], viewing SSO database
- SSO database, viewing
- viewing, SSO database
ms.assetid: 0ebadd2e-6ea5-460c-b0a8-f48589e6bf1c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1328e6066af0d19c68657728f8dc7777ba62f12d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-the-sso-database-information"></a>如何显示的 SSO 数据库信息
可以使用 MMC 管理单元或命令行 (ssomanage) 实用工具来查看 SSO 数据库信息。  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a>使用 MMC 管理单元显示 SSO 数据库信息  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击“系统” ，然后单击“属性” 。  
  
4.  单击选项卡**系统属性**对话框中，若要查看 SSO 数据库信息。  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a>使用命令行显示 SSO 数据库信息  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是**\<驱动器 >**: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-displaydb**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a>使用命令行显示 SSO 服务器连接到的 SSO 数据库  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录是**\<驱动器 >**: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-showdb**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
 下表对这些过程中显示的值进行了说明：  
  
|属性|值|  
|--------------|-----------|  
|SQL Server|**\<SQL Server 名称 >**|  
|单一登录数据库|**\<SQL Server 数据库名称 >**|  
|单一登录密钥服务器名称|**\<单一登录服务器名称 >**|  
|Single Sign-On Administrators 帐户|域\帐户名称|  
|Single Sign-On Affiliate Administrators 帐户|域\帐户名称|  
|已删除的应用程序的审核表大小（审核条目数）|1000 （默认值）|  
|已删除的用户映射的审核表大小（审核条目数）|1000 （默认值）|  
|外部凭据查找的审核表大小（审核条目数）|1000 （默认值）|  
|票证超时（分钟）|2 （默认值）<br /><br /> 此值可为介于 1 到 525,600 之间的整数|  
|凭据缓存超时（分钟）|60 （默认值）|  
|单一登录状态|已启用/已禁用|  
|允许使用票证|是/否（默认）|  
|验证票证|是（默认）/否|  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md)   
 [使用 SSO](../core/using-sso.md)